# 📋 Incident Report Generator

Generate comprehensive incident reports automatically with AI analysis.

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://python.org)
[![Ollama](https://img.shields.io/badge/Ollama-Compatible-green.svg)](https://ollama.com)
[![Gemma 3](https://img.shields.io/badge/Gemma-3-orange.svg)](https://ollama.com)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Privacy First](https://img.shields.io/badge/Privacy-First-red.svg)](#why-local)

## What It Does

- **Auto-generates incident reports** from logs and metrics
- **Root cause analysis** powered by Gemma 3 intelligence
- **Timeline reconstruction** from unstructured incident data
- **Recommendations and remediation steps** for future prevention

## Tech Stack

- **Python 3.8+** — Report generation engine
- **Gemma 3** (via Ollama) — Incident analysis and synthesis
- **Jinja2** — Report template rendering
- **Markdown/PDF export** — Multiple output formats

## Quick Start

`ash
# Clone the repository
git clone https://github.com/kennedyraju55/incident-report-generator.git
cd incident-report-generator

# Install dependencies
pip install -r requirements.txt

# Pull Gemma 3 model locally
ollama pull gemma3:4b

# Generate an incident report
python generator.py --logs incident.log --metrics metrics.json
`

## Architecture

`
incident logs + metrics
    ↓
[Gemma 3 LLM Analysis] ← offline, local
    ↓
timeline + root cause + recommendations
    ↓
Markdown/PDF report
`

## Why Local?

- **Security**: Sensitive incident data remains on your infrastructure
- **Privacy**: No exposure of internal systems or breach details to external services
- **Control**: Full customization for your incident management workflow
- **Confidentiality**: Protect proprietary information and customer data

## Contributing

Contributions welcome! Please fork, create a feature branch, and submit a pull request.

## License

MIT License — see [LICENSE](LICENSE) for details.

---

*Part of 114+ privacy-first AI tools by Nrk Raju*