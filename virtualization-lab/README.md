# 🖥️ Managing Virtual Machines — Virtualization Lab

A completed lab simulating real-world virtualization management tasks using **Virtualization Manager**.

## 🎯 Objectives
- Diagnose and resolve a VM failure causing a company-wide email outage
- Provision a new VM for a business team
- Analyze physical host health and identify capacity risks

## 🔍 Task 1 — Incident Response: Email Outage
Investigated why all employees stopped receiving emails. Found the `Mail-SERVER` VM in an **Error** state. Restarted it via the dashboard, restoring email service.

## 🚀 Task 2 — Provisioning a New VM
Created `Marketing-VM` with: CPU 4 cores, Memory 8 GB, Disk 100 GB.

## 📊 Task 3 — Host Health Monitoring
- `HV-PROD-01` — CPU 45%, Storage 72%, Memory 68% → Capacity available
- `HV-PROD-02` — CPU 98%, Storage 95%, Memory 90% → Near full capacity ⚠️
- `HV-BACKUP-01` — Disconnected, 0 VMs → Server not running

## 💡 Key Learnings
- VM error states can silently break dependent services
- Proactive host monitoring prevents outages
- Virtualization enables fast resource provisioning
- Disconnected backup hosts are a risk worth investigating
