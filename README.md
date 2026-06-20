# 🧠 Recap AI

> Transform conversations into actionable insights.

Recap AI is a **multilingual conversational intelligence platform** that enables users to analyze YouTube videos and audio recordings through AI-powered transcription, summarization, insight extraction, and Retrieval-Augmented Generation (RAG).

The system converts unstructured spoken content into structured knowledge by generating transcripts, summaries, action items, key decisions, open questions, and interactive Q&A experiences.

---

## ✨ Features

### 🎥 Multimedia Processing

* Analyze YouTube videos using URLs
* Process local audio and video recordings
* Support meetings, lectures, podcasts, interviews, and webinars

### 🌍 Multilingual Intelligence

* English transcription support
* Hinglish (Hindi + English mixed conversations) support
* Translation layer for improved understanding

### 📝 AI-Powered Insight Extraction

* Automatic title generation
* Concise summaries
* Action item extraction
* Key decision identification
* Open question detection

### 💬 Conversational Q&A with RAG

* Ask natural language questions about the content
* Grounded responses using transcript context
* Reduces hallucinations by restricting answers to retrieved information

### 🎨 Interactive Dashboard

* Built using Streamlit
* Modern conversational interface
* Chat history support
* Real-time processing feedback

---

## 🏗️ Architecture

```text
                ┌───────────────────────┐
                │   Input Sources       │
                │───────────────────────│
                │ • YouTube URLs        │
                │ • Local Recordings    │
                └──────────┬────────────┘
                           │
                           ▼
                ┌───────────────────────┐
                │  Audio Processing     │
                │ yt-dlp + pydub        │
                └──────────┬────────────┘
                           │
                           ▼
                ┌───────────────────────┐
                │ Whisper Transcription │
                └──────────┬────────────┘
                           │
                           ▼
                ┌───────────────────────┐
                │ Translation Layer     │
                │ (Hinglish Support)    │
                └──────────┬────────────┘
                           │
                           ▼
      ┌─────────────────────────────────────────┐
      │        Insight Extraction               │
      │─────────────────────────────────────────│
      │ • Title Generation                      │
      │ • Summarization                         │
      │ • Action Items                          │
      │ • Key Decisions                         │
      │ • Open Questions                        │
      └────────────────┬────────────────────────┘
                       │
                       ▼
            ┌────────────────────┐
            │  Embedding Model   │
            │ SentenceTransformers
            └─────────┬──────────┘
                      │
                      ▼
            ┌────────────────────┐
            │ ChromaDB Vector DB │
            └─────────┬──────────┘
                      │
                      ▼
            ┌────────────────────┐
            │ LangChain LCEL     │
            │ + Mistral RAG      │
            └─────────┬──────────┘
                      │
                      ▼
            ┌────────────────────┐
            │ Interactive Chat   │
            │ Question Answering │
            └────────────────────┘
```

---

## 🛠️ Tech Stack

### Frontend

* Streamlit

### Backend / AI

* Python
* LangChain (LCEL)
* Mistral AI
* ChromaDB
* Sentence Transformers

### Speech Processing

* OpenAI Whisper
* PyTorch
* Torchaudio

### Multimedia

* yt-dlp
* FFmpeg
* pydub

### Utilities

* Deep Translator
* Python Dotenv

---

## 📂 Project Structure

```text
Recap-AI/
│
├── app.py                 # Streamlit interface
├── main.py                # CLI pipeline entry point
├── requirements.txt
├── README.md
│
├── core/
│   ├── extractor.py       # Action items, decisions, questions
│   ├── rag_engine.py      # RAG pipeline and Q&A
│   ├── summarizer.py      # Summaries and title generation
│   ├── transcriber.py     # Whisper transcription
│   └── vector_store.py    # ChromaDB operations
│
├── utils/
│   └── audio_processor.py # Audio extraction and preprocessing
│
└── downloads/             # Temporary downloaded media
```

---

## 🚀 Getting Started

### Clone the Repository

```bash
git clone https://github.com/MS12code/Recap-AI.git
cd Recap-AI
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

### Install FFmpeg

Verify installation:

```bash
ffmpeg -version
```

### Configure Environment Variables

Create a `.env` file:

```env
MISTRAL_API_KEY=your_api_key_here
```

---

## ▶️ Run the Application

### Streamlit Dashboard

```bash
streamlit run app.py
```

Open:

```text
http://localhost:8501
```

### Command Line Interface

```bash
python main.py
```

The CLI supports both:

* YouTube URLs
* Local audio/video files

---

## 💡 Example Questions

* What were the major decisions discussed?
* Summarize this meeting in bullet points.
* What action items were assigned?
* What unresolved questions remain?
* What did the speaker say about the project timeline?
* What were the next steps agreed upon?

---

## 🔮 Future Enhancements

* Speaker diarization
* Timestamped citations
* PDF report exports
* Multi-document querying
* Additional Indian language support
* Cloud deployment support

---

## 👩‍💻 Author

**Medha Sharma**

Built with ❤️ to make conversations more searchable, actionable, and accessible.

---
