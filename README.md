# Building a Vulnerability Management Lab (Nessus)

## Introduction

In this project, I utilized Nessus Essentials to perform vulnerability scans on a Windows host, identify, prioritize and remediate some of them.

![Visual](https://www.dropbox.com/s/7uhnduacqwhgyd7/visual.jpg?raw=1)

## Steps

1. First I setup an old Windows 10 virtual machine, with outdated software and I disabled security controls and firewalls.
2. I installed and configured Nessus Essentials to perform unauthenticated and credentialed scans against the Windows host.
3. I generated comprehensive vulnerability reports to assess and prioritize vulnerabilities according to severity scores.
4. I analyzed the scan results and reports, highlighting the difference between unauthenticated and credentialed scans.
5. Finally I remediated some identified vulnerabilities, and verified successful remediation through subsequent scans and reports.

## Unauthenticated Scan Results
Although I installed deprecated softwares on the Windows virtual machine, the non credentialed scan was not able to identify critical or high vulnerabilities. 

![Nessus Dashboard](https://www.dropbox.com/s/oajzcmb1np24jj9/Unauthenticated%20scan%20dashboard.jpeg?raw=1)
![Nessus Dashboard](https://www.dropbox.com/s/13l5ishhlfnt0q5/Unauthenticated%20scan%20report.jpeg?raw=1)

## Authenticated Scan Results
The credentialed scan was able to identify many critical and high vulnerabilities, most of them caused by the deprecated softwares installed on the host.

![Nessus Dashboard](https://www.dropbox.com/s/2bj5bo6p2otnn5y/Authenticated%20scan%20dashboard.jpeg?raw=1)
![Nessus Dashboard](https://www.dropbox.com/s/efg23wqrb1ffb5p/Authenticated%20scan%20report.jpeg?raw=1)

## Remediation + Authenticated Scan Results
As remediation I uninstalled the deprecated softwares, and run a new authenticated scan. This time most of the critical and high vulnerabilities were not detected, but some of them still exist because of the version of Windows which is used (Windows 10 Pro 22H2)

![Nessus Dashboard](https://www.dropbox.com/s/wzl5hxwijgevbqw/Authenticated%20scan%20after%20remediation%20dashboard.jpeg?raw=1)
![Nessus Dashboard](https://www.dropbox.com/s/33wcp4txj8uokj7/Authenticated%20scan%20after%20remediation%20report.jpeg?raw=1)

## Conclusion
In this project, Nessus scanner was used to identify, understand and remediate some vulnerabilities. Only authenticated scans can go deeply and find vulnerabilities, the unauthenticated scan only scrathes the surface. We noticed that the more deprecated softwares are the more critical and high vulnerabilities could be identified. So as a good practice for remediation and mitigation it is important to keep our machine and softwares up to date.
