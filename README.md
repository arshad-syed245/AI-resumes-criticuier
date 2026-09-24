# AI Resume Critiquer

An AI-powered resume analysis tool built with Python and Streamlit. Upload a resume (PDF or TXT) and get structured feedback on content clarity, skills presentation, and experience descriptions — optionally tailored to a specific job role.

**Project status:** Learning / development project — not production-ready.

## ⚠️ Known Issue

This project currently uses the Google Gemini API (`google-genai`) for AI analysis. As of writing, new Gemini API projects can intermittently receive a `403 PERMISSION_DENIED` error ("Your project has been denied access") that is **not caused by this code** — it's a widely reported issue on Google's own developer forums affecting newly created API keys/projects, unrelated to billing status or API key correctness in many reported cases.

If you hit this error after following the setup steps below, it is very likely a Gemini account/project-level restriction on Google's side, not a bug here. Things that have worked for some (not guaranteed):
- Verifying your Google account (phone number, age verification)
- Checking Google Cloud Console for a restriction banner on the project
- Creating a brand new Google Cloud project + API key
- Attaching a billing account to the project (does not necessarily mean being charged, due to free tier quota)

This project was originally built using the OpenAI API and was switched to Gemini to avoid needing a paid OpenAI account. If you have access to an OpenAI (or other LLM) API key, swapping the API client back is straightforward since the rest of the app logic (file handling, prompt, UI) is provider-agnostic.

## Features

- Upload a resume as PDF or TXT
- Optional job role input to tailor the feedback
- AI-generated analysis covering:
  1. Content clarity and impact
  2. Skills presentation
  3. Experience descriptions
  4. Role-specific improvement suggestions

## Tech Stack

- Python
- Streamlit (UI)
- PyPDF2 (PDF text extraction)
- Google Gemini API (`google-genai`) for AI analysis
- `uv` for dependency management

## Setup

### 1. Clone the repo

\`\`\`bash
git clone https://github.com/arshad-syed245/AI-resumes-criticuier.git
cd AI-resumes-criticuier
\`\`\`

### 2. Install dependencies

\`\`\`bash
uv sync
\`\`\`

### 3. Get a Gemini API key

Go to [aistudio.google.com/apikey](https://aistudio.google.com/apikey), sign in, and create a key. Note the known issue above — access isn't guaranteed to work immediately for new accounts.

### 4. Set up environment variables

Create a `.env` file in the project root (same folder as `pyproject.toml`) with:

\`\`\`
GEMINI_API_KEY=your_key_here
\`\`\`

### 5. Run the app

\`\`\`bash
streamlit run src/ai_resumes_criticuier/main.py
\`\`\`

The app will open at `http://localhost:8501`.

## Usage

1. Upload your resume as a PDF or TXT file
2. (Optional) Enter the job role you're targeting
3. Click **Analyze Resume**
