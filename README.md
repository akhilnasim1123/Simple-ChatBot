# 🤖 Simple-ChatBot

A full-stack, AI-powered chatbot application utilizing OpenAI's GPT-3 model. This project features a FastAPI backend for handling AI logic and a React-based frontend styled with Tailwind CSS, offering an intuitive and interactive user interface with integrated speech recognition.

---

## ✨ Features

- **Conversational AI**: Powered by OpenAI's language models.
- **Speech Recognition**: Integrated React speech recognition for voice-to-text inputs.
- **FastAPI Backend**: Fast, asynchronous backend handling chat sessions and OpenAI moderation checks.
- **Content Moderation**: Automatically checks user and bot messages against OpenAI's Content Policy.
- **Modern UI**: Built with React and stylish Tailwind CSS.

---

## 💻 Tech Stack

### Frontend
- **Framework**: React.js (`create-react-app`)
- **Styling**: Tailwind CSS
- **HTTP Client**: Axios
- **Speech Integration**: `react-speech-recognition`
- **Other Utilities**: `react-loader-spinner`

### Backend
- **Framework**: FastAPI
- **Server**: Uvicorn
- **AI Model Integration**: OpenAI API
- **Environment Management**: `python-dotenv`
- **Session Management**: `starlette.middleware.sessions`

---

## 📂 Project Structure

```text
Simple-ChatBot/
├── ChatGPT/                  # Backend directory
│   ├── app.py                # FastAPI endpoints & server configuration
│   ├── main.py               # OpenAI integration & core logic
│   ├── datas/                # Contains initial session prompt data (e.g., data.txt)
│   └── manage.py             # Optional Django helper
└── chatbot/                  # Frontend directory
    ├── package.json          # Node dependencies and scripts
    ├── src/                  # React components & source code
    ├── public/               # Static assets
    └── tailwind.config.js    # Tailwind configuration
```

---

## 🚀 Getting Started

Follow these steps to set up the project locally on your machine.

### Prerequisites

- [Node.js](https://nodejs.org/) (v14 or above recommended)
- [Python 3.8+](https://www.python.org/downloads/)
- An active [OpenAI API Key](https://platform.openai.com/account/api-keys)

### 1. Clone the repository

```bash
git clone https://github.com/your-username/Simple-ChatBot.git
cd Simple-ChatBot
```

### 2. Environment Variables Configuration

Create a `.env` file inside the `ChatGPT` directory or the root directory depending on your execution path. The backend requires a `.env` file to securely load secret keys.

Create a `.env` file and add the following context:

```env
OPENAI_API_KEY=your_openai_api_key_here
SECRET_KEY=your_session_secret_key_here
```
*(Note: Ensure that your `openai.api_key` configuration in `main.py` properly references the environment variable instead of using a hardcoded string!)*

### 3. Backend Setup

Open a new terminal session and navigate to the backend folder:

```bash
cd ChatGPT
```

Install the required Python dependencies (preferably inside a virtual environment):

```bash
pip install fastapi uvicorn openai python-dotenv starlette
```

Start the FastAPI backend server:

```bash
python app.py
```
> **Note**: The backend engine runs on port `8000` by default. If port `8000` is already in use, you may change it (e.g., to `8001`) inside `app.py`.

### 4. Frontend Setup

Open another terminal session and navigate to the frontend folder:

```bash
cd chatbot
```

Install the Node dependencies:

```bash
npm install
```

Start the React development server:

```bash
npm start
```

---

## 💡 Usage

1. Verify that your backend is running at `http://localhost:8000` (or `http://127.0.0.1:8000`).
2. Verify that your frontend is running and viewable at `http://localhost:3000`.
3. Start interacting! Type your messages or use voice input to chat with the AI. The backend will seamlessly store session chat logs to maintain context throughout the conversation.

---

## 🛡️ Moderation & Safety

This chatbot includes a built-in safety check using OpenAI's Moderation API (`openai.Moderation.create()`). If either the user's input or the bot's generated response violates OpenAI's safety policies, the message is blocked and an appropriate alert is returned, maintaining a safe chatting environment.
