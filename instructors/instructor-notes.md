---
title: Instructor Notes
---

# HPC Security Orientation - Instructor Notes

## Workshop Overview

**Title**: HPC Security Orientation
**Duration**: 90 minutes to 2 hours (including discussion and Q&A)
**Format**: Can be delivered in-person, synchronous online, or asynchronous (self-paced)
**Audience**: All new Sagehen HPC users; must be completed within 30 days of account creation
**Compliance**: Mandatory training; completion required for account activation; non-completion results in automatic suspension after 30 days

## Critical Context

This is **mandatory training**, not optional. Learners must understand:
- This protects real people and real research
- Violation consequences include account suspension
- You represent Pomona College and your research community
- Data security is everyone's responsibility

## Learning Objectives

By the end of this training, learners will:
1. Understand why data security matters (real consequences)
2. Classify research data correctly using three-tier system
3. Create and manage secure passwords
4. Set up and use DUO Multi-Factor Authentication
5. Know what's allowed and prohibited on Sagehen
6. Know how to report security incidents (no-blame)
7. Understand their role in shared security responsibility

## Pre-Workshop Instructor Preparation

### 1. Verify Your Resources
- [ ] Access to Pomona's Data Classification Policy
- [ ] Access to Acceptable Use Policy
- [ ] FERPA and HIPAA quick reference materials
- [ ] Export Control (CUI) information from your institution
- [ ] IRB contact information
- [ ] Institutional data breach case studies (anonymized)

### 2. Prepare Examples
- [ ] 3-4 real (anonymized) data classification examples from your institution
- [ ] Example of RESTRICTED data in gocryptfs-encrypted folder
- [ ] Example incident scenario
- [ ] Local contacts for FERPA, HIPAA, IRB, Compliance

### 3. Test Technical Setup
- [ ] DUO app is installed on demo phone/device
- [ ] OnDemand access works
- [ ] Can show example of gocryptfs encryption
- [ ] Have backup slides/screenshots in case live demo fails

### 4. Know the Policies Cold
- [ ] Read Acceptable Use Policy in full
- [ ] Understand your institution's specific FERPA/HIPAA obligations
- [ ] Know consequences for different violation types
- [ ] Know how suspension process works

## Episode-by-Episode Teaching Guide

---

### Episode 1: Why Security Matters (15 min teaching + 10 min discussion)

**Learning Outcome**: Learners understand real costs and consequences of security breaches

**Key Concepts**:
- Data breaches affect real people (research participants, students)
- Costs are high: financial, legal, reputational, personal
- Prevention is far easier than remediation
- Pomona College's legal liability
- Individual researcher's liability and career impact

**Teaching Approach**:

1. **Open with impact** (~5 min):

   Tell this story (or one relevant to your institution):

   > "A biology lab discovers that genetic data from a 5-year study: linked to participant IDs and health information: was stored unencrypted in a shared folder. A visiting researcher found it, felt uncomfortable, reported it. The institution was notified by a journalist asking to confirm details for a story.
   >
   > What happens next? Institutional Review Board (IRB) investigation. Notification to 200+ research participants and their families. Media coverage. Lawsuits from participants. HIPAA penalties ($100,000 per violation, minimum). Settlement costs for institution: $2 million. PI loses federal funding. Lab shuts down. Professor leaves institution.
   >
   > The whole thing could have been prevented with one password and encryption."

   Ask: "Has anything like this happened to someone you know?"

2. **Connect to learner context** (~5 min):
   - "Who works with student data?" (FERPA applies)
   - "Who works with health data?" (HIPAA applies)
   - "Who works with human subjects?" (IRB applies)
   - "Who has proprietary research?" (Trade secret risk)

   For each hand, briefly explain consequences of breach:
   - FERPA violation: federal penalties, loss of financial aid for students
   - HIPAA: federal penalties, participant lawsuits
   - IRB: study shutdown, future research blocked
   - Trade secret: loss of competitive advantage, legal exposure

3. **Explain the numbers** (~3 min):
   - Average data breach cost (varies by industry): $2-4 million
   - Per-record cost: $100-300 per person affected
   - Time to contain breach: 6+ months
   - Regulatory fines: $100,000+ per HIPAA violation
   - Legal settlements: Case-by-case, can be very high

4. **Frame as partnership** (~2 min):
   > "Pomona College and the HPC team provide secure infrastructure. You provide responsible data handling. Together, we keep research safe."

**Discussion Prompts**:
- "Why do you think data breaches are so expensive?"
- "Who is responsible if data is breached? The person who stored it? The PI? The institution?"
- "What's the difference between losing data (corruption) and having it stolen (breach)?"
- "How would a breach affect your research participants?"

**Common Questions & Answers**:

Q: "This won't happen to my data. I'm careful."
A: "That's great! But we all make mistakes. A brief inattention: wrong permissions, uploading to wrong folder: can happen to anyone. We're building systems that prevent these mistakes."

Q: "Isn't the IT staff responsible for security?"
A: "Shared responsibility. We provide secure infrastructure. You provide secure practice. Both matter."

Q: "Isn't encryption enough?"
A: "No. Encryption is one layer. You also need: good passwords, correct permissions, access controls, incident awareness. Encryption is necessary but not sufficient."

**Teaching Tips**:
- Make this real and personal; emotional buy-in is critical for compliance
- Use your institution's actual data breach cases (anonymized)
- Don't lecture; discuss in conversational tone
- Acknowledge that security feels burdensome sometimes
- Celebrate that we're preventing problems

---

### Episode 2: Acceptable Use Policy (20 min teaching + 10 min discussion)

**Learning Outcome**: Learners understand what's allowed and prohibited on Sagehen HPC

**Key Concepts**:
- Sagehen is for approved research and education only
- Account is personal and not transferable
- Consequences for violations

**Teaching Approach**:

1. **Summarize the policy** (~10 min):

   Create a table on board/slide:

   | What | Allowed? | Why |
   |------|----------|-----|
   | Run approved research | YES | Primary purpose of cluster |
   | Share password with lab member | NO | Violates AUP; loss of audit trail |
   | Run cryptocurrency mining | NO | Wastes resources; not approved use |
   | Test security of cluster | NO | Contact HPC staff; do it properly |
   | Process personal data (non-research) | NO | Not approved use; no institutional protection |
   | Run job that uses 100% CPU for 30 days | Maybe | Need approval; may violate fair use |
   | Cancel another user's job | NO | Only cancel your own |
   | Access another user's files | NO | Even if you can (permissions bug), don't do it |
   | Harassment or hostile communication | NO | Violates code of conduct |
   | Submit large job as stress test | NO | Violates fair use |
   | Delete files from /bigdata | Maybe | Only your own or with group permission |

   Walk through each row. Ask for examples from learner's experience.

2. **Emphasize key prohibited items** (~5 min):

   **Account Sharing** (This is critical):
   > "Your account is linked to you. Your name. Your research. Your reputation. If someone else uses your account and breaks rules, it's recorded against you. You lose the ability to prove it wasn't you. For shared code or data, create shared folders, not shared accounts. Each person gets their own account."

   **Cryptocurrency Mining**:
   > "Cryptocurrency mining is prohibited because it wastes compute resources and electricity at scale, doesn't generate research output, and violates fair-use principles."

   **Illegal Activity**:
   > "If law enforcement contacts us about illegal activity on Sagehen, we cooperate fully. Your account won't protect you."

3. **Explain consequences** (~5 min):

   Violation escalation:
   - **First minor violation**: Warning, discussion with PI
   - **Second violation or serious first offense**: 7-30 day suspension
   - **Severe violations**: Permanent suspension, possible legal referral
   - **Illegal activity**: Immediate suspension, law enforcement notification

   Who gets told:
   - Your PI
   - Your department
   - Possibly your institution's administration
   - Your institutional affiliations may be affected

**Discussion Prompts**:
- "Why do you think account sharing is prohibited?"
- "What would happen if your lab member accessed cluster and did something illegal?"
- "What's fair use of a shared resource?"

**Common Questions & Answers**:

Q: "Can my lab member use my password?"
A: "No. Each person needs their own account. Contact its-hpc@pomona.edu to request an account for them."

Q: "What if I need to help someone with their job?"
A: "Help them debug, yes. Using their account, no. They should run commands; you guide them."

Q: "How do you catch violations?"
A: "We monitor resource usage, file access logs, job patterns. But mostly, people report problems or self-report mistakes."

---

### Episode 3: Passwords & Authentication (20 min teaching + 15 min exercise)

**Learning Outcome**: Learners create strong passwords and set up DUO MFA correctly

**Key Concepts**:
- Strong password rules
- Password manager importance
- DUO setup and use

**Teaching Approach**:

1. **Password strength** (~8 min):

   Show bad vs. good examples:
   ```
   BAD:  password123, alice1990, sagehen, "Pomona2026"
   GOOD: QuantumLeaf#2026$Pomona, 7kR!x9mP2vQ1L$w
   ```

   Rules:
   - 14+ characters minimum
   - Mix: uppercase, lowercase, numbers, symbols
   - Not dictionary words, names, birthdates
   - Unique per account (especially for Pomona vs. other services)

   Anti-pattern to avoid:
   - Same password for Pomona, OnDemand, Sagehen (if separate systems)
   - Reusing password from other sites
   - Storing passwords in email drafts or text files
   - Using simple substitutions: P@ssw0rd, 123qweasd

2. **Password manager** (~5 min):

   Demonstrate (or show screenshots):
   - Open 1Password, LastPass, Dashlane, or Bitwarden
   - Show how to store a password
   - Show how to auto-fill login
   - Show strength meter

   Key selling points:
   - Generates strong random passwords
   - Remembers them so you don't have to
   - Encrypts them on your device
   - Auto-fills login fields

   Recommendation: "Choose one password manager and commit to it. Worth the effort."

3. **DUO Multi-Factor Authentication setup** (~7 min):

   Live demo (or screenshots):

   Step 1: User gets enrollment email
   ```
   Subject: Enroll in Duo Authentication
   Click link: https://enroll.duosecurity.com/...
   ```

   Step 2: User chooses authentication method
   ```
   Option A: Smartphone (install Duo Mobile app)
   Option B: Landline or mobile phone (SMS/call)
   Option C: Hardware token (less common)
   ```

   Step 3: Download Duo Mobile (if choosing app)
   ```
   - Apple App Store or Google Play
   - Launch app, scan QR code from enrollment page
   - Duo is now set up
   ```

   Step 4: Test during login
   ```
   User logs in with Pomona username and password
   Pomona says: "Duo ready. Check your phone."

   On phone: Duo Mobile app shows push notification
   User taps "Approve"
   Login completes
   ```

   Show backup codes:
   ```
   Save these 10 one-time codes in password manager
   Use if phone is lost or app unavailable
   Each code works once
   ```

4. **If Compromise Happens** (~3 min):

   Scenario: "You realize your Pomona password is stolen (compromised on another site or you told someone accidentally)."

   Steps:
   1. **Change password immediately**: https://duo.pomona.edu
   2. **Email its-hpc@pomona.edu**: "Possible password compromise; changed password at [time]"
   3. **Monitor for 30 days**: Check for unusual logins, file access
   4. **Consider other accounts**: Change password on other sites too if same password was used

   "It happens. Don't panic. Just act quickly."

**Interactive Exercise** (~15 min):

Pair learners or work individually:

**Part 1: Create a strong password** (5 min)
- Use password generator online or mentally
- Write in password manager (or on paper for this exercise)
- Check strength meter
- Is it 14+ characters? Mix of types? No dictionary words?

**Part 2: Set up DUO** (5 min, or demo if already done)
- Check Duo enrollment status (how to verify)
- If not enrolled, follow enrollment link
- Install Duo Mobile or register phone
- Test approval during next login

**Part 3: Prepare for compromise** (5 min)
- Identify your password manager
- Store Pomona password there
- Save backup codes in password manager
- Write down its-hpc@pomona.edu contact for emergency

**Teaching Tips**:
- Many learners haven't used password managers; show value, not burden
- DUO demo is important; have backup screenshots if live demo fails
- Some learners forget phone with Duo app; have SMS backup ready
- Celebrate when they succeed; "You've just secured your account!"

---

### Episode 4: Data Classification & Protection (20 min teaching + 15 min exercise)

**Learning Outcome**: Learners can classify their own data and know protection requirements

**Key Concepts**:
- Four classification tiers
- Storage and encryption requirements per tier
- Access control and permissions
- How to decide classification

**Teaching Approach**:

1. **Introduce the three tiers** (~5 min):

   Use visual (pyramid or table):
   ```
   PUBLIC         (unrestricted sharing)
       ↓
   PROPRIETARY    (restricted access, unpublished research)
       ↓
   RESTRICTED     (encrypted, legally required)
   ```

   Key rule: "As tier increases, protection increases and sharing restrictions increase."

2. **Deep dive into each tier** (~9 min, ~3 min each):

   **PUBLIC** (3 min)
   - Definition: Already published or intended for unrestricted sharing
   - Examples: Published papers, data with DOI, open-source code, datasets on public databases
   - Storage: Anywhere (laptop, GitHub, cloud, campus server)
   - Encryption: Not required
   - Access: Unrestricted; encourage sharing
   - Live example: Show GitHub repo or published dataset
   - Question: "Is there any risk sharing this with the world? No? Then it's PUBLIC."

   **PROPRIETARY** (3 min)
   - Definition: Confidential information with business or research value; unpublished research and draft work
   - Examples: Pre-publication research, draft manuscripts, lab notebooks, unpublished data, novel algorithms, unpublished code with competitive advantage
   - Storage: Sagehen only (/bigdata)
   - Encryption: Recommended (gocryptfs)
   - Access: Individual or small authorized group; chmod 700
   - Sharing: Only with authorized people or with signed NDA (Non-Disclosure Agreement)
   - Legal: Sharing requires NDA review; institution's legal office should review
   - Live example: Show gocryptfs encrypted folder (pre-created for demo)
   - Question: "Is it unpublished? Would you lose competitive advantage if this was public? If not yet published or secret and valuable, it's PROPRIETARY."

   **RESTRICTED** (3 min)
   - Definition: Legally protected personal or sensitive information
   - Examples: Student educational records (FERPA), health information (HIPAA), genetic data linked to IDs, classified information (CUI)
   - Storage: Sagehen only (/bigdata)
   - Encryption: MANDATORY (gocryptfs or VeraCrypt)
   - Access: Only named researchers with authorization; documented
   - Sharing: Only with signed Data Use Agreement; IRB review; recipient must have IRB approval
   - Legal: Cannot share externally without proper agreements; fines for violations ($100k+ per HIPAA violation)
   - Live example: Show encrypted folder mounted and unmounted
   - Question: "Does this data identify people or contain protected health/genetic information? Would breach harm someone? Yes? It's RESTRICTED."

3. **Boundary cases** (~2 min):

   Work through examples:

   "I have code with a proprietary algorithm but no personal data. PUBLIC or PROPRIETARY?"
   → PROPRIETARY (trade secret; wait for publication before PUBLIC)

   "Student thesis with methodology but no raw data. PROPRIETARY or RESTRICTED?"
   → PROPRIETARY (unpublished thesis; wait for publication before PUBLIC)

   "Anonymized genetic data with IDs removed. PROPRIETARY or RESTRICTED?"
   → Likely RESTRICTED (re-identification risk remains; HIPAA still applies)

   "My PI said I can share lab data externally. PROPRIETARY or PUBLIC?"
   → PROPRIETARY until published, then PUBLIC (group decision already made)

**Interactive Exercise** (~15 min):

**Part 1: Classify provided datasets** (8 min)
Provide 4-5 real or realistic datasets; have learners classify:

Example 1:
```
File: student_survey.csv
Contents: student_id, gender, major, exam_score
Source: Course evaluation survey
```
Classification: PROPRIETARY or RESTRICTED
Reasoning: Student IDs are present; links to educational records (FERPA)
→ RESTRICTED if used for research; PROPRIETARY if just course evaluation

Example 2:
```
File: lab_protocols.docx
Contents: Standard procedures for DNA extraction
Source: Lab manual
```
Classification: PROPRIETARY
Reasoning: Unpublished lab procedures; no proprietary methods or personal data
→ Share with lab group; ask before sharing with other labs

Example 3:
```
File: novel_algorithm.py
Contents: Unpublished machine learning algorithm
Source: Pre-publication research
```
Classification: PROPRIETARY
Reasoning: Novel method; not yet published; has competitive value
→ Encrypt; share only with collaborators under NDA

Example 4:
```
File: patient_data.xlsx
Contents: Patient_ID, Age, Diagnosis, MRI_results
Source: Clinical research study
```
Classification: RESTRICTED
Reasoning: Health information; personal identifiers; HIPAA applies
→ MANDATORY encryption; data use agreement required for any sharing

**Part 2: Classify own data** (7 min)
Ask learners to think about (not discuss aloud):
- What data do you work with?
- Does it identify people? (FERPA/HIPAA)
- Is it published yet? (PUBLIC if yes, PROPRIETARY if no)
- Who should access it? (Public/Pomona/PI/research team)
- What would happen if breached? (Gauge impact)
- How should it be stored? (Sagehen; encrypted?)

Pair learners to discuss (optional):
- "My data is mostly..." [classification]
- "I need to..." [encryption? permission setup?]

**Teaching Tips**:
- Boundary cases between PROPRIETARY and RESTRICTED confuse many; clarify: "PROPRIETARY = trade secret; RESTRICTED = legal protection required for people's data"
- Learners often under-classify (too permissive); ask "Could this harm someone if breached?" to recalibrate
- Having real examples from your institution helps; anonymize appropriately
- Celebrate when learners classify conservatively; "Better safe than sorry"

---

### Episode 5: Incident Reporting (15 min teaching + 10 min discussion)

**Learning Outcome**: Learners know how to recognize and report security incidents without fear

**Key Concepts**:
- What counts as an incident
- How to report it
- No-blame policy
- What happens after reporting

**Teaching Approach**:

1. **What counts as an incident** (~5 min):

   Scenario discussion:

   **Scenario 1**: "You notice a file in /bigdata created yesterday at 3 AM by someone else. You weren't working then."
   → **YES, incident**: Unauthorized access or compromised account

   **Scenario 2**: "You accidentally set a folder to chmod 777 (world-readable) and stored sensitive data there for 1 day before realizing."
   → **YES, incident**: Accidental exposure (your mistake, but still reportable)

   **Scenario 3**: "You get an email from 'Pomona ITS' asking you to verify your password by clicking a link."
   → **YES, incident**: Phishing attempt (don't click; report)

   **Scenario 4**: "A collaborator asks for your password so they can 'just run one quick job'."
   → **YES, incident**: Account sharing attempt (not an emergency, but notify HPC)

   **Scenario 5**: "You realize you used the same password for Pomona and an external website, and the external site was hacked."
   → **YES, incident**: Credential compromise

   **Scenario 6**: "You run a job and notice it fails with 'permission denied' accessing another user's files."
   → **YES, incident**: Report to HPC (might be legitimate permission issue, but should be investigated)

2. **How to report** (~5 min):

   Template email:
   ```
   To: its-hpc@pomona.edu
   Subject: SECURITY INCIDENT REPORT

   What happened:
   [Be specific. Include dates, times, file names, usernames if known]

   When you noticed it:
   [Specific date and time]

   What data might be affected:
   [Describe data: research files, personal files, code, etc.]

   What you've already done:
   [Did you change password? Delete anything? Tell anyone?]

   Your contact info:
   [Your phone number and email]
   ```

   Example:
   ```
   To: its-hpc@pomona.edu
   Subject: SECURITY INCIDENT REPORT - Unauthorized File Access

   What happened:
   I noticed a file called "research_backup.tar.gz" in my /bigdata/lab/<labname>/
   directory that I did not create. It was created on March 28 at 2:47 AM.
   I also see a file called "admin_config.sh" created at the same time.
   I was not working at that hour.

   When I noticed:
   This morning, March 29, 2026, at 8:30 AM when I logged in via OnDemand.

   What data might be affected:
   The directory contains research data for my ongoing NSF-funded project.
   I don't know if files were copied, modified, or just accessed.

   What I've already done:
   - Changed my Pomona password at 8:35 AM
   - Did not touch the suspicious files
   - Did not delete anything
   - Immediately logged out

   Contact info:
   alice.chen@pomona.edu
   555-1234
   ```

3. **No-blame policy** (~3 min):

   Make this very clear:

   > "If you make a mistake: wrong permissions, password shared accidentally, data uploaded to wrong location: reporting it is NEVER punitive to you.
   >
   > Our goal is to:
   > 1. Help you fix the problem quickly
   > 2. Prevent it from happening again
   > 3. Limit any impact
   >
   > Reporting early means less damage. Hiding mistakes means more damage when discovered.
   >
   > You will not be suspended for honest mistakes. You MIGHT be suspended for trying to hide them or ignoring warnings."

4. **What happens after you report** (~2 min):

   Timeline:
   - **Within 1 hour**: HPC staff will contact you (phone or email) to gather more details
   - **Within 24 hours**: Staff will investigate and determine scope
   - **Within 48-72 hours**: You'll hear findings and any recommended actions
   - **Ongoing**: You'll be asked to monitor your account; HPC will help you secure it

   What HPC staff will do:
   - Investigate file access logs
   - Check for account compromise
   - Verify no data was stolen
   - Help you change passwords if needed
   - Walk you through security improvements

**Discussion Prompts**:
- "What would you do if you received a phishing email?"
- "When would you report an issue vs. trying to fix it yourself?"
- "What information should you NOT include in incident report?" (Don't try to solve it yourself; don't share passwords even when reporting)

**Common Questions & Answers**:

Q: "If I made a mistake with permissions, will I get in trouble?"
A: "No. Honest mistakes are okay. We help you fix them. Trying to hide them is worse."

Q: "Should I investigate the incident myself first?"
A: "No. Report immediately. Don't delete files or investigate further; you might destroy evidence or make it worse. Let us investigate."

Q: "Can I report anonymously?"
A: "We'd prefer you identify yourself so we can help you, but yes, you can report anonymously. We still have to investigate."

---

### Episode 6: Resources & Summary (10 min teaching + 5 min Q&A)

**Learning Outcome**: Learners know where to find help and have completed all acknowledgments

**Teaching Approach**:

1. **Key resources** (~3 min):

   Display on slide:

   **For Security Issues**:
   - Email: its-hpc@pomona.edu
   - Phone: [Emergency number]
   - OnDemand help: Click "?" icon

   **For Data Classification Help**:
   - Your PI or lab manager
   - its-hpc@pomona.edu
   - Your department compliance officer

   **For Compliance Questions**:
   - IRB (for human subjects)
   - Research & Sponsored Programs (for grant compliance)
   - Legal Office (for legal questions)
   - Compliance Officer (for institutional policy)

   **For Account Issues**:
   - ITS Help Desk

   **For Password Manager Recommendations**:
   - Ask its-hpc@pomona.edu

2. **Key takeaways** (~5 min):

   Summarize on board/slide:

   ```
   1. DATA SECURITY MATTERS: Real data, real people, real consequences
   2. THREE TIERS: PUBLIC, PROPRIETARY, RESTRICTED
   3. STRONG PASSWORD: 14+ chars, random, unique, in password manager
   4. DUO MFA: Second factor prevents most breaches
   5. ACCEPTABLE USE: Follow AUP; account is personal; no sharing
   6. ENCRYPTION: MANDATORY for RESTRICTED; recommended for PROPRIETARY
   7. REPORTING: No-blame; report incidents immediately
   8. RESPONSIBILITY: You and institution working together
   ```

   Then ask: "Any of these you want to discuss more?"

3. **Acknowledgment** (~2 min):

   Explain that learners must confirm:
   - Read Acceptable Use Policy
   - Understand data classification
   - Accept responsibility for account security
   - Know how to report incidents
   - Understand consequences for violations

   Completion is required; system will not activate account without acknowledgment.

## Assessment & Compliance

### During Training:
- Ask classification questions: "What tier is this data?"
- Ask policy questions: "What would happen if you shared your account?"
- Ask incident reporting: "What would you do if...?"

### Post-Training:
- Mandatory acknowledgment form (online system)
- Completion tracked and recorded
- Account activation requires acknowledgment
- Non-completion = automatic suspension after 30 days

### Verification
- Check that completion is logged
- Verify acknowledgment signature
- Monitor for compliance violations in first 6 months

## Teaching Tips

### For In-Person Delivery:
- Use projector/large screen so everyone can see examples
- Pause frequently for questions
- Use whiteboard to track key ideas
- Call on different learners to classify examples (engagement)
- Have printed handouts of quick reference

### For Online Synchronous:
- Use Zoom or Teams with share screen
- Use polls/chat for interaction
- Take questions in chat as you go
- Record for asynchronous viewers later
- Provide slides and links in chat

### For Asynchronous/Self-Paced:
- Use clear written instructions
- Break into shorter episodes (5-10 min each)
- Include video demonstrations (password manager, DUO setup)
- Provide examples and case studies
- Include quiz to check understanding
- Make acknowledgment at the end clear and required

### General Tips:
- Use real examples from your institution (anonymize)
- Celebrate when learners ask good questions
- Normalize that security feels burdensome; explain why it matters
- Invite feedback afterward; this training affects how people work
- Offer follow-up office hours for detailed questions

## Common Learner Mistakes & Prevention

| Mistake | Prevention |
|---------|-----------|
| Sharing password with lab member | Explain account is personal; request account for them |
| Storing password in sticky note | Demo password manager; explain value |
| Using weak password | Show strength meter; show how easily cracked weak passwords are |
| Not setting up DUO | Explain it's required; show enrollment links |
| Not understanding encryption | Demo gocryptfs; show encrypted vs. decrypted folder |
| Misclassifying data | Provide examples; err on side of caution |
| Deleting evidence during incident | Explain why preservation is important |
| Not reporting because of fear | Emphasize no-blame policy repeatedly |

## Post-Workshop Checklist

After delivery:
- [ ] All learners have acknowledged the policy
- [ ] All acknowledgments are logged in system
- [ ] Completion is recorded for compliance
- [ ] If any learner didn't complete, send reminder email
- [ ] Collect feedback on training effectiveness
- [ ] Note common misunderstandings for future improvement

## Resources for Instructors

### Policy Documents
- Pomona College Data Classification Policy
- Acceptable Use Policy
- FERPA regulations: https://www2.ed.gov/policy/gen/guid/fpco/ferpa/
- HIPAA overview: https://www.hhs.gov/hipaa/
- CUI (Controlled Unclassified Information): https://www.archives.gov/cui/

### Tools & Demos
- Duo Mobile App
- Password managers: 1Password, LastPass, Dashlane, Bitwarden
- gocryptfs documentation: https://nuetzlich.net/gocryptfs/
- VeraCrypt (Windows/Mac alternative): https://www.veracrypt.fr/

### Training Materials
- Carpentries HPC resources: https://carpentries-incubator.github.io/hpc-intro/
- SANS Security Awareness: https://www.sans.org/
- NCSC (UK) Security guidance: https://www.ncsc.gov.uk/

## Tips for Engagement

1. **Make it personal**: "Your data is someone's life. Protect it."
2. **Use real scenarios**: Real data breach cases (anonymized) from your institution
3. **Normalize questions**: "Everyone struggles with data classification"
4. **Celebrate caution**: "When in doubt, classify higher. That's good instinct."
5. **Provide templates**: Example incident report, classification checklist
6. **Connect to regulations**: Reference FERPA/HIPAA by name; show why it matters
7. **Offer follow-up**: "Email me if you have questions after this training"

---

**Last Updated**: March 2026
**For questions**: Contact its-hpc@pomona.edu

<!-- highlight <labname>/<myusername> placeholders in code blocks; remove if the varnish theme handles this natively -->
<script>(function(){var CSS='.sh-placeholder{color:#c2410c;font-weight:700}[data-bs-theme="dark"] .sh-placeholder,html.dark .sh-placeholder{color:#fdba74}@media (prefers-color-scheme: dark){[data-bs-theme="auto"] .sh-placeholder{color:#fdba74}}';var RX=/<labname>|<myusername>/g;function firstMatch(el){var w=document.createTreeWalker(el,NodeFilter.SHOW_TEXT,null),nodes=[],full='';while(w.nextNode()){nodes.push({n:w.currentNode,s:full.length});full+=w.currentNode.nodeValue;}RX.lastIndex=0;var m;while((m=RX.exec(full))){var s=m.index,e=s+m[0].length,inSpan=false,parts=[];for(var j=0;j<nodes.length;j++){var ns=nodes[j].s,ne=ns+nodes[j].n.nodeValue.length;if(ne<=s||ns>=e)continue;parts.push({node:nodes[j].n,a:Math.max(s-ns,0),b:Math.min(e-ns,nodes[j].n.nodeValue.length)});var p=nodes[j].n.parentNode;while(p&&p!==el){if(p.classList&&p.classList.contains('sh-placeholder')){inSpan=true;break;}p=p.parentNode;}}if(!inSpan&&parts.length)return parts;}return null;}function wrapParts(parts){for(var i=parts.length-1;i>=0;i--){var t=parts[i].node,txt=t.nodeValue,a=parts[i].a,b=parts[i].b;var span=document.createElement('span');span.className='sh-placeholder';span.textContent=txt.slice(a,b);var f=document.createDocumentFragment();if(a>0)f.appendChild(document.createTextNode(txt.slice(0,a)));f.appendChild(span);if(b<txt.length)f.appendChild(document.createTextNode(txt.slice(b)));t.parentNode.replaceChild(f,t);}}function run(){var st=document.createElement('style');st.textContent=CSS;document.head.appendChild(st);document.querySelectorAll('pre,code').forEach(function(el){var guard=0,parts;while((parts=firstMatch(el))&&guard++<500){wrapParts(parts);}});}if(document.readyState==='loading'){document.addEventListener('DOMContentLoaded',run);}else{run();}})();</script>
