# YouTube Video Summarizer 🎥📝

This repository provides a pipeline that:
1. **Downloads** a YouTube video.
2. **Extracts** or **transcribes** the audio.
3. **Summarizes** the transcript using a Mistral (or any other) LLM model.
4. (Optional) Extracts visual text from frames via OCR.
5. Generates a **Markdown report** summarizing the video.

---

## ✨ Features

- **Video Download** using `yt-dlp` 🚀
- **Transcript Retrieval**:
  - Automatically retrieves transcripts using `youtube-transcript-api` 🎤
  - Falls back to OpenAI Whisper if no transcript is available 🗣️
- **Language Detection** with `langdetect` 🌐
- **AI-Powered Summaries** leveraging a Mistral-based (or custom) language model 🤖
- **Optional OCR** to capture text from video frames using OpenCV and Tesseract 🔍
- **Structured Output**: Generates a comprehensive `.md` report including metadata, summaries, and (optional) OCR results 📄

---

## ⚙️ How It Works

- **Download Video:**
  - Uses `yt-dlp` to download the video file along with its metadata.

- **Transcript Handling:**
  - First tries to fetch an existing transcript with `youtube-transcript-api`.
  - If unavailable, the pipeline uses OpenAI Whisper to transcribe the audio. *(Make sure you have a valid API key if required.)*

- **Language Detection:**
  - The `langdetect` library checks the transcript language and provides this information to the summarization process.

- **Summarization:**
  - The transcript is split into manageable chunks.
  - Each chunk is fed into a Mistral-based LLM (configurable via `config.json`).
  - Summaries of each chunk are then combined into a cohesive final summary.

- **Optional OCR:**
  - If `ocr_enabled` is set to `true`, video frames are captured at specified intervals (based on `frame_interval` in seconds).
  - Tesseract OCR extracts text from each frame.
  - The recognized text is appended to the final summary or provided as an additional section in the report.

- **Markdown Report:**
  - A `.md` file is generated containing:
    - Video metadata (title, URL, duration, etc.).
    - Summaries of the transcript sections.
    - (Optional) OCR text results.
    - Final summary and conclusion.

---

## 📂 Project Structure

```plaintext
## 🛠️ Project Structure

```bash
Youtube_video_summarizer/
├── debug_frames/                 # Preprocessed frames for OCR debugging
├── frames/                       # Frames captured from the video at intervals
├── videos/                       # Downloaded YouTube videos
├── utils/                         # Helper functions for modularity
│   ├── download.py               # Handles video downloading
│   ├── transcript.py             # Retrieves/transcribes video transcripts
│   ├── summarizer.py             # Summarizes transcripts using AI models
│   ├── ocr.py                    # Performs OCR on video frames
├── config.json                    # Configuration file for model settings, OCR, etc.
├── requirements.txt                # List of required Python dependencies
├── Video_Summarizer_Yash_Verma.ipynb  # Jupyter Notebook for demonstration
├── Video_Summarizer_Yash_Verma.py      # Python script version (optional)
├── summary_report.md              # Generated Markdown report of the summarized video
├── README.md                      # This file, explaining the project

