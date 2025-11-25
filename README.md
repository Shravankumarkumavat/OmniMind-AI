# <img src="OmniMind.png" width="30" style="vertical-align: middle;"> OmniMind AI

<div align="center">

![OmniMind AI](https://img.shields.io/badge/OmniMind-AI-blue?style=for-the-badge)
![Python](https://img.shields.io/badge/Python-3.8+-green?style=for-the-badge&logo=python)
![Flask](https://img.shields.io/badge/Flask-2.0+-black?style=for-the-badge&logo=flask)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-yellow?style=for-the-badge&logo=javascript)
![License](https://img.shields.io/badge/License-MIT-red?style=for-the-badge)

**An intelligent multi-mode chatbot with document analysis, web search, and conversation memory**

</div>

---

## 🎯 Overview

OmniMind AI is a sophisticated chatbot application that combines the power of large language models with document understanding and web search capabilities. It features four distinct modes of operation, user authentication, and conversation memory management.

### Why OmniMind AI?

- 🧠 **4 Intelligent Modes** - Document, Web, Model, and Advanced
- 📄 **Document Analysis** - Upload and chat with PDFs, DOCX, TXT files
- 🌐 **Web Search** - Real-time internet search with answer synthesis
- 💬 **Conversation Memory** - Context-aware responses across chat sessions
- 🔒 **Secure Authentication** - User management with session control
- ⚡ **Real-Time Streaming** - ChatGPT-like streaming responses
- 📱 **Responsive UI** - Works on desktop, tablet, and mobile

---

## ✨ Features

### 🎨 Four Operating Modes

1. **📄 Document Mode**
   - Upload PDF, DOCX, or TXT files (up to 10MB)
   - Ask questions about document content
   - Smart chunking and vector search
   - Context aware
2. **🌐 Web Mode**
   - Real-time internet search for current information
   - Scrapes and analyzes 3-5 websites automatically
   - Multi-source answer synthesis
   - Query rewriting for better retrieval
3. **🧠 Model Mode**
   - Pure AI conversation with context of past chat
   - Uses model's pre-trained knowledge
   - Query understanding and clarification
   - Conversational and creative responses

4. **🚀 Advanced Mode**
   - Hybrid retrieval combining documents + memory
   - Episodic memory across conversation turns
   - Context-aware query rewriting
   - Most intelligent and powerful mode

### 🔐 Authentication & Security

- User registration and login
- SHA-256 password hashing
- Session-based authentication
- System passkey protection
- Secure cookie management

### 💬 Chat Management

- Multiple conversation sessions per user
- 10-turn limit per conversation (episodic memory)
- Automatic chat titling
- Conversation history with context retrieval
- Session switching and management
- Turn counter display with limit warnings

### 🧠 Advanced AI Features

- **Query Rewriting**: Reformulates questions for better retrieval
- **Intent Classification**: Understands user intent for optimal retrieval strategy selection
- **Episodic Memory**: Maintains context across conversation turns
- **Hybrid Retrieval**: Combines vector search with conversation context
- **Context-Aware Responses**: Uses last 5 turns for coherent dialogues
- **Smart Chunking**: 1000-token chunks with 200-token overlap
- **Top-K Retrieval**: Fetches 3 most relevant document chunks
- **Multi-Source Synthesis**: Combines information from multiple websites

### 🎨 Modern UI/UX

- Dark theme with blue gradients
- Smooth animations and transitions
- Real-time message streaming
- Drag & drop file upload
- Responsive design
- Loading states and error handling

---

## 🏗️ System Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                         Frontend (UI)                       │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌──────────┐     │
│  │  Login   │  │   Chat   │  │  Upload  │  │ Settings │     │
│  └──────────┘  └──────────┘  └──────────┘  └──────────┘     │
└─────────────────────────────────────────────────────────────┘
                              ↕ HTTP/REST
┌─────────────────────────────────────────────────────────────┐
│                   Chat Manager (Flask)                      │
│  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐          │
│  │    Auth     │  │   Session   │  │   Context   │          │
│  │  Management │  │  Management │  │  Retrieval  │          │
│  └─────────────┘  └─────────────┘  └─────────────┘          │
│ • User Authentication   • Multi-session      • Last N turns │
│ • Password Hashing      • Turn Limiting      • Memory Mgmt  │
└─────────────────────────────────────────────────────────────┘
                              ↕ HTTP/REST
┌─────────────────────────────────────────────────────────────┐
│                 LLM Server (Google Colab)                   │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌──────────┐     │
│  │ Mistral  │  │  FAISS   │  │   Web    │  │ Document │     │
│  │   LLM    │  │  Vector  │  │  Search  │  │ Processor│     │
│  └──────────┘  └──────────┘  └──────────┘  └──────────┘     │
│ • Streaming      • GPU Accel.    • DuckDuckGo    • RAG      │
│ • Query Rewrite  • Top-K Search  • Scraping      • Chunk    │
│ • Intent Class.  • Similarity    • Synthesis     • Embed    │
└─────────────────────────────────────────────────────────────┘
```

### Component Overview

| Component | Technology | Purpose |
|-----------|-----------|---------|
| **Frontend** | HTML/CSS/JavaScript | User interface and interaction |
| **Chat Manager** | Flask + Python | Session and user management |
| **LLM Server** | Mistral-7B + FAISS | AI inference and document search |
| **Storage** | JSON Files | User and session data persistence |
| **Deployment** | Google Colab + ngrok | Cloud hosting with public URL |

---

## 🛠️ Technologies Used

### AI/ML Stack
- **Mistral-7B-Instruct-v0.2** - Large language model for chat
- **Sentence-Transformers** - Text embeddings (all-MiniLM-L6-v2)
- **FAISS** - Vector database with GPU acceleration
- **LangChain** - Document processing and text splitting

### Intelligence Features
- **Query Rewriting** - Reformulates queries for better context retrieval
- **Intent Classification** - Identifies user intent and optimal response strategy
- **Episodic Memory** - Maintains conversation context across turns
- **Hybrid Retrieval** - Combines vector search with contextual understanding
- **Top-K Search** - Retrieves 3 most relevant chunks (configurable)
- **Smart Chunking** - RecursiveCharacterTextSplitter (1000/200 tokens)
- **Multi-Source Synthesis** - Aggregates information from multiple sources

### Backend
- **Flask** - Web framework
- **Flask-CORS** - Cross-origin resource sharing
- **PyPDF2** - PDF text extraction
- **python-docx** - DOCX processing
- **BeautifulSoup4** - Web scraping
- **DuckDuckGo Search API** - Web search

### Frontend
- **Vanilla JavaScript** - No frameworks needed
- **CSS3** - Modern styling with gradients
- **Font Awesome** - Icon library
- **HTML5** - Semantic markup

### Deployment
- **Google Colab** - Free GPU for LLM server
- **ngrok** - Secure tunneling for public access
- **JSON** - Lightweight data storage

---

## 📦 Installation

### Prerequisites

- Python 3.8 or higher
- Google Colab account (for LLM server)
- ngrok account (free tier)
- Modern web browser

### Step 1: Clone Repository

```bash
git clone https://github.com/yourusername/omnimind-ai.git
cd omnimind-ai
```

### Step 2: Set Up LLM Server (Google Colab)

1. Open Google Colab
2. Upload the LLM server notebook
3. Create a `.env` or Set variables file with:

```env
PASSKEY=your_secure_passkey
NGROK_AUTH_TOKEN=your_ngrok_token
HF_TOKEN = your_huggingface_token
```

4. Run all cells in the notebook
5. Copy the ngrok URL displayed

### Step 3: Set Up Chat Manager (Local)

1. Install dependencies:

```bash
pip install flask flask-cors python-dotenv pyngrok
```
or
```bash
pip install -r requiremnet.txt
```

2. Create `.env` file in the chat manager directory:

```env
LLM_SERVER_URL=your_ngrok_url_from_step2
PASSKEY=same_passkey_as_above
SECRET_KEY=your_secret_key_for_sessions
FRONTEND_URL=http://localhost:8000
NGROK_AUTH_TOKEN=your_ngrok_token
```

3. Run the chat manager:

```bash
python chat_manager.py
```

The server will start on `http://localhost:5002`

### Step 4: Set Up Frontend

1. Update `auth.html` and `index.html`:

```javascript
// In auth.html and index.html, update config
let config = {
    chatManagerUrl: 'http://localhost:5002',
    llmServerUrl: 'your_ngrok_url',
    currentUser: null
};
```

2. Serve the frontend:

**Option 1: Using Python**
```bash
python -m http.server 8000
```

**Option 2: Using Node.js**
```bash
npx http-server -p 8000
```

**Option 3: Using VS Code**
- Install "Live Server" extension
- Right-click on `auth.html` and select "Open with Live Server"

3. Open browser and navigate to:
```
http://localhost:8000/auth.html
```

---

## ⚙️ Configuration

### Environment Variables

#### LLM Server (.env)
```env
PASSKEY=test123                    # Secure passkey for API access
NGROK_AUTH_TOKEN=your_token          # ngrok authentication token
```

#### Chat Manager (.env)
```env
LLM_SERVER_URL=https://xxx.ngrok.io  # LLM server URL
PASSKEY=test123                    # Must match LLM server
SECRET_KEY=your_secret_flask_key     # Flask session secret
FRONTEND_URL=http://localhost:8000   # Frontend URL for CORS
NGROK_AUTH_TOKEN=your_token          # ngrok token (optional)
```

### System Settings

You can configure these in the settings modal:

- **Chat Manager URL**: `http://localhost:5002`
- **LLM Server URL**: Your Google Colab ngrok URL
- **Passkey**: Must match between all components

---

## 🚀 Usage

### 1. Register an Account

- Navigate to the registration page
- Enter your name, username, and password
- Provide the system passkey
- Click "Create Account"

### 2. Login

- Enter your username and password
- Provide the system passkey
- Click "Sign In"

### 3. Start a Conversation

- Click "New Conversation" button
- Select a mode (Document/Web/Model/Advanced)
- Type your message and press Enter
- The system automatically:
  - Classifies your intent
  - Rewrites query if needed (for better retrieval)
  - Retrieves relevant context (document or web)
  - Generates response with conversation memory

### 4. Upload Documents (Document/Advanced Mode)

- Click "Upload Doc" button
- Drag & drop or select a file (PDF/DOCX/TXT)
- System processes document:
  - Extracts text from file
  - Splits into 1000-token chunks (200 overlap)
  - Creates vector embeddings
  - Stores in FAISS database
- Start asking questions about the document
- Query rewriting ensures best retrieval results

### 5. Switch Between Sessions

- Click any conversation in the sidebar
- View conversation history
- Continue from where you left off

### 6. Manage Sessions

- Delete conversations using the trash icon
- Track turn count (X/10)
- Create multiple parallel conversations

---

## 📚 API Documentation

### Chat Manager Endpoints

#### Authentication

**POST /auth/register**
```json
{
  "name": "John Doe",
  "username": "johndoe",
  "password": "password123",
  "confirm_password": "password123",
  "passkey": "test123"
}
```

**POST /auth/login**
```json
{
  "username": "johndoe",
  "password": "password123",
  "passkey": "test123"
}
```

**POST /auth/logout**
```
No body required
```

**GET /auth/check**
```
Returns authentication status
```

#### Session Management

**GET /sessions**
```
Returns all user sessions
```

**POST /session/new**
```json
{
  "mode": "document"
}
```

**GET /session/{session_id}**
```
Returns session details
```

**DELETE /session/{session_id}**
```
Deletes session
```

#### Messaging

**POST /message**
```json
{
  "session_id": "chat_abc123",
  "role": "user",
  "content": "Hello!"
}
```

**GET /context/{session_id}?turns=5**
```
Returns conversation context
```

#### System

**GET /health**
```
Returns system health status
```

### LLM Server Endpoints

**POST /upload-document**
```json
{
  "passkey": "test123",
  "file_content": "base64_encoded_file",
  "file_name": "document.pdf",
  "session_id": "chat_abc123"
}
```

**POST /query**
```json
{
  "passkey": "test123",
  "query": "What is AI?",
  "mode": "document",
  "session_id": "chat_abc123",
  "conversation_context": "Previous conversation..."
}
```

**POST /clear-document**
```json
{
  "passkey": "test123",
  "session_id": "chat_abc123"
}
```

**GET /health**
```
Returns LLM server status
```


---

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Development Guidelines

- Follow PEP 8 style guide for Python code
- Use meaningful variable and function names
- Add comments for complex logic
- Test your changes thoroughly
- Update documentation as needed

---

## 🐛 Known Issues

- [ ] Web search may fail for some websites (blocked by bot detection)
- [ ] Large documents (>5MB) may take longer to process
- [ ] Session data is stored in JSON (not suitable for production scale)
- [ ] No support for images or multimedia files yet

---

## 🔮 Future Enhancements

### Planned Features
- [ ] **Advanced Query Understanding**
  - Multi-turn query refinement
  - Ambiguity detection and clarification
  - Query expansion techniques
- [ ] **Enhanced Memory System**
  - Long-term memory across sessions
  - User preference learning
  - Personalized responses
- [ ] **Multimedia Support**
  - Voice input/output integration
  - Image understanding capabilities
  - Video content analysis
- [ ] **Multi-language Support**
  - Automatic language detection
  - Translation capabilities
  - Cross-lingual retrieval
- [ ] **Export & Sharing**
  - Export conversations (PDF/JSON/Markdown)
  - Share chat links
  - Conversation templates
- [ ] **Advanced RAG Features**
  - Citation and source tracking
  - Confidence scoring
  - Fact verification
  - Multi-document reasoning
- [ ] **Infrastructure Improvements**
  - PostgreSQL database migration
  - Redis caching layer
  - Docker containerization
  - Kubernetes deployment
- [ ] **UI/UX Enhancements**
  - Message editing and regeneration
  - Code syntax highlighting
  - Markdown rendering
  - Dark/light theme toggle
  - Customizable chat interface

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 👨‍💻 Author

**Your Name**

- GitHub: [@Shravankumarkumavat](https://github.com/Shravankumarkumavat)
- LinkedIn: [Shravankumar Kumavat](https://linkedin.com/in/shravankumar-kumavat)
- Email: skumarkumavat@gmail.com

---

## 🙏 Acknowledgments

- **Mistral AI** for the amazing Mistral-7B model
- **Hugging Face** for model hosting and transformers library
- **Sentence-Transformers** for embedding models
- **Facebook AI** for FAISS vector database
- **LangChain** for document processing utilities
- **Flask** team for the excellent web framework
- **DuckDuckGo** for privacy-focused search API

---

## 📞 Support

If you have any questions or need help, feel free to:

- Open an issue on GitHub
- Email: skumarkumavat@gmail.com



---

<div align="center">

**Made with ❤️ by SK**

[⬆ Back to Top](#-omnimind-ai)

</div>
