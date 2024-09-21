# Network Enumeration with Nmap
The tools are just tools, and tools alone should never replace our knowledge and our attention to detail.
Enumeration is collecting as much information as possible. The more information we have, the easier it will be for us to find vectors of attack.
`Enumeration is the key`.
# Login Brute Forcing
# Attacking Web Applications with Ffuf
# # Introduction to Security Incident Reporting

## Identification
There are primarily three key sources for incident identification:

**Security Systems/Tooling in Place:** IDS/IPS, EDR/XDR, SIEM tools, or even basic anti-virus alerts and NetFlow data. Security systems that are usedin your organization.
**Human Observations:** Users may notice and report suspicious activities, unusual emails, or systems behaving abnormally.
**Third Party Notifications:** Partners, vendors, or even customers might inform organizations about any vulnerabilities or breaches they are experiencing.

## Categorisation
### Types
-   `Malware`: Malicious software encompassing viruses, worms, and ransomware.
-   `Phishing`: Fraudulent endeavors to exfiltrate sensitive information, predominantly via email.
-   `DDoS Attacks`: Deliberate attempts to inundate a system or network, thereby disrupting its regular functionality.
-   `Unauthorised Access`: Incidents where unauthorized entities gain access to systems or data repositories.
-   `Data Leakage`: Inadvertent exposure of confidential data, both within and outside the organizational perimeter.
-   `Physical Breach`: Unauthorized physical access to secure locations.
### Severity
-   `Critical` (P1): Imminent threats that jeopardize core business functionalities or sensitive data, necessitating immediate intervention.
-   `High` (P2): Latent threats to business operations that, while not immediately detrimental, are of elevated priority.
-   `Medium` (P3): Incidents that, although not posing an immediate threat to business operations, warrant timely attention.
-   `Low` (P4): Trivial incidents or routine anomalies that can be managed within standard operational workflows.

## Reporting Process
### 1. Initial Detection & Acknowledgment
### 2. Preliminary Analysis
Scope and potential ramifications are ascertained. Incident is categorized
### 3. Incident Logging
Popular platforms for this purpose include [JIRA](https://www.atlassian.com/software/jira) and [TheHive Project](https://thehive-project.org/).
Even rudimentary tools like pen and paper or a spreadsheet can suffice in a pinch.
### 4. Notification of Relevant Parties
Stakeholders must be promptly identified.
notifications should be segmented into:
-   `Internal Communications`
    Relevant internal departments, such as IT, legal, PR, and executive teams, should be alerted. In cases where the incident has widespread and severe implications, an organization-wide notification may be warranted.
-   `External Communications`
    Depending on the incident's nature and impact, external communications may be necessary. This could involve notifying customers, partners, regulatory bodies, or even the general public.
### 5. Detailed Investigation & Reporting
The duration of this phase can vary significantly, ranging from a couple of days to potentially years.
### 6. Final Report Creation
This document will furnish regulators, insurers, and executive leadership with a detailed account of the incident, its origins, and the remedial actions taken.
### 7. Feedback Loop!
Post-incident reflection involves revisiting and analyzing the incident to identify areas for improvement.
## Elements of Proper Incident Report
### Executive Summary
 gateway to our report, designed to cater to a broad audience, including non-technical stakeholders. many stakeholders may only peruse the `Executive Summary`, it's imperative to nail this section
 - Incident ID
 - Incident Overview
 - Key findings
 - Immediate Actions Taken
 - Stakeholder Impact
### Technical Analysis
- Affected Systems & Data
- Evidence Sources & Analysis
- Indicators of Compromise (IoCs)
- Root Cause Analysis
- Technical Timeline
	-   Reconnaissance
	-   Initial Compromise
	-   C2 Communications
	-   Enumeration
	-   Lateral Movement
	-   Data Access & Exfiltration
	-   Malware Deployment or Activity (including Process Injection and Persistence)
	-   Containment Times
	-   Eradication Times
	-   Recovery Times
- Nature of the Attack
### Impact Analysis
### Response and Recovery Analysis
chronological account of the measures implemented to mitigate the impact and prevent future occurrences of similar incidents.
#### Immediate Response Actions
- Revocation of Access
	- Identification of Compromised Accounts/Systems
	- Timeframe
	- Method of Revocation
	- Impact
- Containment Strategy
	- Short-term Containment: Immediate actions taken to isolate affected systems from the network to prevent lateral movement of the threat actor.
	- Long-term Containment: Strategic measures, such as network segmentation or zero-trust architecture implementation, aimed at long-term isolation of affected systems.
	- Effectiveness
#### Eradication Measures
- Malware Removal
- System Patching
#### Recovery Steps
- Data Restoration
	- Backup Validation
	-   Restoration Process`
	-   Data Integrity Checks
- System Validation
	- Secuirty Measures
	- Operational Checks
#### Post-Incident Actions
- Monitoring
	- Enhanced Monitoring Plans
	-  Tools and Technologies
- Lessons Learned
	- Gap Analysis
	- Recommendations for Improvement
	- Future Strategy
### Diagrams
- Incident FLowchart
- Affected Systems Map
- Attack Vector Diagram
![[Pasted image 20240704124427.png]]
### Appendices
repository for supplementary material that provides additional context, evidence, or technical details
## Best Practices
- Root Cause Analysis
- Community Sharing: Share non-sensitive details with a community of defenders to improve collective cybersecurity.
- Regular Updates
- External Review
## Communications
In the midst of any crisis, effective communication is not just beneficial but crucial.
### Navigating Communication Channels During Cybersecurity Incidents
#### **Security Dimensions of Communication Channels**:
- Encrption
- Authentication and Authorization
- Data Integrity
- Ephemeral Communications: For those top-secret discussions, we might consider using messaging platforms that auto-destruct messages post-reading.
- Air-Gapped Communications: In situations where we suspect our primary communication backbone might be under threat, we might need to resort to air-gapped systems. These systems are our last line of defense, completely isolated from other potentially compromised networks.
#### **Regulatory Dimensions of Communication Channels**:
- Data Privacy Laws: If we're discussing or sharing personal data, especially of EU residents, we need to toe the line with GDPR mandates.
- Breach Notification Mandates: Certain jurisdictions have clear-cut timelines for breach notifications. We need to be aware of these
- Record-Kepping: While we might lean towards ephemeral messages for security, some regulations mandate a clear record of all incident-related communications.
- Cross-Border Communications: When our incident spills over national borders, the communication game changes.
- Chain of Custody:  If there's even a hint that legal actions might follow the incident, we need to maintain an unbroken chain of custody for all communications. This ensures that if we need to present evidence in court, it's deemed admissible.

# Documentation And Reporting
## Logging
[Tmux logging](https://github.com/tmux-plugins/tmux-logging) is an excellent choice for terminal logging
First, clone the [Tmux Plugin Manager](https://github.com/tmux-plugins/tpm) repo to our home directory (in our case `/home/htb-student` or just `~`).
Next, create a `.tmux.conf` file in the home directory.
```shell-session
Eerem@htb[/htb]$ cat .tmux.conf 

# List of plugins

set -g @plugin 'tmux-plugins/tpm'
set -g @plugin 'tmux-plugins/tmux-sensible'
set -g @plugin 'tmux-plugins/tmux-logging'

# Initialize TMUX plugin manager (keep at bottom)
run '~/.tmux/plugins/tpm/tpm'
```
After creating this config file, we need to execute it in our current session, so the settings in the `.tmux.conf` file take effect. We can do this with the [source](https://www.geeksforgeeks.org/source-command-in-linux-with-examples/) command.
```shell-session
tmux source ~/.tmux.conf 
```
Next, we can start a new Tmux session (i.e., `tmux new -s setup`).

Once in the session, type `[Ctrl] + [B]` and then hit `[Shift] + [I]` (or `prefix` + `[Shift] + [I]` if you are not using the default prefix key), and the plugin will install (this could take around 5 seconds to complete).

Once the plugin is installed, start logging the current session (or pane) by typing `[Ctrl] + [B]` followed by `[Shift] + [P]` (`prefix` + `[Shift] + [P]`) to begin logging. If all went as planned, the bottom of the window will show that logging is enabled and the output file. To stop logging, repeat the `prefix` + `[Shift] + [P]` key combo or type `exit` to kill the session.

If we forget to enable Tmux logging and are deep into a project, we can perform retroactive logging by typing `[Ctrl] + [B]` and then hitting `[Alt] + [Shift] + [P]` (`prefix` + `[Alt] + [Shift] + [P]`), and the entire pane will be saved. The amount of saved data depends on the Tmux `history-limit`

Finally, here are some additional plugins that we like:

-   [tmux-sessionist](https://github.com/tmux-plugins/tmux-sessionist) -
- [tmux-pain-control](https://github.com/tmux-plugins/tmux-pain-control)
- [tmux-resurrect](https://github.com/tmux-plugins/tmux-resurrect)

Check out the complete [tmux plugins list](https://github.com/tmux-plugins/list) to see if others would fit nicely into your workflow. For more on Tmux, check out this excellent [video](https://www.youtube.com/watch?v=Lqehvpe_djs) by Ippsec and this [cheat sheet](https://mavericknerd.github.io/knowledgebase/ippsec/tmux/) based on the video.
## Assessement Types
### Vulnerability Assessment
 running an automated scan of an environment to enumerate vulnerabilities.
 No exploitation is attempted goal is not to gain a foothold and move laterally/vertically. Some customers will even ask for scan results with no validation.
### Internal vs External
An external scan is performed from the perspective of an anonymous user on the internet targeting the organization's public systems.

An internal scan is conducted from the perspective of a scanner on the internal network and investigates hosts from behind the firewall.
## Penetration Testing
Testing can be performed with `zero evasion` to attempt to uncover as many vulnerabilities as possible, from a `hybrid evasive` standpoint to test the customer's defenses by starting out evasive and gradually becoming "noisier" to see at what level internal security teams/monitoring tools detect and block us.

we may be asked to perform `evasive testing` throughout the assessment. In this type of assessment, we will try to remain undetected for as long as possible and see what kind of access, if any, we can obtain while working stealthily

## Beyond This Module
-   You can use the report template provided with this module, find sample pentest reports on GitHub, or use the report templates included in tools such as [WriteHat](https://github.com/blacklanternsecurity/writehat), [Pwndoc](https://github.com/pwndoc/pwndoc), or something similar.
    
-   Read through reports in the [public pentesting reports repo](https://github.com/juliocesarfort/public-pentesting-reports) to expose yourself to various reporting styles.
- Start a personal blog and make walkthroughs or retired HTB boxes and challenges, tier0 modules, and CTFs that you participate in. Write about vulnerabilities and techniques that interest you, even if other blog posts already exist on the topic. Creating well-thought-out posts on your favorite technologies, video games, or personal interests is another great way to practice your writing skills.
# Bug Bounty Hunting Process
If you want to study the anatomy of a vulnerability disclosure program, refer to the following resource. [VDP vs. BBP](https://docs.hackerone.com/organizations/vdp-vs-bbp.html#gatsby-focus-wrapper)

We strongly suggest that you go over [HackerOne's Code of Conduct](https://www.hacker101.com/resources/articles/code_of_conduct)
 
 Navigate to [HackerOne's bug bounty program list](https://hackerone.com/bug-bounty-programs) to go over some bug bounty programs. Take [Alibaba BBP](https://hackerone.com/alibaba?type=team) and [Amazon Vulnerability Research Program](https://hackerone.com/amazonvrp?type=team) as examples and go through their "Policy."
 
 One of the best online resources to identify bug bounty programs of your liking is [HackerOne's Directory](https://hackerone.com/directory/programs).
## Writing A Good Report
when reporting to less mature companies, we may have to translate technical security issues into more understandable/business terms for them to understand the actual impact of each vulnerability.
The essential elements of a good bug report are (the element order can vary):

`Vulnerability Title`

Including vulnerability type, affected domain/parameter/endpoint, impact etc.

`CWE & CVSS score`

For communicating the characteristics and severity of the vulnerability.

`Vulnerability Description`

Better understanding of the vulnerability cause.

`Proof of Concept (POC)`

Steps to reproduce exploiting the identified vulnerability clearly and concisely.

`Impact`

Elaborate more on what an attacker can achieve by fully exploiting the vulnerability. Business impact and maximum damage should be included in the impact statement.

`Remediation`

Optional in bug bounty programs, but good to have.


MITRE describes [Common Weaknesses Enumeration (CWE)](https://cwe.mitre.org/) as a community-developed list of software and hardware weakness types. It serves as a common language
When it comes to communicating the severity of an identified vulnerability, then [Common Vulnerability Scoring System (CVSS)](https://www.first.org/cvss/) should be used

 [CVSS v3.1 Calculator](https://www.first.org/cvss/calculator/3.1)
 
##  Good Report Examples

Find below some good report examples selected by HackerOne:

-   [SSRF in Exchange leads to ROOT access in all instances](https://hackerone.com/reports/341876)
-   [Remote Code Execution in Slack desktop apps + bonus](https://hackerone.com/reports/783877)
-   [Full name of other accounts exposed through NR API Explorer (another workaround of #476958)](https://hackerone.com/reports/520518)
-   [A staff member with no permissions can edit Store Customer Email](https://hackerone.com/reports/980511)
-   [XSS while logging in using Google](https://hackerone.com/reports/691611)
-   [Cross-site Scripting (XSS) on HackerOne careers page](https://hackerone.com/reports/474656)

##  Interacting with Organizations/BBP Hosts
you have submitted a bug report. How should you interact with the security/triage team after that?

Well, to begin with, do not interact with them. Allow the security/triage team some time to process your report If the security/triage team does not get back to you in a reasonable amount of time, then if the submission was through a bug bounty platform, you can contact [Mediation](https://docs.hackerone.com/hackers/hacker-mediation.html).

Once the security/triage team gets back to you, note the team member's username and tag them in any future communications since they will probably be dealing with your submission

# Introduction to Bash Scripting
[Bash](https://en.wikipedia.org/wiki/Bash_(Unix_shell)) is the scripting language we use to communicate with Unix-based OS and give commands to the system
 Since May 2019, Windows provides a [Windows Subsystem for Linux](https://docs.microsoft.com/en-us/windows/wsl/about) that allows us to use `Bash` in a Windows environment.
**Scripting vs Programming Languages:** we don't need to compile the code to execute the scripting language, as opposed to programming languages.
```
[!bash!]$ bash script.sh <optional arguments>
```

```
[!bash!]$ sh script.sh <optional arguments>
```

```
[!bash!]$ ./script.sh <optional arguments>
```
## Shebang

The shebang line is always at the top of each script and always starts with "`#!`". This line contains the path to the specified interpreter (`/bin/bash`) with which the script is executed. We can also use Shebang to define other interpreters like Python, Perl, and others.
```python
#!/usr/bin/env python
```
```perl
#!/usr/bin/env perl
```
## If-Else-Fi
```bash
if [ $# -eq 0 ]
then
	echo -e "You need to specify the target domain.\n"
	echo -e "Usage:"
	echo -e "\t$0 <domain>"
	exit 1
else
	domain=$1
fi
```
-   Equal: `-eq`
-   Not equal: `-ne`
-   Less than or equal: `-le`
-   Less than: `-lt`
-   Greater than or equal: `-ge`
-   Greater than: `-gt`
-   Is null: `-z`
## Arguments
The advantage of bash scripts is that we can always pass up to 9 arguments (`$0`-`$9`) to the script without assigning them to variables or setting the corresponding requirements for these.

 `9 arguments` because the first argument `$0` is reserved for the script.
These variables are called special variables.

## Special Variables

Special variables use the [Internal Field Separator](https://bash.cyberciti.biz/guide/$IFS) (`IFS`) to identify when an argument ends and the next begins.

IFS	Description
$#	This variable holds the number of arguments passed to the script.
$@	This variable can be used to retrieve the list of command-line arguments.
$n	Each command-line argument can be selectively retrieved using its position. For example, the first argument is found at $1.
\$\$	The process ID of the currently executing process.
$?	The exit status of the script. This variable is useful to determine a command's success. The value 0 represents successful execution, while 1 is a result of a failure.

## Variables
When assigning variables, there must be no spaces between the names and values.

In contrast to other programming languages, there is no direct differentiation and recognition between the types of variables in Bash like "`strings`," "`integers`," and "`boolean`."

### Arrays.sh
```bash
#!/bin/bash

domains=(www.inlanefreight.com ftp.inlanefreight.com vpn.inlanefreight.com www2.inlanefreight.com)

echo ${domains[0]}
```

## String Operators
If we compare strings, then we know what we would like to have in the corresponding value.

Operator	Description
==	is equal to
!=	is not equal to
<	is less than in ASCII alphabetical order
\>	is greater than in ASCII alphabetical order
-z	if the string is empty (null)
-n	if the string is not null

It is important to note here that we put the variable for the given argument (`$1`) in double-quotes (`"$1"`). This tells Bash that the content of the variable should be handled as a string. Otherwise, we would get an error.

String comparison operators "`<` / `>`" works only within the double square brackets `[[ <condition> ]]`

## Integer Operators
Operator	Description
-eq	is equal to
-ne	is not equal to
-lt	is less than
-le	is less than or equal to
-gt	is greater than
-ge	is greater than or equal to

## File Operators
The file operators are useful if we want to find out specific permissions or if they exist.

Operator	Description
-e	if the file exist
-f	tests if it is a file
-d	tests if it is a directory
-L	tests if it is if a symbolic link
-N	checks if the file was modified after it was last read
-O	if the current user owns the file
-G	if the file’s group id matches the current user’s
-s	tests if the file has a size greater than 0
-r	tests if the file has read permission
-w	tests if the file has write permission
-x	tests if the file has execute permission

## Debugging
 [Bash debugging](https://tldp.org/LDP/Bash-Beginners-Guide/html/sect_02_03.html)
 Bash allows us to debug our code by using the "`-x`" (`xtrace`) and "`-v`" options.