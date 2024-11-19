# Introduction

This well-renowned concept is being applied to cybersecurity solutions like [Cisco Security](https://gblogs.cisco.com/ca/2020/08/26/the-canadian-bacon-cisco-security-and-the-pyramid-of-pain/), [SentinelOne](https://www.sentinelone.com/blog/revisiting-the-pyramid-of-pain-leveraging-edr-data-to-improve-cyber-threat-intelligence/), and [SOCRadar](https://socradar.io/re-examining-the-pyramid-of-pain-to-use-cyber-threat-intelligence-more-effectively/) to improve the effectiveness of CTI (Cyber Threat Intelligence), threat hunting, and incident response exercises.

Understanding the Pyramid of Pain concept as a Threat Hunter, Incident Responder, or SOC Analyst is important.

Are you ready to explore what hides inside the Pyramid of Pain? 

# Hash Values (Trivial)

As per Microsoft, the hash value is a numeric value of a fixed length that uniquely identifies data. A hash value is the result of a hashing algorithm. The following are some of the most common hashing algorithms: 

- **MD5 (Message Digest, defined by [RFC 1321](https://www.ietf.org/rfc/rfc1321.txt))** - was designed by Ron Rivest in 1992 and is a widely used cryptographic hash function with a 128-bit hash value. MD5 hashes are **NOT** considered **cryptographically secure**. In 2011, the IETF published RFC 6151, "[Updated Security Considerations for the MD5 Message-Digest and the HMAC-MD5 Algorithms](https://datatracker.ietf.org/doc/html/rfc6151)," which mentioned a number of attacks against MD5 hashes, including the hash collision.
  
- **SHA-1 (Secure Hash Algorithm 1, defined by [RFC 3174](https://datatracker.ietf.org/doc/html/rfc3174)** - was invented by United States National Security Agency in 1995. When data is fed to SHA-1 Hashing Algorithm, SHA-1 takes an input and produces a 160-bit hash value string as a 40 digit hexadecimal number. [NIST deprecated the use of SHA-1 in 2011](https://csrc.nist.gov/news/2017/research-results-on-sha-1-collisions) and banned its use for digital signatures at the end of 2013 based on it being susceptible to brute-force attacks. Instead, NIST recommends migrating from SHA-1 to stronger hash algorithms in the SHA-2 and SHA-3 families.

- **The SHA-2 (Secure Hash Algorithm 2)** - SHA-2 Hashing Algorithm was designed by The National Institute of Standards and Technology (NIST) and the National Security Agency (NSA) in 2001 to replace SHA-1. SHA-2 has many variants, and arguably the most common is SHA-256. The SHA-256 algorithm returns a hash value of 256-bits as a 64 digit hexadecimal number.
- 
A hash is not considered to be cryptographically secure if two files have the same hash value or digest.

Security professionals usually use the hash values to gain insight into a specific malware sample, a malicious or a suspicious file, and as a way to uniquely identify and reference the malicious artifact.

You've probably read ransomware reports in the past, where security researchers would provide the hashes related to the malicious or suspicious files used at the end of the report. You can check out The [DFIR Report](https://thedfirreport.com/) and [FireEye Threat Research Blogs](https://www.trellix.com/blogs/research/) if you’re interested in seeing an example.

Various online tools can be used to do hash lookups like [VirusTotal](https://www.virustotal.com/gui/home/upload) and [Metadefender Cloud - OPSWAT](https://metadefender.opswat.com/).

![image](https://github.com/user-attachments/assets/9e445917-8a12-4754-87fd-7ec532e055c4)

Below the hash in the screenshot above, you can see the filename. In this case, it is "m_croetian.wnry"

![image](https://github.com/user-attachments/assets/8b896942-31c1-4f35-bf10-75ab5da971ab)

As you might have noticed, it is really easy to spot a malicious file if we have the hash in our arsenal.  However, as an attacker, modifying a file by even a single bit is trivial, which would produce a different hash value. With so many variations and instances of known malware or ransomware, threat hunting using file hashes as the IOC (Indicators of Compromise) can become difficult.

Let’s take a look at an example of how you can change the hash value of a file by simply appending a string to the end of a file using **echo**: File Hash (Before Modification)

![image](https://github.com/user-attachments/assets/8bde1f53-dc5d-4a96-981e-894a39373ee7)

# IP Address (Easy)

An IP address is used to identify any device connected to a network. These devices range from desktops, to servers and even CCTV cameras! We rely on IP addresses to send and receive the information over the network. But we are not going to get into the structure and functionality of the IP address. As a part of the Pyramid of Pain, we’ll evaluate how IP addresses are used as an indicator.

In the Pyramid of Pain, IP addresses are indicated with the color green. You might be asking why and what you can associate the green colour with?

From a defense standpoint, knowledge of the IP addresses an adversary uses can be valuable. A common defense tactic is to block, drop, or deny inbound requests from IP addresses on your parameter or external firewall. This tactic is often not bulletproof as it’s trivial for an experienced adversary to recover simply by using a new public IP address.

Malicious IP connections ([app.any.run](https://app.any.run/tasks/a66178de-7596-4a05-945d-704dbf6b3b90)):

![image](https://github.com/user-attachments/assets/ddca5cc5-e7c3-4fc7-9a69-454ecac8f4fa)

**NOTE!** Do not attempt to interact with the IP addresses shown above.

One of the ways an adversary can make it challenging to successfully carry out IP blocking is by using Fast Flux.

According to [Akamai](https://www.akamai.com/blog), Fast Flux is a DNS technique used by botnets to hide phishing, web proxying, malware delivery, and malware communication activities behind compromised hosts acting as proxies. The purpose of using the Fast Flux network is to make the communication between malware and its command and control server (C&C) challenging to be discovered by security professionals. 

So, the primary concept of a Fast Flux network is having multiple IP addresses associated with a domain name, which is constantly changing. Palo Alto created a great fictional scenario to explain Fast Flux: "[Fast Flux 101: How Cybercriminals Improve the Resilience of Their Infrastructure to Evade Detection and Law Enforcement Takedowns](https://unit42.paloaltonetworks.com/fast-flux-101/)"

# Domain Names (Simple)

Let's step up the Pyramid of Pain and move on to Domain Names. You can see the transition of colors - from green to teal.

Domain Names can be thought as simply mapping an IP address to a string of text. A domain name can contain a domain and a top-level domain.

Domain Names can be a little more of a pain for the attacker to change as they would most likely need to purchase the domain, register it and modify DNS records. Unfortunately for defenders, many DNS providers have loose standards and provide APIs to make it even easier for the attacker to change the domain.

![image](https://github.com/user-attachments/assets/87192f1e-9f67-4e49-a05f-fe724987cd56)

![image](https://github.com/user-attachments/assets/a5c606d0-8d63-4d25-8a18-a934ce1cef30)

Can you spot anything malicious in the above screenshot? Now, compare it to the legitimate website view below:

![image](https://github.com/user-attachments/assets/a97c172e-cafe-4943-9703-22d31ecdca95)

This is one of the examples of a Punycode attack used by the attackers to redirect users to a malicious domain that seems legitimate at first glance.

What is Punycode? As per [Wandera](https://www.jamf.com/blog/punycode-attacks/), "Punycode is a way of converting words that cannot be written in ASCII, into a Unicode ASCII encoding."

What you saw in the URL above is **adıdas.de** which has the Punycode of **http://xn--addas-o4a.de/**

Internet Explorer, Google Chrome, Microsoft Edge, and Apple Safari are now pretty good at translating the obfuscated characters into the full Punycode domain name.

To detect the malicious domains, proxy logs or web server logs can be used.

Attackers usually hide the malicious domains under URL Shorteners. A URL Shortener is a tool that creates a short and unique URL that will redirect to the specific website specified during the initial step of setting up the URL Shortener link. According to [Cofense](https://cofense.com/url-shorteners-fraudsters-friend/), attackers use the following URL Shortening services to generate malicious links: 

- bit.ly
- goo.gl
- ow.ly
- s.id
- smarturl.it
- tiny.pl
- tinyurl.com
- x.co
- 
You can see the actual website the shortened link is redirecting you to by appending "+" to it (see the examples below). Type the shortened URL in the address bar of the web browser and add the above characters to see the redirect URL.

**NOTE: The examples of the shortened links below are non-existent.**

![image](https://github.com/user-attachments/assets/5ef7d028-cc60-4f0f-ae72-399806065537)

**Viewing Connections in Any.run:**

Because Any.run is a sandboxing service that executes the sample, we can review any connections such as HTTP requests, DNS requests or processes communicating with an IP address. To do so, we can look at the "networking" tab located just below the snapshot of the machine.

Please note: you should be extremely cautious about visiting any of the IP addresses or HTTP requests made in a report. After all, these are behaviours from the malware sample - so they're probably doing something dangerous!

**HTTP Requests:**

This tab shows the recorded HTTP requests since the detonation of the sample. This can be useful to see what resources are being retrieved from a webserver, such as a dropper or a callback.

![image](https://github.com/user-attachments/assets/1c94553f-2c38-4bc9-85cc-90943386a38c)

**Connections:**

This tab shows any communications made since the detonation of the sample. This can be useful to see if a process communicates with another host. For example, this could be C2 traffic, uploading/downloading files over FTP, etc.

![image](https://github.com/user-attachments/assets/217be002-6f39-4def-bb7c-c91501ebceb6)

**DNS Requests:**

This tab shows the DNS requests made since the detonation of the sample. Malware often makes DNS requests to check for internet connectivity (I.e. if It can't reach the internet/call home, then it's probably being sandboxed or is useless). 

# Host Artifacts (Annoying)
Let's take another step up to the yellow zone.

On this level, the attacker will feel a little more annoyed and frustrated if you can detect the attack. The attacker would need to circle back at this detection level and change his attack tools and methodologies. This is very time-consuming for the attacker, and probably, he will need to spend more resources on his adversary tools.

Host artifacts are the traces or observables that attackers leave on the system, such as registry values, suspicious process execution, attack patterns or IOCs (Indicators of Compromise), files dropped by malicious applications, or anything exclusive to the current threat.

![image](https://github.com/user-attachments/assets/463b0235-4496-44bf-83fd-b1fe4f31c61f)

**The files modified/dropped by the malicious actor:**

![image](https://github.com/user-attachments/assets/17500754-2ae1-498d-8959-50daa7babb28)

# Network Artifacts (Annoying)

Network Artifacts also belong to the yellow zone in the Pyramid of Pain. This means if you can detect and respond to the threat, the attacker would need more time to go back and change his tactics or modify the tools, which gives you more time to respond and detect the upcoming threats or remediate the existing ones.

A network artifact can be a user-agent string, C2 information, or URI patterns followed by the HTTP POST requests.An attacker might use a User-Agent string that hasn’t been observed in your environment before or seems out of the ordinary. The User-Agent is defined by [RFC2616](https://datatracker.ietf.org/doc/html/rfc2616#page-145) as the request-header field that contains the information about the user agent originating the request.

Network artifacts can be detected in Wireshark PCAPs (file that contains the packet data of a network) by using a network protocol analyzer such as TShark or exploring IDS (Intrusion Detection System) logging from a source such as [Snort](https://www.snort.org/).

HTTP POST requests containing suspicious strings:

![image](https://github.com/user-attachments/assets/6d9af58f-ee60-450e-9581-b3ceca45affb)

Let's use TShark to filter out the User-Agent strings by using the following command: 
**tshark --Y http.request -T fields -e http.host -e http.user_agent -r analysis_file.pcap**

![image](https://github.com/user-attachments/assets/304e1219-3554-4d92-965c-d583c09c52fc)

These are the most common User-Agent strings found for the [Emotet Downloader Trojan](https://www.mcafee.com/blogs/other-blogs/mcafee-labs/emotet-downloader-trojan-returns-in-force/)

If you can detect the custom User-Agent strings that the attacker is using, you might be able to block them, creating more obstacles and making their attempt to compromise the network more annoying.

# Tools (Challenging)

Congratulations! We have made it to the challenging part for the adversaries!

At this stage, we have levelled﻿ up our detection capabilities against the artifacts. The attacker would most likely give up trying to break into your network or go back and try to create a new tool that serves the same purpose. It will be a game over for the attackers as they would need to invest some money into building a new tool (if they are capable of doing so), find the tool that has the same potential, or even gets some training to learn how to be proficient in a certain tool. 

Attackers would use the utilities to create malicious macro documents (maldocs) for spearphishing attempts, a backdoor that can be used to establish **C2 (Command and Control Infrastructure)**, any custom .EXE, and .DLL files, payloads, or password crackers.

**A Trojan dropped the suspicious "Stealer.exe" in the Temp folder:**

![image](https://github.com/user-attachments/assets/acefcadc-bd70-4608-8fd3-c011ee2c4721)

The execution of the suspicious binary:

![image](https://github.com/user-attachments/assets/a052e355-4f92-458a-abd1-d71860e3f66d)

Antivirus signatures, detection rules, and YARA rules can be great weapons for you to use against attackers at this stage.

[MalwareBazaar](https://bazaar.abuse.ch/) and [Malshare](https://malshare.com/) are good resources to provide you with access to the samples, malicious feeds, and YARA results - these all can be very helpful when it comes to threat hunting and incident response. 

For detection rules, [SOC Prime Threat Detection Marketplace](https://tdm.socprime.com/signup) is a great platform, where security professionals share their detection rules for different kinds of threats including the latest CVE's that are being exploited in the wild by adversaries. 

Fuzzy hashing is also a strong weapon against the attacker's tools. Fuzzy hashing helps you to perform similarity analysis - match two files with minor differences based on the fuzzy hash values. One of the examples of fuzzy hashing is the usage of [SSDeep](https://ssdeep-project.github.io/ssdeep/index.html); on the SSDeep official website, you can also find the complete explanation for fuzzy hashing. 

Example of SSDeep from VirusTotal:

![image](https://github.com/user-attachments/assets/4062f341-cf0f-41e3-a762-5555c823fcdb)


