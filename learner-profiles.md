# HPC Security Orientation - Learner Profiles

These personas describe representative learners on the Sagehen cluster. The
personas help instructors anticipate questions, calibrate examples, and shape
group discussions. Every learner — regardless of profile — must complete this
mandatory orientation within 30 days of account activation per Pomona ITS
Policy 24 and NIST SP 800-171 control 3.2.1.

---

## Persona 1: Faculty Member New to HPC

**Profile**: Dr. Maria Lopez, tenure-track Assistant Professor in Biology, just
hired this academic year. Has used desktop R and Excel for two decades. Submitted
her first NIH grant that promises HPC analysis of de-identified clinical samples.
Has never used SLURM, Linux command line, or SSH keys.

**Background and motivation**:
- Highly motivated; the grant will not be funded if the security plan is weak
- Anxious about doing something wrong with the data
- Comfortable with HIPAA conceptually; unfamiliar with how it maps to file
  permissions and gocryptfs
- Will be the responsible PI — her name is on the IRB and on any incident report

**Strengths**:
- Treats compliance seriously and reads policies carefully
- Asks the right questions about who can see her data and where it lives

**Likely struggles**:
- Conflates "private" (filesystem permissions) with "encrypted" (gocryptfs)
- Unsure when to call ITS vs. the IRB office vs. the grant compliance officer
- Worries that DUO push approvals will block her at conferences abroad

**What this orientation gives her**:
- A vocabulary (PUBLIC / PROPRIETARY / RESTRICTED) she can use in her IRB
  protocols and grant Data Management Plans
- Confidence that the workflow her grant requires (RESTRICTED tier with
  gocryptfs, 700 permissions, /bigdata) maps to a documented Pomona process
- A single contact — its-hpc@pomona.edu — for everything HPC-security related

**Instructor support**:
- Pair her in challenges with someone who has Linux fluency
- Reassure her that "if uncertain, classify higher" is the safe default
- Point her to Workshop 14 for the full data classification deep dive and
  Workshop 15 for gocryptfs hands-on

---

## Persona 2: Graduate Student Handling FERPA Data

**Profile**: David Park, third-year PhD candidate in Educational Studies. His
dissertation analyzes course-taking patterns and outcomes for ~3,000 Pomona
undergraduates over five years. The Registrar's Office has provided a dataset
that contains student names, IDs, course enrollments, and grades.

**Background and motivation**:
- Comfortable with R, Python, and basic SLURM batch jobs
- Has heard "FERPA" but treats it as paperwork, not a daily-practice concern
- Stores datasets on his laptop "for convenience" and copies up to /rhome ad hoc
- His advisor signed a data-use agreement but has not walked him through the
  technical handling requirements

**Strengths**:
- Strong technical baseline; he can follow gocryptfs and SSH-key procedures
- Already uses git and version control

**Likely struggles**:
- Default instinct is to email datasets to himself or a collaborator
- Has used `chmod 755` reflexively without realizing it exposes restricted data
- Has not yet internalized that *student names + grades* is a FERPA education
  record, even though either field alone might be classified differently

**What this orientation gives him**:
- A precise mental model: this dataset is RESTRICTED (red, 700 + gocryptfs),
  not PROPRIETARY directory information
- An incident-reporting pathway he can use *without fear* if he or a labmate
  makes a mistake
- A framework for discussions with his advisor about lab data hygiene

**Instructor support**:
- Use his FERPA scenario as a teaching example in Episode 4 (with permission)
- Reinforce that emailing datasets, even to one's self, is a reportable
  incident
- Connect him to Workshop 14 for the full 12-episode classification course

---

## Persona 3: Postdoc Moving from Another Institution

**Profile**: Dr. Aaditya Singh, postdoctoral researcher in Computer Science.
Joined Pomona 60 days ago from a large R1 institution where she ran tens of
thousands of cores and stored data wherever the sysadmins told her to. Familiar
with SLURM, conda, Singularity, and SSH. Unfamiliar with Pomona's policy
environment.

**Background and motivation**:
- Wants to be productive immediately; views training as a hurdle to clear
- Already has an Ed25519 SSH key generated at her previous institution
- Brought a 200 GB dataset from her PhD; some of it may be export-controlled
  but she is not sure
- Is on a J-1 visa, which is relevant for some export-control categories

**Strengths**:
- Technically sophisticated; will follow gocryptfs and best-practice scripts
  without hand-holding
- Reads documentation carefully when she has time

**Likely struggles**:
- Assumes that practices from her previous institution carry over — they may
  not (different filesystems, different quotas, different policies)
- May reuse her old SSH key rather than generating a Pomona-specific one
- Has not thought about export control implications of her PhD dataset
- Unfamiliar with Pomona's incident-reporting flow and may default to "just
  fix it quietly"

**What this orientation gives her**:
- A clear statement that Pomona has a 14+ character password floor (NIST SP
  800-63B) and DUO at https://duo.pomona.edu — no exceptions
- A pathway to ask about export-control classification *before* she runs the
  first job (its-hpc@pomona.edu and the compliance office)
- The phishing/social-engineering tools (SLAM check, hover-before-click,
  out-of-band verification) which apply at any institution

**Instructor support**:
- Encourage her to generate a Pomona-specific SSH key and retire the old one
- Walk through Episode 7 (social engineering) carefully — attackers often
  target newcomers within their first 90 days
- Connect her to Workshop 16 for cluster-specific operational details

---

## Persona 4: Student Researcher (Undergraduate)

**Profile**: Emily Chen, junior physics major, working in Prof. Kim's lab on a
summer research project. First HPC user in her cohort. Has taken one Linux
class. Has never managed her own cluster account before.

**Background and motivation**:
- Curious and eager, but easily overwhelmed by jargon
- Excited about her summer stipend and afraid of "breaking something"
- Has been told vaguely "don't share your password" but does not yet
  internalize *why* the rule exists
- Will be sharing a `/bigdata/lab/kim_lab` directory with five other students

**Strengths**:
- Asks questions readily and takes notes
- Has not yet developed bad habits — she'll learn things the right way the
  first time

**Likely struggles**:
- May confuse the lab shared directory (PROPRIETARY) with her personal
  workspace (also PROPRIETARY by default but with different access)
- Is the most common target of phishing emails in this group — attackers
  know undergraduates often click first and ask later
- May feel that the AUP is too long and skim it

**What this orientation gives her**:
- A simple rule of three (PUBLIC / PROPRIETARY / RESTRICTED) she can use
  without memorizing the regulatory citations
- Confidence that asking its-hpc@pomona.edu is *expected*, not an admission
  of failure
- The phishing examples in Episode 7 — she will see at least one of these in
  her Pomona inbox during the semester

**Instructor support**:
- Use scenario-based teaching (challenges, not pure lecture) where possible
- Reassure her that account suspension follows *unreported* incidents, not
  reported ones
- Pair her in challenges with someone more senior so she can hear how an
  experienced user thinks through a security decision

---

All four learners share the same goal: protecting research, protecting one
another, and meeting Pomona's NIST SP 800-171 obligations. The orientation's
job is to give each of them the same baseline vocabulary and the same
single contact (its-hpc@pomona.edu) for anything they cannot resolve on
their own.
