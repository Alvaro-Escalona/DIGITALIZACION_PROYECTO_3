<p align="center">
  <img src="icono.ico" alt="Transversor PDF Logo" width="120" >
</p>

<h1 align="center">Transversor</h1>

# 🌐 Transversor
<p align="center">
  ![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)
  ![License MIT](https://img.shields.io/badge/license-MIT-yellow.svg)
  ![Hugging Face](https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-Spaces-blue)
</p>


🌐 **Transversor** is an open-source document processing tool designed to bridge linguistic barriers by providing seamless translation of PDF documents. Unlike conventional translation tools that often struggle with document structure, Transversor focuses on generating clean, accessible output in both **Microsoft Word (.docx)** and **PDF** formats, ensuring that the essence and readability of your content remain intact across languages.

Whether you are handling academic papers, business reports, or technical manuals, Transversor provides a streamlined workflow that respects the integrity of the original source while delivering a nuanced translation experience.

> **Important Note:** 🌐 Transversor is intended to assist in multilingual support for small-scale projects or personal use where professional translation may not be immediately accessible. It provides a practical solution for high-quality results in contexts where speed and accessibility are paramount, ensuring that language is never a barrier to the global reach of your content.

[Demo](https://huggingface.co/spaces/AlvaroEC/Transversor) · [Report a Bug](https://github.com/AlvaroEC/transversor/issues) · [Request a Feature](https://github.com/AlvaroEC/transversor/issues)

---

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

In the era of **Digital Transformation**, the ability to process and understand technical documentation in multiple languages is a strategic asset. **Transversor** was developed to solve a critical bottleneck in industrial and business environments: the friction of dealing with foreign-language technical manuals, contracts, and specifications.

By automating the extraction and translation process while maintaining logical paragraph structures, this tool:
* **Accelerates Decision-Making:** Reduces the time spent on manual translation.
* **Optimizes IT/OT Integration:** Bridges the gap between international machinery documentation (OT) and digital information systems (IT).
* **Ensures Data Privacy:** Operates locally to protect sensitive corporate information from being stored on external servers.

---

## 🌐 Live Demo
The fastest way to experience **Transversor** is through our web-based demonstration. No installation required.

> [!TIP]
> **[🚀 Click here to launch the Online Demo](https://huggingface.co/spaces/AlvaroEC/Transversor)**

### ⛔ Free Version Constraints
Please note that this demonstration operates under the following technical limitations:
* **Character Limit:** Due to the free translation API usage policy, **documents exceeding 5,000 characters cannot be translated** in this version.
* **Full Support:** For larger documents, a premium API key or local deployment with a specialized engine would be required.

---

##  Why Transversor❓

In many industrial and corporate sectors, technical documentation is still a barrier to efficiency. **Transversor** was born from the need to:

* **Preserve Context:** Unlike standard copy-paste translators, Transversor analyzes paragraph structures to ensure that technical meaning isn't lost in translation.
* **Empower Users:** By allowing a visual selection of pages, we avoid the "all-or-nothing" approach, saving time and focus.
* **Bridge the Language Gap:** It enables non-multilingual staff to operate machinery or review legal specs with the same confidence as a native speaker.
* **Security First:** Businesses shouldn't have to upload sensitive blueprints to the cloud just to understand them. Transversor keeps everything local.

---

## ⚙️ How Transversor Works

The "magic" behind the transmutation process follows a robust 4-step pipeline:

1.  **Extraction (Parsing):** Using `PyMuPDF` (fitz) and `PyPDF2`, the system decodes the PDF structure, identifying text blocks and page coordinates.
2.  **Segmentation:** The text is divided into manageable chunks. This prevents API overflows and allows the software to maintain the original document's logical flow.
3.  **Neural Translation:** Each segment is sent to the translation engine (Deep Translator). The system manages these calls through a queuing system to ensure stability.
4.  **Reconstruction:** * For **PDFs**: It uses `ReportLab` to re-draw the text into a new document.
    * For **DOCX**: It uses `python-docx` to create an editable version with professional styling.
5.  **Multi-threading:** All these steps run in a separate execution thread, meaning the user can still interact with the UI or load more files while the "Transversor" is working in the background.

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

| Step 2: Load | Step 2: Select the laguage | Step 3: Result |
| :---: | :---: | :---: |
| <img width="1392" height="910" alt="1" src="https://github.com/user-attachments/assets/d73e52c3-42ba-4820-937c-e0f02dde8243" width="200"> | <img width="1398" height="907" alt="Captura de pantalla 2026-04-25 194539" src="https://github.com/user-attachments/assets/6a29a717-5b94-431b-bc11-f5e6664672ca"  width="200"> | <img width="1396" height="910" alt="Captura de pantalla 2026-04-25 194621" src="https://github.com/user-attachments/assets/b41c3b04-9847-4100-8f6b-aa176a61ccd5"  width="200">




### 2. Selective Processing
1. **Visual Selection:** Double-click any file in the list to open the visual page editor.
2. **Filter Content:** Select only the specific pages (e.g., technical specs) you need to translate.
3. **Optimized Output:** The software will only process the selected pages, saving time and API resources.

| Step 1: Load | Step 2: Select Pages | Step 3: Result |
| :---: | :---: | :---: |
| <img width="1392" height="910" alt="1" src="https://github.com/user-attachments/assets/d73e52c3-42ba-4820-937c-e0f02dde8243" width="200"> | <img width="1398" height="907" alt="Captura de pantalla 2026-04-25 190025" src="https://github.com/user-attachments/assets/d5353c7d-781c-4b0f-8d31-a2991a3a46ca" width="200"> | <img width="1397" height="911" alt="Captura de pantalla 2026-04-25 185932" src="https://github.com/user-attachments/assets/cb35c91e-7aac-4aa0-8223-1bc1794c61ca" width="200"> 




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
