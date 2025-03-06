# 🎥 YouTube Video Summarizer

A minimal working example of a pipeline that:
1. Downloads a YouTube video and metadata.
2. Retrieves or transcribes the transcript.
3. Summarizes the transcript using a Hugging Face model.
4. (Optional) Extracts text from frames via OCR.
5. Produces a Markdown report.

## 📌 Features

- **Video Download**: Uses `yt-dlp`.
- **Transcript Retrieval**: Via `youtube-transcript-api` (and optionally `openai-whisper`).
- **Summarization**: Uses a Hugging Face model (default: `facebook/bart-large-cnn`).
- **OCR Extraction**: (Optional) Uses `pytesseract` and OpenCV to grab frames and extract text.
- **Markdown Report**: Outputs a simple `.md` file summarizing the video.

## 🚀 Installation

1. **Clone the Repository**
   ```bash
   git clone https://github.com/yourusername/Youtube_video_summarizer.git
   cd Youtube_video_summarizer
