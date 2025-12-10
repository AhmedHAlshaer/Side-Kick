# SideKick - Autonomous AI Agent

An agentic AI assistant built with **LangGraph** that autonomously completes tasks using a worker-evaluator architecture. The agent can browse the web, search information, execute code, and iteratively work toward user-defined success criteria.

## 🎯 Overview

SideKick implements an **agentic loop** where:
1. A **Worker Agent** receives tasks and uses tools to complete them
2. An **Evaluator Agent** assesses if success criteria are met
3. The loop continues until the task is complete or user input is needed

This architecture enables autonomous multi-step task completion with built-in quality control.

## ✨ Features

- **Autonomous Task Execution** - Agent works independently until success criteria are met
- **Web Browsing** - Navigate and extract information from websites using Playwright
- **Web Search** - Query the internet via Google Serper API
- **Wikipedia Integration** - Quick access to encyclopedic knowledge
- **Python Execution** - Run Python code for calculations and data processing
- **File Management** - Create, read, and manage files in a sandboxed environment
- **Push Notifications** - Get notified via Pushover when tasks complete

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────┐
│                      User Request                        │
└─────────────────────────┬───────────────────────────────┘
                          ▼
┌─────────────────────────────────────────────────────────┐
│                    Worker Agent                          │
│  ┌─────────────────────────────────────────────────┐    │
│  │  Tools: Browser, Search, Wikipedia, Python, etc │    │
│  └─────────────────────────────────────────────────┘    │
└─────────────────────────┬───────────────────────────────┘
                          ▼
┌─────────────────────────────────────────────────────────┐
│                   Evaluator Agent                        │
│         Checks if success criteria are met               │
└─────────────────────────┬───────────────────────────────┘
                          ▼
              ┌───────────────────────┐
              │   Criteria Met?       │
              │   ┌─────┐   ┌─────┐   │
              │   │ Yes │   │ No  │   │
              │   └──┬──┘   └──┬──┘   │
              └──────┼────────┼──────┘
                     ▼        ▼
                  [Done]   [Loop back to Worker]
```

## 🚀 Quick Start

### Prerequisites
- Python 3.12+
- [uv](https://docs.astral.sh/uv/) package manager
- [DeepSeek API key](https://platform.deepseek.com)

### Installation

```bash
# Clone the repository
git clone https://github.com/AhmedHAlshaer/Side-Kick.git
cd Side-Kick

# Install dependencies
uv sync

# Install browser for web automation
uv run playwright install

# Configure environment
cp .env.example .env
# Add your DEEPSEEK_API_KEY to .env
```

### Run

```bash
uv run python src/app.py
```

Opens a Gradio interface at `http://127.0.0.1:7860`

## 💡 Usage Examples

| Request | What SideKick Does |
|---------|-------------------|
| "Find the latest SpaceX launch date" | Searches the web, extracts and summarizes findings |
| "Calculate compound interest on $10k at 7% for 5 years" | Writes and executes Python code |
| "Go to github.com and find trending Python repos" | Launches browser, navigates, and extracts data |
| "What is quantum entanglement?" | Queries Wikipedia and synthesizes an explanation |

## 🛠️ Tech Stack

| Technology | Purpose |
|------------|---------|
| **LangGraph** | Agent orchestration and state management |
| **LangChain** | Tool integration and LLM abstraction |
| **DeepSeek** | Large language model backend |
| **Playwright** | Headless browser automation |
| **Gradio** | Web-based user interface |

## 📁 Project Structure

```
Side-Kick/
├── src/
│   ├── app.py              # Gradio UI application
│   ├── sidekick.py         # Core agent logic & LangGraph workflow
│   └── sidekick_tools.py   # Tool definitions
├── pyproject.toml          # Dependencies
├── .env.example            # Environment template
└── README.md
```

## 🔑 Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `DEEPSEEK_API_KEY` | ✅ | DeepSeek API key |
| `GOOGLE_SERPER_API_KEY` | Optional | For web search |
| `PUSHOVER_TOKEN` | Optional | Push notification token |
| `PUSHOVER_USER` | Optional | Push notification user |

## 🎓 Learning Outcomes

This project demonstrates:
- Building **agentic AI systems** with LangGraph
- Implementing **autonomous task loops** with evaluation checkpoints
- Integrating **multiple tools** (browser, search, code execution)
- **State management** in multi-step AI workflows
- Creating user interfaces for AI agents with Gradio

## 📄 License

MIT License - feel free to use and modify for your own projects.

## 👤 Author

**Ahmed H. Alshaer**  
Computer Science @ Indiana University Bloomington  
[GitHub](https://github.com/AhmedHAlshaer)
