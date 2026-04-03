# TryHackMe - Practical Example of OS Security

## Room Overview
**Task 3: Practical Example of OS Security**  
A beginner-friendly lab focused on gaining unauthorized access to a Linux system using basic enumeration and password guessing via SSH.

---

## Objective
- SSH into a target machine using discovered credentials
- Enumerate files and users on the system
- Attempt privilege escalation by guessing passwords for other users

---

## Commands Used

| Command | Description |
|--------|-------------|
| `whoami` | Displays the current logged-in user |
| `ssh USERNAME@MACHINE_IP` | Connect to remote machine via SSH |
| `ls` | List files in the current directory |
| `cat FILENAME` | Display contents of a file |
| `history` | Show previously executed commands |
| `su - USERNAME` | Switch to another user account |

---

## Attack Walkthrough

### Step 1: SSH into Target
A sticky note on a client's screen revealed credentials:
- **Username:** `sammie`
- **Password:** `dragon`
```bash
ssh sammie@MACHINE_IP
# Accept the ECDSA fingerprint warning (type: yes)
# Enter password: dragon (invisible while typing)
```

### Step 2: Enumerate the System
```bash
whoami        # confirms: sammie
ls            # files: country.txt, draft.md, icon.png, password.txt, profile.jpg
cat draft.md  # content about OS Security
history       # review past commands
```

### Step 3: Lateral Movement
Two other users discovered: `johnny` and `linda`

**From outside (not logged in as sammie):**
```bash
ssh johnny@MACHINE_IP
```

**From inside (logged in as sammie):**
```bash
su - johnny
```
Manually try common passwords to gain access.

---

## Key Takeaways
- Credentials left on sticky notes are a major physical security risk
- Reusing passwords across services increases exposure if one is compromised
- `root` (Linux/Mac) and `administrator` (Windows) have unrestricted system access
- SSH hides password input — this is normal behavior, keep typing

---

## Tools Used
- TryHackMe AttackBox
- Linux Terminal (SSH, basic commands)

---

## Platform
[TryHackMe](https://tryhackme.com) — *Beginner OS Security Room*
