# AI Resume Criticuier

An AI-powered resume reviewing application built with Python, Streamlit, and Google Gemini.

The application allows users to upload their resume as a PDF or text file and receive AI-generated feedback. Users can also provide a target job role so the feedback can be more relevant to that position.

## Features

* Upload a resume in PDF or TXT format
* Extract text from PDF resumes
* Analyze resumes using Google Gemini
* Get AI-generated feedback about the resume
* Enter a target job role for more specific feedback
* Simple and user-friendly Streamlit interface
* API key loaded safely from a `.env` file
* Runs locally in a web browser

## Tech Stack

* Python 3.13
* [uv](https://github.com/astral-sh/uv) for package and environment management
* Streamlit
* Google Gemini
* `langchain-google-genai`
* `python-dotenv`
* PyPDF2
* OpenAI-compatible / LangChain components for AI interaction

## How the Project Works

The application takes a resume from the user and sends the extracted resume text to the AI model.

The basic process is:

```text
User uploads resume
        ↓
Application extracts resume text
        ↓
User can enter a target job role
        ↓
Resume information is sent to Gemini
        ↓
Gemini analyzes the resume
        ↓
AI-generated feedback is displayed
```

For example, a user can upload a resume and enter:

```text
Target Job Role:
Software Engineer
```

The AI can then provide feedback related to the Software Engineer role.

## Project Structure

```text
ai-resumes-criticuier/
│
├── src/
│   └── ai_resumes_criticuier/
│       ├── __init__.py
│       └── main.py
│
├── pyproject.toml
├── uv.lock
├── .gitignore
└── .env
```

The `.env` file contains the API key and should **not** be uploaded to GitHub.

## Setup

### 1. Install Dependencies

Make sure `uv` is installed.

Then, from the project folder, run:

```powershell
uv sync
```

This installs the required packages and sets up the project environment.

### 2. Create the `.env` File

Create a file named:

```text
.env
```

in the main project folder:

```text
ai-resumes-criticuier/
├── .env
├── pyproject.toml
└── src/
```

Add your Google API key:

```text
GOOGLE_API_KEY=your_api_key_here
```

Do not share your API key publicly.

The project uses `python-dotenv` to load the API key from the `.env` file.

## Run the Application

Open PowerShell and go to the project folder:

```powershell
cd "D:\AI resumes criticuier"
```

Then run:

```powershell
uv run streamlit run src\ai_resumes_criticuier\main.py
```

Streamlit will start the application and provide a local address in the terminal.

Open the provided address in your browser to use the application.

## Example Usage

### Step 1 — Upload Resume

The user uploads a resume:

```text
resume.pdf
```

or:

```text
resume.txt
```

### Step 2 — Enter Job Role

The user can optionally enter a target role:

```text
Software Engineer
```

### Step 3 — Analyze Resume

The user clicks the:

```text
Analyze Resume
```

button.

### Step 4 — Receive AI Feedback

The application sends the resume information to Gemini and displays AI-generated feedback.

The feedback can help identify areas such as:

* Resume strengths
* Weak sections
* Skills
* Experience
* Education
* Areas that could be improved
* Suggestions for the target job role

## PDF Text Extraction

The project uses `PyPDF2` to extract text from PDF resumes.

The application reads the PDF pages and extracts the available text before sending it to the AI model.

This allows the AI to analyze the actual content of the uploaded resume.

## AI Model

The project has been updated to use **Google Gemini** instead of the previous OpenAI-based setup.

The application uses Google's Gemini model through the `langchain-google-genai` package.

The API key is loaded from:

```text
GOOGLE_API_KEY
```

using:

```python
load_dotenv()
```

This keeps the API key outside the main Python source code.

## Previous Version vs Current Version

The previous version of this project used the OpenAI Python client and an `OPENAI_API_KEY`.

The project has now been changed to use **Google Gemini**.

### Previous setup

```text
OpenAI
↓
OPENAI_API_KEY
↓
OpenAI Python client
```

### Current setup

```text
Google Gemini
↓
GOOGLE_API_KEY
↓
langchain-google-genai
```

This means the `.env` file should now contain:

```text
GOOGLE_API_KEY=your_api_key_here
```

instead of:

```text
OPENAI_API_KEY=your_api_key_here
```

## Current Status

**Working**

The current version of the project:

* Starts successfully
* Opens in the browser using Streamlit
* Allows PDF resume uploads
* Allows TXT resume uploads
* Extracts text from PDF files
* Accepts an optional target job role
* Uses Google Gemini for AI analysis
* Displays AI-generated resume feedback
* Loads the API key from `.env`

## Security

The Google API key is stored in:

```text
.env
```

The `.env` file should **never be committed to GitHub**.

Make sure `.gitignore` contains:

```text
.env
```

This helps prevent your API key from accidentally being uploaded to your GitHub repository.

## Known Limitations

* The application currently supports PDF and TXT resumes.
* Scanned/image-only PDFs may not provide usable text if the PDF does not contain selectable text.
* The quality of the feedback depends on the resume content and AI model response.
* The application currently focuses on resume reviewing rather than automatically rewriting the entire resume.

## Future Improvements

Possible improvements for this project include:

* Add DOCX resume support
* Add OCR for scanned resumes
* Add resume scoring
* Compare a resume against a job description
* Detect missing skills for a specific job
* Generate an improved version of the resume
* Generate cover letters
* Add multiple AI model options
* Add error handling for API failures
* Add an option to download the AI feedback
* Add more structured resume analysis
* Compare responses from different LLMs

## Relevance to My AI and LLM Learning

This project helped me understand the basic concepts of:

* Large Language Models (LLMs)
* Generative AI
* Prompting
* AI-powered document analysis
* Google Gemini
* LangChain
* Streamlit
* API keys
* Environment variables
* PDF text extraction
* AI-generated feedback

It also provides a foundation for future projects involving **LLM evaluation and LLM bias research**, especially by comparing how different models analyze the same resume.

## License

This project is created for learning and educational purposes.
