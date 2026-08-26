---
title: "Social Engineering and Phishing"
teaching: 20
exercises: 15
---

:::::::::::::::::::::::::::::::::::::: questions
- What is social engineering and why are HPC users targeted?
- How can you recognize phishing attempts?
- What should you do when you suspect a phishing attack?
- How does insider threat awareness fit into HPC security?
::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives
- Define social engineering and identify common attack patterns
- Recognize phishing emails by their structural and content tells
- Apply a clear reporting workflow when phishing is suspected
- Connect these practices to NIST SP 800-171 controls 3.2.2 (insider threat) and 3.2.3 (social engineering)
::::::::::::::::::::::::::::::::::::::::::::::::

## What Is Social Engineering?

Social engineering is the use of psychological manipulation to trick people into giving up credentials, access, or sensitive information. Instead of attacking computers directly, an attacker attacks the **human** in the loop.

Common forms on an HPC cluster:

- **Phishing email** that pretends to be ITS, a journal, a collaborator, or a vendor
- **Pretexting**: a phone call or chat message inventing a plausible reason to "verify" your password or DUO code
- **Baiting**: a USB drive labeled "Sagehen HPC Backup" left in a hallway
- **Tailgating**: someone slipping into a restricted area behind a badge holder
- **Quid pro quo**: "Free GPU hours if you forward me your SSH key"

Compliance reference: this material maps to **NIST SP 800-171 controls 3.2.2 (insider threat awareness)** and **3.2.3 (social engineering)**, both required for the Sagehen NIST Phase 1 baseline.

## Why HPC Users Are Targeted

HPC accounts are high-value targets because they unlock:

- Significant compute capacity (useful for cryptomining, model training, password cracking)
- Privileged data: unpublished research, FERPA records, export-controlled work
- A trusted launchpad into other Claremont Colleges systems
- Storage volume that can host illicit data exfiltration

A compromised HPC account is rarely about *you*. It is usually a stepping stone.

## Anatomy of a Phishing Email

Below is a realistic example modeled on the Module 1 reference scenario:

```
From: ITS Support <its-support@pomona-verify.com>
Subject: URGENT: Sagehen Account Suspension Notice

Dear User,

Your Sagehen HPC account has exceeded its quota and will be
SUSPENDED within 24 hours unless you re-verify your credentials.

Click here to confirm your account: http://pomona-secure-login.net/verify

Failure to act will result in permanent loss of all research data.

Sincerely,
Pomona ITS Security Team
```

What makes this phishing, not legitimate ITS communication:

| Tell | What to look for |
|------|------------------|
| Sender domain mismatch | `pomona-verify.com` is **not** `pomona.edu`; real HPC mail comes from `its-hpc@pomona.edu` or `@pomona.edu` |
| Urgency/threats | "24 hours", "permanent loss", "URGENT" — designed to bypass thinking |
| Generic greeting | "Dear User" — Pomona ITS uses your name |
| Suspicious link | `pomona-secure-login.net` is a lookalike domain, not a Pomona-owned host |
| Action via link | Real ITS will never ask you to "re-verify" credentials over email |
| Mismatched signature | "Pomona ITS Security Team" is not a real internal signature line |

::::::::::::::::::::::::::::::::::::: callout
## Quick Test: Hover Before You Click

Before clicking any link in an email, hover over it (do not click) and check the **destination URL** in the status bar. If the visible text is `https://duo.pomona.edu` but the destination is `http://login-secure.example/`, it is phishing. Forward to security@pomona.edu and delete.
::::::::::::::::::::::::::::::::::::::::::::::::

## Recognizing Phishing in Practice

Use the **SLAM** quick check:

- **S**ender: does the address really come from the claimed organization?
- **L**inks: do hover-previewed URLs match what the text claims?
- **A**ttachments: were you expecting them? Office macros and `.zip` files are high risk.
- **M**essage: is there urgency, threats, secrecy, or a too-good-to-be-true offer?

If any one of these fails, treat the email as phishing.

## Insider Threat Awareness (NIST 3.2.2)

Insider threats are not always malicious. Common scenarios at a research cluster:

- A graduate student leaves the lab and keeps using shared credentials
- A collaborator emails their `gocryptfs` passphrase in plain text "just this once"
- A user pastes their SSH private key into a shared chat to "save time"
- A lab member shares an account with an undergraduate to bypass onboarding

Each of these is reportable. Insider mistakes do as much damage as outside attackers.

## What To Do When You Suspect Phishing

1. **Do not click** any link or open any attachment
2. **Do not reply** to the message — even to "ask if it's real"
3. **Forward the full message** (with headers) to **security@pomona.edu**. Verify this address with ITS the first time you use it; do not trust the address printed in a suspicious email itself.
4. **Cc its-hpc@pomona.edu** if the phish references HPC, Sagehen, SSH, or research data
5. **Delete the message** from your inbox after forwarding
6. If you already clicked: change your Pomona password immediately at the legitimate `https://duo.pomona.edu`, run a malware scan, and report the incident through Workshop 13 Episode 5's process

::::::::::::::::::::::::::::::::::::: callout
## Verify Out of Band

If you genuinely cannot tell whether a message is real, **call or visit** the supposed sender through a channel you already trust. Walk to the ITS office. Look up its-hpc@pomona.edu in the campus directory yourself. Never use phone numbers or addresses given inside the suspicious message.
::::::::::::::::::::::::::::::::::::::::::::::::

## Compliance Mapping

| NIST SP 800-171 control | What it asks | How this episode satisfies it |
|--------------------------|--------------|-------------------------------|
| 3.2.1 Awareness training | Provide security awareness to users | Workshop 13 overall |
| 3.2.2 Insider threat awareness | Train users to recognize and report insider risk | "Insider Threat Awareness" section above |
| 3.2.3 Social engineering | Train users to recognize and resist social engineering / phishing | This entire episode |

## Reference: Trusted Pomona Channels

| Purpose | Real address |
|---------|--------------|
| HPC support and incidents | its-hpc@pomona.edu |
| Campus security incidents | security@pomona.edu (verify with ITS) |
| Identity / login | https://duo.pomona.edu |
| OnDemand portal | https://ondemand.hpc.pomona.edu |

If a message claims to be from any of these and the URL or address does not match exactly, treat it as phishing.

::::::::::::::::::::::::::::::::::::: challenge

## Challenge: Classify These Messages

For each message below, decide whether it is **legitimate** or **phishing**, and identify the specific tell(s) you used to decide.

1. From `its-hpc@pomona.edu`, subject "Scheduled Sagehen maintenance Friday 2 AM", with a link to `https://www.pomona.edu/its/`. No request for credentials.

2. From `noreply@pomona-it-helpdesk.com`, subject "Mandatory password reset within 12 hours", with a link to `http://pomona-it-login.net/reset?user=you`.

3. From `andrew.wilson@pomona.edu`, subject "Quick favor — gift cards", asking you to buy iTunes gift cards on behalf of the department because he's "in a meeting and can't take calls".

4. From `journal-submissions@nature.com`, subject "Decision on your manuscript", with a `.docx` attachment named `decision-letter.docx`. You did not submit anything to Nature.

5. From `its-hpc@pomona.edu`, subject "DUO push you didn't trigger?", asking you to call the ITS help desk at the number listed in the campus directory.

:::::::::::::::::::::::::::::::: solution

1. **Legitimate.** Sender domain matches `pomona.edu`. Link domain matches Pomona. No credential request. Maintenance announcements are routine.

2. **Phishing.** Sender domain is `pomona-it-helpdesk.com` (not `pomona.edu`). Link is HTTP (not HTTPS) and domain is a lookalike. Urgency tell ("12 hours"). Forward to security@pomona.edu.

3. **Phishing (gift card scam / pretexting).** Even though the visible name is real, the *behavior* is wrong: real Pomona staff do not ask for gift cards over email. Verify out of band by walking to Andrew Wilson's office or calling ITS. This is a classic CEO-impersonation phish.

4. **Phishing (attachment-based).** You did not submit a manuscript, so the message has no legitimate context. The `.docx` likely contains malicious macros. Do not open. Forward to security@pomona.edu and delete.

5. **Legitimate.** Sender domain matches. The message asks you to call a number you look up yourself in the campus directory — this is the correct out-of-band verification pattern. No credential entry is requested.

Key lesson: **sender domain, link domain, and out-of-band verification** catch most phish. Forward suspicious messages to security@pomona.edu and copy its-hpc@pomona.edu when HPC is involved.

:::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: keypoints
- Social engineering attacks the human, not the computer; HPC accounts are valuable targets
- Phishing tells: sender domain mismatch, urgency, generic greeting, suspicious links, unexpected attachments
- Never click links or open attachments in suspicious messages; verify out of band through trusted channels
- Forward suspected phishing to security@pomona.edu; cc its-hpc@pomona.edu when HPC is involved
- Insider mistakes (shared credentials, leaked passphrases, account sharing) are reportable too
- This episode satisfies NIST SP 800-171 controls 3.2.2 (insider threat) and 3.2.3 (social engineering)
::::::::::::::::::::::::::::::::::::::::::::::::
