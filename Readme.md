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
