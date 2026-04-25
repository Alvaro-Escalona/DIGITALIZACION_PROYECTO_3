<p align="center">
  <img src="https://img.icons8.com/fluency/144/pdf-2.png" alt="Transversor PDF Logo" width="120">
</p>

<h1 align="center">Transversor PDF</h1>

<p align="center">
  <strong>Advanced Document Transmutation & Multilingual Digitalization Tool.</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Status-Active-brightgreen" alt="Status">
  <img src="https://img.shields.io/badge/License-MIT-blue" alt="License">
  <img src="https://img.shields.io/badge/Python-3.10+-yellow" alt="Python">
  <img src="https://img.shields.io/badge/Platform-Cross--Platform-lightgrey" alt="Platform">
</p>

---

## 💡 Motivation

In the era of **Digital Transformation**, the ability to process and understand technical documentation in multiple languages is a strategic asset. **Transversor PDF** was developed to solve a critical bottleneck in industrial and business environments: the friction of dealing with foreign-language technical manuals, contracts, and specifications.

By automating the extraction and translation process while maintaining logical paragraph structures, this tool:
* **Accelerates Decision-Making:** Reduces the time spent on manual translation.
* **Optimizes IT/OT Integration:** Bridges the gap between international machinery documentation (OT) and digital information systems (IT).
* **Ensures Data Privacy:** Operates locally to protect sensitive corporate information from being stored on external servers.

---

## ✨ Key Features

* **🌐 Intelligent Translation:** Powered by `deep-translator` with support for Google Translate API.
* **🖱️ Modern UX:** A sleek Dark Mode interface built with `customtkinter`.
* **📥 Drag & Drop System:** Mass file loading for high-volume environments.
* **🔍 Visual Page Selector:** Granular control over which parts of the document to process.
* **⚡ Multi-threaded Processing:** Ensures the UI remains responsive during heavy translation tasks.
* **📄 Professional Output:** Exports to both editable `.docx` and read-only `.pdf` formats.

---

## 🚀 Getting Started (Deployment)

### Prerequisites
* **Python 3.10** or higher.
* `pip` (Python package installer).

### Installation (Generic)

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/your-username/Transversor-PDF.git](https://github.com/your-username/Transversor-PDF.git)
   cd Transversor-PDF

2. **Set up a Virtual Environment (Recommended):**
   ```bash
   python -m venv venv
    # On Windows:
    .\venv\Scripts\activate
    # On macOS/Linux:
    source venv/bin/activate

3. **Install Dependencies:**
   ```bash
     pip install -r requirements.txt

**Platform-Specific Notes**

Windows: The application includes a specific ctypes fix for high-DPI scaling and taskbar icon integration.

Linux: Ensure you have tk-dev installed for the graphical interface to render correctly (sudo apt-get install python3-tk).

---

## 🛠️ Usage Examples

### 1. Basic Translation
1. **Launch the application:** Run `python traductorv4.py`.
2. **Load documents:** Drag and drop your PDF files into the main window or use the "Add PDFs" button.
3. **Configure:** Select your target language and desired output format (.pdf or .docx).
4. **Translate:** Click **"Translate All"** and monitor progress through the real-time status bar.

### 2. Selective Processing
1. **Visual Selection:** Double-click any file in the list to open the visual page editor.
2. **Filter Content:** Select only the specific pages (e.g., technical specs) you need to translate.
3. **Optimized Output:** The software will only process the selected pages, saving time and API resources.

---

## 🏗️ Architecture & Security

This project is built with a focus on **Data Integrity** and **Privacy**:

* **Local Processing:** All PDF parsing and file generation happen on the user's machine.
* **Volatile Memory:** Data is stored in temporary dictionaries (`cola_archivos`) during the session and is completely cleared upon closing the app.
* **Threaded Execution:** Translation runs in background threads to ensure the UI remains responsive and prevent data corruption during processing.
* **Input Validation:** Strict file type checks and path verification to prevent system errors.

---

## 🎯 Strategic Objectives

As part of the organization's **Digital Transformation** roadmap, this project fulfills the following:

- **Strategic Integration:** Aligning technical production with administrative needs by providing instant multilingual support.
- **Code Excellence:** Transitioning from a functional script to a modular, documented, and professional codebase (Open Source standards).
- **Scalability:** Designed to allow future integrations with Cloud Storage (S3, Google Drive) or Enterprise OCR engines.

---

## ⚖️ License

Distributed under the MIT License. See LICENSE for more information.
