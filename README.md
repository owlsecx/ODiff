# 🦉 ODiff

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux-0a0c10?style=flat-square"/>
  <img src="https://img.shields.io/badge/Category-OForensics-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-1.0-cyan?style=flat-square"/>
</p>

> **ODiff** — Crypto Diff & Comparison Tool

---

> ⚠️ **AUTHORISED USE ONLY** — Use only on systems you own or have explicit written permission to test. Unauthorised use is illegal.

---

## 📌 Overview

ODiff compares hashes, keys, certificates, binaries, and encoded blobs at byte, bit, and character granularity. It emphasises timing-safe comparison, Hamming distance, entropy, and similarity scoring so crypto and forensics reviews can quantify how two artefacts differ. Structured JSON reports support audit documentation.

---

## ✨ Features

- Compare hashes, keys, certs, binary files, and encoded data side by side
- Byte-, bit-, and character-level difference highlighting
- Timing-safe comparison helpers for secret material checks
- Hamming distance, entropy analysis, and similarity scoring
- Non-interactive --cli mode for two-file comparisons
- JSON report output and optional auto-save for evidence packs

---

## ⚙️ Requirements

- **Linux**
- **No Python installation needed** — runs as a standalone executable

---

## 🚀 Usage

```bash
./ODiff --cli file_a.bin file_b.bin
./ODiff --cli a.pem b.pem --json
./ODiff --cli left.bin right.bin --save --json
./ODiff --help
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
