# 🦉 OJupyterX

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-OWeb-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-Proprietary-orange?style=flat-square"/>
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

This tool is part of the **OwlSec** suite — a collection of 275+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

Proprietary — © 2026 Owlsec LLC. All rights reserved.

*Tools are distributed as pre-built executables. Source code is proprietary.*

---

## 🔍 Verification & Transparency

This tool is closed-source. These files let you see exactly what is inside it,
without the source:

- [`SBOM.cdx.json`](SBOM.cdx.json) — CycloneDX inventory: SHA-256 of this
  binary, bundled CPython version, and every bundled library with its exact
  version and license. Feed it to Grype, Trivy or Dependency-Track to audit
  our dependencies for CVEs yourself.
- [`THIRD-PARTY-NOTICES.md`](THIRD-PARTY-NOTICES.md) — the full license text
  of every third-party component, extracted from this binary.

**No telemetry, no analytics, no licence check-in.** This tool does not phone
home. Verify that claim yourself:

```bash
sudo strace -f -e trace=network ./OJupyterX --help   # watch every network call
firejail --net=none ./OJupyterX --help               # deny the network entirely
```

Release signing, GPL compliance and vulnerability reporting:
[**TRUST.md**](https://github.com/owlsecx/owl-os/blob/main/TRUST.md)
