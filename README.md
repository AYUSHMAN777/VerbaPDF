# VerbaPDF 🧠📄

VerbaPDF is a full-stack AI-powered application that allows users to **upload PDF documents** and interact with them using **natural language queries**. It uses advanced **embedding techniques** and **LLMs (Large Language Models)** to retrieve relevant answers from the uploaded content.

---

## 🚀 Features

- 📄 Upload and parse PDF documents
- 🔐 Secure authentication via Clerk
- 🧠 Ask questions related to the uploaded PDF
- 🤖 Uses OpenAI + LangChain for LLM-based responses
- 🧬 Embedding and semantic search using Qdrant vector DB
- ⚙️ Background job processing using BullMQ

---

## 🛠 Tech Stack

### 🧑‍💻 Frontend
- **Next.js** – React framework for SSR and routing
- **Tailwind CSS** – Utility-first styling
- **shadcn/ui** – Accessible and beautiful UI components
- **Clerk** – Authentication and user session management

### 🖥 Backend
- **Express.js** – Lightweight web server
- **LangChain** – LLM orchestration and prompt templates
- **OpenAI** – GPT models for conversational intelligence
- **pdf-parse** – PDF content extraction
- **Multer** – Handles file uploads
- **Qdrant** – Vector database for storing embeddings
- **BullMQ** – Message queue for processing tasks asynchronously
- **CORS** – Cross-origin request support

---

## 📈 Architecture & Data Flow

1. **User Authentication**: Users log in using Clerk.
2. **PDF Upload**: Users upload PDFs via the frontend.
3. **File Handling**: PDFs are sent to the Express server and stored using Multer.
4. **PDF Parsing**: `pdf-parse` extracts the raw text from the document.
5. **Embedding Generation**: LangChain generates vector embeddings from document chunks.
6. **Vector Storage**: Embeddings are stored in Qdrant for later retrieval.
7. **Querying**: When a user asks a question, the system retrieves relevant chunks using semantic search from Qdrant.
8. **LLM Response**: OpenAI GPT model is used via LangChain to generate an intelligent answer.
9. **Job Queuing**: BullMQ ensures background embedding tasks don’t block the server.

---

## 📦 Setup Instructions

1. Clone the repository:
   ```bash
   git clone https://github.com/AYUSHMAN777/VerbaPDF.git
