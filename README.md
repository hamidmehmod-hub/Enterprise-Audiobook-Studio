# 📚 Enterprise Multilingual Audiobook Studio

An enterprise-grade, local web application engineered for converting massive documents (PDFs, DOCX, TXT) into chapter-chunked audiobooks and subtitled MP4 videos.

It features an advanced **Dual-Voice Sub-segmented Engine** specifically designed for complex multilingual manuscripts (such as Urdu Islamic texts embedded with Arabic Quranic verses or honorifics).

## ✨ Key Technical Features
* **Dual-Voice Sub-Segmented TTS Engine:** Seamlessly tags and switches between different native voice personas for embedded quotes/verses without breaking sentence flow.
* **Diacritic Density Auto-Tagger:** Uses mathematical diacritic density analysis to distinguish between sparse diacritic usage (Urdu Izhafat/Tanween) and dense vowelization (Arabic Quranic script).
* **Calligraphy Artifact Interceptor:** Detects and normalizes corrupted OCR ligatures (such as PBUH honorific artifacts) into standardized text.
* **Smart Semantic Line Stitcher:** Fixes PDF line breaks and hyphens while preserving chapter headings, Quranic verse boundaries, and natural paragraphs.
* **Dual Extraction Pipeline:** Choose between offline **Local EasyOCR** or context-aware **Google Gemini Vision AI**.
* **Smart Resume Workspace:** Caches rendered chunks to disk via MD5 hashes. Interrupted generations pick up exactly where they stopped without re-rendering existing audio.
* **Automated Media Export:** Exports clean MP3 chapter bundles, SRT subtitle files, DOCX script copies, and MP4 videos with burned-in subtitles.

---

## 🛠️ Prerequisites & System Requirements

### 1. Python 3.8+
Ensure Python is installed on your operating system.
* **Windows Users:** Check the box **"Add Python to PATH"** during installation.

### 2. FFmpeg (Required for MP4 Video Export)
FFmpeg must be installed and registered in your environment system PATH if you wish to export MP4 videos.

* **Windows (via Winget):**
      winget install ffmpeg

* **macOS (via Homebrew):**
      brew install ffmpeg

* **Linux (Ubuntu/Debian):**
      sudo apt update && sudo apt install -y ffmpeg

---

## 🚀 Quick Start & Installation

1. **Clone the Repository:**
      git clone https://github.com/hamidmehmod-hub/Enterprise-Audiobook-Studio.git
      cd Enterprise-Audiobook-Studio

2. **Create & Activate a Virtual Environment:**
   * **Windows:**
         python -m venv venv
         venv\Scripts\activate

   * **macOS / Linux:**
         python3 -m venv venv
         source venv/bin/activate

3. **Install Dependencies:**
      pip install -r requirements.txt

4. **Run the Application:**
      streamlit run app.py

---

## 🔑 Environment Variables (Optional)

You can set your Gemini API key as an environment variable to avoid entering it manually in the UI every session:

* **Windows (CMD):**
      set GEMINI_API_KEY="your_api_key_here"

* **macOS / Linux:**
      export GEMINI_API_KEY="your_api_key_here"

---

## 🛡️ Privacy & Data Security

* **Local Audio Processing:** All TTS audio rendering, chapter chunking, database storage, and video assembly occur locally on your machine.
* **Zero API Key Storage:** API keys entered into the UI are held exclusively in Streamlit in-memory session state and are never written to disk or logs.
* **Ignored Workspace Files:** The included `.gitignore` prevents project workspaces, local caches, and generated audio assets from being tracked or pushed to public Git repositories.
