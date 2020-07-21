Hi, my name is [Will Oram](https://willoram.com/). I’m a cyber security consultant living in London. You can follow me on [Twitter](https://twitter.com/willoram). I help companies respond to cyber security breaches and prevent cyber attacks. I also tweet and blog about cyber security, and maintain this collection of resources for [managing](https://github.com/WillOram/cyber-incident-management) and [remediating](https://github.com/WillOram/cyber-remediation) from cyber security breaches. 

# Remediating from major cyber security incidents 

Quick-reference notes I use when remediating from major cyber incidents. Loosely organised into three sections.

## Performing successful remediations 
[Remediation objectives](#remediation-objectives)  
[Key considerations](#key-considerations)  
[Five remediation steps](#five-remediation-steps)  
1. [Uplift detection capabilities](#uplift-detection-capabilities)  
2. [Harden the environment](#harden-the-environment)  
3. [Plan "eradication event"](#plan--eradication-event-)  
4. [Execute "eradication event"](#execute--eradication-event-)  
5. [Deliver tactical improvements](#deliver-tactical-improvements)  
6. [Build a sustainable response](#Build-a-sustainable-response)

## Executing eradication events 
[Planning for an eradication event](#planning-for-an-eradication-event)  
[Removing attacker access to the environment](#removing-attacker-access-to-the-environment)  

## Delivering tactical improvements 
[Key considerations for delivering tactical improvements](#key-considerations-for-delivering-tactical-improvements)  
[Top ways attackers gain initial access](#top-ways-attackers-gain-initial-access)  
[Checklist for remediating from external cyber attacks](#checklist-for-remediating-from-external-cyber-attacks)   
1. [Prevent the attacker from re-gaining access to the environment](#prevent-the-attacker-from-re-gaining-access-to-the-environment)  
2. [Detect the attacker if they re-gain access to the environment](#detect-the-attacker-if-they-re-gain-access-to-the-environment)  
3. [Limiting the attacker’s ability to achieve their objectives if they re-gain access to the environment](#limiting-the-attacker-s-ability-to-achieve-their-objectives-if-they-re-gain-access-to-the-environment)  

# Performing successful remediations 

## Remediation objectives

Remediation has three key objectives:
1. Remove the attacker’s access to the environment 
2. Provide confidence the attacker no longer has access to the environment 
3. Prevent the attacker from re-gaining access to the environment and achieving their objectives 

## Key considerations

Against a motivated and targeted attacker failure to perform each of the following, will likely result in the eradication not being successful (with the attacker maintaining access and embedding deeper in the network):
- identify all attacker access; 
- improve detection capabilities so that all attacker activity is detected; and,
- implement sufficient improvements to prevent the attacker from quickly re-gaining access to the environment. 

## Five remediation steps

### Uplift detection capabilities 
- Rapidly improve detect and response capabilities so that all attacker activity is promptly detected
- Key to understanding all access the attacker has to the environment before the eradication event
- Key to gaining confidence the attacker no longer has access to the environment after the eradication event
- Often requires deploying new tooling to gain visibility of systems the attacker compromised 
- Develop detection and response plans and playbooks 

### Harden the environment 
- Map out attack paths used by the attacker and weaknesses in the environment 
- Identify targeted improvements to prevent the attacker immediately re-gaining access to the environment 
  - using the same or similar attacks to gain initial access (e.g. patching external vulnerabilities)
  - using other common methods (e.g. phishing, compromised credentials)
- Identify targeted improvements to prevent the attacker achieving their objectives using the same or similar attack paths  if they re-gain access to the environment(e.g. segmenting POS terminals)
- Focus on quick-win improvements and identifying pragmatic actions 
- Plan and implement any improvements that will not tip-off the attacker  
- Plan to implement all other hardening activities during the eradication event 
- Focus on developing the minimum list of actions required to achieve objectives

### Plan "eradication event"
- Prepare for an ‘eradication event’ to remove the attacker from the environment
- Develop an "Eradication event criteria"
- Prepare for reactive containment actions if required to prevent the attacker compromising critical assets, taking destructive actions or stealing sensitive data.  

### Execute "eradication event"
- Remove attacker access to the environment in a single coordinated event (known and unknown) 
- Perform remaining hardening activities during the eradication event 
- Be ready to react quickly if any attacker access to the enviornment was overlooked, or if the attacker quickly re-gains access (e.g. using developed detection and response plans and playbooks)

### Deliver tactical improvements 
- Reduce risk of further repeat attacks by the attacker in the short- / medium-term by delivering tactical improvements
- Target improvements at: 
  - Preventing the attacker from re-gaining access to the environment
  - Detecting the attacker if they re-gain access to the environment
  - Limiting the attacker’s ability to achieve their objectives if they re-gain access to the environment
- Feed requirements into strategic cyber security programmes / IT modernisation plans 

### Build a sustainable response
- Build a sustainable detection and response capability  
- Continue to deliver targeted improvements at pace
- Identify and address root-cause issues that allowed the attack to happen

# Executing eradication events 

## Planning for an eradication event 

Effective remediation events need to be planned and coordinated. 

### Eradication event planning checklist
- [ ] Identified date
- [ ] Setup out of band communications and collaboration methods
- [ ] "Eradication event criteria" have been defined
- [ ] Surged monitoring and response team has been stood up 
- [ ] Playbooks and red line criteria have been written to respond to any new attacker activity identified 
- [ ] Response actions have been documented (e.g., blockings IPs, sinkholing DNS, resetting accounts and isolating systems)

### Developing an "Eradication event criteria"
- [ ] Confident all attacker access has been identified (e.g. malware, command and control methods, compromised accounts)
- [ ] Attacker TTPs are consistent, understood and not changing 
- [ ] Confident all current attacker activity is being detected
- [ ] Confident any new attacker activity will be detected
- [ ] Confident we have the ability to response quickly to any new attacker activity 
- [ ] Plans have been developed to carry out eradication event activities and resources identified
- [ ] Key activities from plans have been documented and tested
- [ ] Business impact assessed and managed  

## Removing attacker access to the environment 

### Remove known access
- [ ] Remove attacker tools and backdoors (executables, configuration files, temporary files, persistence methods, web shells)
- [ ] Block known bad IPs (onprem / offprem)
- [ ] Block known bad domains (sinkhole?)
- [ ] Block known bad hashes from executing
- [ ] Reset / disable known compromised accounts

### Remove unknown access
- [ ] Decommission, rebuild or restart compromised systems
- [ ] Scan external facing systems for web-shells (YARA or threat hunting for modified files)
- [ ] Audit and remove mail-forwarding rules configured on email server / systems
- [ ] Reset administrator account passwords (+ golden ticket)
- [ ] Reset privileged account passwords 
- [ ] Reset service account passwords 
- [ ] Reset user account passwords (change on next logon?)
- [ ] Audit MFA tokens issued

# Uplifting detection capabilities 

TO BE DONE

EDR

Domain Controllers + Windows Event Logs + Powershell logging + DNS logging + Sysmon + Cloud SIEM

VPN

O365

AV

# Delivering tactical improvements 

## Key considerations for delivering tactical improvements 

Planning and mobilising programmes to deliver such rapid risk reduction.

1. Understand the organisation’s vulnerability to the threat (attack path analysis)
2. Identify pragmatic and threat-focused actions to remediate vulnerabilities
3. Develop and deliver a programme focused on rapid risk reduction
4. Validate and measure progress at reducing risk
5. Address root-causes of vulnerabilities with strategic transformation programmes

### Example projects to stand-up

- Active Directory hygiene (e.g. secure the use of Domain Admin accounts, set strong passwords on service accounts)
- IT hygiene (e.g. patch workstations and servers, deploy LAPS)
- Secure administration
- Harden workstation and server configuration
- Harden email and web filtering 
- Security tooling deployment (e.g. deploy EDR, deploy Azure ATP, deploy Windows Defender ATP)
- Detection uplift (e.g. onboard Windows Event logs to SIEM, write custom detection rules, write detection alert playbooks)

## Top ways attackers gain initial access

1. Phishing attacks

2. Leveraging compromised credentials 

3. Exploiting external vulnerabilities / misconfigurations

4. Supply-chain 

## Checklist for remediating from external cyber attacks 

Checklist of key actions to take organised around remediation objectives (by no means comprehensive, but I find these a helpful list of actions to sense check plans!)

The following actions cannot be taken in isolation to be effective, they require mature capabilities to design, implement and operate. 

### Prevent the attacker from re-gaining access to the environment

#### External vulnerabilities being exploited 
- [ ] Remediate vulnerabilities on external-facing systems and services 
- [ ] Remediate vulnerabilities on external-facing web applications 
- [ ] Setup alerting for new external vulnerabilities / services (e.g. Tenable.io)
- [ ] Audit all external-facing systems and services 
- [ ] Decommission external-facing legacy systems
- [ ] Penetration test external-facing systems and services 
- [ ] Penetration test external-facing web applications

#### Phishing attacks  
- [ ] Configure email filtering tools to whitelist file-types users can receive in email attachments and scan files for malicious content 
- [ ] Configure web filtering tools to restrict file-types users can download from the internet and scan files for malicious content 
- [ ] Configure web filtering tools to block domains registered within the last two weeks
- [ ] Prevent untrusted Microsoft Office macros from being run by users on workstations 
- [ ] Restrict the use of PowerShell on workstations (Constrained Language mode + disable PowerShell v2)
- [ ] Restrict scripts files that can be executed on workstations (e.g. HTA, and CHM files) 
- [ ] Restrict executables that can be executed on workstations (e.g. based on location, trust, whitelisting)
- [ ] Deploy tooling to detect and block / flag suspicious emails using advanced analytics (e.g. O365 ATP)
- [ ] Deploy tooling so that it is easy for employees to report suspicious emails 
- [ ] Deploy / upgrade AV to ensure common commodity malware infections are prevented and contained
- [ ] Remove administrator rights from standard users on workstations
- [ ] Enable Windows 10 security features such as Attack Surface Reduction and Credential Guard

#### Weak or compromised credentials being exploited 
- [ ] Roll out multi-factor authentication for all authentication to external-facing / cloud applications (e.g. email, Salesforce)
- [ ] Roll out multi-factor authentication for all authentication to remote access systems (e.g. VPN)
- [ ] Roll out multi-factor authentication for all authentication for third-party vendor access 
- [ ] Prevent users from setting weak passwords (e.g. by deploying Azure AD Password protect)
- [ ] Disable legacy and unused authentication protocols

### Detect the attacker if they re-gain access to the environment 

#### Attacker activity on workstations or servers 
- [ ] Deploy an advance endpoint agent (EPP/EDR) to detect suspicious activity on all systems using behavioural analytics
- [ ] Add rules to endpoint agent (EPP/EDR) to detect the tools and techniques commonly used by the attackers
- [ ] Collect and monitor logs from servers (WEVTs with enhanced configuration, Sysmon) and security tooling (prioritise domain controllers / consider going further with using Sysmon for domain controllers)
- [ ] Deploy / upgrade AV to ensure AMSI capabilities to detect malicious use of PowerShell and VBA (macros)
- [ ] Deploy file integrity monitoring on web servers to detect web shells and malicious code 
- [ ] Enable enhanced PowerShell logging (e.g. Script block logging)

#### Compromise of privileged accounts
- [ ] Detect anomalous use of user accounts for remote access
- [ ] Detect anomalous use of administrator and service accounts

#### Command and control traffic
- [ ] Collect and monitor logs from VPN and authentication services (Azure Sentinel)(geo, impossible logons, privileged accounts) 
- [ ] Deploy cloud web filtering capabilities to detect and prevent malicious web traffic on-prem and off-prem (e.g. download of PowerShell scripts)
- [ ] Restrict servers' access to the internet to whitelisted services, detect on traffic to other destinations 
- [ ] Collect and monitor logs from firewalls, DNS servers and web proxies (Azure Sentinel)

### Limiting the attacker’s ability to achieve their objectives if they re-gain access to the environment

#### Escalate privileges
- [ ] Remediate vulnerabilities on workstation and server builds 
- [ ] Use a local admin password solution to set unique random  passwords for all local admin accounts on workstations and servers (e.g. LAPS)
- [ ] Audit and identify owners for all Active Directory accounts 
- [ ] Set strong passwords on all service accounts, domain administrator accounts and privileged accounts 
- [ ] Prevent domain administrator accounts from logging into servers and workstations 
- [ ] Prevent standard user accounts from being able to log into servers 
- [ ] Enforce the use of dedicated accounts for administration and not shared between users
- [ ] Deploy privileged access management (PAM) tooling to enforce multi-factor authentication for the use of admin accounts 
- [ ] Ensure that domain admin accounts are only used on hardened administration systems or within PAM session management 
- [ ] Limit the accounts in the local administrator groups of workstations and servers
- [ ] Limit the accounts in the remote desktop groups of workstations and servers
- [ ] Restrict how service accounts are used (disable interactive logon privileges) 
- [ ] Implement Windows ATA / Azure ATP to detect and respond to advanced attacks on AD and its identities.
- [ ] Identify and remove old accounts with passwords set to not expire

#### Move laterally
- [ ] Limit what workstations can access on the internal network 
- [ ] Patch vulnerabilities on endpoints, applications and appliances and segmenting systems that cannot be patched;
- [ ] Restrict access to high-risk networks with bastion hosts
- [ ] Limit network access to systems and databases hosting critical applications
- [ ] Validate all Active Directory domain trusts 

#### Compromise sensitive data 
- [ ] Deploy tooling to enforce multi factor authentication for access to critical applications
- [ ] Remove sensitive data stored in information shares accessible to standard users
- [ ] Restrict access to open network shares and other potentially sensitive data stores (e.g., Intranet, internal wikis, and file servers)
- [ ] Deploy data loss prevention (DLP) tooling to prevent exfiltration of sensitive data
- [ ] Restrict servers access to the internet to whitelisted services 
