# ConvoAI Assistant

**Fast • Mindful • Powered by 💙**

A clean, responsive full-stack AI chatbot web application built with **FastAPI** and the **Groq API** (`openai/gpt-oss-20b`), paired with a lightweight, mobile-friendly **HTML, CSS, and Vanilla JavaScript** frontend.

---

## Features

- **Low-Latency AI Responses:** Powered by Groq's inference engine (`openai/gpt-oss-20b`) via the OpenAI-compatible Python SDK.
- **Responsive Design:** Adapts seamlessly from a centered desktop card layout to an edge-to-edge mobile experience using `100dvh` viewport units.
- **Minimalist & Maintainable Frontend:** Built with clean semantic HTML, pure CSS, and Vanilla JavaScript using the Fetch API.
- **Interactive Chat UX:** Supports `Enter` key submission, automatic scroll-to-latest-message, disabled button state while awaiting responses, and graceful server error handling.

---

## Tech Stack

- **Backend:** Python, FastAPI, Uvicorn, OpenAI Python SDK, Pydantic, Python-Dotenv
- **AI Provider:** Groq API (`openai/gpt-oss-20b`)
- **Frontend:** HTML5, CSS3, JavaScript (ES6+), Font Awesome

---

## Project Structure

```text
convoai-assistant/
├── backend/
│   ├── main.py              # FastAPI server, CORS config & Groq API endpoint
│   └── .env                 # Environment variables (excluded from Git)
├── frontend/
│   ├── index.html           # Chat UI markup
│   ├── style.css            # Responsive desktop & mobile styling
│   ├── script.js            # Frontend messaging logic & API requests
│   └── logo.png             # ConvoAI Assistant logo
├── .gitignore               # Ignores .venv, .env, __pycache__, and OS files
├── LICENSE                  # MIT License
├── requirements.txt         # Python dependencies
└── README.md                # Project documentation
```

---

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/chhabilalpun/convoai-assistant.git
cd convoai-assistant
```

### 2. Create & Activate a Virtual Environment

**macOS / Linux:**
```bash
python3 -m venv .venv
source .venv/bin/activate
```

**Windows:**
```bash
python -m venv .venv
.venv\Scripts\activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure Environment Variables

Create a `.env` file inside the `backend/` directory and add your Groq API key:

```env
GROQ_API_KEY=your_groq_api_key_here
```

*(You can generate a free API key from the [Groq Console](https://console.groq.com/).)*

### 5. Run the Backend Server

From the root `convoai-assistant/` directory, start FastAPI with Uvicorn:

```bash
uvicorn backend.main:app --reload
```

The API will run at `[http://127.0.0.1:8000](http://127.0.0.1:8000)` (interactive Swagger docs available at `[http://127.0.0.1:8000/docs](http://127.0.0.1:8000/docs)`).

### 6. Launch the Frontend

Open `frontend/index.html` directly in your browser, or serve it using the **VS Code Live Server** extension (`[http://127.0.0.1:5500/frontend/index.html](http://127.0.0.1:5500/frontend/index.html)`).

---

## API Reference

### `POST /chat`

Sends a user message to the Groq language model and returns the generated reply.

**Request Body:**
```json
{
  "message": "Hello, how can you help me today?"
}
```

**Response Body (`200 OK`):**
```json
{
  "reply": "Hello! 👋 How can I assist you today?"
}
```

**Example `curl` Request:**
```bash
curl -X POST "http://127.0.0.1:8000/chat" \
  -H "Content-Type: application/json" \
  -d '{"message": "Hello!"}'
```

---

## License

This project is open-source and available under the [MIT License](LICENSE).