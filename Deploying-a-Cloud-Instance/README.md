# ☁️ TryHackMe — Deploying a Cloud Instance


---

## 📌 Overview

This repository documents my hands-on lab from TryHackMe focused on deploying and managing cloud infrastructure using a simulated AWS-like console. The goal of the exercise was to understand how cloud resources are created, managed, and billed — core skills for anyone working in cybersecurity or cloud environments.

> **Platform:** TryHackMe  
> **Task:** Deploying a Cloud Instance  
> **Completion:** 100% ✅
![Billing Analysis](screenshots/billing-analysis.png)
---

## 🧠 Concepts Learned

### What is EC2?
EC2 (Elastic Compute Cloud) represents a **virtual computer in the cloud**. Just like a physical computer, it has a CPU and RAM, and can run applications. Adding an EC2 instance means adding a virtual server to your environment.

### Instance Types
Instance types determine how powerful a virtual machine is:

| Instance Type | Power Level | Cost |
|---------------|-------------|------|
| `t3.micro` | Low | Low (~10 credits/month) |
| `m5.large` | High | High (~70 credits/month) |
| `t3a.small` | Medium | Medium (~38 credits/month) |

> **Rule of thumb:** Bigger instance = more CPU/RAM = higher cost. Choose based on your workload needs.

### Regions
A **region** is a geographical location where your cloud resources physically live (e.g., `us-east-1` = N. Virginia, USA). Choosing the right region can affect latency, compliance, and pricing.

### IaaS (Infrastructure as a Service)
This lab demonstrated the **IaaS model** — where you get full access to the underlying operating system. This is particularly useful in cybersecurity because it lets you:
- Install custom tools
- Configure system settings directly
- Safely simulate attacks and defenses

---

## 🛠️ What I Built

Three virtual machines (EC2 instances) were deployed to host a cybersecurity training application:

| Instance Name | Type | Purpose | Monthly Cost |
|---------------|------|---------|-------------|
| `application-interface` | t3.micro | App front-end | 10 credits |
| `study-machine-1` | m5.large | Cybersecurity practice lab | 70 credits |
| `study-machine-2` | m5.large | Cybersecurity practice lab | 70 credits |

> **Note:** The lab environment already had `web-1` and `db-1` (both t3.micro) pre-deployed, bringing the total to **5 instances**.

---

## 💰 Billing Analysis

One of the most important parts of cloud management is **cost optimization**. Here's how the billing changed based on instance states:

### All 5 Instances Running
| Name | Type | Status | Monthly Cost |
|------|------|--------|-------------|
| web-1 | t3.micro | running | 10.0 |
| db-1 | t3.micro | running | 10.0 |
| application-interface | t3.micro | running | 10.0 |
| study-machine-1 | m5.large | running | 70.0 |
| study-machine-2 | m5.large | running | 70.0 |
| | | **Total** | **170.0 credits/month** |

### After Stopping the Study Machines
| Name | Type | Status | Monthly Cost |
|------|------|--------|-------------|
| web-1 | t3.micro | running | 10.0 |
| db-1 | t3.micro | running | 10.0 |
| application-interface | t3.micro | running | 10.0 |
| study-machine-1 | m5.large | **stopped** | **0.0** |
| study-machine-2 | m5.large | **stopped** | **0.0** |
| | | **Total** | **30.0 credits/month** |

**💡 Cost reduced from 170 → 30 credits/month just by stopping unused VMs!**

---

## ❓ Lab Questions & Answers

| Question | Answer |
|----------|--------|
| Total cost if study-machine-1 and study-machine-2 are stopped? | **30 credits/month** |
| How many credits does an `m5.large` instance cost per month? | **70 credits/month** |
| Total cost if only the new instances we created are running? | **150 credits/month** |
| Total running cost if a third `t3a.small` study machine is added? | **188 credits/month** |

---

## 🔑 Key Takeaways

- **Stopped VMs don't cost anything** — only *running* instances add to your bill.
- **Cloud costs are highly flexible** — you can scale up and down in minutes.
- **IaaS gives full OS control** — ideal for cybersecurity training environments.
- **Region selection matters** — always verify your region before launching resources.
- **Right-sizing instances** is critical — don't pay for compute power you don't need.

---

## 🗺️ Skills Demonstrated

- Cloud console navigation (AWS EC2-style interface)
- Virtual machine deployment and configuration
- Instance type selection and cost analysis
- Cloud billing management and cost optimization
- Understanding IaaS architecture in a real-world context

---

*Completed as part of the TryHackMe Cloud Computing learning path. Screenshots from the lab are included in the `/screenshots` folder.*
