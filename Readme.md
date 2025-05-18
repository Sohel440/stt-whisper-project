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
     ```

3. **Upload MP3 Files**:
   - Run the second cell to upload MP3 files:
     ```python
     from google.colab import files
     uploaded = files.upload()
     ```
   - Upload `the-raven-100-bpm-71717.mp3` or another MP3 file.
   - Note: The notebook currently references `dataset2.mp3`, which isn’t in the repository. Update the `audio_path` to match your uploaded file (e.g., `/content/the-raven-100-bpm-71717.mp3`).

4. **Run the Transcription**:
   - Execute the third cell to transcribe the audio. Update `audio_path` if needed:
     ```python
     audio_path = "/content/the-raven-100-bpm-71717.mp3"
     ```

### Local Linux Environment
1. **Install Python**:
   - Ensure Python 3.9 is installed:
     ```bash
     sudo apt-get update
     sudo apt-get install python3.9 python3-pip
     ```

2. **Set Up a Virtual Environment**:
   ```bash
   python3 -m venv whisper_env
   source whisper_env/bin/activate
   ```

3. **Install Dependencies**:
   - Install `ffmpeg`:
     ```bash
     sudo apt-get install ffmpeg
     ```
   - Install Python libraries:
     ```bash
     pip install transformers torch
     ```

4. **Prepare the MP3 File**:
   - Place `the-raven-100-bpm-71717.mp3` (or another MP3) in your project directory (e.g., `~/stt-whisper-project/`).

5. **Update the Script**:
   - In `stt_whisper.py`, update `audio_path` to the full path of your MP3 file:
     ```python
     audio_path = "/home/yourusername/stt-whisper-project/the-raven-100-bpm-71717.mp3"
     ```

## Usage

### Running in Google Colab
1. Open `Speech_to_Text.ipynb` in Colab.
2. Run all cells in order:
   - Install dependencies.
   - Upload an MP3 file (e.g., `the-raven-100-bpm-71717.mp3`).
   - Transcribe the audio.
3. View the transcription in the output.

### Running Locally in Terminal
1. Navigate to the project directory:
   ```bash
   cd ~/stt-whisper-project
   ```
2. Activate the virtual environment:
   ```bash
   source whisper_env/bin/activate
   ```
3. Run the script:
   ```bash
   python stt_whisper.py
   ```
4. The transcription will be printed in the terminal.

## Sample Output
Using `the-raven-100-bpm-71717.mp3` (an excerpt from *The Raven* by Edgar Allan Poe), the transcription output is:

```
Transcribing audio...
Transcription:
 Once upon a midnight dreary, while I pondered weakened weary, over many acquaintance curious volume of forgotten lore, while I nodded nearly napping suddenly there came a tapping as of someone gently wrapping, wrapping at my chamber door to some visitor I muttered, tapping at my chamber door, only this and nothing more. When the raven never flitting still is sitting, still is sitting on the pallet bust of palace just above my chamber door, and his eyes have all the seeming of demons that is dreaming and the lamplight or him streaming throws his shadow on floor, and my soul from out that shadow that lies floating on the floor shall be lifted, never more. the Raven never more.
```

## Dependencies
- Python 3.7–3.10 (3.9 recommended for local setup; Colab uses 3.11).
- `transformers`: For the Whisper model.
- `torch`: For model inference (CPU or GPU).
- `ffmpeg`: For audio processing.

Install locally with:
```bash
pip install transformers torch
sudo apt-get install ffmpeg
```

## Notes
- **Long-Form Audio**: The project supports audio files longer than 30 seconds by enabling `return_timestamps=True`, which resolves the `ValueError: You have passed more than 3000 mel input features` error.
- **FutureWarning**: A warning about the deprecated `inputs` parameter in `transformers` is present but doesn’t affect functionality. It can be suppressed by adding:
  ```python
  import warnings
  warnings.filterwarnings("ignore", category=FutureWarning)
  ```
- **File Path**: Update `audio_path` in the code to match your MP3 file’s location.
- **Colab Limitations**: Files uploaded to Colab are temporary and deleted after the session ends. For persistent storage, use the local setup or save files to Google Drive.

## Credits
- **Whisper Model**: OpenAI, via Hugging Face `transformers` library.
- **Sample Audio**: `the-raven-100-bpm-71717.mp3` from Freesound.org (public domain).
- **Development**: This project was developed iteratively, starting in Google Colab and adapted for local execution on Linux, meeting the requirement for a "working demo on local terminal."
