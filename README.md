# 🦉 ODiff

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Linux%20%2F%20Windows-informational?style=flat-square&logo=linux&logoColor=white&color=0a0c10"/>
  <img src="https://img.shields.io/badge/Category-OCipher%20%2F%20Forensics%20%26%20Verification-cyan?style=flat-square"/>
  <img src="https://img.shields.io/badge/No%20Dependencies-Stdlib%20Only-green?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-MIT-green?style=flat-square"/>
  <img src="https://img.shields.io/badge/Part%20of-OwlSec%20Toolkit-7b5ea7?style=flat-square"/>
  <img src="https://img.shields.io/badge/Version-1.0-cyan?style=flat-square"/>
</p>

> **ODiff** is a crypto diff and comparison tool — compare hashes, files, keys, and text at byte and bit level with timing-safe comparison, Hamming distance, similarity score, XOR analysis, per-byte heatmap, and JSON diff reports.

---

## 📌 Overview

ODiff compares two cryptographic values side-by-side and highlights every difference — from the overall IDENTICAL/DIFFERENT verdict down to individual differing bits. All five modules accept flexible input formats and output structured reports to `odiff_output/`.

---

## 🖥️ Modules

| # | Module | Description |
|---|--------|-------------|
| **[1] Compare Hashes** | Timing-safe comparison of two hash values — Hamming distance, similarity %, side-by-side hex, per-byte XOR breakdown |
| **[2] Compare Files** | Deep byte-level file comparison — changed byte count, Hamming distance, similarity %, 4-algorithm hash table, first 32 changed bytes |
| **[3] Compare Text / Keys** | Unified diff (colour-coded +/− lines) + char-level diff for short strings ≤ 80 chars — supports files, hex, base64, or plain text |
| **[4] Multi-Hash Compare** | Compute 10 hash algorithms for both inputs and compare every result side-by-side |
| **[5] Deep Byte Analysis** | XOR of A⊕B, non-zero XOR byte count, Hamming distance, byte-diff table, per-byte bit-change heatmap (up to 32 bytes) |

---

## 📥 Input Formats

Every module accepts values in any of these formats:

| Format | Example |
|--------|---------|
| **Text string** | `hello world` |
| **Hex bytes** | `5f4dcc3b5aa765d6...` |
| **Base64** | `WW91ciBzdHJpbmc=` |
| **Binary file** | `/path/to/file.bin` |
| **Text file** | `/path/to/file.txt` |

---

## 📊 Key Metrics

| Metric | Description |
|--------|-------------|
| **Identical** | Timing-safe byte comparison via `hmac.compare_digest` — safe against timing attacks |
| **Hamming distance** | Total count of bits that differ between A and B |
| **Similarity %** | Matching bytes ÷ max length × 100 |
| **XOR (A⊕B)** | Byte-by-byte XOR result — all zeros means values are identical |
| **Byte diff table** | Colour-coded hex table at 16 bytes/row with offset |
| **Bit heatmap** | Per-byte bar showing how many of the 8 bits changed (green = 0, yellow ≤ 2, red > 2) |

---

## 🔗 Multi-Hash Algorithms (Module 4)

Computes 10 algorithms for both inputs simultaneously:

`MD5` · `SHA-1` · `SHA-224` · `SHA-256` · `SHA-384` · `SHA-512` · `SHA3-256` · `SHA3-512` · `BLAKE2b` · `BLAKE2s`

Each pair is shown with a `=` / `≠` indicator per algorithm.

---

## 💡 Use Cases

- Verify two hash outputs match after key export or transfer
- Compare a backup file against the original
- Detect single-bit changes in ciphertext (avalanche effect analysis)
- Audit config file changes between versions
- Validate a key before and after serialisation/deserialisation
- Confirm certificate fingerprints match across environments

---

## 📤 Output

JSON reports saved to `odiff_output/`:

| Module | Filename | Contents |
|--------|----------|----------|
| **Compare Files** | `odiff_files_YYYYMMDD_HHMMSS.json` | File paths, sizes, identical flag, bytes differ, Hamming bits, similarity %, all 4 hashes for each, first 20 diff offsets |
| **Multi-Hash Compare** | `odiff_multihash_YYYYMMDD_HHMMSS.json` | Sizes, identical flag, similarity %, all 10 algorithm results |

---

## ⚙️ Requirements

- **Linux or Windows**
- **No Python installation needed** — runs as a standalone executable
- **No external dependencies** — stdlib only

---

## 🚀 Usage

```bash
./ODiff
```

---

## 📦 Part of OwlSec Toolkit

This tool is part of the **OwlSec** suite — a collection of 300+ security and privacy tools.

🔗 [owlsec.org](https://owlsec.org)

---

## ©️ License

MIT License — © Khaled S. Haddad

*Tools are distributed as pre-built executables. Source code is proprietary.*
