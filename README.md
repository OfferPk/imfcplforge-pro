# IMFCPLForge Pro (v1.0.0)

> **SMPTE ST 2067-2 / ST 2067-3 Interoperable Master Format (IMF) Composition Playlist Studio & Package Validator CLI**

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](http://LICENSE) [![SMPTE](https://img.shields.io/badge/Standard-SMPTE%20ST%202067--2%20%2F%202067--3-orange.svg)](https://www.smpte.org) [![Python](https://img.shields.io/badge/Python-3.8%2B-brightgreen.svg)](https://www.python.org/) ![Platform](https://img.shields.io/badge/Platform-Web%20%7C%20CLI%20%7C%20Docker-purple.svg)

---

## 📽 Overview

**IMFCPLForge Pro** is an autonomous engineering workstation designed for broadcast post-production engineers, mastering technicians, and streaming localization facilities. It bridges the gap between complex SMPTE standards and real-world delivery pipelines by providing:

1. **Virtual Track Timeline Studio**: Visual multi-track timeline displaying Main Image, Multi-language Audio essences, Timed Text subtitles, and Content Markers with sub-frame precision.  
2. **Deterministic CPL / PKL / ASSETMAP XML Generator**: Produces standard-compliant SMPTE ST 2067-3 XML documents, Packing Lists, and Asset Map manifests with proper namespace declarations (`http://www.smpte-ra.org/schemas/2067-3/2013`).  
3. **10-Point Normative Auditor**: Instant validation engine checking UUID RFC 4122 compliance, rational edit rates, track duration alignment, segment boundary integrity, and XML structure.  
4. **Standalone Python CLI (`imf-cpl-cli.py`)**: Scriptable command-line utility for automated CI/CD and cloud ingest pipelines.

---

## 🚀 Key Features

- **Multi-Track Virtual Assembly**: Support for Main Image (`MainImageSequence`), Multi-channel Audio (`MainAudioSequence`), Timed Text (`SubSequence`), and Ancillary Data.  
- **Strict Frame Alignment**: Enforces SMPTE ST 2067-2 Rule: All virtual tracks inside an IMF segment must share identical duration.  
- **Non-Drop / Rational Edit Rates**: Full calculation support for `24/1` (Film), `25/1` (PAL/Europe), `30/1`, and `24000/1001` (23.976 fps NTSC).  
- **Package Manifest Generation**: Generates matching `PKL.xml` (SMPTE ST 2067-2 Packing List) and `ASSETMAP.xml` linking all MXF track files.  
- **Zero Heavy Dependencies**: Pure standard library Python 3 CLI and zero-dependency modern HTML5/ES6 web studio.

---

## 🛠 Quick Start

### 1\. Interactive Web Studio

Open `source-code/index.html` directly in any modern web browser:

- Adjust Timeline frame rate, duration, and track properties.  
- Click **"Generate SMPTE CPL XML"** to preview and copy production-ready XML.  
- Run **"Audit CPL Compliance"** to execute the 10-point normative verification.

### 2\. Standalone Python CLI

\# Display CLI help

python3 build/imf-cpl-cli.py \--help

\# Create a sample CPL file

python3 build/imf-cpl-cli.py create sample\_cpl.xml \--title "WAR\_AND\_PEACE\_EP01" \--fps 24 \--duration 72000

\# Audit an existing CPL file

python3 build/imf-cpl-cli.py audit sample\_cpl.xml

\# Generate matching PKL and ASSETMAP manifests

python3 build/imf-cpl-cli.py manifest sample\_cpl.xml \--out-dir ./package\_manifests/

### 3\. Run Automated Test Suite

python3 test\_imf\_cpl.py

---

## 📁 Repository Structure

product\_274/

├── README.md                          \# Main project overview & user guide

├── test\_imf\_cpl.py                    \# 10-point automated unit test suite

├── source-code/

│   ├── index.html                     \# Interactive multi-tab IMF Studio UI

│   ├── imf.css                        \# Post-production dark theme stylesheet

│   ├── imf-engine.js                  \# CPL, PKL, ASSETMAP XML synthesis engine

│   ├── imf-auditor.js                 \# 10-point normative compliance rules

│   └── app.js                         \# Application event controller & UI glue

├── build/

│   ├── imf-cpl-cli.py                 \# Standalone executable CLI utility

│   └── imfcplforge-pro-v1.0.0.zip      \# Complete production release package

├── documentation/

│   ├── ARCHITECTURE.md                \# SMPTE ST 2067 specification deep-dive

│   ├── USER\_GUIDE.md                  \# Comprehensive operational manual

│   └── MONETIZATION\_AND\_MARKETING\_PLAYBOOK.md \# Commercial strategy & pricing tiers

└── screenshots/

    └── imf-studio-preview.svg         \# High-resolution vector preview of GUI

---

## 📄 License

Released under the MIT License. Copyright © 2026 Autonomous Digital Product Factory.