# Contributing to Transversor PDF 🛠️

Thank you for your interest in contributing to **Transversor**! This project aims to provide an open and efficient way to translate documents. Just like major open-source projects, we follow quality standards to ensure the code remains maintainable and scalable.

To ensure a smooth collaboration, please read the following guidelines.

---

## 📑 Table of Contents

<b>[Code of Conduct](#-code-of-conduct)</b>
[How Can I Contribute?](#-how-can-i-contribute)
[Reporting Bugs](#-reporting-bugs)
[Feature Requests](#-feature-requests)
[Development Workflow](#-development-workflow)
[Coding Style](#-coding-style)
[Roadmap & Future Enhancements](#-roadmap--future-enhancements)

---

## 📜 Code of Conduct
This project adheres to a respectful communication standard. All contributors are expected to maintain an inclusive, professional, and harassment-free environment.

## 🤝 How Can I Contribute?
You can contribute to the project in several ways:
* **Fixes**: Correcting logic errors in translation or file management.
* **Features**: Implementing new functionalities (e.g., new output formats).
* **Docs**: Improving this file or the main README.
* **UI/UX**: Optimizing the Gradio interface for a more intuitive user experience.

## 🐛 Reporting Bugs
If you find an error, please open an **Issue** including:
1. **Description**: What is happening and what should happen.
2. **Logs**: A screenshot of the Hugging Face logs if the error occurs during deployment.
3. **File**: If the error is specific to a certain PDF, describe its characteristics (without sharing sensitive data).

## 💡 Feature Requests
If you have an idea to improve Transversor, please open an Issue tagged as `enhancement` to discuss its feasibility before you start coding.

---

## ⚙️ Development Workflow

We follow a branch-based workflow to keep the `main` branch stable at all times:

1. **Fork** the repository.
2. Create a descriptive branch for your change: `git checkout -b feat/amazing-feature` or `fix/specific-error`.
3. Install dependencies: `pip install -r requirements.txt`.
4. Make your changes and verify they work locally by running `python app.py`.
5. **Commit** your changes following clear conventions (e.g., `feat: add support for Italian translation`).
6. **Push** to your branch: `git push origin feat/amazing-feature`.
7. Open a **Pull Request (PR)** towards the original `main` branch.

---

## 🎨 Coding Style
To ensure readability:
* **Python**: Follow [PEP 8](https://peps.python.org/pep-0008/) conventions.
* **Comments**: Document functions that handle format conversion (`fpdf2`, `python-docx`).
* **Modularity**: Try to separate the processing logic from the Gradio interface logic.

---

## 🚀 Roadmap & Future Enhancements (Interest Areas)
If you are looking for ideas to contribute, these are the current high-priority areas:

1. **Character Limit Management**: Develop a text-segmentation system to automatically process documents exceeding 5,000 characters.
2. **Layout Preservation**: Improve text extraction so the output document maintains the original position of images and tables.
3. **Translation Engines**: Add support for paid APIs like DeepL or local Hugging Face models for increased privacy.
4. **OCR Integration**: Implement `pytesseract` to allow translation of scanned PDFs (images).

---
*This document is reviewed periodically. Last updated: April 2026.* Developed by [AlvaroEC](https://github.com/AlvaroEC)
