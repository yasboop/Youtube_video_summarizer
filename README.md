YouTube Video Summarization Pipeline

This repository provides a comprehensive pipeline for summarizing YouTube videos. The process involves downloading videos, extracting transcripts, summarizing content using AI models, and optionally extracting visual text from video frames. The final output is a detailed Markdown report summarizing the video's content.​

Features

Video Download and Metadata Extraction: Utilizes yt-dlp to download videos and extract metadata such as title, description, and format details.​
Transcript Retrieval:
YouTube Transcripts: Fetches transcripts using the youtube-transcript-api for preferred languages (e.g., English, Hindi).​
Audio Transcription: If transcripts are unavailable, downloads audio and transcribes it using OpenAI's Whisper model.​
github.com
Language Detection: Determines the language of the transcript using langdetect.​
Text Summarization: Summarizes the transcript using the Mistral AI model via LangChain integration.​
Visual Text Extraction (Optional): Extracts text from video frames using OpenCV and Tesseract OCR to enrich the report with on-screen information.​
Markdown Report Generation: Compiles the extracted and summarized information into a structured Markdown report.​
github.com
+2
github.com
+2
github.com
+2
Installation

Clone the Repository:
git clone https://github.com/yourusername/your-repo-name.git
cd your-repo-name
Set Up a Virtual Environment:
python -m venv venv
source venv/bin/activate  # On Windows, use 'venv\Scripts\activate'
Install Dependencies:
pip install -r requirements.txt
Ensure that system dependencies like FFmpeg and Tesseract OCR are installed on your machine.
Usage

Define the YouTube Video URL:
Specify the YouTube video URL you wish to process in the script or notebook.
Run the Pipeline:
Execute the main script or notebook to process the video. The pipeline will:

Download the video and extract metadata.​
Retrieve or transcribe the video transcript.​
Detect the language of the transcript.​
Summarize the transcript using the Mistral AI model.​
Optionally extract visual text from video frames.​
Generate a Markdown report summarizing the video's content.​
View the Report:
The generated Markdown report will be saved in the specified output directory. You can view it using any Markdown viewer or convert it to other formats as needed.
Configuration

API Keys: Ensure that you have set the necessary API keys for services like Mistral AI. These can be set as environment variables or directly in the script.​
Optional Features: Enable or disable features like visual text extraction by setting the corresponding flags in the script.​
Dependencies

Python Libraries:
yt-dlp​
youtube-transcript-api​
github.com
whisper​
langchain​
github.com
opencv-python​
pytesseract​
pydub​
matplotlib​
langdetect​
System Dependencies:
FFmpeg​
github.com
Tesseract OCR​
Ensure that these dependencies are installed and properly configured on your system.​

Contributing

Contributions to enhance the functionality of this pipeline are welcome! Feel free to fork the repository and submit a pull request with your improvements.​
github.com
+1
github.com
+1

License

This project is licensed under the MIT License. See the LICENSE file for more details.​
github.com
+1
github.com
+1

Acknowledgements

This pipeline leverages several open-source tools and models. Special thanks to the developers and contributors of these projects for their invaluable work.​

This README provides an overview of the pipeline's functionality, installation instructions, usage guidelines, and other essential information. Customize it further based on your specific implementation details and preferences.​
