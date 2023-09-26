# Penetration Testing Notes & Resources
I am creating this in order to take notes, as well as to share them with others
who may be interested in cybersec and penetration testing.


# Table of Contents

- [Resources!](#resources)

- [Penetration Testing Fundamentals](#Penetration-Testing-Fundamentals)

	- [Penetration Testing Methodologies](#penetration-testing-methodologies)

- [Penetration Testing Frameworks](#penetration-testing-frameworks)

- [Walking An Application](Walking%20An%20Application%205d62967c31384fe2a6df8b40f2b707c0.md)

- [Content Discovery](Content%20Discovery%203ac5c1f37a2042fea87a520540fe9ba6.md)





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

### **OWASP**

The “****************************Open Web Application Security Project”**************************** framework is a community-driven and frequently updated framework used solely to test the security of web applications and services.

The foundation regularly writes reports stating the top ten security vulnerabilities a web application may have, the testing approach, and remediation.

| Advantages | Disadvantages |
| --- | --- |
| Easy to pick up and understand. | It may not be clear what type of vulnerability a web application has (they can often overlap). |
| Actively maintained and is frequently updated. | OWASP does not make suggestions to any specific software development life cycles. |
| It covers all stages of an engagement: from testing to reporting and remediation. | The framework doesn't hold any accreditation such as CHECK. |
| Specializes in web applications and services. | Intentionally left blank. |

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





# Walking An Application

Manually review a web application for security Issues using only a browsers developer tools.

### ********Browser Tools:********

Here is a short breakdown of the in-built browser tools you will use:

- **View Source** - Use your browser to view the human-readable source code of a website.
- **Inspector** - Learn how to inspect page elements and make changes to view usually blocked content.
- **Debugger** - Inspect and control the flow of a page's JavaScript
- **Network** - See all the network requests a page makes.





