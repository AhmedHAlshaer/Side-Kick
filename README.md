# SideKick - Personal AI Assistant

A LangGraph-powered AI assistant that can browse the web, search information, and execute tasks autonomously.

## Features

- 🌐 Web browsing with Playwright
- 🔍 Wikipedia and web search integration
- 📝 File management capabilities  
- 🔔 Push notifications (via Pushover)
- 🐍 Python code execution
- 🤖 Powered by LangGraph and DeepSeek

## Prerequisites

- Python 3.10 or higher
- [uv](https://docs.astral.sh/uv/) package manager
- DeepSeek API key (get from [platform.deepseek.com](https://platform.deepseek.com))

## Installation

1. **Clone the repository:**
```bash
   git clone https://github.com/c212/a310-fall2025-ahmealsh.git
   cd Lab12
```

2. **Install dependencies:**
```bash
   uv sync
```

3. **Install Playwright browsers:**
```bash
   uv run playwright install
```

4. **Set up environment variables:**
```bash
   cp .env.example .env
```
   
   Then edit `.env` and add your API keys:
   - `DEEPSEEK_API_KEY`: Required - Get from [DeepSeek Platform](https://platform.deepseek.com)
   - `PUSHOVER_TOKEN` & `PUSHOVER_USER`: Optional - For push notifications
   - `GOOGLE_SERPER_API_KEY`: Optional - For web search (get from [serper.dev](https://serper.dev))

## Usage

Run the application:
```bash
uv run app.py
```

This will launch a Gradio interface in your browser at `http://127.0.0.1:7860`

### How to Use

1. Enter your request in the "Your request" field
2. (Optional) Specify success criteria to help the AI understand when the task is complete
3. Click "Go!" to start
4. The AI will work autonomously, using tools as needed
5. View the conversation and results in the chat interface

### Example Requests

- "Search for the latest news about AI"
- "Find information about LangGraph on Wikipedia"
- "Calculate the factorial of 10 using Python"
- "Browse to example.com and extract the main heading"

## Project Structure
```
Lab12/
├── app.py                 # Gradio UI
├── sidekick.py           # Core LangGraph agent logic
├── sidekick_tools.py     # Tool definitions (web, search, files, etc.)
├── pyproject.toml        # Dependencies
├── uv.lock              # Locked dependency versions
└── .env.example         # Environment variable template
```

## Technologies Used

- **LangGraph**: Agent workflow orchestration
- **LangChain**: LLM integration and tool management
- **DeepSeek**: Large language model
- **Playwright**: Web browser automation
- **Gradio**: User interface
- **Python 3.12+**: Core language

## Troubleshooting

**Issue:** `ModuleNotFoundError`  
**Solution:** Run `uv sync` to install all dependencies

**Issue:** Playwright browsers not found  
**Solution:** Run `uv run playwright install`

**Issue:** API key errors  
**Solution:** Check your `.env` file has valid API keys

## License

MIT License - feel free to use for educational purposes

## Author

Ahmed H Alshaer - Indiana University, Fall 2025

## Assignment

This project was created for A310 Class, Lab 12