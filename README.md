<div align="center">
<img src="https://img.shields.io/badge/📋_Incident_Report_Generator-Local_LLM_Powered-blue?style=for-the-badge&labelColor=1a1a2e&color=16213e" alt="Project Banner" width="600"/>
<br/>
<img src="https://img.shields.io/badge/Gemma_4-Ollama-orange?style=flat-square&logo=google&logoColor=white" alt="Gemma 4"/>
<img src="https://img.shields.io/badge/Python-3.9+-blue?style=flat-square&logo=python&logoColor=white" alt="Python"/>
<img src="https://img.shields.io/badge/Streamlit-Web_UI-red?style=flat-square&logo=streamlit&logoColor=white" alt="Streamlit"/>
<img src="https://img.shields.io/badge/Click-CLI-green?style=flat-square&logo=gnu-bash&logoColor=white" alt="Click CLI"/>
<img src="https://img.shields.io/badge/License-MIT-yellow?style=flat-square" alt="License"/>
<br/><br/>
<strong>Part of <a href="https://github.com/kennedyraju55/90-local-llm-projects">90 Local LLM Projects</a> collection</strong>
</div>
<br/>
# 📋 Incident Report Generator

[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/downloads/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)
[![Powered by Ollama](https://img.shields.io/badge/LLM-Ollama-orange.svg)](https://ollama.ai)
[![Tests](https://img.shields.io/badge/tests-passing-brightgreen.svg)]()

> **Generate professional, template-driven incident reports from raw logs — with timeline building, impact calculators, and lessons learned analysis. All powered by a local LLM.**

---

## ✨ Features

| Feature | Description | LLM Required |
|---------|-------------|:---:|
| 📄 **Report Generation** | Full incident reports with executive summary, RCA, and remediation | ✅ |
| ⏱️ **Timeline Builder** | Parse logs into structured chronological timelines | ❌ |
| 📊 **Impact Calculator** | Severity scoring based on users, systems, data, downtime | ❌ |
| 📚 **Lessons Learned** | AI-generated post-mortem with action items | ✅ |
| 🏷️ **Template Library** | P1–P4 priority templates with SLA-aware sections | ❌ |
| 🖥️ **Streamlit Web UI** | Interactive incident form, timeline, and impact dashboard | — |
| 💻 **Rich CLI** | Beautiful terminal output with tables and panels | — |

## 🏗️ Architecture

```
72-incident-report-generator/
├── src/incident_reporter/
│   ├── __init__.py          # Package metadata
│   ├── core.py              # Business logic: templates, timeline, impact calc
│   ├── cli.py               # Click CLI with Rich output
│   ├── web_ui.py            # Streamlit dashboard (4 tabs)
│   └── config.py            # YAML config management
├── tests/
│   ├── test_core.py         # Core logic tests
│   └── test_cli.py          # CLI integration tests
├── config.yaml              # Configuration file
├── .env.example             # Environment variables template
├── setup.py                 # Package installation
├── Makefile                 # Development commands
├── requirements.txt         # Dependencies
└── README.md
```

### Priority Templates

| Priority | Label | Response SLA | Update Frequency | Escalation |
|----------|-------|-------------|------------------|------------|
| **P1** | Critical / SEV-1 | 15 minutes | Every 30 min | VP + CISO |
| **P2** | High / SEV-2 | 30 minutes | Every 1 hour | Eng Manager |
| **P3** | Medium / SEV-3 | 2 hours | Every 4 hours | Team Lead |
| **P4** | Low / SEV-4 | Next business day | Daily | Ticket queue |

## 🚀 Quick Start

### Installation

```bash
cd 72-incident-report-generator
pip install -r requirements.txt
cp .env.example .env
```

### CLI Usage

```bash
# Generate full incident report
python -m src.incident_reporter.cli --logs incident.log --type security --priority P1

# Generate timeline only
python -m src.incident_reporter.cli --logs incident.log --timeline-only

# Calculate impact (no LLM needed)
python -m src.incident_reporter.cli --logs incident.log --impact --affected-users 5000 --downtime 120

# Generate lessons learned
python -m src.incident_reporter.cli --logs incident.log --type security --lessons

# Save report to file
python -m src.incident_reporter.cli --logs incident.log --output report.md
```

### 🖥️ Web UI

```bash
streamlit run src/incident_reporter/web_ui.py
```

| Tab | Description |
|-----|-------------|
| 📝 **Incident Form** | Enter logs, set priority, generate reports |
| ⏱️ **Timeline** | Visual chronological event timeline |
| 📄 **Generated Report** | Full report with download button |
| 📊 **Impact Assessment** | Severity score, affected systems, revenue impact |

## 🧪 Testing

```bash
python -m pytest tests/ -v
python -m pytest tests/ -v --cov=src/incident_reporter --cov-report=term-missing
```

## ⚙️ Configuration

```yaml
model:
  name: "llama3"
  temperature: 0.3
report:
  default_priority: "P2"
  default_type: "security"
  include_appendix: true
```

## 📦 Makefile Commands

| Command | Description |
|---------|-------------|
| `make install` | Install dependencies |
| `make test` | Run tests |
| `make run ARGS="--help"` | Run CLI |
| `make web` | Launch Streamlit UI |
| `make clean` | Clean artifacts |

---

## 📸 Screenshots

> _Screenshots coming soon! Run the app and see it in action._

<!-- Add your screenshots here -->
<!-- ![Screenshot 1](docs/images/screenshot1.png) -->
<!-- ![Screenshot 2](docs/images/screenshot2.png) -->