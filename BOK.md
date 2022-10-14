#

# **Cyber Security**

![](https://github.com/wendelaQuist/Cyber_security/blob/main/Pictures/front.jpg?raw=true)


# Body Of Knowledge

Semester 4

Wen Quist

Version 3.0

#

# Table of Contents
- [Intro](#intro)
- [Types of Cyber Security Threats](#types-of-cyber-security-threats)
- [IP configuration](#ip-configuration)
- [Web shop](#web-shop)
- [Kali](#kali)
- [DVWA](#dvwa)
  - [Path traversal](#path-traversal)
  - [File Inclusion](#file-inclusion)
  - [Command injection](#command-injection)
  - [HIDS](#hids)
  - [SQL injection](#sql-injection)
  - [Same-Origin Policy](#same-origin-policy)
  - [Cookies](#cookies)
  - [XSS](#xss)
  - [Stored XSS Attack](#stored-xss-attack)
  - [Reflected XSS](#reflected-xss)
  - [Cross Domain Acces Controls](#cross-domain-acces-controls)
  - [DOM-based XSS](#dom-based-xss)
  - [CSRF](#csrf)

#

## Intro
Everyday there is a threat of a cyber invasion going on in the world. Especially Ukraine was a victim of cyber-attacks that targeted important public and private individuals just before the war broke out. These attacks were focussed on ministries, armed forces and banks.

This is why I think it's important to learn more about cyber security to be able to protect yourself as much as you can. This semester I will learn more about diverse security systems, risks, detection and how to defend yourself against an hack. 

In the end I will be able to do a pentest on a company. This will mean detecting possible security threats and being able to report How these threats can be minimized.
#

## Types of Cyber Security Threats

There are a lot of ways to protect yourself, like using a antivirus program, never clicking on suspicious links, not sharing sensitive data, keeping systems up to date and make back-ups frequently. But there are some specialized attacks that require different ways to protect yourself or a company.

|Name|What does it do?|How to stay protected|
|:---------|:---------|:---------|
|Malware|It's a general term for virusses and trojans. Malicious software can be transmitted over an unsecured network and the goal is to corrupt as many machines possible.|To protect yourself from malware it's important to use an antivirus program and be carefull when downloading software.|
|Spam| Spam is unwanted email that is trying to make people click on links to unsecured websites or give up sensitive information. |It's important to look out for hidden hyperlinks that could hide itself as a image for instance. Also never reply to a spam mail. Some anti virus programs use a spam filter.|
|Phishing|Some hackers can pretend to be someone you know or a familiar company, and lure you into clicking on links or giving up private info, like your username and password.| Phishing mails to avoid, use keywords like "urgent" or "immediate action". Most of the times when a hacker is imitating a familiar person the text or email will look odd.|
|Spear Phishing|Instead of sending a general mail to as many people as possible, spear phishing is way more targeted. They usually investigate their target more and try to get high level executives to fall for a scam. An other term is Whaling.| It's very important to encrypt any sensitive company data and to use DMARC. Domain-based Message Authentication, Reporting & Conformance technology verifies if the email adress is stored in the database.|
|Adware|Adware is advertisement pop-ups which trap people into clicking on it. They earn money everytime people click on the link, or by how many times an ad is shown. Adware can track your search history to target and personalize the ads. Once they track your location and browser history, they can sell it to third paries.|When you download software from the internet, make sure you don't install unnecessary additional software.|
|Man-in-the-middle attack|When an end-user is exchanging data with a server a hacker could come in between and pretend to be both to manipulate the transfer and intercept sensitive data or send malicious links.| To prevent MITM attacks, companies could use multi-factor authentication, so an extra security like a personal pin code could help block a hacker.|
|Ransomware| As the name says, ransomware can encrypt or lock important information. It's a way to exploit people and companies for ransom money. It can degrade operations or shut down completely.|Don't plug unkown devices on to your system and use a anti-ransomware software.|
|Denial of Service (DoS and DDoS)|With a DoS attack a server will be flooded with Transmission Control Protocol and User Datagram Protocol packets. DDoS uses a lot of systems to send many packets to one network from multiple locations. By bombarding a server with many packets, it will overload and becomes unavailable. By shutting down servers, companies can lose a lot of money by being unusable untill the servers are up and running again.|It's hard to prevent Dos & DDoS, so it's important to decrease the damage of an attack. By regular network monitoring, It's possible to detect attacks before they take systems offline by not recognizing certain processes.|
|Advanced persistent threats|Instead of obtaining information in a short period of time, APT gaines information over a long period of time. Because it takes so much effort it is usually applied to big targets like, large corporations. This way they can implement malware that can open back doors undetected. Hackers can get more classified information in a matter of time and use it later for exploitation.|APT is very hard to prevent. It's important to use multiple measures from a firewall to spreading awareness of social engineering methods.|

![](https://github.com/wendelaQuist/Cyber_security/blob/main/Pictures/phishing-6926470_1280.png?raw=true)

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

To practise this I used help, which said I had to get acces to the passwords of 5 users. these users are stored in de database. When you look at the source code, you can see there is no validation which gives me the opportunity to inject lines of code. I looked up what pieces of code I could implement for exploitation. At first I submitted 1 to 5 to see what pieces of information I have acces to, which were ID, first name and surname. When I submitted an invalid input I got a SQL error message. The URL changed and I modified it to find how many colums the database uses so I can match the structure. Order by 2 is the only input that redirects me back tot the page, which means it's correct and the database uses two columns. 
I used HackBar add-on as a pentest tool to check for vulnerabilities. This helped me with executing SQL injections to gain the hashes of the users.

![](https://github.com/wendelaQuist/Cyber_security/blob/main/Pictures/hackbar-hashes.png?raw=true)

I converted these hashes by using crackstation which gave me the passwords of the 5 users.

![](https://github.com/wendelaQuist/Cyber_security/blob/main/Pictures/crackstation.png?raw=true)

#

## Same-origin policy

SOP is an important tool that regulates the way a document or script is loaded and interact. One origin can interact with the recourses of an other origin. 

It's possible for multiple URL's to have the same origin. This means the protocol, port and host would be indentical.

One of the reasons why Internet Explorer isn't safe to use is because it doesn't do same-origin checks. This means there are no restrictions and third parties could get acces between by cross-site scripting.

#

## Cookies

Cookies are text documents with pieces of information that contain the username and password. Browser cookies are very important in the present day, because a server creates the data that is stored in a cookie and attaches a unique ID. When there is an exchange between a server and computer the server will read the ID to confirm the user.  

![](https://media.nu.nl/m/m1nx532as18u_std1024.jpg)

#

## XSS

XSS is a form of an attack by injecting mischievous Javascript code in a normally trusted web page. It's an end-user attack by basically hijacking the users control. This can happen when a client visits a fake page and leaving credentials or clicking on malicious links. Because of the site's security the script will be executed without being detected. Doing this will give the attacker access to cookies, session tokens, sensitive information and even the opportunity to rewrite html code.

#

## Stored XSS Attack

When an application is used to store data, it can be compromised by injecting malicous code and storing it on the server. With this method hackers can open backdoors to gain more acces and information, but this will take a long time. In this time hackers can implement backdoors to get deeper into the system and learn more about the vulnerabilities. In the end the client could retreive scripts from the infected server to swap data. This is a persistent type of attack

![](https://github.com/wendelaQuist/Cyber_security/blob/main/Pictures/stored%20xss.png?raw=true)

#

## Reflected XSS

 When a server is unsecured enough a hacker could put malicious code into a input field like a login screen and send it to a server. A hacker would try to get the victim to give him/her access by sending phishing mails or creating a fake web page to get to the server. In this case the Hacker would retreive the session identifier to pretend to be the victim. The server will identify the Hacker as the victim and give up privileged data.

![](https://github.com/wendelaQuist/Cyber_security/blob/main/Pictures/reflected%20xss.png?raw=true)

#

## Cross Domain Acces Controls

Some web pages use iframes which integrates one website within another. These sites can't communicate with eachother due to Same-Origin policy. Only when the scheme, port and host are the same.

#

## CSRF

Cross-site request forgery is a way to partially bypass the same-origin policy. This way hackers can get remote control and change information like email adresses and passwords. 