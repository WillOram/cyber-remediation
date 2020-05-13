# Remediating from major cyber security incidents 

Planning and mobilising programmes to deliver such rapid risk reduction.

1. Understand the organisation’s vulnerability to the threat (attack path analysis)
2. Identify pragmatic and threat-focused actions to remediate vulnerabilities
3. Develop and deliver a programme focused on rapid risk reduction
4. Validate and measure progress at reducing risk
5. Address root-causes of vulnerabilities with strategic transformation programmes

## Remediation objectives

Remediation has four key objectives:

1. Removing attacker access to the environment 
3. Prevent the attacker from re-gaining access to the environment
4. Detect the attacker if they re-gain access to the environment 
5. Limit the attacker’s ability to achieve any objectives if access to the environment is reacquired

These four objectives are achieved by carrying out posturing, eradication and hardening. 

Against a motivated and targeted attacker, failure to identify all attacker access, improve detection capabilities and carry out improvements to prevent the attacker from immediately re-gaining access to the environment, will likely result in the eradication not being successful (with the attacker maintaining access and embedding deeper in the network). 

# Planning for an eradication event 

Effective remediation events need to be planned and coordinated. 

## Eradication event planning checklist
- [ ] Identified date
- [ ] Setup out of band communications and collaboration methods
- [ ] "Eradication event criteria" have been defined
- [ ] Surged monitoring and response team has been stood up 
- [ ] Playbooks and red line criteria have been written to respond to any new attacker activity identified 
- [ ] Response actions have been documented (e.g., blockings IPs, sinkholing DNS, resetting accounts and isolating systems)

## Example "Eradication event criteria"
- [ ] Confident all attacker access has been identified (e.g. malware, command and control methods, compromised accounts)
- [ ] Attacker TTPs are consistent, understood and not changing 
- [ ] Confident all current attacker activity is being detected
- [ ] Confident any new attacker activity will be detected
- [ ] Confident we have the ability to response quickly to any new attacker activity 
- [ ] Plans have been developed to carry out eradication event activities and resources identified
- [ ] Key activities from plans have been documented and tested
- [ ] Business impact assessed and managed  

# Remediating external cyber attacks

Checklist of key actions to take organised around remediation objectives (by no means comprehensive, but I find these a helpful list of actions to sense check plans!)

The following actions cannot be taken in isolation to be effective, they require mature capabilities to design, implement and operate. 

## Removing attacker access to the environment 

### Remove known access
- [ ] Remove malware (executables, configuration files, temporary files, persistence methods, web shells)
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

## Prevent the attacker from re-gaining access to the environment

### External vulnerabilities being exploited 
- [ ] Remediate vulnerabilities on external-facing systems and services 
- [ ] Remediate vulnerabilities on external-facing web applications 
- [ ] Setup alerting for new external vulnerabilities / services (e.g. Tenable.io)
- [ ] Audit all external-facing systems and services 
- [ ] Decommission external-facing legacy systems
- [ ] Penetration test external-facing systems and services 
- [ ] Penetration test external-facing web applications

### Phishing attacks  
- [ ] Configure email filtering tools to whitelist file-types users can receive in email attachments and scan files for malicious content 
- [ ] Configure web filtering tools to restrict file-types users can download from the internet and scan files for malicious content 
- [ ] Configure web filtering tools to block domains registered within the last two weeks
- [ ] Prevent untrusted Microsoft Office macros from being run by users on workstations 
- [ ] Restrict the use of PowerShell on workstations
- [ ] Restrict scripts files that can be executed on workstations (e.g. HTA, and CHM files) 
- [ ] Restrict executables that can be executed on workstations (e.g. based on location, trust, whitelisting)
- [ ] Deploy tooling to detect and block / flag suspicious emails using advanced analytics (e.g. O365 ATP)
- [ ] Deploy tooling so that it is easy for employees to report suspicious emails 
- [ ] Deploy / upgrade AV to ensure common commodity malware infections are prevented and contained

### Weak or compromised credentials being exploited 
- [ ] Roll out multi-factor authentication for all authentication to external-facing / cloud applications (e.g. email, Salesforce)
- [ ] Roll out multi-factor authentication for all authentication to remote access systems (e.g. VPN)
- [ ] Roll out multi-factor authentication for all authentication for third-party vendor access 
- [ ] Prevent users from setting weak passwords (e.g. by deploying Azure AD Password protect)
- [ ] Disable legacy and unused authentication protocols

## Detect the attacker if they re-gain access to the environment 

### Attacker activity on workstations or servers 
- [ ] Deploy an advance endpoint agent (EPP/EDR) to detect suspicious activity on all systems using behavioural analytics
- [ ] Add rules to endpoint agent (EPP/EDR) to detect the tools and techniques commonly used by the attackers
- [ ] Collect and monitor logs from servers (WEVTs with enhanced configuration, Sysmon) and security tooling
- [ ] Deploy / upgrade AV to ensure AMSI capabilities to detect malicious use of PowerShell 
- [ ] Deploy file integrity monitoring on web servers to detect web shells and malicious code 

### Detect command and control traffic
- [ ] Collect and monitor logs from VPN and authentication services (Azure Sentinel)(geo, impossible logons, privileged accounts) 
- [ ] Deploy cloud web filtering capabilities to detect and prevent malicious web traffic on-prem and off-prem (e.g. download of PowerShell scripts)
- [ ] Restrict servers' access to the internet to whitelisted services, detect on traffic to other destinations 
- [ ] Collect and monitor logs from firewalls, DNS servers and web proxies (Azure Sentinel)

## Limit the attacker’s ability to achieve any objectives if access to the environment is reacquired

### Escalate privileges
- [ ] Remove administrator rights from standard users on workstations
- [ ] Remediate vulnerabilities on workstation and server builds 
- [ ] Use a local admin password solution to set strong passwords for all local admin accounts on workstations and servers  - [ ] Audit and identify owners for all Active Directory accounts 
- [ ] Set strong passwords on all service accounts, domain administrator accounts and privileged accounts 
- [ ] Prevent domain administrator accounts from logging into servers and workstations 
- [ ] Prevent standard user accounts from being able to log into servers 
- [ ] Enforce the use of dedicated for administration and not shared between users
- [ ] Deploy privileged access management (PAM) tooling to enforce multi-factor authentication for the use of admin accounts 
- [ ] Ensure that domain admin accounts are only used on hardened administration systems or within PAM session management 
- [ ] Limit the accounts in the local administrator groups of workstations and servers
- [ ] Limit the accounts in the remote desktop groups of workstations and servers
- [ ] Restrict how service accounts are used
- [ ] Implement Windows ATA / Azure ATP to detect and respond to advanced attacks on AD and its identities.

### Move laterally
- [ ] Limit what workstations can access on the internal network 
- [ ] Detect anomalous use of user accounts for remote access
- [ ] Detect anomalous use of administrator and service accounts
- [ ] Patch vulnerabilities on endpoints, applications and appliances and segmenting systems that cannot be patched;
- [ ] Restrict access to high-risk networks with bastion hosts
- [ ] Limit network access to systems and databases hosting critical applications

### Compromise sensitive data 
- [ ] Deploy tooling to enforce multi factor authentication for access to critical applications
- [ ] Remove sensitive data stored in information shares accessible to standard users
- [ ] Restrict access to open network shares and other potentially sensitive data stores (e.g., Intranet, internal wikis, and file servers)
- [ ] Deploy data loss prevention (DLP) tooling to prevent exfiltration of sensitive data
- [ ] Restrict servers access to the internet to whitelisted services 
