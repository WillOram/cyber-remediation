# Remediating from cyber security incidents 

Planning and mobilising programmes to deliver such rapid risk reduction.

1. Understand the organisation’s vulnerability to the threat (attack path analysis)
2. Identify pragmatic and threat-focused actions to remediate vulnerabilities
3. Develop and deliver a programme focused on rapid risk reduction
4. Validate and measure progress at reducing risk
5. Address root-causes of vulnerabilities with strategic transformation programmes

## Remediating external attacks against legacy enterprise IT environments

Checklist of key actions to take, by no means comprehensive! 

The folllowing actions can not be taken in isolation to be effective, they require mature capabilities to design, implement and operate them. 

# Planning for a remediation event 

## Removing known attacker access to the environment 
- [ ] Remove malware
- [ ] Block known bad IPs
- [ ] Block known bad domains
- [ ] Block known bad hashes from executing
- [ ] Reset known compromised accounts

## Removing unknown attacker access to the environment 
- [ ] Decomission, rebuild or restart compromised systems
- [ ] Scan external facing systems for webshells (YARA or threat hunting for modified files)
- [ ] Check for mail-forwarding rules configured on email server / systems
- [ ] Reset administrator account passwords
- [ ] Reset privileged account passwords 
- [ ] Reset service account passwords 
- [ ] Reset user account passwords

## Prevent the attacker from re-gaining access to the environment

### External vulnerabilities being exploited 
- [ ] Remediate vulnerabilities on external-facing systems and services 
- [ ] Remediate vulnerabilities on external-facing web applications 
- [ ] Setup alerting for new external vulnerabilities / services (e.g. Tenable.io)
- [ ] Decomission external-facing legacy systems
- [ ] Audit all external-facing systems and services 
- [ ] Penetration test external-facing systems and services 
- [ ] Penetration test external-facing web applications

### Phishing attacks  
- [ ] Configure email filtering tools to whitelist file-types users can receive in email attachments
- [ ] Configure web filtering tools to restrict file-types users can download from the internet
- [ ] Prevent untrusted Microsoft Office macros from being run by users on workstations 
- [ ] Restrict scripts that can be executed on workstations (e.g. PowerShell, HTA, and CHM files) 
- [ ] Restrict executables that can be executed on workstations (e.g. based on location, trust, whitelisting)
- [ ] Deploy tooling to detect and block / flag suspicious emails using advanced analytics
- [ ] Deploy tooling so that it is easy for employees to report suspicious emails 
- [ ] Deploy / upgrade AV to ensure common commodity malware infections are prevented and contained

### Weak or compromised credentials being exploited 
- [ ] Roll out multi-factor authentication for all authentication to external-facing / cloud applications (e.g. email, Salesforce)
- [ ] Roll out multi-factor authentication for all authentication to remote access systems (e.g. VPN)
- [ ] Roll out multi-factor authentication for all authentication for third-party vendor access 
- [ ] Prevent users from setting weak passwords (e.g. by deploying Azure AD Password protect)
