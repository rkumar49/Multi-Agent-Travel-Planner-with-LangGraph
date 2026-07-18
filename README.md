# TripMate AI - Multi-Agent Travel Planner with LangGraph

An intelligent multi-agent travel planning system built with LangGraph that helps users plan complete trips with flight recommendations, hotel suggestions, and detailed itineraries.

## 🚀 Features

- **Multi-Agent Architecture**: Uses specialized agents for different tasks:
  - Flight Agent: Searches and recommends flights
  - Hotel Agent: Finds accommodation options
  - Itinerary Agent: Creates day-by-day travel plans
  - Final Agent: Compiles everything into a comprehensive response
- **Real-time Flight Data**: Integrates with AviationStack API for live flight information
- **Smart Search**: Uses Tavily API for intelligent web searches
- **LLM-Powered**: Powered by Groq's Llama 3.3 70B model for natural language understanding
- **Persistent Memory**: PostgreSQL checkpointer for conversation state management
- **REST API**: FastAPI backend for easy integration
- **Container Ready**: Docker support for easy deployment

## 🛠️ Tech Stack

- **LangGraph**: Agent orchestration framework
- **LangChain**: LLM integration and tools
- **Groq**: Llama 3.3 70B model
- **FastAPI**: Web framework
- **PostgreSQL**: Database with pgvector for state management
- **Docker**: Containerization
- **Python 3.11+**: Core programming language

## 📁 Project Structure

```
TripMate-AI/
├── app.py                 # FastAPI application entry point
├── backend.py             # Core agent logic and graph definition
├── tools/
│   ├── flight_tool.py    # Flight search functionality
│   └── tavily_tool.py    # Web search functionality
├── static/
│   └── index.html        # Frontend interface
├── docker-compose.yml    # Docker orchestration
├── Dockerfile            # Container configuration
├── requirements.txt      # Python dependencies
├── .env                  # Environment variables (not in git)
└── README.md            # This file
```

## 🔧 Installation

### Prerequisites
- Python 3.11 or higher
- PostgreSQL database (or use Render's free tier)
- API keys (see below)

### Local Setup

1. **Clone the repository**
```bash
git clone https://github.com/rkumar49/Multi-Agent-Travel-Planner-with-LangGraph.git
cd Multi-Agent-Travel-Planner-with-LangGraph
```

2. **Create and activate virtual environment**
```bash
python -m venv .venv
# On Windows:
.\.venv\Scripts\Activate.ps1
# On macOS/Linux:
source .venv/bin/activate
```

3. **Install dependencies**
```bash
pip install -r requirements.txt
```

4. **Configure environment variables**
Create a `.env` file in the root directory:
```env
GROQ_API_KEY=your_groq_api_key
AVIATIONSTACK_API_KEY=your_aviationstack_api_key
TAVILY_API_KEY=your_tavily_api_key
DATABASE_URL=your_postgresql_url
LANGSMITH_TRACING=true
LANGSMITH_ENDPOINT=https://api.smith.langchain.com
LANGSMITH_API_KEY=your_langsmith_api_key
LANGSMITH_PROJECT=TripMate-AI
DEFAULT_ORIGIN_IATA=DAC
```

5. **Run the application**
```bash
python app.py
```

6. **Open in browser**
```
http://localhost:8000
```

### 🐳 Docker Setup

1. **Build and run with Docker Compose**
```bash
docker-compose up --build
```

2. **Access the application**
```
http://localhost:8000
```

## 🔑 API Keys Required

To run this application, you'll need the following API keys:

| Service | Purpose | Get it from |
|---------|---------|-------------|
| Groq | LLM for travel planning | [Groq Console](https://console.groq.com/keys) |
| AviationStack | Flight data | [AviationStack](https://aviationstack.com/) |
| Tavily | Web search | [Tavily](https://tavily.com/) |
| LangSmith | Tracing and debugging | [LangSmith](https://smith.langchain.com/) |
| PostgreSQL | Persistent storage | Render or your own server |

## 🤖 How It Works

### Agent Workflow

1. **User Input**: User provides travel destination and preferences
2. **Flight Agent**: Searches for available flights
3. **Hotel Agent**: Finds accommodation options
4. **Itinerary Agent**: Creates a day-by-day plan
5. **Final Agent**: Compiles everything into a beautiful response

### State Management

The system maintains state using PostgreSQL checkpointer, allowing:
- Conversation persistence
- Multi-turn conversations
- Session management with thread IDs

## 🌐 Deployment

### Deploy on Render

1. Push your code to GitHub
2. Create a new Web Service on Render
3. Connect your repository
4. Add environment variables
5. Deploy!

### Deploy on Railway

1. Push your code to GitHub
2. Create a new project on Railway
3. Connect your repository
4. Add environment variables
5. Deploy!

## 🧪 Testing

Test the API endpoints:

```bash
# Health check
curl http://localhost:8000/health

# Send a travel query
curl -X POST http://localhost:8000/chat \
  -H "Content-Type: application/json" \
  -d '{"message": "Plan a 3-day trip to Paris"}'
```

## 📝 API Endpoints

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/` | GET | Frontend interface |
| `/health` | GET | Health check |
| `/chat` | POST | Send travel query |
| `/docs` | GET | API documentation (Swagger) |

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [LangChain](https://www.langchain.com/) for the amazing framework
- [Groq](https://groq.com/) for high-performance LLM inference
- [Render](https://render.com/) for free hosting
- [AviationStack](https://aviationstack.com/) for flight data

## 📞 Contact

- **Author**: Rahul Kumar
- **GitHub**: [rkumar49](https://github.com/rkumar49)
- **Project Link**: [Multi-Agent-Travel-Planner-with-LangGraph](https://github.com/rkumar49/Multi-Agent-Travel-Planner-with-LangGraph)

---

**Made with ❤️ using LangGraph and Python**
