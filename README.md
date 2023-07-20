# Building a Vulnerability Management Lab (Nessus)

## Introduction

In this project, I utilized Nessus Essentials to perform vulnerability scans on a Windows host, identify, assess, prioritize and remediate some of them.

![Visual](https://www.dropbox.com/s/7uhnduacqwhgyd7/visual.jpg?raw=1)

## Steps

1. I setup a vulnerable Windows 10 virtual machine, with outdated software and I disabled security controls and firewalls.
2. I installed and configured Nessus Essentials to perform unauthenticated and credentialed scans against the Windows host.
3. I generated comprehensive vulnerability reports to assess and prioritize vulnerabilities according to severity scores.
4. I analyzed the scan results and reports, highlighting the difference between unauthenticated and credentialed scans.
5. I remediated most critical and highest identified vulnerabilities, and verified successful remediation through subsequent scans and reports.

## Unauthenticated Scan Results
Although I installed deprecated softwares on the Windows virtual machine, the non credentialed scan was not able to identify critical or high vulnerabilities. 

![Non credentialed report](https://www.dropbox.com/s/g6lb0j83ow2bk4r/non-credentialed-screenshot.png?raw=1)

## Authenticated Scan Results
The credentialed scan was able to identify many critical and high vulnerabilities, most of them caused by the deprecated softwares installed on the host.

![Credentialed report before remediation](https://www.dropbox.com/s/h6lfjhq2mjdh3to/credentialed-screenshot-with-deprecated-softwares.png?raw=1)

## Remediation

1. First step of remediation, I analyzed carefully the Nessus generated report about credentialed scan
2. I noticed that many vulnerabilities could be addressed by removing deprecated softwares and installing the latest Windows updates
3. So I removed the deprecated softwares that were install for purpose, and runned Windows update

![Removing deprecated softwares](https://www.dropbox.com/s/tdn0mr74v6ry5qy/removing-softwares.png?raw=1)
![Latest Windows updates](https://www.dropbox.com/s/7onuppl3hsktp44/updating-windows.png?raw=1)

## Post Remediation Authenticated Scan Results

Now that I removed the deprecated softwares and installed the latest Windows updates, I can see that critical and high vulnerabilities have been reduced drastically. And all vulnerabilties caused by deprecated softwares don't appear anymore.
There are still some critical and high vulnerabilities that were not remediated in this lab, I suppose that it is due to the deprecated Windows host itself (Windows 10 22H2)

![Post remediation scan](https://www.dropbox.com/s/2o9i5lgob3kol3i/credentialed-scan-post-remediation.png?raw=1)

## Conclusion
In this project, Nessus scanner was used to identify, understand and remediate some vulnerabilities. Generated reports were used to assess and prioritize vulnerabilities. Only authenticated scans can go deeply and find vulnerabilities, the unauthenticated scan only scrathes the surface. 
We noticed that the more deprecated softwares are the more critical and high vulnerabilities could be identified. Same for updates, a Windows machine should always has the latest updates. 
So as a good practice for remediation and mitigation it is important to keep our machine and softwares up to date.
