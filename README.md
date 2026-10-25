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

OJupyterX is an offline, read-only auditor for Jupyter Notebook, JupyterLab, and JupyterHub configuration. It parses Python configs with `ast` (never executing them), JSON configs, and systemd ExecStart flags to surface authentication, TLS, CORS/XSRF, spawner, and runtime-permission issues. Findings map to CWE and MITRE ATT&CK and can be exported as TXT, Markdown, JSON, CSV, or SARIF for CI use.

---

## ✨ Features

- Safe config reading via `ast` for Python files, plus JSON and systemd unit ExecStart flag analysis
- Jupyter Server checks for disabled auth, weak/plaintext passwords, `allow_root`, bind-all without TLS, CORS `*`, XSRF, and CSP
- JupyterHub checks for Dummy/PAM/open signup, `admin_access`, inline secrets, Spawner `--allow-root`, resource limits, and `internal_ssl`
- Runtime directory permission review for token and kernel connection files
- Secret masking by default; rule catalogue with `--list-rules` / `--explain`
- Self-test `--demo` and CI gates via `--fail-on` / `--min-severity`; multi-format report export

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./OJupyterX --scan
./OJupyterX --server jupyter_server_config.py --hub jupyterhub_config.py -f json -o report.json
./OJupyterX --demo --fail-on high
./OJupyterX --help
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
