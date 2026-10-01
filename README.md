# 📨 Chat with Gmail Inbox

### 🤖 RAG-Powered Gmail Assistant

A Retrieval-Augmented Generation (RAG) application that allows you to **chat with your Gmail inbox using natural language**.

The application connects to Gmail, retrieves email content, stores the information in a vector database, and uses an LLM to retrieve relevant context and generate accurate answers based on your emails.

## ✨ Features

* 📧 Connect to your Gmail Inbox
* 🔐 Secure Gmail OAuth authentication
* 🔎 Semantic search across emails
* 🧠 Retrieval-Augmented Generation (RAG)
* 🤖 OpenAI-powered responses
* 🗄️ ChromaDB vector database
* 💬 Ask natural-language questions about your emails
* ⚡ Streamlit web interface
* 🔒 Gmail read-only access

## 🛠️ Tech Stack

* **Python**
* **Streamlit**
* **Gmail API**
* **Google OAuth 2.0**
* **OpenAI**
* **ChromaDB**
* **Embedchain**
* **RAG**

## 🔄 How It Works

```text
Gmail Inbox
     ↓
Gmail API + OAuth
     ↓
Email Extraction
     ↓
Document Chunking
     ↓
OpenAI Embeddings
     ↓
ChromaDB
     ↓
Relevant Email Retrieval
     ↓
OpenAI LLM
     ↓
Answer
```

## 🚀 Installation

### 1. Clone the repository

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
cd ChatwithMail
```

### 2. Create a virtual environment

```bash
python -m venv venv
```

Activate it on Windows PowerShell:

```powershell
.\venv\Scripts\Activate.ps1
```

### 3. Install the required dependencies

```bash
pip install -r requirements.txt
```

### 4. Set up Gmail API

Go to the [Google Cloud Console](https://console.cloud.google.com/) and create a new project.

Navigate to:

```text
APIs & Services → Library → Gmail API
```

Enable the **Gmail API**.

Then configure the OAuth consent screen and create an **OAuth Client ID**.

Select:

```text
Desktop App
```

Download the credentials JSON file and rename it:

```text
credentials.json
```

Place it in the project root:

```text
ChatwithMail/
├── credentials.json
├── chat_gmail.py
├── requirements.txt
└── README.md
```

### 5. Configure OpenAI API Key

Create an OpenAI API key from the [OpenAI Platform](https://platform.openai.com/).

Create a `.env` file:

```env
OPENAI_API_KEY=your_openai_api_key
```

**Do not commit your API key or OAuth credentials to GitHub.**

Add the following to `.gitignore`:

```gitignore
venv/
.env
credentials.json
token.json
__pycache__/
```

### 6. Run the Streamlit App

```bash
streamlit run chat_gmail.py
```

The application will open in your browser.

## 💬 Example Queries

Once your Gmail inbox has been indexed, you can ask questions such as:

```text
What companies have contacted me for jobs?
```

```text
Summarize my recent interview emails.
```

```text
Which emails contain interview dates?
```

```text
Find emails related to internships.
```

```text
Which recruiters have contacted me?
```

```text
What deadlines are mentioned in my emails?
```

## 🧠 RAG Pipeline

The application doesn't send your entire inbox to the LLM for every question.

Instead:

```text
User Question
     ↓
Generate Query Embedding
     ↓
Search ChromaDB
     ↓
Retrieve Relevant Emails
     ↓
Provide Context to LLM
     ↓
Generate Answer
```

This allows the LLM to answer questions using information retrieved from your actual Gmail inbox.

## 🔒 Security

This application uses Gmail's OAuth authentication and requests read-only access to your inbox.

Never commit these files:

```text
credentials.json
token.json
.env
```

## 🚧 Future Improvements

* [ ] Email source citations
* [ ] Conversation memory
* [ ] Automatic email summarization
* [ ] Important email detection
* [ ] Deadline extraction
* [ ] Email categorization
* [ ] AI-generated reply drafts
* [ ] Gmail label filtering
* [ ] Date-based filtering
* [ ] Incremental email synchronization
* [ ] Agentic email workflows
* [ ] Docker deployment

## 👨‍💻 Author

**Shubham Singh**

Built with:

**Python • RAG • OpenAI • ChromaDB • Gmail API • Streamlit**
