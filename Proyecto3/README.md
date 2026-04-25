# Transversor PDF Pro 📄🌍

<p align="left">
  <img src="https://img.shields.io/badge/Python-3.13-blue.svg" alt="Python Version">
  <img src="https://img.shields.io/badge/License-MIT-green.svg" alt="License">
  <img src="https://img.shields.io/badge/Platform-Windows%20%7C%20Linux%20%7C%20macOS-lightgrey.svg" alt="Platform">
</p>

An advanced open-source suite for **intelligent PDF translation** and structural digital transformation. Transversor PDF Pro bridges the gap between static multilingual documents and actionable data by preserving layouts while translating.

## 🌟 Why Transversor PDF?
In a globalized business environment, efficient information management is a competitive advantage. Traditional translators often break document structures; our tool identifies **paragraphs, bullet points, and numbered lists** to ensure the output remains professional.

## ✨ Features
| Feature | Description |
| :--- | :--- |
| **Structural Awareness** | Automatically detects and preserves layouts (lists and blocks). |
| **Visual Selector** | Choose specific pages to minimize API costs and energy waste. |
| **Multi-threading** | Asynchronous processing to keep the UI responsive during tasks. |
| **Multi-Language** | Neural translation support for Spanish, English, French, Italian, Portuguese, German, and Chinese. |
| **Hybrid Export** | Generate both structured PDF and editable Word (.docx) files. |

## 🚀 Installation & Deployment

### 🪟 Windows (Recommended)
1. Download the latest `.exe` from the **Releases** section on the right.
2. Run directly—no Python installation required.

### 🐧 Linux (Ubuntu/Debian)
1. Install system dependencies:
   ```bash
   sudo apt update && sudo apt install python3-tk python3-pip

Clone the repo and install requirements:

Bash
pip install -r requirements.txt
Run: python3 traductorv4.py

🍎 macOS
Install Tcl/Tk (required for the GUI) via Homebrew: brew install python-tk

Install requirements and run: pip3 install -r requirements.txt && python3 traductorv4.py

🛠️ Tech Stack
This project is built using professional-grade Python libraries:

GUI: customtkinter for a modern Dark Mode interface.

PDF Engine: PyMuPDF (Fitz) for high-precision text extraction.

Translation: deep-translator utilizing Neural Machine Translation.

Document Generation: python-docx and reportlab.

📖 User Manual
Load Files: Drag PDFs into the window or use the "Añadir PDFs" button.

Page Selection: Double-click any document in the list to open the visual editor.

Configuration: Choose your target language and output format (PDF or Word).

Execution: Click "🚀 Traducir todo" and track progress in real-time.

⚖️ License
This project is licensed under the MIT License.
