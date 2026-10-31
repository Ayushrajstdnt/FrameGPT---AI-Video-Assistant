# 🎬 FrameGPT – AI Video Assistant

### Your Videos. Your Meetings. Your AI Assistant.

FrameGPT is an AI-powered video and meeting assistant that transforms YouTube videos, audio recordings, and video files into searchable, intelligent knowledge sources.

Powered by **Retrieval-Augmented Generation (RAG)**, FrameGPT allows users to transcribe meetings, generate structured summaries, extract important insights, and interact with video content through natural language conversations.

Instead of manually watching long recordings or searching through transcripts, users can simply ask questions and receive context-aware answers based on the video content.

---

## 🚀 Key Features

### 🎥 1. Multiple Input Sources
- Process YouTube videos using their URLs.
- Upload audio and video files.
- Extract audio for transcription and processing.

### 🎙️ 2. Multilingual Transcription
- **OpenAI Whisper:** Local speech-to-text transcription for English meetings.
- **Sarvam AI:** Hindi and Hinglish meeting transcription.
- Convert spoken conversations into searchable text.

### 📝 3. AI-Powered Meeting Summarization
Automatically generates structured meeting reports containing:
- Meeting summaries in bullet points.
- Important discussion highlights.
- Key decisions made during meetings.
- Action items with assigned owners and deadlines.
- Open questions and follow-up tasks.

### 🧠 4. RAG-Based Video Chat
Interact with your video content using natural language.

- Ask questions about specific discussions.
- Retrieve relevant information from video transcripts.
- Generate context-aware responses using semantic search.
- Store and retrieve document embeddings using ChromaDB.
- Use LangChain LCEL to connect retrieval and LLM generation.

### 📄 5. Report Export
- Export meeting summaries and reports as PDF.
- Download reports in TXT format.
- Keep important meeting information organized and accessible.

---

## 🏗️ How FrameGPT Works

FrameGPT follows a Retrieval-Augmented Generation (RAG) pipeline.

```text
             USER INPUT
                  |
          +-------+-------+
          |               |
      YouTube URL      Audio/Video
          |               |
          +-------+-------+
                  |
            Audio Extraction
                  |
                  v
             Transcription
                  |
        +---------+---------+
        |                   |
     Whisper              Sarvam AI
     (English)          (Hindi/Hinglish)
        |                   |
        +---------+---------+
                  |
                  v
           Transcript Text
                  |
                  v
          Text Processing
                  |
                  v
          Text Chunking
                  |
                  v
       HuggingFace Embeddings
                  |
                  v
            ChromaDB
          (Vector Store)
                  |
          +-------+-------+
          |               |
       Retrieval       Summarization
          |               |
     User Query       Meeting Report
          |
          v
     Semantic Search
          |
          v
    Relevant Context
          |
          v
       Mistral AI
      (LLM Generation)
          |
          v
    Contextual Answer
```

### Understanding the RAG Pipeline

**1. Data Ingestion**

The application accepts YouTube URLs or uploaded audio/video files.

**2. Transcription**

Audio is converted into text using Whisper or Sarvam AI, depending on the language.

**3. Text Chunking**

The transcript is divided into smaller chunks to make retrieval more efficient.

**4. Embedding Generation**

Hugging Face embedding models convert text chunks into numerical vector representations.

**5. Vector Storage**

The generated embeddings are stored in ChromaDB for efficient similarity-based retrieval.

**6. Semantic Search**

When a user asks a question, the query is converted into an embedding and compared with stored vectors using similarity search.

**7. LLM Response Generation**

Relevant transcript chunks are passed as context to Mistral AI through a LangChain pipeline to generate a context-aware response.

---

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| Python | Core application logic |
| Streamlit | Interactive user interface |
| OpenAI Whisper | Local speech transcription |
| Sarvam AI | Hindi and Hinglish transcription |
| LangChain LCEL | RAG pipeline orchestration |
| Mistral AI | LLM-based response generation |
| ChromaDB | Vector database |
| Hugging Face | Local text embeddings |
| yt-dlp | YouTube audio extraction |
| Pydub | Audio processing |
| ReportLab | PDF report generation |
| python-dotenv | Environment variable management |

---

## 📂 Project Structure

```text
FrameGPT/
│
├── core/
│   └── Core application and processing modules
│
├── utils/
│   └── Helper functions and utilities
│
├── app.py
│   └── Streamlit application interface
│
├── main.py
│   └── Application entry point
│
├── test.py
│   └── Testing and validation
│
├── Requirements.txt
│   └── Python dependencies
│
├── .gitignore
│   └── Git ignored files
│
└── README.md
    └── Project documentation
```

---

## ⚙️ Installation & Setup

### Prerequisites

- Python 3.10 or 3.11
- Git
- FFmpeg
- Mistral AI API key
- Sarvam AI API key

### 1. Clone the Repository

```bash
git clone https://github.com/Ayushrajstdnt/FrameGPT---AI-Video-Assistant.git
```

### 2. Navigate to the Project Directory

```bash
cd FrameGPT---AI-Video-Assistant
```

### 3. Create a Virtual Environment

```bash
python -m venv venv
```

Activate the environment:

**Windows:**

```bash
venv\Scripts\activate
```

**Linux / macOS:**

```bash
source venv/bin/activate
```

### 4. Install Dependencies

```bash
pip install -r Requirements.txt
```

### 5. Configure Environment Variables

Create a `.env` file in the project root directory.

```env
MISTRAL_API_KEY=your_mistral_api_key
SARVAM_API_KEY=your_sarvam_api_key
```

Use the exact variable names expected by your application code.

**Important:** Never upload your `.env` file or expose API keys on GitHub.

### 6. Run the Application

```bash
streamlit run app.py
```

Open the local Streamlit URL displayed in your terminal.

---

## 🔍 Why RAG in FrameGPT?

Traditional AI chatbots generally respond using information learned during model training or information supplied directly in a prompt.

FrameGPT uses Retrieval-Augmented Generation to ground answers in the actual meeting or video transcript.

The RAG approach provides:

- Context-aware question answering.
- Retrieval of relevant meeting discussions.
- Reduced dependence on the LLM's general knowledge for meeting-specific answers.
- The ability to work with different video and meeting transcripts.
- A searchable knowledge base built from uploaded content.

---

## 🔮 Future Enhancements

- [ ] Timestamp-based video navigation.
- [ ] Support for multiple languages.
- [ ] Multiple video conversations in a single workspace.
- [ ] Improved speaker identification.
- [ ] Conversation history.
- [ ] Advanced transcript search.
- [ ] Improved retrieval using metadata filtering.
- [ ] Real-time meeting transcription.
- [ ] Better source references for generated answers.

---

## 🎯 Project Objective

The goal of FrameGPT is to make video and meeting content more accessible, searchable, and useful through Generative AI and Retrieval-Augmented Generation.

It combines speech recognition, vector embeddings, semantic search, and LLM-powered generation into a unified AI assistant.

**Stop watching hours of recordings. Start interacting with your knowledge.**

---

## 👨‍💻 Author

**Ayush Raj**

B.Tech – Computer Science & Engineering (Data Science)

GitHub: [Ayushrajstdnt](https://github.com/Ayushrajstdnt)

Project: [FrameGPT – AI Video Assistant](https://github.com/Ayushrajstdnt/FrameGPT---AI-Video-Assistant)

---

*FrameGPT – Turning Video Content into Conversational Knowledge.*
