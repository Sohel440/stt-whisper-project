# Speech-to-Text (STT) with Whisper

This project demonstrates how to convert audio files in MP3 format to text using OpenAI's Whisper model (`openai/whisper-tiny`). It includes implementations for both Google Colab (via a Jupyter notebook) and local execution on Linux (via a Python script in the terminal).

## Table of Contents

- [Project Overview](#project-overview)
- [Files](#files)
- [Setup Instructions](#setup-instructions)
  - [Google Colab](#google-colab)
  - [Local Linux Environment](#local-linux-environment)
- [Usage](#usage)
  - [Running in Google Colab](#running-in-google-colab)
  - [Running Locally in Terminal](#running-locally-in-terminal)
- [Sample Output](#sample-output)
- [Dependencies](#dependencies)
- [Notes](#notes)
- [Credits](#credits)

## Project Overview

The goal of this project is to transcribe MP3 audio files into text using the Whisper model from OpenAI, provided by Hugging Face's `transformers` library. The project supports:

- Audio files longer than 30 seconds (with timestamp support).
- Execution in Google Colab for cloud-based testing.
- Local execution on Linux in a terminal, meeting the requirement for a "working demo on local terminal."

The project was developed iteratively, addressing issues like long-form audio transcription and deprecated API warnings.

## Files

- `Speech_to_Text.ipynb`: Jupyter notebook for running the STT project in Google Colab.
- `stt_whisper.py`: Python script for running the STT project locally in a Linux terminal.
- `the-raven-100-bpm-71717.mp3`: Sample MP3 file (an excerpt from Edgar Allan Poe's *The Raven*).
- `i-dont-like-you-87027.mp3`: Additional sample MP3 file for testing.

## Setup Instructions

### Google Colab

1. **Open the Notebook**:
   - Open `Speech_to_Text.ipynb` in Google Colab by clicking the "Open in Colab" badge at the top of the notebook, or upload it manually via [colab.research.google.com](https://colab.research.google.com).

2. **Install Dependencies**:
   - Run the first cell to install `transformers` and `ffmpeg`:
     ```bash
     !pip install transformers
     !apt-get update && apt-get install -y ffmpeg



---

### Changes Made to Convert to Proper Markdown
1. **Headers**:
   - Added proper Markdown headers using `#` for sections (e.g., `## Project Overview`, `### Google Colab`).
   - Ensured the Table of Contents links to sections using `[Section](#section)` syntax.
2. **Lists**:
   - Used `-` for unordered lists (e.g., under “Files” and “Dependencies”).
   - Used numbered lists (`1.`, `2.`) for step-by-step instructions (e.g., under “Setup Instructions”).
3. **Code Blocks**:
   - Formatted code snippets with triple backticks (```) and specified the language (e.g., `bash`, `python`) for syntax highlighting.
   - Example: `!pip install transformers` is wrapped in a `bash` code block.
4. **Emphasis**:
   - Used backticks (`) for inline code (e.g., `Speech_to_Text.ipynb`, `transformers`).
   - Used italics (`*text*`) for emphasis (e.g., *The Raven*).
5. **Spacing and Formatting**:
   - Added line breaks between sections for readability.
   - Ensured consistent indentation in lists and code blocks.
6. **Links**:
   - Formatted URLs as clickable links (e.g., `[colab.research.google.com](https://colab.research.google.com)`).
7. **Quotes**:
   - Wrapped the sample output in a plain code block (using triple backticks without a language specifier) to preserve formatting.

---

### How to Update Your `README.md` on GitHub
1. **Go to Your Repository**:
   - Open `github.com/Sohel440/stt-whisper-project`.
   - Click on `README.md` to view it.
2. **Edit the File**:
   - Click the pencil icon (✏️) to edit.
   - Replace the existing content with the raw Markdown content above.
   - If you want to keep parts of the existing `README.md`, you can manually merge them (e.g., append new sections).
3. **Commit the Changes**:
   - Scroll to the bottom.
   - Enter a commit message (e.g., “Format README with proper Markdown”).
   - Click **Commit changes**.

---

### Alternative: Update Locally and Push to GitHub
Since you’re working on Linux:
1. **Edit `README.md` Locally**:
   - Navigate to your local repository:
     ```bash
     cd ~/stt-whisper-project
