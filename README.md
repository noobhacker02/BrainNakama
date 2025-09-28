# AI Learning Assistant

[![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)](https://www.python.org/)
[![Flask](https://img.shields.io/badge/flask-%23000.svg?style=for-the-badge&logo=flask&logoColor=white)](https://flask.palletsprojects.com/)
[![OpenAI](https://img.shields.io/badge/OpenAI-412991?style=for-the-badge&logo=openai&logoColor=white)](https://openai.com/)
[![PyMuPDF](https://img.shields.io/badge/PyMuPDF-412991?style=for-the-badge&logo=python&logoColor=white)](https://pymupdf.readthedocs.io/en/latest/)
[![Tesseract OCR](https://img.shields.io/badge/Tesseract%20OCR-F8991D?style=for-the-badge&logo=tesseract&logoColor=white)](https://tesseract-ocr.github.io/)
[![YouTube API](https://img.shields.io/badge/YouTube%20API-FF0000?style=for-the-badge&logo=youtube&logoColor=white)](https://developers.google.com/youtube/v3)
[![Socket.IO](https://img.shields.io/badge/Socket.io-010101?style=for-the-badge&logo=socket.io&logoColor=white)](https://socket.io/)

This project is an **AI-powered learning assistant** designed to provide personalized study recommendations, answer user queries, and assist with document analysis. It features a modular architecture, offering a versatile platform for various learning needs.

## ✨ Features

* **Intelligent Chat Assistant:**
    * Powered by a **Mistral 7B LLM** (local inference via LM Studio) for well-reasoned and helpful answers.
    * Engages in conversational interactions to provide information and guidance.
* **PDF Savior (Document OCR & Q&A):**
    * Upload PDF and image files for text extraction using **Tesseract OCR** (via PyMuPDF for PDFs).
    * Summarizes and allows querying the extracted document content using the integrated LLM.
* **YouTube Aider (Video Search & Recommendations):**
    * Search for YouTube videos directly within the platform.
    * Displays video links, titles, and thumbnails for easy access to educational content.
* **Modular Architecture:** Built with Flask, allowing for easy expansion and integration of new functionalities.
* **Lightweight UI:** A simple and intuitive HTML/CSS user interface.

## 🛠️ Tech Stack

* **Backend Framework:** Flask
* **Real-time Communication:** Flask-SocketIO
* **LLM Integration:** OpenAI Python client (configured for local LM Studio inference)
* **Language Model:** Mistral 7B Instruct v0.2 GGUF (used locally)
* **PDF Processing:** PyMuPDF (fitz)
* **Optical Character Recognition (OCR):** PyTesseract
* **Image Processing:** Pillow (PIL)
* **YouTube API:** Google API Client for Python (`googleapiclient.discovery`)
* **Frontend:** HTML, CSS, JavaScript


## 🤝 Images
![image](https://github.com/user-attachments/assets/5be6fc5f-4f10-4466-9715-06d0cdb3e33f)
![image](https://github.com/user-attachments/assets/dd5045b9-9dd4-4323-84b4-86af698da15e)
![image](https://github.com/user-attachments/assets/4c4bfbfc-3122-4a96-9932-6f5aaa42334f)
![image](https://github.com/user-attachments/assets/09d35366-b937-4d9f-aba3-835b8532ab4c)



## ⚙️ Getting Started

To get this project up and running locally, follow these steps.

### Prerequisites

* **Python 3.x:** Ensure Python is installed on your system.
* **pip:** Python's package installer.
* **Tesseract OCR:** [Install Tesseract OCR](https://tesseract-ocr.github.io/tessdoc/Installation.html) on your operating system. Make sure it's added to your system's PATH.
* **LM Studio:** Download and install [LM Studio](https://lmstudio.ai/). You will need to download the `TheBloke/Mistral-7B-Instruct-v0.2-GGUF/mistral-7b-instruct-v0.2.Q4_K_S.gguf` model within LM Studio and run its local server.
* **YouTube Data API Key:** Obtain a [YouTube Data API v3 key](https://developers.google.com/youtube/v3/getting-started).

### Installation

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/your-username/your-repository-name.git](https://github.com/your-username/your-repository-name.git)
    cd your-repository-name
    ```

2.  **Create a virtual environment (recommended):**
    ```bash
    python -m venv venv
    source venv/bin/activate # On Windows use `venv\Scripts\activate`
    ```

3.  **Install Python dependencies:**
    ```bash
    pip install -r requirements.txt
    ```
    *(Note: You'll need to create a `requirements.txt` file from your current environment. You can generate one using `pip freeze > requirements.txt`)*

4.  **Configure API Keys:**
    * Open `app.py`.
    * Replace `"ADD YOUR KEY"` with your actual **YouTube Data API Key**.
    * Ensure the `client = OpenAI(...)` line is correctly pointing to your LM Studio server (default `http://localhost:1234/v1`).

### Running LM Studio

1.  Open LM Studio.
2.  Navigate to the "Discover" tab and search for `Mistral-7B-Instruct-v0.2-GGUF`. Download `mistral-7b-instruct-v0.2.Q4_K_S.gguf`.
3.  Go to the "Local Inference Server" tab (the chat icon on the left).
4.  Select the downloaded `mistral-7b-instruct-v0.2.Q4_K_S.gguf` model.
5.  Click "Start Server." Ensure it's running on `http://localhost:1234`.

### Running the Flask Application

1.  **Start the Flask development server:**
    ```bash
    python app.py
    ```

2.  **Access the application:**
    Open your web browser and go to `http://127.0.0.1:5000/`.

## 🚀 Usage

Upon starting the application, you'll be greeted by a landing page with options:

* **Chat Assistant:** Interact with the Mistral 7B LLM for general queries and learning assistance.
* **YouTube Aider:** Search for educational videos on YouTube.
* **PDF Savior:** Upload PDF or image files to extract text, summarize, or ask questions about their content.

## 📂 Project Structure
.
├── app.py                     # Main Flask application file<br>
├── requirements.txt           # Python dependencies<br>
├── templates/<br>
│   ├── index.html             # Landing page<br>
│   ├── chat_assistant.html    # Chat interface<br>
│   ├── youtube_aider.html     # YouTube search interface<br>
│   ├── pdf_savior.html        # PDF upload and display interface<br>
│   ├── display_text.html      # Displays extracted text from PDF/image<br>
│   └── display_file.html      # Displays uploaded image file<br>
├── uploads/                   # Directory for uploaded files (created automatically)<br>
└── static/                    # For CSS, JS, images (if any)<br>
├── css/<br>
└── js/<br>

*(Note: You'll need to verify and create the actual HTML files in your `templates` directory and CSS/JS in `static` based on your frontend implementation.)*

*(Note: You'll need to verify and create the actual HTML files in your `templates` directory and CSS/JS in `static` based on your frontend implementation.)*

## 🤝 Contributing

Contributions are welcome! If you have suggestions for improvements, new features, or bug fixes, please feel free to:

1.  Fork the repository.
2.  Create a new branch (`git checkout -b feature/YourFeatureName`).
3.  Make your changes and commit them (`git commit -m 'Add Your Feature'`).
4.  Push to the branch (`git push origin feature/YourFeatureName`).
5.  Open a Pull Request.

## 📄 License

Distributed under the MIT License. See `LICENSE` for more information.

## 👤 Author

**Talha**
* *Add your Portfolio/GitHub/LinkedIn links here*

Brain Nakama

https://github.com/user-attachments/assets/83e46e35-8f12-4a0f-a891-7246d534f3ac
