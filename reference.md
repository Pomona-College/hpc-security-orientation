---
title: Quick Reference
---

# HPC Security Orientation - Quick Reference Card

## Three-Tier Data Classification System

::::::::::::::::::::::::::::::::::: challenge
### Quick Classification Guide

| Tier | Examples | Storage | Encryption | Sharing |
|------|----------|---------|------------|---------|
| **PUBLIC** | Published papers, open-source code, datasets with DOI | Anywhere | Not required | Unrestricted |
| **PROPRIETARY** | Draft papers, lab notes, unpublished research, pre-publication data, novel algorithms, unpublished code | Sagehen HPC | Recommended | With authorized people or NDA |
| **RESTRICTED** | Student records (FERPA), health data (HIPAA), genetic data with IDs, classified info (CUI) | Sagehen only | REQUIRED | With DUA only, IRB approval |

**Key Rule**: When in doubt, classify higher (more secure). Ask your PI if unsure.

:::::::::::::::::::::::::::::::::::

## Data Classification by Field

### Biology/Life Sciences
- Raw sequencing data: Usually RESTRICTED (identifiable, re-identification risk)
- Published genome data: PUBLIC
- Lab protocols: PROPRIETARY
- Participant samples linked to health info: RESTRICTED (HIPAA)

### Psychology/Social Sciences
- Student survey responses: PROPRIETARY or RESTRICTED (depends on identifiability)
- Interview transcripts: RESTRICTED (even if anonymized - re-identification risk)
- Published results: PUBLIC
- Pre-publication manuscripts: PROPRIETARY

### Computer Science/Engineering
- Published code: PUBLIC
- Proprietary algorithms: PROPRIETARY
- Lab code/scripts: PROPRIETARY
- Code with security implications: Check with PI

### Chemistry/Physics
- Published datasets: PUBLIC
- Experimental procedures: PROPRIETARY
- Synthesis routes for hazardous compounds: Check with PI
- Safety-sensitive data: Check with PI

## Password Security Essentials

### Creating Strong Passwords
- **Minimum 14 characters**
- Mix: uppercase, lowercase, numbers, symbols
- **Avoid**: Dictionary words, names, birthdates, sequences
- **Do not reuse** passwords across different services
- **Store securely**: Use password manager (1Password, LastPass, Dashlane, etc.)

### Good Password Example
```
QuantumLeaf#2026$Pomona  (25 chars, mixed types, random)
```

### Bad Password Examples
```
password123          (Too common)
Alice2026            (Guessable with public info)
sagehen              (Actual account)
```

### Password Manager Tips
- Choose one trusted manager and stick with it
- Store Pomona password there
- Store Sagehen/OnDemand password there
- Never write passwords on sticky notes
- Never email passwords to anyone

## DUO Multi-Factor Authentication (MFA)

### Why MFA Matters
- Password alone is not enough
- MFA prevents unauthorized access even if password is stolen
- Your smartphone or device is your second factor

### DUO Options
1. **Duo Mobile app** (Best): Download Duo Mobile app to phone
2. **SMS**: Get 6-digit codes via text message
3. **Backup codes**: Save in secure location (use only when other methods fail)

### During Login
1. Enter Pomona username and password
2. Choose authentication method:
   - Option 1: Approve push on your Duo app
   - Option 2: Enter 6-digit SMS code
   - Option 3: Enter backup code (if using one)
3. You're logged in!

### If You Lose Your Phone
1. Contact ITS Help Desk immediately
2. They can reset your Duo
3. Have backup codes available (if you saved them)
4. Don't delay - your account is at risk

## Credential Compromise: What to Do

::::::::::::::::::::::::::::::::::: callout
### If You Suspect Compromise

**Immediately** (within 5 minutes):
1. Change your Pomona password at https://duo.pomona.edu
2. Change any other systems using same password
3. Email its-hpc@pomona.edu with "Password Compromise" in subject
4. If on shared computer, logout from everywhere

**Within 1 hour**:
5. Contact ITS Help Desk (phone number in directory)
6. Check recent login activity (ask HPC staff how)
7. Check for unusual files in /rhome or /bigdata
8. Set up account monitoring alerts if available

**Follow-up**:
- Monitor account for next 30 days
- Change passwords again in 1 month as precaution
- Follow any guidance from HPC security staff

:::::::::::::::::::::::::::::::::::

## Reporting Security Incidents

### What Counts as an Incident?
- Suspected password compromise
- Lost or stolen laptop with credentials
- Unusual account activity
- Suspected unauthorized access to your files
- Receiving suspicious emails requesting credentials (phishing)
- Finding files you didn't create
- Accidental data exposure (wrong permissions)

### How to Report
**Email**: its-hpc@pomona.edu
**Subject**: "Security Incident Report"

Include:
- What happened (be specific)
- When you noticed it
- What data might be affected
- What you've already done
- Your contact information

Example:
```
I noticed unusual files in /bigdata/lab/<labname>/ created
yesterday at 2 AM. I didn't create them. Files include
research_data_backup.tar and new_user_admin_script.sh.
I have not opened or deleted them. My last login was
at 5 PM, and I was not working at 2 AM.
```

### No-Blame Policy
- Reporting incidents is **never punitive**
- We want to know about problems quickly
- Early reporting limits damage
- Your account won't be suspended for reporting honest mistakes
- Security team's job is to help, not penalize

## Acceptable Use Summary

### Allowed Uses
- Approved research (by your PI/department)
- Educational use (by your instructor)
- Computational work (simulations, data processing, analysis)
- Collaborative work (with other authorized users)
- Storage of research data (properly classified)

### Prohibited Uses
- **Illegal activity**: No hacking, piracy, illegal downloads
- **Unauthorized access**: Only access your own files
- **Account sharing**: Don't share password; each person gets own account
- **Cryptocurrency mining**: Strictly prohibited (wastes resources)
- **Harassment or threats**: No hostile behavior
- **Excessive resource waste**: Don't submit massive jobs as tests
- **Commercial use**: Not allowed without special approval
- **Sharing credentials**: Never give your password to anyone

### Violations and Consequences

| Violation | First Offense | Second Offense | Severe |
|-----------|--------------|----------------|--------|
| Minor (large test job) | Warning | 7-day suspension | 30-day suspension |
| Moderate (account sharing) | 7-day suspension | 30-day suspension | Permanent + legal |
| Severe (illegal activity) | Suspension | Permanent | Legal action |

Your PI will be notified of suspensions.

## Key Contacts

::::::::::::::::::::::::::::::::::: callout

### For Different Issues

**Password or Account Problems**
- ITS Help Desk (see directory or https://servicedesk.pomona.edu/)
- Email: servicedesk@pomona.edu

**HPC Technical Issues**
- its-hpc@pomona.edu
- https://www.pomona.edu/its/

**Security Incidents or Concerns**
- its-hpc@pomona.edu with "SECURITY" in subject
- Phone: [Ask HPC staff for emergency number]

**Data Classification Questions**
- Your PI or lab manager
- its-hpc@pomona.edu
- Your department compliance officer

**FERPA/HIPAA/IRB Questions**
- IRB office (Research Compliance)
- Your department chair
- See directory for Research Compliance contact

**Suspicious Emails (Phishing)**
- Report to ITS Help Desk
- Don't click links or download attachments
- Forward suspicious email to its-hpc@pomona.edu

:::::::::::::::::::::::::::::::::::

## Encryption Basics: When & Why

### When to Encrypt
- **MUST encrypt**: All RESTRICTED data
- **Should encrypt**: PROPRIETARY data
- **Optional**: PUBLIC data

### How to Encrypt on Sagehen HPC
- **Tool**: gocryptfs (taught in Workshop 15)
- **Command**: `gocryptfs -init /path/to/data`
- **Then mount**: `gocryptfs /path/to/data /mount/point`
- **Only password holder** can decrypt

### Key Points
- Encryption is **not a substitute for access control** (permissions)
- Use both: good file permissions AND encryption for sensitive data
- Store encryption passwords in password manager
- Don't lose the password - data becomes inaccessible
- You don't need encryption for every file, only sensitive ones

## Before Using Sagehen HPC: Acknowledge

You must confirm:
- [ ] I've read the Acceptable Use Policy
- [ ] I understand the three data classification tiers
- [ ] I know my responsibility for account security
- [ ] I know how to report security incidents (no-blame)
- [ ] I understand violations can result in suspension
- [ ] I will not share my account or password
- [ ] I will encrypt RESTRICTED data
- [ ] I know who to contact with questions

**Confirmation is required to activate your HPC account.**

---

**Last Updated**: March 2026
**For more information**: Visit https://www.pomona.edu/its/ or email its-hpc@pomona.edu

<!-- highlight <labname>/<myusername> placeholders in code blocks; remove if the varnish theme handles this natively -->
<script>(function(){var CSS='.sh-placeholder{color:#c2410c;font-weight:700}[data-bs-theme="dark"] .sh-placeholder,html.dark .sh-placeholder{color:#fdba74}@media (prefers-color-scheme: dark){[data-bs-theme="auto"] .sh-placeholder{color:#fdba74}}';var RX=/<labname>|<myusername>/g;function firstMatch(el){var w=document.createTreeWalker(el,NodeFilter.SHOW_TEXT,null),nodes=[],full='';while(w.nextNode()){nodes.push({n:w.currentNode,s:full.length});full+=w.currentNode.nodeValue;}RX.lastIndex=0;var m;while((m=RX.exec(full))){var s=m.index,e=s+m[0].length,inSpan=false,parts=[];for(var j=0;j<nodes.length;j++){var ns=nodes[j].s,ne=ns+nodes[j].n.nodeValue.length;if(ne<=s||ns>=e)continue;parts.push({node:nodes[j].n,a:Math.max(s-ns,0),b:Math.min(e-ns,nodes[j].n.nodeValue.length)});var p=nodes[j].n.parentNode;while(p&&p!==el){if(p.classList&&p.classList.contains('sh-placeholder')){inSpan=true;break;}p=p.parentNode;}}if(!inSpan&&parts.length)return parts;}return null;}function wrapParts(parts){for(var i=parts.length-1;i>=0;i--){var t=parts[i].node,txt=t.nodeValue,a=parts[i].a,b=parts[i].b;var span=document.createElement('span');span.className='sh-placeholder';span.textContent=txt.slice(a,b);var f=document.createDocumentFragment();if(a>0)f.appendChild(document.createTextNode(txt.slice(0,a)));f.appendChild(span);if(b<txt.length)f.appendChild(document.createTextNode(txt.slice(b)));t.parentNode.replaceChild(f,t);}}function run(){var st=document.createElement('style');st.textContent=CSS;document.head.appendChild(st);document.querySelectorAll('pre,code').forEach(function(el){var guard=0,parts;while((parts=firstMatch(el))&&guard++<500){wrapParts(parts);}});}if(document.readyState==='loading'){document.addEventListener('DOMContentLoaded',run);}else{run();}})();</script>
