# AI Resume Criticuer 📄🤖

An AI-powered resume analysis application built with Python and Streamlit.

This project allows users to upload a resume in PDF or TXT format and receive AI-generated feedback about their resume, including content clarity, skills presentation, experience descriptions, and improvements tailored to a specific job role.

> **Project Status:** 🚧 Learning / Development Project

---

## 📌 About the Project

I built this project as part of my learning journey in Python, Streamlit, and AI application development.

The goal of this application is to help users improve their resumes by providing structured feedback based on the content of their resume and the job role they are targeting.

The application currently supports:

- Uploading PDF resumes
- Uploading TXT resumes
- Extracting text from PDF files
- Extracting text from TXT files
- Entering an optional target job role
- Creating an AI prompt based on the resume
- Sending the resume content to an AI model for analysis
- Displaying structured resume feedback in the Streamlit interface

---

## ✨ Features

### 📄 Resume Upload

Users can upload their resume in either:

- PDF format
- TXT format

### 🔍 Resume Text Extraction

For PDF files, the application uses `PyPDF2` to extract text from the document.

For TXT files, the application reads the text directly.

### 🎯 Job-Specific Feedback

Users can optionally enter the job role they are targeting.

For example:

```text
Python Developer
```

or:

```text
Data Analyst
```

The selected job role is included in the AI prompt so the feedback can be tailored to that role.

### 🤖 AI-Powered Resume Analysis

The application is designed to use the OpenAI API to analyze the uploaded resume.

The analysis focuses on:

1. Content clarity and impact
2. Skills presentation
3. Experience descriptions
4. Specific improvements for the selected job role

### 🖥️ Streamlit Interface

The application uses Streamlit to provide a simple and interactive web interface without requiring a separate frontend framework.

---

## 🛠️ Technologies Used

- Python
- Streamlit
- OpenAI API
- PyPDF2
- python-dotenv
- io
- os
- uv

---

## 📁 Project Structure

```text
ai-resumes-criticuer/
│
├── .env
├── .venv/
│
├── src/
│   └── ai_resumes_criticier/
│       ├── __init__.py
│       └── main.py
│
├── .gitignore
├── .python-version
├── pyproject.toml
├── README.md
└── uv.lock
```

### Important Files

#### `main.py`

This is the main application file.

It contains:

- Streamlit UI
- Resume file uploading
- PDF text extraction
- TXT text extraction
- AI prompt creation
- OpenAI API integration
- Error handling
- Displaying the AI-generated analysis

#### `.env`

The `.env` file is used to store the OpenAI API key locally.

Example:

```env
OPENAI_API_KEY=your_api_key_here
```

**Do not upload your real API key to GitHub.**

#### `pyproject.toml`

Contains the Python project configuration and dependencies.

#### `uv.lock`

Contains locked dependency versions for the project.

#### `.gitignore`

Used to prevent sensitive and unnecessary files from being uploaded to GitHub.

---

## 🚀 How to Run the Project

### 1. Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/ai-resumes-criticuer.git
```

Then move into the project directory:

```bash
cd ai-resumes-criticuer
```

Replace `YOUR_USERNAME` with your GitHub username.

---

### 2. Install Dependencies

This project uses `uv` for Python project and dependency management.

Run:

```bash
uv sync
```

---

### 3. Configure Environment Variables

Create a `.env` file in the root directory of the project.

Add:

```env
OPENAI_API_KEY=your_api_key_here
```

Replace `your_api_key_here` with your own API key.

**Never upload your real API key to GitHub.**

---

### 4. Run the Streamlit Application

Run:

```bash
uv run streamlit run src/ai_resumes_criticier/main.py
```

Alternatively, if Streamlit is available directly in your environment:

```bash
streamlit run src/ai_resumes_criticier/main.py
```

After running the command, Streamlit will provide a local URL similar to:

```text
http://localhost:8501
```

Open that URL in your browser.

---

## 🔑 OpenAI API Key

This project is designed to use the OpenAI API for resume analysis.

The application loads the API key from the `.env` file using `python-dotenv`.

The relevant code is:

```python
load_dotenv()

OPENAI_API_KEY = os.getenv("OPENAI_API_KEY")
```

The OpenAI client is then created using:

```python
client = OpenAI(api_key=OPENAI_API_KEY)
```

### Current API Limitation

At the moment, I do not have an OpenAI API account with available API access/credits, so I have not been able to fully test the live AI analysis functionality using a real OpenAI API key.

Because of this, the project is currently considered a learning/development project.

The application structure, Streamlit interface, file uploading, and resume text extraction have been developed, while the complete live OpenAI API workflow still needs to be tested with valid API access.

I am keeping the project public on GitHub as part of my learning journey and to document my progress in building AI-powered applications.

---

## 🔄 Application Workflow

The intended workflow of the application is:

```text
User uploads resume
        ↓
Application detects file type
        ↓
Extract resume text
        ↓
User enters target job role
        ↓
Create AI analysis prompt
        ↓
Send request to OpenAI API
        ↓
Receive AI-generated feedback
        ↓
Display resume analysis
```

---

## 🧪 Current Project Status

| Feature | Status |
|---|---|
| Streamlit interface | ✅ Implemented |
| PDF upload | ✅ Implemented |
| TXT upload | ✅ Implemented |
| PDF text extraction | ✅ Implemented |
| TXT text extraction | ✅ Implemented |
| Job role input | ✅ Implemented |
| AI prompt generation | ✅ Implemented |
| OpenAI API integration | ✅ Implemented |
| Live OpenAI API testing | ⚠️ Not completed |
| Production deployment | 🚧 Future work |

---

## 🐛 Known Limitations

The main current limitation is that I do not have an available OpenAI API key/credits for fully testing the live AI analysis workflow.

Other areas that can be improved include:

- Better error handling
- More robust PDF text extraction
- Support for scanned/image-based PDFs
- ATS-focused analysis
- Resume scoring
- Job description comparison
- More detailed feedback categories
- Improved UI/UX
- Loading indicators
- Automated testing
- Production deployment

---

## 🔮 Future Improvements

Planned improvements for this project include:

- [ ] Add ATS compatibility analysis
- [ ] Add resume section detection
- [ ] Add keyword analysis
- [ ] Allow users to upload a job description
- [ ] Compare the resume with a specific job description
- [ ] Provide more detailed recommendations
- [ ] Add resume scoring
- [ ] Improve Streamlit UI
- [ ] Add loading/progress indicators
- [ ] Improve PDF processing
- [ ] Add automated tests
- [ ] Add deployment configuration
- [ ] Explore alternative AI providers for development and testing

---

## 🔒 Security

Never upload API keys or other sensitive credentials to GitHub.

Your `.gitignore` file should contain at least:

```gitignore
.env
.venv/
__pycache__/
*.pyc
```

The `.env` file should remain on your local computer and should not be committed to the Git repository.

If an API key is accidentally uploaded to GitHub, it should be revoked immediately and replaced with a new key.

---

## 📚 What I Learned

This project has helped me practice several important concepts in Python and AI application development.

Through this project, I am learning about:

- Python project structure
- Python virtual environments
- Dependency management with `uv`
- Streamlit application development
- File uploads
- PDF text extraction
- Environment variables
- API integration
- Prompt engineering
- Error handling
- Git
- GitHub
- Building AI-powered applications

---

## 🎓 Learning Purpose

This project is primarily an educational project.

I am using it to gain practical experience in building applications that combine Python, web interfaces, document processing, and AI APIs.

The project will continue to evolve as I learn more about AI application development and software engineering.

---

## ⚠️ Disclaimer

This application is intended for educational and experimental purposes.

AI-generated resume feedback should be treated as suggestions rather than professional career advice. Users should review the recommendations and make their own decisions about changes to their resumes.

---

## 👨‍💻 Author

Built as a personal learning project while learning Python, Streamlit, and AI application development.

This repository documents my progress and learning process as I continue developing my programming and AI skills.

---

## ⭐ Future Goal

The long-term goal of this project is to develop a more complete resume analysis tool that can compare a resume against a specific job description and provide actionable suggestions for improving relevance, clarity, keyword usage, and ATS compatibility.

---

## 📌 Project Status

This project is actively being improved as part of my learning journey.

More features, testing, and improvements will be added over time.