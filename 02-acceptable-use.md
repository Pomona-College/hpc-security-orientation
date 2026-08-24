---
title: "Acceptable Use Policy"
teaching: 20
exercises: 10
---

:::::::::::::::::::::::::::::::::::::: questions
- What activities are allowed on Sagehen?
- What is strictly prohibited?
- How are policy violations handled?
- What counts as "appropriate use"?
::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives
- Understand Pomona's Acceptable Use Policy
- Recognize prohibited activities
- Know consequences of policy violation
- Understand appropriate use guidelines
::::::::::::::::::::::::::::::::::::::::::::::::

## Pomona's Acceptable Use Policy

Sagehen is provided for Pomona College's educational and research mission. Using the cluster means you agree to certain policies.

## Acceptable Uses

HPC is appropriate for:

- **Research computing**: Data analysis, simulations, modeling
- **Educational activities**: Course projects, learning programming
- **Collaboration**: Working with others on approved research
- **Development**: Creating and testing research software
- **Data management**: Storing and processing research data
- **Publication support**: Computations enabling published research

All use must be:

- **Approved by your PI**: Your advisor must sponsor your account
- **Mission-aligned**: Supporting Pomona's educational/research work
- **Responsible**: Not wasteful or excessive
- **Compliant**: Following all policies

## Strictly Prohibited Activities

The following are **never permitted** on Sagehen:

### Security Violations

- Attempting to gain unauthorized access
- Sharing accounts or credentials
- Running tools to crack passwords
- Exploiting known vulnerabilities
- Attempting to access others' data without permission

::::::::::::::::::::::::::::::::::::: callout

## No Exceptions: Account Sharing is Automatic Violation

Even sharing your account with a colleague "just this once" is an automatic violation resulting in investigation for both parties. Your account is for you alone. If others need access, they must get their own accounts. No exceptions.

::::::::::::::::::::::::::::::::::::::::::::::::

### Illegal Activities

- Downloading pirated software
- Distributing copyrighted material without permission
- Creating or distributing malware
- Facilitating illegal activity
- Anything that violates state or federal law

### Misuse of Resources

- Mining cryptocurrency
- Streaming video or entertainment
- Hosting websites or web services
- Commercial work without arrangement
- Anything not related to research/education

### Harassment and Abuse

- Offensive messages or content
- Harassment of other users
- Hate speech
- Discrimination
- Creating hostile environment

### Data Protection Violations

- Removing data without authorization
- Exposing restricted data publicly
- Sharing student data (FERPA violation)
- Violating export control restrictions
- Breaching confidentiality agreements

## Specific Examples

### NOT Allowed

- Sharing your password with a friend to run their job
- Using HPC to analyze data for a startup company (without approval)
- Installing cryptocurrency mining software
- Accessing files in `/bigdata/lab/<labname>` without permission
- Sending threatening messages to another user
- Running jobs for a consulting client without special arrangement
- Downloading the entire internet to your /bigdata directory

### Allowed (Usually)

- Running your own research code for 200 hours
- Working on class project for approved CS course
- Analyzing data as part of degree-required thesis
- Storing 5 TB of research data in `/bigdata/lab/<labname>`
- Collaborating with co-PI who also has HPC account
- Publishing results from computations on Sagehen

## Consequences of Violations

### First Offense (Minor)

- Verbal warning from HPC staff
- Explanation of correct behavior
- Account remains active
- Educational interaction

### Second Offense or Serious First Violation

- Account suspension (typically 30 days)
- Meeting required with PI
- Possible referral to administration
- Written documentation

### Severe Violations

- Immediate account deactivation
- Full investigation by ITS
- Possible disciplinary action
- Potential police involvement (if criminal)
- Expelled from HPC program permanently

### Automatic Violations

These result in immediate investigation:

- Attempted hacking or unauthorized access
- Sharing accounts (both parties involved)
- Storing illegal content
- Threat or harassment
- Violation of export control

## Special Approval Cases

Some uses require special approval:

### Commercial Use

- Industry collaboration: Requires special arrangement
- Patent work: Must be disclosed
- Consulting: Not allowed without approval
- Data for startup: Contact its-hpc@pomona.edu

### Resource-Intensive Work

- Very long jobs (>720 hours): Contact its-hpc@pomona.edu
- GPU usage (>1 week/month): May need approval
- Excessive storage: Quota system manages this

### Sensitive Data

- FERPA data (student records): Special handling required
- Medical information: Encryption mandatory
- Export-controlled research: Restricted access
- Proprietary data: Access controls applied

## Policy Acknowledgment

By using Sagehen, you acknowledge:

- You have read and understand this policy
- You will follow all rules
- You understand consequences of violations
- You will report violations you witness
- You hold yourself accountable

**You will be asked to sign this acknowledgment. This is legally binding.**

## Gray Areas

Some situations are less clear. If you're unsure:

**Ask its-hpc@pomona.edu before proceeding.**

Examples of situations requiring clarification:

- "Can I share results with external collaborator?"
- "Is this startup work allowed?"
- "Can I download this dataset?"
- "Does this course project qualify?"

Asking protects you and shows good judgment.

::::::::::::::::::::::::::::::::::::: callout
## Best Practice: Ask First, Act Second

When uncertain, send an email to its-hpc@pomona.edu describing what you want to do. Staff will respond within 24 hours. This single question can prevent weeks of account suspension. Good judgment means asking before acting on gray-area decisions.
::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: challenge

## Challenge: Policy Scenarios

For each scenario, decide if it's allowed, prohibited, or requires asking:

1. You want to download a TV show episode to relax during a break
2. Your brother wants to run a quick job on your account
3. You're analyzing data for a company project your advisor approved
4. You need to store research data containing student ID numbers
5. You want to help a friend debug their code by looking at their files

Discuss your answers and reasoning.

:::::::::::::::::::::::::::::::: solution

1. **Download TV show**: PROHIBITED - not research/educational, entertainment
2. **Brother uses your account**: PROHIBITED - account sharing never allowed, automatic violation
3. **Company analysis with approval**: LIKELY ALLOWED - but confirm with PI and its-hpc@pomona.edu to verify "approved"
4. **Student ID storage**: REQUIRES ASKING - student data needs special handling, probably needs encryption
5. **Help friend debug code**: ASK FIRST - depends on data type and whether they authorized you to access it

Key lesson: When uncertain, ask its-hpc@pomona.edu. It's better to ask and learn the policy than to assume and violate it.

:::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::

## Reporting Violations

If you witness someone violating the Acceptable Use Policy:

1. **Report to its-hpc@pomona.edu** with specific information
2. **Don't confront the violator** directly
3. **Include details**: What, when, who (if known)
4. **Investigations are confidential**
5. **Reporting is not retaliation** - protected action

## Questions About Policy?

Before doing anything you're unsure about:

**Email: its-hpc@pomona.edu**

This is why the support team exists - to answer questions and help users stay compliant.

::::::::::::::::::::::::::::::::::::: keypoints

- Acceptable use means research/education only, approved by PI
- Sharing accounts, illegal activity, and harassment are automatic violations
- Minor violations result in warnings; serious violations in account suspension
- Severe violations may result in police involvement
- Always ask its-hpc@pomona.edu if you're unsure
- You acknowledge this policy by using the cluster
- Reporting violations helps protect the community

::::::::::::::::::::::::::::::::::::::::::::::::

<!-- highlight <labname>/<myusername> placeholders in code blocks; remove if the varnish theme handles this natively -->
<script>(function(){var CSS='.sh-placeholder{color:#c2410c;font-weight:700}[data-bs-theme="dark"] .sh-placeholder,html.dark .sh-placeholder{color:#fdba74}@media (prefers-color-scheme: dark){[data-bs-theme="auto"] .sh-placeholder{color:#fdba74}}';var RX=/<labname>|<myusername>/g;function firstMatch(el){var w=document.createTreeWalker(el,NodeFilter.SHOW_TEXT,null),nodes=[],full='';while(w.nextNode()){nodes.push({n:w.currentNode,s:full.length});full+=w.currentNode.nodeValue;}RX.lastIndex=0;var m;while((m=RX.exec(full))){var s=m.index,e=s+m[0].length,inSpan=false,parts=[];for(var j=0;j<nodes.length;j++){var ns=nodes[j].s,ne=ns+nodes[j].n.nodeValue.length;if(ne<=s||ns>=e)continue;parts.push({node:nodes[j].n,a:Math.max(s-ns,0),b:Math.min(e-ns,nodes[j].n.nodeValue.length)});var p=nodes[j].n.parentNode;while(p&&p!==el){if(p.classList&&p.classList.contains('sh-placeholder')){inSpan=true;break;}p=p.parentNode;}}if(!inSpan&&parts.length)return parts;}return null;}function wrapParts(parts){for(var i=parts.length-1;i>=0;i--){var t=parts[i].node,txt=t.nodeValue,a=parts[i].a,b=parts[i].b;var span=document.createElement('span');span.className='sh-placeholder';span.textContent=txt.slice(a,b);var f=document.createDocumentFragment();if(a>0)f.appendChild(document.createTextNode(txt.slice(0,a)));f.appendChild(span);if(b<txt.length)f.appendChild(document.createTextNode(txt.slice(b)));t.parentNode.replaceChild(f,t);}}function run(){var st=document.createElement('style');st.textContent=CSS;document.head.appendChild(st);document.querySelectorAll('pre,code').forEach(function(el){var guard=0,parts;while((parts=firstMatch(el))&&guard++<500){wrapParts(parts);}});}if(document.readyState==='loading'){document.addEventListener('DOMContentLoaded',run);}else{run();}})();</script>
