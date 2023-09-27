# Penetration Testing Notes & Resources
I am creating this in order to consolidate my notes, as well as to share the abundance of information I've gathered and will continue to gather, with others
who may be interested in cybersec and penetration testing.


# Table of Contents

- [Resources!](#resources)

- [Penetration Testing Fundamentals](#Penetration-Testing-Fundamentals)

	- [Penetration Testing Methodologies](#penetration-testing-methodologies)

- [Penetration Testing Frameworks](#penetration-testing-frameworks)

	- [OSSTMM](#osstmm)
	- [OWASP](#owasp)
	- [NIST](#nist)
   	- [NCSC CAF](#ncsc-caf)

- [Walking An Application](#walking-an-application)

	- [Browser Tools](#browser-tools)

- [Content Discovery](#content-discovery)
	- [Manual Discovery](#manual-discovery)
   		- [Robots.txt](#robotstxt)
   		- [Favicon](#Favicon)
		- [Sitemap.xml](#sitemapxml)
  		- [HTTP Headers](#http-headers)
	- [OSINT](#osint)
 		- [Google Dorking](#google-dorking)
   		- [Wappalyzer](#wappalyzer)
   		- [Wayback Machine](#wayback-machine)
   		- [S3 Buckets](#s3-buckets)
   	- [Automated Discovery](#automated-discovery)
   		- [Automation Tools](automation-tools)
 

---


# Resources!

[https://github.com/saisathvik1/OSCP-Cheatsheet#oscp-cheatsheet](https://github.com/saisathvik1/OSCP-Cheatsheet#oscp-cheatsheet)




# Penetration Testing Fundamentals

### **Penetration Testing Methodologies**

| Stage | Description |
| --- | --- |
| Information Gathering | This stage involves collecting as much publicly accessible information about a target/organization as possible, for example OSINT and research This does not involve scanning systems |
| Enumeration/Scanning | This stage involves discovering applications and services running on the systems. For example, finding a web server that may be potentially vulnerable. |
| Exploitation | This stage involves leveraging vulnerabilities discovered on a system or application. This stage can involve the use of public exploits or exploiting application logic. |
| Privilege Escalation | Once you have exploited a system and have access, this stage is where you attempt to expand your access to a system. You can escalate **horizontally** and **vertically**, where **horizontally** is accessing another account of the same permission group. And escalating **vertically** is accessing another user that is of another permission group (an admin) |
| Post-exploitation | This stage involves a few sub-stages: **1.** What other hosts can be targeted (pivoting), **2.** What additional information can we gather from the host now that we are a privileged user?, **3.** Covering your tracks. , **4.** Reporting |




---


# Penetration Testing Frameworks

### **OSSTMM**

The **Open Source Security Testing Methodology Manual**

- Provides a detailed framework of testing strategies for systems, software,	applications, communications and the human aspects of cybersecurity.
    - [https://www.isecom.org/OSSTMM.3.pdf](https://www.isecom.org/OSSTMM.3.pdf)

The methodology focuses primarily on how these systems, applications communicate, so it
includes a methodology for:

1. **Telecommunications (phones, VoIP, etc.)**
2. Wired Networks
3. Wireless communications

| Advantages | Disadvantages |
| --- | --- |
| Covers various testing strategies in-depth | The Framework is difficult to understand, very detailed, and tends to use unique definitions. |
| Includes testing strategies for specific targets (i.e. telecommunications and networking) | Intentionally left blank. |
| The framework is flexible depending upon the organizations needs | Intentionally left blank. |
| The framework is meant to set a standard for systems and applications Meaning that a universal methodology can be used in a penetration testing scenario. | Intentionally left blank. |

---

### **OWASP**

The “****************************Open Web Application Security Project”**************************** framework is a community-driven and frequently updated framework used solely to test the security of web applications and services.

The foundation regularly writes reports stating the top ten security vulnerabilities a web application may have, the testing approach, and remediation.

| Advantages | Disadvantages |
| --- | --- |
| Easy to pick up and understand. | It may not be clear what type of vulnerability a web application has (they can often overlap). |
| Actively maintained and is frequently updated. | OWASP does not make suggestions to any specific software development life cycles. |
| It covers all stages of an engagement: from testing to reporting and remediation. | The framework doesn't hold any accreditation such as CHECK. |
| Specializes in web applications and services. | Intentionally left blank. |

---

### **NIST**

The NIST Cybersecurity Framework is a popular framework used to improve an organizations cybersecurity standards and manage the risk of cyber threats. This framework is a bit of an honorable mention because of its popularity and detail.

The framework provides guidelines on security controls & benchmarks for success for organizations from critical infrastructure to commercial. 

There is a limited section on a standard guideline for the methodology a penetration tester should take.

| Advantages | Disadvantages |
| --- | --- |
| The NIST Framework is estimated to be used by 50% of American organizations by 2020. | NIST has many iterations of frameworks, so it may be difficult to decide which one applies to your organization. |
| The framework is extremely detailed in setting standards to help organizations mitigate the threat posed by cyber threats. | The NIST framework has weak auditing policies, making it difficult to determine how a breach occurred. |
| The framework is very frequently updated. | The framework does not consider cloud computing, which is quickly becoming increasingly popular for organizations. |
| NIST provides accreditation for organizations that use this framework. | Intentionally left blank. |
| The NIST framework is designed to be implemented alongside other frameworks. | Intentionally left blank. |

---

### **NCSC CAF**

The [Cyber Assessment Framework](https://www.ncsc.gov.uk/collection/caf/caf-principles-and-guidance) (CAF) is an extensive framework of fourteen principles used to assess  the risk of various cyber threats and an organization's defenses against these.

The framework applies to organizations considered to perform "vitally 
important services and activities" such as critical infrastructure, banking, and the likes. The framework mainly focuses on and assesses the
 following topics:

- Data security
- System security
- Identity and access control
- Resiliency
- Monitoring
- Response and recovery planning

---



# Walking An Application

Manually review a web application for security Issues using only a browsers developer tools.

### ********Browser Tools:********

Here is a short breakdown of the in-built browser tools you will use:

- **View Source** - Use your browser to view the human-readable source code of a website.
- **Inspector** - Learn how to inspect page elements and make changes to view usually blocked content.
- **Debugger** - Inspect and control the flow of a page's JavaScript
- **Network** - See all the network requests a page makes.

---


# Content Discovery

Learn the various ways of discovering hidden or private content on a web-server that could lead to new vulnerabilities.

- In pentesting content can mean many things.
    - A file, video, picture, backup-file or website feature
        - Ex: Administration panels, configuration files, older version of the website.

************************************************************************************************There are three main ways of discovering website content************************************************************************************************

- Manually
- Automated
- OSINT (Open Source Intelligence)

---

# Manual Discovery

### Robots.txt

```markdown
Example:
http://URL/robots.txt
```

**robots.txt** is a file that tells search engines which pages they are ******NOT****** allowed to show, or ban specific search engines from crawling the website at all.

- These pages may contain administration portals, or files.
    - This is a good place to look as these are areas that the website owners don’t want us to discover.

---

### Favicon

A favicon is a small icon displayed in the address bar of the browser.

Sometimes when a framework is used to build a website, a favicon (part of the installation) is left over. 

- This can give us a clue as to what framework is in use.
    - Once we know the framework stack we can use external resources to discover more information about it
    - Viewing the framework’s documentation page gives us the path of the framework’s administration portal

Using the **view source** tool in your browser you can discover the favicon

```html
<!-- Favicon Example -->

<title> Hello World!</title>
<link rel="shortcut icon" type="image/jpg" href="**images/favicon.ico**"/>
```

Once the favicon path has been discovered copy the path and add it to the end of the URL and run the following command to download the favicon and obtain its md5 hash, which you can lookup here: [https://wiki.owasp.org/index.php/OWASP_favicon_database](https://wiki.owasp.org/index.php/OWASP_favicon_database)

```bash
user@machine$ curl https://**URL**/images/favicon.ico | md5sum
```

- If the hash ends with ********427e******** then the curl failed

---

### Sitemap.xml

Sitemap.xml is essentially the opposite of robots.txt, as sitemap.xml gives a list of every file the website owner wishes to be listed

- **********************************************************Be sure to check sitemap.xml as it can contain old webpages and other information**********************************************************

```bash
https://www.**URL**/sitemap.xml
```

---

### HTTP Headers

Whenever we make requests to a web server, the server responds with various HTTP headers. 

- These headers can sometimes contain useful information such as webserver software, and programming languages in use

As seen in the example below, we can see the webserver is running NGINX version 1.18.0 and PHP version 7.4.3 allowing us to see if there are any vulnerabilities in the software being used.

```bash
#Example HTTP Header curl command

$ curl http://WEBSITE_URL -v
*   Trying WEBSITE_URL:80...
* TCP_NODELAY set
* Connected to WEBSITE_URL (WEBSITE_URL) port 80 (#0)
> GET / HTTP/1.1
> Host: WEBSITE_URL
> User-Agent: curl/7.68.0
> Accept: */*
> 
* Mark bundle as not supporting multiuse
< HTTP/1.1 200 OK
< Server: nginx/1.18.0 (Ubuntu)
< X-Powered-By: PHP/7.4.3
< Date: Mon, 19 Jul 2021 14:39:09 GMT
< Content-Type: text/html; charset=UTF-8
< Transfer-Encoding: chunked
< Connection: keep-alive
```

---

# OSINT

OSINT or Open-source Intelligence is the action or use of freely available tools to gather information.

### Google Dorking

Google dorking allows you to use Google’s advanced search engine features to pick out custom content using filters

Below is a list of example filters: (more can be found online)

| Filter | Example | Description |
| --- | --- | --- |
| site | site:google.com | returns results only from the specified website address |
| inurl | inurl:admin | returns results that have the specified word in the URL |
| filetype | filetype:pdf | returns results which are a particular file extension |
| intitle | intitle:admin | returns results that contain the specified word in the title |

---

### Wappalyzer

Wappalyzer is an online tool/browser extenstion that helps identify what technologies a website uses

[https://www.wappalyzer.com/](https://www.wappalyzer.com/)

---

### Wayback Machine

The Wayback Machine ([https://archive.org/web/](https://archive.org/web/)) is an archive of webistes that dates back to the late 90s, you can enter a domain name and search the scraped webpages and potenially uncover old pages, and files.

---

### S3 Buckets

**S3 Buckets**

S3 Buckets are a storage service provided by Amazon AWS, allowing people to save files and even static website content in the cloud accessible 
over HTTP and HTTPS. The owner of the files can set access permissions 
to either make files public, private and even writable. 

Sometimes these access permissions are incorrectly set and inadvertently allow access to files that shouldn't be available to the public. The format of the S3 buckets is http(s)://**{name}.[s3.amazonaws.com](http://s3.amazonaws.com/)** where {name} is decided by the owner, such as [google.s3.amazonaws.com](http://tryhackme-assets.s3.amazonaws.com/). 

S3 buckets can be discovered in many ways, such as finding the URLs in the website's page source, GitHub repositories, or even automating the process. One common automation method is by using the company name followed by common terms such as:

 **{name}-**assets , **{name}-**www , **{name}-**public , **{name}-**private , etc.

---

# Automated Discovery

Automated Discovery is the process of using tools to discover content instead of doing it manually, this can allow for hundreds, thousands, or millions of requests to be made to a web-server.

[Daniel Miessler SecLists](https://github.com/danielmiessler/SecLists)

### Automation Tools

There are countless content discovery tools freely available online. Here are some example commands from **ffuf**, **dirb** and **gobuster**

********ffuf********

```bash
ffuf -w /usr/share/wordlists/SecLists/Discovery/Web-Content/common.txt -u http://WEBSITE_URL/FUZZ
```

********dirb********

```bash
user@machine$ dirb http://WEBSITE_URL/ /usr/share/wordlists/SecLists/Discovery/Web-Content/common.txt
```

****************gobuster****************

```bash
gobuster dir --url http://WEBSITE_URL/ -w /usr/share/wordlists/SecLists/Discovery/Web-Content/common.txt
```







