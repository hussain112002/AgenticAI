# AI Agent with Supervisor Integration

A sophisticated AI agent system with quality control supervision, mathematical reasoning capabilities, and multi-modal document processing.

## Features

- **Supervisor Agent**: Independent validation and quality control system
- **Mathematical Reasoning**: Advanced math problem solving with verification
- **Document Processing**: Support for PDF, DOCX, TXT, and CSV files
- **RAG Integration**: Retrieval-Augmented Generation with FAISS indexing
- **Web Search**: Real-time information retrieval
- **Performance Monitoring**: Comprehensive metrics and insights
- **Interactive UI**: Gradio-based web interface
- **Memory System**: Persistent conversation context

## Architecture

### Core Components

1. **Controller Agent**: Routes queries to appropriate tools
2. **Math Solver**: Handles complex mathematical word problems
3. **Calculator**: Performs arithmetic calculations
4. **Web Search**: Retrieves current information
5. **Document QA**: Answers questions from uploaded documents
6. **Supervisor**: Validates outputs and ensures quality

### Quality Control System

- Independent verification of mathematical solutions
- Multi-attempt retry mechanism
- Performance tracking and optimization
- Error detection and recovery

## Installation

### Prerequisites

- Python 3.8+
- GROQ API Key
- Serper API Key (for web search)
- Hugging Face Token (optional)

### Setup Instructions

1. **Clone the repository**
   ```bash
   git clone https://github.com/hussain112002/AgenticAI.git
   cd AgenticAI
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Configure environment variables**
   Create a `.env` file in the project root:
   ```env
   GROQ_API_KEY=your_groq_api_key_here
   web_search=your_serper_api_key_here
   HF_TOKEN=your_huggingface_token_here
   ```

4. **Run the application**
   ```bash
   python agentic7_0.py
   ```

## Usage

### Quick Start

```python
from agentic7_0 import supervised_agent_query

# Ask a math question
result = supervised_agent_query("What is 25% of 480?", use_supervisor=True)
print(result['final_answer'])
```

### Web Interface

Launch the interactive Gradio interface:

```bash
python agentic7_0.py
```

Then select "Y" when prompted to launch the web interface.

### Document Processing

1. Create a `docs/` folder in the project root
2. Upload your documents (PDF, DOCX, TXT, CSV)
3. The system will automatically process and index them

## API Keys Setup

### GROQ API Key
1. Visit [GROQ Console](https://console.groq.com/)
2. Create an account and generate an API key
3. Add to your `.env` file

### Serper API Key (Web Search)
1. Visit [Serper.dev](https://serper.dev/)
2. Sign up and get your API key
3. Add to your `.env` file as `web_search`

### Hugging Face Token (Optional)
1. Visit [Hugging Face](https://huggingface.co/)
2. Create account and generate access token
3. Add to your `.env` file

## Configuration

Key configuration options in the `CONFIG` dictionary:

```python
CONFIG = {
    "model": "llama3-8b-8192",        # GROQ model
    "temperature": 0.1,                # Response randomness
    "use_memory": True,                # Enable conversation memory
    "use_planning": True,              # Enable query planning
    "verification_mode": True,         # Enable supervisor validation
    "max_retries": 2,                  # Maximum retry attempts
    "chunk_size": 256,                 # Document chunk size
    "rag_k": 3,                       # Number of retrieved documents
}
```

## Testing and Evaluation

### Run Integration Tests
```python
test_supervisor_integration()
```

### Evaluate on GSM8K Dataset
```python
gsm8k_df, gsm8k_stats = evaluate_gsm8k_with_supervisor(n=30, use_supervisor=True)
```

### Full Evaluation Suite
```python
run_supervised_evaluation_suite()
```

## Project Structure

```
ai-agent-supervisor/
├── agentic7_0.py              # Main application file
├── requirements.txt           # Python dependencies
├── README.md                  # This file
├── .env.example              # Environment variables template
├── docs/                     # Document storage folder
├── agent_memory.jsonl        # Persistent memory (auto-generated)
└── comprehensive_agent_report.md  # Evaluation reports (auto-generated)
```

## Performance Metrics

The system tracks various performance metrics:

- **Accuracy**: Percentage of correct answers
- **Response Time**: Average processing time
- **Quality Control Pass Rate**: Supervisor approval rate
- **Tool Usage Distribution**: Usage patterns across tools
- **Error Rates**: System reliability metrics

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## Troubleshooting

### Common Issues

1. **Import Errors**: Ensure all dependencies are installed
   ```bash
   pip install -r requirements.txt
   ```

2. **API Key Errors**: Verify your `.env` file has correct API keys

3. **Memory Issues**: Reduce `chunk_size` and `max_doc_chunks` in CONFIG

4. **FAISS Installation**: Install with conda if pip fails
   ```bash
   conda install faiss-cpu -c conda-forge
   ```

### Error Messages

- `LLM-UNAVAILABLE`: Check GROQ API key
- `SearchError`: Verify Serper API key
- `CalculatorError`: Check mathematical expression syntax
- `DocQAError`: Ensure documents are in `docs/` folder

## License

MIT License - see LICENSE file for details

## Changelog

### v7.0
- Added Supervisor Agent with independent verification
- Implemented quality control system
- Enhanced mathematical reasoning capabilities
- Added comprehensive evaluation metrics
- Integrated file upload functionality

## Support

For issues and questions:
- Create an issue on GitHub
- Check the troubleshooting section
- Review the configuration options

## Acknowledgments

- GROQ for fast LLM inference
- Hugging Face for embeddings and tokenizers
- FAISS for vector similarity search
- LangChain for LLM abstractions
