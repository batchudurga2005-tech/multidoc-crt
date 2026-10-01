# MULTIDOC-AI

> **"Your Intelligent AI Assistant for Multiple Documents"**

MULTIDOC-AI is an AI-powered document analysis platform built using Django. Users can upload multiple documents (PDF, DOCX, TXT) and interact with them using natural language. The system analyzes uploaded documents to provide instant Q&A answers, smart summaries, side-by-side document comparisons, and structured entity extractions.

---

## 🌟 Key Features

- 📁 **Multiple Document Upload**: Drag-and-drop batch upload for PDF, Word (.docx), and plain text (.txt) files.
- 💬 **Ask AI (Q&A)**: Conversational multi-document Q&A with source document citations.
- ⚡ **Smart Summarization**: Executive Short Summaries, Detailed Analyses, or bulleted Key Points with copy & download features.
- ⚖️ **Document Comparison**: Side-by-side comparative analysis of 2+ documents highlighting similarities, differences, and unique terms.
- 🔑 **Key Information Extraction**: Automated entity extraction (Names, Dates, Organizations, Financial Figures, and Keywords).
- 🛡️ **User Security & CSRF Protection**: Strict document isolation ensuring users only access their own documents.

---

## 🛠️ Tech Stack

- **Backend**: Python 3.12+, Django 5+
- **Frontend**: HTML5, CSS3 (Glassmorphism Dark Theme), JavaScript (Vanilla ES6), Bootstrap 5, FontAwesome 6
- **Database**: SQLite3 (Development)
- **Document Extractors**: `pypdf`, `python-docx`
- **AI Integration Layer**: Modular AI service layer (`documents/services/ai_service.py`) supporting Google Gemini API & OpenAI API with an intelligent local NLP fallback.

---

## 🚀 Beginner-Friendly Setup Instructions

Follow these step-by-step instructions to get **MULTIDOC-AI** running locally:

### Step 1: Create Virtual Environment
```bash
python -m venv venv
```

### Step 2: Activate Virtual Environment
- **Windows (PowerShell)**:
  ```powershell
  .\venv\Scripts\Activate.ps1
  ```
- **Windows (CMD)**:
  ```cmd
  venv\Scripts\activate.bat
  ```
- **macOS / Linux**:
  ```bash
  source venv/bin/activate
  ```

### Step 3: Install Requirements
```bash
pip install -r requirements.txt
```

### Step 4: Configure Environment Variables (.env)
Copy `.env.example` to `.env`:
```bash
cp .env.example .env
```
Open `.env` in a text editor and configure your secrets / API keys:
```env
SECRET_KEY=your_secret_key_here
DEBUG=True
AI_API_KEY=your_gemini_or_openai_api_key_here
```

### Step 5: Run Migrations
```bash
python manage.py makemigrations
python manage.py migrate
```

### Step 6: Create Superuser (Admin Account)
```bash
python manage.py createsuperuser
```
Follow the prompts to specify a username, email, and password.

### Step 7: Start Django Server
```bash
python manage.py runserver
```

### Step 8: Open in Browser
Open your web browser and navigate to:
```
http://127.0.0.1:8000/
```

---

## 🔒 Security & Verification

- **User Isolation**: All document uploads, chat histories, and AI extractions are linked to the authenticated user.
- **CSRF Protection**: All form submissions and AJAX endpoints enforce Django's CSRF token check.
- **File Validation**: Enforces extension checking (`.pdf`, `.docx`, `.txt`) and file size limits (15 MB).

---

## 📜 License

This project is open-source under the MIT License.
