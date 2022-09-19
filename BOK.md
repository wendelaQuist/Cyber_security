#
# **Cyber Security**

#
# Body Of Knowledge

Semester 4

Wen Quist

Version 1.0

![](./Pictures/front.jpg)

#
# **Contents**

[**Web shop** 3](#_Toc114476199)

[**Kali** 4](#_Toc114476200)

[**Damn vulnerable web application** 5](#_Toc114476201)

[**File Inclusion** 6](#_Toc114476202)

[**Microsoft Server network** 8](#_Toc114476203)

[**XSS** 9](#_Toc114476204)

[**Stored XSS Attack** 9](#_Toc114476205)

#
# **Web shop**

To get started we had to set up a test web shop. I created a virtual machine in VMware by using the Kali template. To be able to work in a safe environment we had to connect to our virtual local area network. VLAN divides one physical switch into multiple virtual switches.

![](RackMultipart20220919-1-yjkp55_html_f872225179982067.png)

#

#
# **Kali**

Kali is a very useful operating system for penetration testing. It is open-source and has many tools and features to use for ethical hacking.

![](RackMultipart20220919-1-yjkp55_html_34cd8662a3754a14.png)

#

#
# **Damn vulnerable web application**

DVWA is a web application specialized for hackers to improve and test their skills. DVWA has PHP and MySQL embedded to it. PHP is a multipurpose scripting language that can be used to develop dynamic websites without having to add extra files or any data. MySQL is an open-sourced system which manages databases.

I deployed an Ubuntu server with DVWA with a template made by school and connected to it with kali. Because I still need to learn a lot about hacking, I chose the low security level.

![](RackMultipart20220919-1-yjkp55_html_1e87e89eff9510cf.png)

#

#

#

#

#

#

#

#

#
# **File Inclusion**

Remote File Inclusion is a way to detect vulnerabilities in web applications that can be exploited. The main goal would be to use a "backdoor" to upload files that contains malware. This way you can sabotage servers

The challenges were to find 5 hidden quotes with file inclusion. At first, I opened all the three files and found one quickly in file 2.

I then thought maybe there was a hidden file, so I changed the link from 3 to 4: 172.16.1.2/dvwa/vulnerabilities/fi/?page=4.php and did not find a quote but came across this screen.

![](RackMultipart20220919-1-yjkp55_html_48f15e9d91be0572.png)

When you click on view help you can likely see the directory where on of the quotes is stored.

![](RackMultipart20220919-1-yjkp55_html_422acbeb4e5094d8.png)

You need to go back twice before the site shows the hidden information.

![](RackMultipart20220919-1-yjkp55_html_1af6655010f0184d.png)

|
 | **Quotes** |
| --- | --- |
| **1.** | "I needed a password eight characters long, so I picked Snow White and the Seven Dwarves" ~Nick Helm |
| **2.** | "Bond. James Bond" |
| **3.** | "My name is Sherlock Holmes. It is my business to know what other people don't know" |
| **4.** | "the pool on the roof must have a leak" |
| **5.** |
 |

#

#

#

#

#
# **Microsoft Server network**

I wanted to setup a windows server and use it to function as a router.

![](RackMultipart20220919-1-yjkp55_html_39bb8cf675a826bb.png)I've had some trouble connecting to the internet, so I still need to figure out what went wrong when configuring the IP-settings.

#
# **XSS**

XSS is a form of an attack by injecting mischievous code in a normally trusted web page. Because of the site's security the script will be executed without being detected. Doing this will give the attacker access to cookies, session tokens, sensitive information and even rewrite the html code.

##
# **Stored XSS Attack**
