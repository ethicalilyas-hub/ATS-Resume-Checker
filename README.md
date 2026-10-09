# 📄 ATS Resume Checker

A Streamlit app that scores a resume for ATS (Applicant Tracking System) friendliness and suggests concrete improvements, powered by Google Gemini Flash.

## Features
- Upload a resume as PDF, DOCX or TXT
- Overall ATS score (0-100) plus section scores (formatting, keywords, impact, skills, education, readability)
- Optional job description for keyword-match analysis
- Strengths, missing keywords, prioritized improvements and suggested bullet rewrites
- Download the report as JSON

## Run locally
1. Install Python 3.10+.
2. Install dependencies:
```bash
   pip install -r requirements.txt
```
3. Get a free API key at https://aistudio.google.com/apikey
4. Set the key and run:
```bash
   export GEMINI_API_KEY="your-key"      # Windows PowerShell: $env:GEMINI_API_KEY="your-key"
   streamlit run app.py
```
   Or skip the variable and paste the key into the sidebar.

## Configuration
| Setting | Purpose |
|---|---|
| `GEMINI_API_KEY` | Your Gemini API key (env variable or Streamlit secret) |
| `GEMINI_MODEL` | Optional. Override the model name, e.g. when Google retires one |

## Deploy on Streamlit Community Cloud
1. Push this repo to GitHub (never commit your API key).
2. Go to https://share.streamlit.io, sign in with GitHub and click **Create app**.
3. Choose the repo, branch `main` and main file `app.py`.
4. Open **Advanced settings → Secrets** and add:
```toml
   GEMINI_API_KEY = "your-key"
```
5. Click **Deploy**.

## Notes
- Scanned/image-only PDFs have no extractable text; use a text-based PDF or DOCX.
- Scores are an AI estimate, not the output of a real ATS.
- Resume text is sent to the Gemini API; don't upload anything you aren't comfortable sharing.