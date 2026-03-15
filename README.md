# 🔐 Applied Cryptography – SSH Key Authentication 

##  Overview

This repository demonstrates how **SSH key-based authentication** works using asymmetric cryptography.
Instead of using passwords, SSH authentication relies on a **public–private key pair** to securely verify a user's identity.

This lab shows how SSH keys are generated, added to GitHub, and used to securely clone and push code to a repository.

---

# Cryptography Concept

SSH uses **public-key cryptography**.

Two keys are generated:

| Key             | Description                            |
| --------------- | -------------------------------------- |
| **Private Key** | Stored securely on the user's machine  |
| **Public Key**  | Uploaded to the remote server (GitHub) |

# Authentication process:
Client (Local Machine)
        │
        │ Sign authentication challenge
        ▼
Private Key
        │
        │ Signature
        ▼
GitHub Server
        │
        │ Verify signature
        ▼
Public Key (stored on GitHub)
        │
        ▼
Access Granted
```

The private key **never leaves the client machine**, which makes SSH authentication highly secure.

---

---------------------------------**Lab Steps-**----------------------------------------

## Generate SSH Key Pair

SSH keys were generated using:

```bash
ssh-keygen -t rsa -C "info.abhaypatel98@gmail.com"
```

Output files:

```
onlyPrivat      → Private key
onlyPrivat.pub  → Public key
```

---

## Add Public Key to GitHub

The public key was added to GitHub:

```
GitHub → Settings → SSH and GPG Keys → New SSH Key
```

GitHub stores the public key and uses it to verify authentication requests.

---

## Test SSH Authentication

The SSH connection was verified using:

```bash
ssh -T git@github.com
```

Successful output:

```
Hi AbhayPatel98! You've successfully authenticated.
```

---

## Clone Repository Using SSH

The repository was cloned securely using SSH:

```bash
git clone git@github.com:AbhayPatel98/applied-crypto-lab-SSH.git
```

---

## Add and Commit Files

```bash
git add README.md
git commit -m "First commit - SSH Key"
```

---

## Push Changes to GitHub

```bash
git push origin main
```

This pushed the local changes to the remote GitHub repository.

---

# Security Advantages of SSH Keys

| SSH Key Authentication                | Password Authentication    |
| ------------------------------------- | -------------------------- |
| Uses strong cryptography              | Vulnerable to brute force  |
| Private key never transmitted         | Password sent during login |
| Resistant to phishing                 | Can be stolen              |
| Widely used in DevOps & cloud systems | Less secure                |

---

# Real-World Applications

SSH key authentication is widely used in:

* Linux server access
* Cloud infrastructure (AWS, Azure, GCP)
* DevOps pipelines
* GitHub repository access
* Secure remote administration

---

# Repository Structure

```
applied-crypto-lab-SSH
│
├── README.md
```

---

# Author

**Abhay Patel**
MSc Cyber Security
Edinburgh Napier University

## Specialisation:

* Blockchain Security
* Smart Contract Auditing
* Applied Cryptography
