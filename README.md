# turn-Ubuntu-terminal-to-Kali-terminal

Got it 👍
You **must stay on `bash`**, not `zsh` — and you still want the **exact Kali-style two-line prompt with symbols**.

That’s **100% possible in bash**. Kali’s *look* can be recreated even though Kali defaults to zsh now.

Below is the **clean, safe, bash-only solution**.

---

## ✅ What We’ll Achieve (in **bash**)

```
┌──(harish㉿harbor-node1)-[~/Desktop/demo-projects]
└─$ kubectl get pods
```

✔ Two-line prompt
✔ Same Kali symbols (`┌──`, `└─$`)
✔ Command always on **next line**
✔ No zsh, no oh-my-zsh, no powerlevel10k

---

## 🔧 STEP-BY-STEP: Kali Prompt in **bash**

### 1️⃣ Edit bash config

```bash
nano ~/.bashrc
```

---

### 2️⃣ Add THIS at the **bottom** of `.bashrc`

```bash
# ===== Kali-style multiline bash prompt =====
# Colors
GREEN="\[\033[01;32m\]"
BLUE="\[\033[01;34m\]"
CYAN="\[\033[01;36m\]"
RESET="\[\033[00m\]"

# Username & Host
USER_HOST="(${GREEN}\u${RESET}㉿${BLUE}\h${RESET})"

# Working directory
WORK_DIR="${CYAN}[\w]${RESET}"

# Multiline PS1
export PS1="┌──${USER_HOST}-${WORK_DIR}\n└─\$ "
```

---

### 3️⃣ Reload bash

```bash
source ~/.bashrc
```

---

## ✅ FINAL RESULT (bash)

You will now see:

```
┌──(harish㉿harbor-node1)-[~/Desktop/demo-projects/EKS-AWS-Terraform-Module-Project]
└─$ kubectl get nodes
```

This behaves **exactly like Kali**:

* Prompt info on line 1
* Command typing on line 2
* Cursor never overlaps the path

---

## 🔥 OPTIONAL EXTRAS (bash-safe)

### Root-style prompt (`#`)

```bash
└─# 
```

Change:

```bash
└─\$ 
```

to:

```bash
└─# 
```

---

### Shorten path like Kali

Replace `\w` with:

```bash
\W
```

---

### Git branch (bash)

If you want:

```
┌──(harish㉿host)-[~/proj]-(main)
└─$
```

Say **“add git branch in bash”** 👌

---

## ☸ Kubernetes Context (bash)

Yes, bash can show:

```
(⎈ eks-prod/default)
```

in prompt too.

Say **“add kubectl context bash”** and I’ll give the exact function.

---

### ✅ Summary

| Requirement          | Status |
| -------------------- | ------ |
| Bash shell           | ✅      |
| Kali symbols         | ✅      |
| Multiline            | ✅      |
| Commands on new line | ✅      |
| kubectl friendly     | ✅      |

You’re now using a **Kali-grade terminal prompt on Ubuntu bash** 🔥
