
# 🤖 LLM Chatbot (FastAPI + Groq + Streamlit)

A clean and minimal end-to-end **LLM-based chatbot** built with **FastAPI** for the backend, **Groq LLM API** for inference, and **Streamlit** for the frontend UI.

This project demonstrates a **production-style architecture** with clear separation between frontend, backend, and LLM logic.

---

## 📌 Key Features

- 🔹 FastAPI backend with clean API design  
- 🔹 Groq LLM API integration  
- 🔹 Streamlit-based chat UI  
- 🔹 Secure API key handling using environment variables  
- 🔹 Request & response validation with Pydantic  
- 🔹 Scalable and extensible project structure  

---

## 🧠 System Architecture

```

User (Browser)
↓
Streamlit Frontend
↓  HTTP POST /chat
FastAPI Backend
↓
Groq LLM API
↓
FastAPI Response
↓
Streamlit UI

```

- Frontend handles **UI only**
- Backend handles **validation, orchestration, and security**
- LLM inference is done by **Groq**

---

## 📁 Project Structure

```

llm_chatbot/
│
├── app/                    # FastAPI Backend
│   ├── main.py             # Application entry point
│   ├── api/                # API routes
│   │   └── chat.py
│   ├── schemas/            # Request/Response models
│   │   └── chat.py
│   ├── services/           # LLM logic
│   │   └── groq_client.py
│   └── core/               # Configuration & settings
│       └── config.py
│
├── frontend/               # Streamlit Frontend
│   └── app.py
│
├── .env                    # Environment variables (not committed)
├── requirements.txt
└── README.md

````

---

## ⚙️ Setup & Installation

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/your-username/llm_chatbot.git
cd llm_chatbot
````

---

### 2️⃣ Create a Virtual Environment

```bash
python -m venv venv
source venv/bin/activate      # Linux / Mac
venv\Scripts\activate         # Windows
```

---

### 3️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

---

### 4️⃣ Configure Environment Variables

Create a `.env` file in the root directory:

```env
GROQ_API_KEY=your_groq_api_key_here
```

⚠️ **Never commit this file to GitHub**

---

## ▶️ Running the Application

### Start Backend (FastAPI)

```bash
uvicorn app.main:app --reload
```

Backend will be available at:

```
http://127.0.0.1:8000
```

Swagger API Docs:

```
http://127.0.0.1:8000/docs
```

---

### Start Frontend (Streamlit)

Open a new terminal and run:

```bash
streamlit run frontend/app.py
```

Frontend will be available at:

```
http://localhost:8501
```

---

## 💬 Example API Usage

### Request

**POST** `/chat`

```json
{
  "message": "Explain transformers in simple words"
}
```

### Response

```json
{
  "reply": "Transformers are models that understand relationships between words..."
}
```

---

## 🛠 Tech Stack

* **Python**
* **FastAPI**
* **Groq LLM API**
* **Streamlit**
* **Pydantic**
* **Uvicorn**

---

## 🚀 Future Improvements

* Chat history on backend
* Streaming token responses
* RAG (Retrieval-Augmented Generation)
* Authentication & rate limiting
* Dockerization
* Cloud deployment (AWS / GCP / Railway)

---

## 🔒 Security Notes

* API keys are stored in environment variables
* `.env` file is excluded using `.gitignore`
* LLM calls are handled only by the backend

---

## 📄 License

This project is intended for **learning and demonstration purposes**.

```
