# 🤖 Q&A Chatbot With Ollama

[![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)](https://www.python.org/)
[![LangChain](https://img.shields.io/badge/LangChain-Framework-green.svg)](https://www.langchain.com/)
[![Streamlit](https://img.shields.io/badge/Streamlit-App-red.svg)](https://streamlit.io/)
[![License](https://img.shields.io/badge/License-Educational-lightgrey.svg)](#-license)

An AI-powered Question & Answer chatbot built with **Python, LangChain, Streamlit, and Ollama**. Chat with locally running, open-source LLMs (Llama 3, Mistral) through a clean, interactive web interface — no API keys or cloud inference required for the core chat experience.

---

## 🚀 Features

- 💬 Interactive Question & Answer chatbot
- 🧠 Runs fully open-source LLMs locally via Ollama
- 🔄 Supports **Llama 3** and **Mistral** (easily extendable to other Ollama models)
- 🔗 Built with **LangChain** for prompt templating and LLM orchestration
- 🖥️ Clean, responsive web interface using **Streamlit**
- 📊 **LangSmith** integration for tracing, debugging, and monitoring
- ⚙️ Model selection directly from the sidebar
- 🌡️ Adjustable **temperature** and **max tokens** for response control
- 🔒 Runs entirely on your machine — your data never leaves your system

---

## 🛠️ Tech Stack

| Category | Tools |
|---|---|
| Language | Python |
| LLM Orchestration | LangChain |
| Local Inference | Ollama |
| Models | Llama 3, Mistral |
| UI | Streamlit |
| Observability | LangSmith |
| Config | python-dotenv |

---

## 🏗️ Project Architecture

```text
User
  │
  ▼
Streamlit Interface
  │
  ▼
LangChain Prompt Template
  │
  ▼
Ollama Runtime
  │
  ├── Llama 3
  └── Mistral
  │
  ▼
LLM Response
  │
  ▼
Streamlit Interface (displayed to User)
```

---

## ⚙️ How It Works

1. The user enters a question through the Streamlit interface.
2. The selected open-source model is loaded via Ollama.
3. LangChain builds a structured prompt from the user's input.
4. The prompt is sent to the selected local LLM.
5. The model generates a response.
6. The response is rendered back in the Streamlit UI.
7. (Optional) LangSmith traces the full run for monitoring and debugging.

---

## 📂 Project Structure

```text
Q-A_Chatbot_With_Ollama/
│
├── app.py              # Main Streamlit application
├── requirements.txt    # Python dependencies
├── .env                # Environment variables (not committed)
├── .gitignore
├── README.md
└── venv/                # Local virtual environment (not committed)
```

---

## 🔧 Installation

### 1. Clone the repository
```bash
git clone https://github.com/Aswinsurya-sivakumar/Q-A_Chatbot_With_Ollama.git
cd Q-A_Chatbot_With_Ollama
```

### 2. Create a virtual environment
```bash
python -m venv venv
```

### 3. Activate the virtual environment

**Windows:**
```bash
venv\Scripts\activate
```

**Linux / macOS:**
```bash
source venv/bin/activate
```

### 4. Install dependencies
```bash
pip install -r requirements.txt
```

---

## 🦙 Ollama Setup

1. [Install Ollama](https://ollama.com/download) and make sure it's running.
2. Pull the required models:

```bash
ollama pull llama3
ollama pull mistral
```

3. Once pulled, select your preferred model from the Streamlit sidebar at runtime.

---

## 🔐 Environment Variables

Create a `.env` file in the project root:

```env
LANGCHAIN_API_KEY=your_langsmith_api_key
LANGCHAIN_TRACING_V2=true
LANGCHAIN_PROJECT=qa-chatbot-ollama
```

> ⚠️ **Security note:** Never commit your `.env` file or real API keys to GitHub. Add `.env` to your `.gitignore`.

---

## ▶️ Run the Application

```bash
streamlit run app.py
```

The app will automatically open in your default browser at `http://localhost:8501`.

---

## 💡 Example

**Input:**
```text
What is Machine Learning?
```

**Output:** The selected Ollama model processes the question through the LangChain pipeline and returns a generated response directly in the chat UI — adjustable in real time via the temperature and token-limit controls.

---


