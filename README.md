# sharingeye Documentation

Sharingeye is a system for external threat intelligence collection and asset monitoring/scanning for enterprises. Through its search capabilities, it provides a clear view of external network asset distribution, and can use specified vulnerability plugins to quickly perform service fingerprint detection on search results.

This site only performs preliminary detection and does not engage in any offensive behavior. Users must comply with the [Cybersecurity Law of the People's Republic of China](http://www.npc.gov.cn/npc/xinwen/2016-11/07/content_2001605.htm). Do not use it for unauthorized testing. This site assumes no joint legal liability.

## Feature Overview

The system monitors threats to companies by simulating a hacker's penetration-testing mindset. The main functions include the following:

### 1. Source Code Leak Threats

1.1 Code Leaks

    1.1.1 On the GitHub code hosting platform, trace leakage threats based on relevant keyword matching and target site employee information. (Implemented)

    1.1.2 On the Gitee code hosting platform, trace leakage threats based on relevant keyword matching and target site employee information. (In progress)

1.2 Data Leaks (Dark Web Monitoring)

    Real-time dark web monitoring to warn about leakage of employee or user information, helping address compliance and public relations concerns.

    1.2.1 Chinese dark web sites (Implemented)

    1.2.2 Alibaba (In progress)

    1.2.3 Tea Horse Road (In progress)

    1.2.4 Loulan (Implemented)
    ...

### 2. Vulnerability Early Warning Intelligence (In progress)

2.1 Public Vulnerability Intelligence

    2.1.1 [cert360](https://cert.360.cn/daily?date=)

    2.1.2 cnnvd

    2.1.3 cnvd

    2.1.4 cve

    2.1.5 exploitdb

    2.1.6 xz

    2.1.7 exploitalert

    2.1.8 xuanwu
    ...

### 3. Asset Information Monitoring

- Collect key information such as domain and IP asset port services and version fingerprints. Combined with vulnerability intelligence, vulnerability detection PoCs, and high-risk ports, this helps enterprises mitigate internal and external threats quickly and efficiently.
- To avoid the source IP being blocked by WAF/firewall devices during scanning, customers need to enable the appropriate protection policies.

3.1 Asset Collection

    3.1.1 Domain collection, including subdomain discovery (from search engines, GitHub, open APIs, etc.) and subdomain brute-forcing. (Implemented)

    3.1.2 Port scanning and middleware fingerprint identification. (Implemented)

    3.1.3 Website web application fingerprint identification. (Implemented)

3.2 Vulnerability Scanning

    3.2.1 Scan for common vulnerabilities in the collected fingerprints. (In progress)

3.3 Customized Vulnerability Scanning

    3.3.1 Scan web services and interfaces for common vulnerabilities (SQLi, XSS, RCE, etc.). (Not implemented)

    3.3.2 Based on customized dictionaries, automatically brute-force middleware and web applications that require authentication or backend login pages. (Not implemented)

    3.3.3 Scan sensitive files and folders in web services with high accuracy and compatibility. (Not implemented)

    3.3.4 Generate customized user and password dictionaries based on public information collected in the previous stage and other leaked databases. (Not implemented)

    3.3.5 IP geolocation and identification of target-owned Class C network segments. (Not implemented)

3.4 Collection-Based Monitoring

This mode uses collected open-source data and a big-data correlation model to provide early warnings before attackers begin active information gathering, helping customers eliminate potential enterprise risks in time.

    3.4.1 Use open-source intelligence such as Shodan/Fofa to obtain IP port/service fingerprint information, and combine it with vulnerability intelligence for timely alerts

    3.4.2 Monitor system components provided by customers or proactively collected by the system using Google hacking techniques

    3.4.3 Extract sensitive asset data from leaked GitHub code, such as database account credentials

    3.4.4 Monitor the SSL certificate status of running business systems and warn about abnormal certificates such as expiration or self-signed certificates

    3.4.5 Focus on monitoring externally exposed customer mailboxes and email security gateways, along with personal security awareness training

    3.4.6 Monitor API interfaces of external sites for possible API data/privacy leakage

    3.4.7 Map the supply chain of procurement systems and link it with vulnerability intelligence

    3.4.8 Provide focused security awareness education for externally exposed email accounts

### 4. Business Intelligence

4.1 Compliance Monitoring

    4.1.1 Monitor WeChat Official Accounts (In progress)

4.2 Public Opinion Monitoring on Coupon/Abuse Communities

    4.2.1 zuanke8

    ...

### 5. Feedback

Submit issues in [sharingeye_docs](https://github.com/hahadaxia/sharingeye_docs).
