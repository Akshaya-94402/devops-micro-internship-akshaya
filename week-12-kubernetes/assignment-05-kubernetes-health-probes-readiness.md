# Assignment 5 — Kubernetes Health Probes (Readiness)

Part of the DevOps Micro Internship (DMI) with Agentic AI

---

## Purpose

In this assignment, you will configure and test a Kubernetes readiness probe. You will create a baseline NGINX Deployment, add an HTTP readiness probe, intentionally break it, observe a stalled rollout, and restore the working configuration.

You will also demonstrate how readiness probes protect rolling updates.

---

# Task 0 — Prepare the Lab Environment

## Goal

Confirm that you are connected to your learning cluster and remove the previous assignment’s HPA and NGINX Deployment before starting this lab.

No screenshot or written notes are required for this pre-check.

---

# Task 1 — Set Up Your Lab Directory

## Goal

Create and enter a dedicated directory for the readiness-probe lab.

### Evidence

#### Screenshot 1 — Terminal showing that you are working inside `~/k8s-labs/health-probes-readiness`

Add your screenshot here.

---

### Notes

**1. What is the purpose of a readiness probe?**

Add your answer here.

**2. Why is a Pod being Running not always enough to confirm it can serve traffic?**

Add your answer here.

---

# Task 2 — Create a Baseline Deployment Without Probes

## Goal

Create a baseline NGINX Deployment with two replicas and no readiness probe.

### Evidence

#### Screenshot 2 — Completed `00-nginx-deploy-baseline.yaml` manifest

Add your screenshot here.

---

#### Screenshot 3 — Output showing a successful rollout and two running NGINX Pods

Add your screenshot here.

---

#### Screenshot 4 — Relevant output from `kubectl describe deployment nginx-deployment`

Add your screenshot here.

---

### Notes

**1. How many replicas does this Deployment maintain?**

Add your answer here.

**2. What does `maxUnavailable: 0` mean during a rolling update?**

Add your answer here.

**3. Is a readiness probe configured in this baseline Deployment?**

Add your answer here.

---

# Task 3 — Add a Readiness Probe

## Goal

Add an HTTP readiness probe so Kubernetes checks whether each NGINX container is ready to accept requests.

### Evidence

#### Screenshot 5 — Completed `01-nginx-deploy-readiness.yaml` manifest showing the readiness probe

Add your screenshot here.

---

#### Screenshot 6 — Output of the successful rollout and ready Pods

Add your screenshot here.

---

#### Screenshot 7 — Pod description showing readiness conditions and readiness probe details

Add your screenshot here.

---

### Notes

**1. What path and port does the readiness probe check?**

Add your answer here.

**2. What does `initialDelaySeconds: 2` do?**

Add your answer here.

**3. What does `periodSeconds: 5` do?**

Add your answer here.

**4. What must happen before Kubernetes considers this Pod ready?**

Add your answer here.

---

# Task 4 — Break and Restore Readiness

## Goal

Intentionally fail the readiness probe, observe the NotReady behavior, and then restore the working probe configuration.

### Evidence

#### Screenshot 8 — `02-nginx-readiness-broken.yaml` showing `/does-not-exist`

Add your screenshot here.

---

#### Screenshot 9 — Output showing the rollout timeout or incomplete rollout

Add your screenshot here.

---

#### Screenshot 10 — Pod details showing `Ready: False` or readiness-probe failure events

Add your screenshot here.

---

#### Screenshot 11 — Output showing successful rollout and ready Pods after the fix

Add your screenshot here.

---

### Notes

**1. Why did the readiness probe fail?**

Add your answer here.

**2. What happened to the Pod readiness status?**

Add your answer here.

**3. Why did the rollout fail to complete?**

Add your answer here.

**4. How did you restore the Deployment successfully?**

Add your answer here.

---

# Task 5 — See How Readiness Protects Rolling Updates

## Goal

Observe how readiness prevents a bad new Pod from replacing healthy Pods during a rolling update.

### Evidence

#### Screenshot 12 — Successful update command and rollout status

Add your screenshot here.

---

#### Screenshot 13 — ReplicaSets and Pods after the successful rolling update

Add your screenshot here.

---

#### Screenshot 14 — Completed `04-readiness-broken-patch.yaml`

Add your screenshot here.

---

#### Screenshot 15 — Output showing the expected stalled rollout or timeout

Add your screenshot here.

---

#### Screenshot 16 — Deployment or Pod output showing the effect of the broken readiness probe

Add your screenshot here.

---

#### Screenshot 17 — Successful rollout status after restoring the fixed configuration

Add your screenshot here.

---

### Notes

**1. What happened during the successful rolling update?**

Add your answer here.

**2. Why did Kubernetes create a new ReplicaSet?**

Add your answer here.

**3. Why were the new Pods unable to replace the existing healthy Pods after readiness was broken?**

Add your answer here.

**4. How does `maxUnavailable: 0` protect availability during this rollout?**

Add your answer here.

---

# Task 6 — Share Your Readiness-Probe Learning on LinkedIn

## Goal

Share what you learned about Kubernetes readiness probes and how they protect rolling updates.

### Evidence

#### Screenshot 18 — Published LinkedIn post

Add your screenshot here.

#### Linkedin post link

Add your post link here

---

# Submission Instructions

- Add all required screenshots numbered 1–18.
- Ensure your full name is visible in required screenshots.
- Use clear, readable screenshots showing the relevant manifest or output.
- Include the completed baseline and readiness-probe manifests in your repository.
- Answer all Notes questions for Tasks 1–5 in your own words.
- Include evidence of the intentional readiness failure and successful recovery.
- Do not expose tokens, passwords, kubeconfig files, account IDs, or other sensitive information.

---

# Completion Checklist

- [ ] Learning cluster confirmed and previous assignment resources removed where applicable
- [ ] Readiness-probe lab directory created (Screenshot 1)
- [ ] Baseline Deployment created successfully (Screenshot 2)
- [ ] Two baseline Pods running and successful rollout verified (Screenshot 3)
- [ ] Baseline Deployment details reviewed (Screenshot 4)
- [ ] Readiness probe added successfully (Screenshot 5)
- [ ] Successful readiness rollout verified (Screenshot 6)
- [ ] Pod readiness conditions and probe details inspected (Screenshot 7)
- [ ] Broken readiness configuration created (Screenshot 8)
- [ ] Stalled rollout or timeout observed (Screenshot 9)
- [ ] NotReady status or readiness-probe failure events captured (Screenshot 10)
- [ ] Working readiness configuration restored (Screenshot 11)
- [ ] Successful image update completed (Screenshot 12)
- [ ] ReplicaSets and Pods inspected after the update (Screenshot 13)
- [ ] Broken-readiness patch created (Screenshot 14)
- [ ] Stalled rollout observed after the patch (Screenshot 15)
- [ ] Effect of broken readiness captured (Screenshot 16)
- [ ] Final recovery completed (Screenshot 17)
- [ ] LinkedIn post published (Screenshot 18)
- [ ] Notes for Tasks 1–5 completed
- [ ] Required manifests included
- [ ] All screenshots are clear and readable
- [ ] No sensitive data exposed

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
