#

# **Cyber Security**

![](https://github.com/wendelaQuist/Cyber_security/blob/main/Pictures/front.jpg?raw=true)


# Body Of Knowledge

Semester 4

Wen Quist

Version 2.0

#

# Table of Contents
1. [Ip configuration](#ip-configuration)
2. [Web shop](#web-shop)
3. [Kali](#kali)
4. [DVWA](#dvwa)
    1. [Path traversal](#path-traversal)
    2. [File inclusion](#file-inclusion)
    3. [Command injection](#command-injection)
    4. [SQL injection](#sql-injection)
5. [HIDS](#hids)
6. [XSS](#xss)
    1. [Stored XSS attack](#stored-xss-attack)

#

## IP configuration

To get an image of how my own network looks like, I looked up my configurations in Windows Powershell. An Ip address is a 32-bit long binary number seperated in four octets and an unique adress connected to individual devices. With an Internet Protocol it's possible to communicate information between systems. Here you can see my desktop and the plugged in bluetooth adapter. 

![](https://github.com/wendelaQuist/Cyber_security/blob/main/Pictures/ipconfig.png?raw=true)


To make sure the host (my desktop) is properly connected to the internet, I succesfully pinged google.com. 

![](https://github.com/wendelaQuist/Cyber_security/blob/main/Pictures/ping.png?raw=true)

You can clearly see the ip adress of my desktop is 192.168.1.43 and Routers and switches will see it in binary, which would be: 11000000.10101000.00000001.00101011. To demonstrate how a router works i've also looked up the configuration of my laptop. 

![](https://github.com/wendelaQuist/Cyber_security/blob/main/Pictures/ipconfig-laptop.png?raw=true)

The ip adress of my notebook is 192.168.1.40, so my router is succesfully managing the traffic between other networks and my systems. 

#

## Web shop

To get started we had to set up a test web shop. I created a virtual machine in VMware by using the Kali template. To be able to work in a safe environment we had to connect to our virtual local area network. VLAN divides one physical switch into multiple virtual switches.

![](https://github.com/wendelaQuist/Cyber_security/blob/main/Pictures/Webshop.png?raw=true)

Now I had to install Apache, MySQL and PHP.

#

## Kali

Kali is a very useful operating system for penetration testing. It is open-source and has many tools and features to use for ethical hacking.

![](https://github.com/wendelaQuist/Cyber_security/blob/main/Pictures/Kali.png?raw=true)

#

## DVWA

DVWA is a web application specialized for hackers to improve and test their skills. DVWA has PHP and MySQL embedded to it. PHP is a multipurpose scripting language that can be used to develop dynamic websites without having to add extra files or any data. MySQL is an open-sourced system which manages databases.

I deployed an Ubuntu server with DVWA with a template made by school and connected to it with kali. Because I still need to learn a lot about hacking, I chose the low security level.

![](https://github.com/wendelaQuist/Cyber_security/blob/main/Pictures/DVWA.png?raw=true)

#

## Path traversal

Path or directory traversal gives hackers the opportunity to abuse security misconfigurations of a web server. This way hackers can acces databases outside the servers root directory or execute commands. 

#

## File Inclusion

Remote File Inclusion is a way to detect vulnerabilities in web applications that can be exploited. The main goal would be to use a "backdoor" to upload files that contains malware. This way you can sabotage servers

The challenges were to find 5 hidden quotes with file inclusion. At first, I opened all the three files and found one quickly in file 2.

I then thought maybe there was a hidden file, so I changed the URL from 3 to 4: 172.16.1.2/dvwa/vulnerabilities/fi/?page=4.php and did not find a quote but came across this screen.

![](https://github.com/wendelaQuist/Cyber_security/blob/main/Pictures/Vulnerability.png?raw=true)

When you click on view help you can likely see the directory where one of the quotes is stored.

![](https://github.com/wendelaQuist/Cyber_security/blob/main/Pictures/Objective.png?raw=true)

You need to go back twice before the site shows the hidden information.

![](https://github.com/wendelaQuist/Cyber_security/blob/main/Pictures/quotes.png?raw=true)

|**Quotes**| |
|:---------|:---------|
|1| **“I needed a password eight characters long, so I picked Snow White and the Seven Dwarves”**|
|2| **“Bond. James Bond”**|
|3| **“My name is Sherlock Holmes. It is my business to know what other people don’t know”**|
|4| **“The pool on the roof must have a leak”**|
|5| **"Line Hidden"**|

#

## Command injection

An unsecured web server can use vulnerable transmissions of data, like cookies and forms. 
Command injections is a cyber attack by using arbitrary code and basically breaching the system and getting acces to private data. There are multiple ways to use command injections such as shell commands or injecting infected files to a server. 

![](https://github.com/wendelaQuist/Cyber_security/blob/main/Pictures/IP-injection.png?raw=true)

I've entered my ip adress and this way I could acces an external server through an unsecured HTML element. I then implemented PHP code which the web server then executed.

#

## HIDS
Intrusion Detection Systems is a way to monitor network traffic. IDS will receive a copy of all the transferred data and uses signatures to compare normal with hackers activity. This way IDS can alert when there is malicious activity. 

IPS is a physical or virtual prevention system between a firewall and a network port. with the same signature system as IDS but will block the traffic between the router and port.

When an IDS software directly runs on a server , it is an Host intrusion detection/prevention system. Because HIDS operates with a signature-based system it works almost the same as an antivirus and functions as a firewall by looking for a pattern in the data. An anomaly system looks for irregular activity by the user or process

NIDS also surveys network traffic and events like HIDS, but works in a more targeting way by also analysing packet data when it travels through a network.

To keep a company as safe as possible for hackers it would be best to use both HIDS and IPS to complete eachother.

#

## SQL injection
SQL is a common language and it's purpose is to acces or modify databases. SQLI can be used to adjust the backend to display private information, like important business data or sensitive customer info. There are multiple types of SQL injection. With In-band SQLi the hacker launches their attacks through the same way of communication. In-band has two variations:

| | |
|:---------|:---------|
| Error-Based SQLi| The attacker sends wrong inputs to create error messages. These errors gives an implication about the structure of a database.|
| Union-based SQLi| The attacker can obtain information from a database by expanding results from the original query. This only works if the new queries have the same structure as the original ones.|

#

To practise this I had to get acces to the passwords of 5 users that are stored in de database. At first I submitted 1 to 5 to see what information I have acces to which is ID, first name and surname. When I submitted an invalid input I got a SQL error message. The URL changed and i modified it to find how many colums the database uses so i can match the structure. Order by 2 is the only input that redirects me back tot the page, which means it's correct and the database uses two columns. 
I used HackBar add-on as a pentest tool. This helped me with executing SQL injections to gain the hashes of the users. I converted these hashes by using crackstation which gave me the passwords of the 5 users.


#

## XSS

XSS is a form of an attack by injecting mischievous code in a normally trusted web page. Because of the site's security the script will be executed without being detected. Doing this will give the attacker access to cookies, session tokens, sensitive information and even the opportunity to rewrite html code.

#

## Stored XSS Attack
