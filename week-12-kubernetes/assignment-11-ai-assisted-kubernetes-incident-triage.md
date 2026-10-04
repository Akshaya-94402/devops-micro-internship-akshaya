# Assignment 11 — AI-Assisted Kubernetes Incident Triage

Part of the DevOps Micro Internship (DMI) with Agentic AI

---

## Purpose

Configure a read-only Bash triage script for your Book Review App, connect it to Claude Code through `/k8s-triage`, simulate one controlled failure, recover the application manually, and verify recovery.

**Workflow: Gather → Analyze → Human Act → Verify**

---

## Submission Details

**Full Name:** Add your full name here.

**Kubernetes Platform:** Add your platform here.

**Selected Workload:** Add the Deployment name here.

**Namespace:** Add the namespace here.

**GitHub Repository URL:** Add your project repository URL here.

**Simulated Incident:** Invalid image or broken readiness probe.

**Baseline Status:** HEALTHY or explained WARN.

**Recovery Status:** HEALTHY or explained WARN, with no FAIL.

---

# Task 1 — Discover the Application and Capture a Healthy Baseline

## Goal

Identify the actual application configuration and prove that the selected workload is healthy before incident simulation.

### Evidence

#### Screenshot 1 — Healthy Pods and ready Service backends

Add your screenshot here.

---

#### Screenshot 2 — Workspace directory structure

Add your screenshot here.

### Notes

**1. What proves the selected Pods are ready, not merely running?**

Add your answer here.

**2. What proves the Service has ready backends?**

Add your answer here.

**3. Why must the original image be recorded before incident simulation?**

Add your answer here.

---

# Task 2 — Configure CLAUDE.md

## Goal

Define the project configuration, incident workflow, and safety boundary for Claude Code.

### Evidence

#### Screenshot 3 — CLAUDE.md showing application configuration, workflow, safety rules, and output rules

Add your screenshot here.

### Notes

**1. Why does Claude need project-specific cluster rules?**

Add your answer here.

**2. Why must a human execute recovery commands?**

Add your answer here.

**3. Which rule prevents an unsupported diagnosis?**

Add your answer here.

---

# Task 3 — Plan the Read-Only Triage Workflow

## Goal

Ask Claude Code to explain the five health checks before running the supplied script.

### Evidence

#### Screenshot 4 — Claude Code showing the five-check read-only plan

Add your screenshot here.

### Notes

**1. Which part represents the Gather phase?**

Add your answer here.

**2. How did you verify that Claude did not change anything?**

Add your answer here.

**3. Why is planning before coding useful for incident triage?**

Add your answer here.

---

# Task 4 — Configure and Validate the Bash Script

## Goal

Configure the supplied triage script for the selected workload and validate its syntax.

### Evidence

#### Screenshot 5 — Script configuration variables and checks array

Add your screenshot here.

---

#### Screenshot 6 — Functions for status, readiness, restarts, events, and Service backends

Add your screenshot here.

---

#### Screenshot 7 — Preflight, summary, and exit-code logic

Add your screenshot here.

---

#### Screenshot 8 — Successful syntax validation and executable permission

Add your screenshot here.

### Notes

**1. Why must the script fail when no Pods match the configured selector?**

Add your answer here.

**2. How does the readiness check detect a running but unready Pod?**

Add your answer here.

**3. Why are Service backends checked separately from Pod health?**

Add your answer here.

**4. What do exit codes 0, 1, and 2 represent?**

Add your answer here.

---

# Task 5 — Run the Healthy Baseline Report

## Goal

Run the script on the healthy application and confirm that it contains no failed checks.

### Evidence

#### Screenshot 9 — Baseline report showing your full name and all checks

Add your screenshot here.

---

#### Screenshot 10 — Captured exit code and final summary

Add your screenshot here.

### Notes

**1. What is the baseline status?**

Add your answer here.

**2. Which evidence proves the Service has a ready backend?**

Add your answer here.

**3. What is the difference between a warning and a failure?**

Add your answer here.

---

# Task 6 — Configure and Run the Claude Code Skill

## Goal

Connect the Bash script to a manually invoked Claude Code evidence-analysis workflow.

### Evidence

#### Screenshot 11 — SKILL.md showing frontmatter and safety rules

Add your screenshot here.

---

#### Screenshot 12 — Baseline `/k8s-triage` analysis

Add your screenshot here.

### Notes

**1. What does Bash do in this workflow?**

Add your answer here.

**2. What does Claude do in this workflow?**

Add your answer here.

**3. Why are instructions alone insufficient to guarantee read-only access?**

Add your answer here.

---

# Task 7 — Simulate One Controlled Incident

## Goal

Create one controlled failure, save its evidence, and let Claude analyze it without executing recovery.

### Evidence

#### Screenshot 13 — Failed or unready Pod evidence and current Service backends

Add your screenshot here.

---

#### Screenshot 14 — Failed `/k8s-triage` analysis with evidence and a suggested manual recovery command

Add your screenshot here.

---

#### Screenshot 15 — Saved `incident-failure-report.txt`

Add your screenshot here.

### Notes

**1. Which failure did you choose?**

Add your answer here.

**2. Which checks failed, and what evidence proved it?**

Add your answer here.

**3. Did Claude execute recovery? Why is that important?**

Add your answer here.

**4. Why might the Service retain ready backends during the incident?**

Add your answer here.

---

# Task 8 — Recover Manually and Verify

## Goal

Restore the healthy configuration yourself and verify recovery using a second triage report.

### Evidence

#### Screenshot 16 — Recovered Pods and ready Service backends

Add your screenshot here.

---

#### Screenshot 17 — Recovered `/k8s-triage` analysis

Add your screenshot here.

---

#### Screenshot 18 — Reports directory showing failure and recovery reports

Add your screenshot here.

---

#### Screenshot 19 — `incident-summary.md` with all required sections

Add your screenshot here.

### Notes

**1. What manual recovery action did you execute?**

Add your answer here.

**2. What proves the workload recovered?**

Add your answer here.

**3. Why is the second triage run necessary?**

Add your answer here.

**4. Why should AI not automatically restart every failing production workload?**

Add your answer here.

### Remaining WARN Results

Explain any WARN results remaining after recovery, or write “None.”

Add your explanation here.

---

# Task 9 — Publish Your Kubernetes Incident-Triage Workflow on LinkedIn

## Goal

Share the incident-triage workflow you completed and explain the role of human control.

### Evidence

#### Screenshot 20 — Published LinkedIn post about your Kubernetes incident-triage workflow

Add your screenshot here.

### LinkedIn Post URL

Add your published LinkedIn post URL here.

---

# Required Project Files

Include these files in your project repository:

- `CLAUDE.md`
- `lab-config.md`
- `scripts/k8s-triage.sh`
- `.claude/skills/k8s-triage/SKILL.md`
- `reports/incident-failure-report.txt`
- `reports/recovery-report.txt`
- `incident-summary.md`

Your `incident-summary.md` must contain:

1. Reported Symptom
2. Evidence Collected
3. Most Likely Cause
4. Human-Approved Recovery Action
5. Verification
6. Safety Decision
7. Agentic Loop Mapping

---

# Final Summary

## Evidence and Cause

Summarize the evidence and the supported cause of the incident.

Add your summary here.

## Manual Recovery

Describe the command or configuration change you performed.

Add your summary here.

## Verification

Explain how the recovery report and Kubernetes outputs confirmed recovery.

Add your summary here.

## Safety Decision

Explain how you kept Claude’s role limited to evidence gathering and analysis.

Add your summary here.

---

# Submission Instructions

- Include all 20 required screenshots under their corresponding Evidence sections.
- Complete all Notes questions in your own words.
- Include the required project files in your linked repository.
- Include your published LinkedIn post URL.
- Use clear, readable screenshots showing relevant commands, configuration, and outputs.
- Display your full name before taking required terminal screenshots.
- Preserve the failure report before recovery.
- Ensure the baseline and recovery reports contain no FAIL results.
- Explain any WARN results remaining after recovery.
- Review reports, logs, configuration records, and screenshots before publishing.
- Do not expose credentials, kubeconfig contents, tokens, certificates, JWT secrets, or confidential account information.

---

# Completion Checklist

- [ ] Confirmed the personal lab context
- [ ] Discovered and recorded application configuration
- [ ] Recorded the original working image
- [ ] Captured healthy Pods and ready Service backends (Screenshot 1)
- [ ] Created the workspace (Screenshot 2)
- [ ] Configured CLAUDE.md (Screenshot 3)
- [ ] Reviewed the five-check triage plan (Screenshot 4)
- [ ] Configured and reviewed the supplied script (Screenshots 5–7)
- [ ] Passed Bash syntax validation and set executable permission (Screenshot 8)
- [ ] Captured a baseline report with no FAIL (Screenshot 9)
- [ ] Captured the correct exit code (Screenshot 10)
- [ ] Configured and invoked `/k8s-triage` (Screenshots 11–12)
- [ ] Simulated one controlled incident manually (Screenshot 13)
- [ ] Reviewed Claude’s failed-state analysis (Screenshot 14)
- [ ] Saved failure evidence before recovery (Screenshot 15)
- [ ] Executed recovery manually and waited for rollout completion
- [ ] Confirmed recovered Pods and ready Service backends (Screenshot 16)
- [ ] Captured recovery analysis with no FAIL (Screenshot 17)
- [ ] Explained any remaining warnings
- [ ] Saved failure and recovery reports (Screenshot 18)
- [ ] Completed the seven-section incident summary (Screenshot 19)
- [ ] Answered all Notes questions
- [ ] Published the LinkedIn post (Screenshot 20)
- [ ] Included the LinkedIn post URL
- [ ] Included all required project files
- [ ] Checked that no sensitive information is exposed

---

## 📌 About DMI & CloudAdvisory

DevOps Micro Internship (DMI) is a project-based DevOps program run by Pravin Mishra (The CloudAdvisory) focused on real-world execution, systems thinking, and career readiness.

It helps learners build strong DevOps foundations with hands-on experience.

---

## 📌 Resources

- 🌐 DMI Official Website: https://dmi.pravinmishra.com?utm_source=github&utm_medium=readme  
- 🎓 University: https://university.pravinmishra.com?utm_source=github&utm_medium=readme  
- 💬 Discord Community: https://discord.pravinmishra.com?utm_source=github&utm_medium=readme  
- 📝 Blog: https://dmi.pravinmishra.com/blog?utm_source=github&utm_medium=readme  
- ▶️ YouTube Playlist: https://www.youtube.com/playlist?list=PLFeSNDtI4Cho  
- 🔗 Pravin Mishra (LinkedIn): https://www.linkedin.com/in/pravin-mishra-aws-trainer/  
- 🏢 CloudAdvisory (LinkedIn): https://www.linkedin.com/company/thecloudadvisory/

---

*This submission is part of DevOps Micro Internship (DMI) — Agentic AI Track.*
