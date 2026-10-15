# 🦉 OJupyterX

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-OWeb-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-1.0.0-cyan?style=flat-square"/>
</p>

> **OJupyterX** — Jupyter Notebook / Lab / Hub Config Auditor

---

> ⚠️ **AUTHORISED USE ONLY** — Use only on systems you own or have explicit written permission to test. Unauthorised use is illegal.

---

## 📌 Overview

Jupyter Notebook / JupyterLab / JupyterHub configuration hardening auditor

---

## ✨ Features

- Safe reader — Python configs parsed with ast (NEVER executed), JSON configs, systemd ExecStart flags
- Server — auth disabled, sha1 / plaintext passwords, allow_root, 0.0.0.0 without TLS, CORS *, XSRF, CSP
- Hub — Dummy / PAM / open signup, admin_access, inline secrets, Spawner --allow-root, limits, internal_ssl
- Runtime dir — token / kernel connection file perms
- Secrets masked; CWE + ATT&CK; TXT/MD/JSON/CSV/SARIF
- Self-test --demo, CI gates --fail-on / --min-severity

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./OJupyterX
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
