# Building a Vulnerability Management Lab (Nessus)

## Introduction

In this project, I utilized Nessus scan to perform vulnerability scanning on a Windows host. Then, I identified, assessed, prioritized and remediated most critical and highest vulnerabilities.

![Visual](https://www.dropbox.com/s/7uhnduacqwhgyd7/visual.jpg?raw=1)

## Steps

1. Setup a vulnerable Windows 10 virtual machine, with outdated software and I disabled security controls and firewalls.
2. Installed and configured Nessus on another Linux Virtual Machine to perform unauthenticated and credentialed scans against the Windows VM.
3. Generated comprehensive vulnerability reports to assess and prioritize vulnerabilities according to severity scores.
4. Analyzed the scan results and reports, highlighting the difference between unauthenticated and credentialed scans.
5. Remediated most critical and highest identified vulnerabilities, and verified successful remediation through subsequent scans and reports.

## Preparation and Scope
The specific requirements is to be able to detect critical and hight vulnerabilities caused by the deprecated softwares installed on the Windows 10 VM.
The system and network infrastructure are simple : it is only a Windows 10 vulnerable virtual machine for which the security controls and firewalls have been disabled.

## Information Gathering
Regarding the environment it is only a Windows 10 Virtual Machine with one IP address. The ISO version of Windows 10 is Windows 10 22H2.

## Identify Vulnerabilities

### Unauthenticated Scan Results
The first scan is a non credentialed scan. It was not able to detect any critical or high vulnerabilities, although deprecated softwares were installed.

![Non credentialed report](https://www.dropbox.com/s/g6lb0j83ow2bk4r/non-credentialed-screenshot.png?raw=1)

### Authenticated Scan Results
The credentialed scan was able to identify many critical and high vulnerabilities. These vulnerabilities are caused by the presence of deprecated softwares installed on the host.

![Credentialed report before remediation](https://www.dropbox.com/s/h6lfjhq2mjdh3to/credentialed-screenshot-with-deprecated-softwares.png?raw=1)

## Prioritize Vulnerabilities
By analyzing the report of the authenticated scan we can see that there is a lot of critical and high vulnerabilities, but also some medium vulnerabilities and a bunch of informational ones. We exclude the informational vulnerabilities because there is no score for them, and we decide to prioritize only critical and high vulnerabilities.

## Risk Assessment
Critical vulnerabilities have a high severity score, so they can potentially impact the host.

## Recommendations
We recommand to remediate ni the first time critical vulnerabilities, then high vulnerabilities.

## Remediation Planning
As most of critical and high vulnerabilities are caused by the deprecated softwares and a lack of Windows updates, we plan to remove the deprecated softwares from the system and install the latest Windows updates.

![Removing deprecated softwares](https://www.dropbox.com/s/tdn0mr74v6ry5qy/removing-softwares.png?raw=1)
![Latest Windows updates](https://www.dropbox.com/s/7onuppl3hsktp44/updating-windows.png?raw=1)

## Verification

Now that the deprecated softwares were removed and Windows updates were installed, the next authenticated scan reveals that critical and high vulnerabilities have been reduced drastically. By analysing the report we notice that all vulnerabilties caused by the deprecated softwares don't appear anymore.
Nevertheless,there are still some remaining critical and high vulnerabilities. We didn't remediate them in this lab, but we suppose that they are caused by the version of the system itself; Windows 10 22H2 ISO installed on the Virtual Machine.

![Post remediation scan](https://www.dropbox.com/s/2o9i5lgob3kol3i/credentialed-scan-post-remediation.png?raw=1)

## Conclusion
In this project, Nessus scan was used to identify, assess, prioritize and remediate some vulnerabilities. 
Generated reports were used to assess and prioritize vulnerabilities. Only authenticated scans could go deeply and identify vulnerabilities, the unauthenticated scan only scrathed the surface. 
We noticed that the more deprecated softwares are installed on a system the more critical and high vulnerabilities could be identified.
Same for Windows updates, if the system is not updated regularly with security patches a vulnerability scan will display high or critical vulnerabilities. 
So, as a good practice to mitigate threats it is recommended to keep our system and softwares up to date.
