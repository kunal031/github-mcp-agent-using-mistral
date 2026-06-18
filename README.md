# GitHub Repo Intelligence AI Agent 🤖

A context-aware AI chatbot built with Python that queries and analyzes any GitHub repository on demand. Powered by the **Model Context Protocol (MCP)** and **Mistral AI**, this agent dynamically discovers and executes native GitHub tools (via Docker) to read files, examine issues, check commits, and summarize repositories based on natural language queries.

## 🌟 Features

- **On-Demand Repo Querying:** Type any GitHub repository URL or name, and the agent automatically targets it.
- **Model Context Protocol (MCP):** Connects to the official GitHub MCP server to instantly access 43 distinct developer tools.
- **Mistral Large Engine:** Utilizes `mistral-large-latest` for accurate, reliable tool-calling and structured reasoning.
- **Secure Architecture:** Built with isolated Docker execution to safeguard environment paths and secure access tokens.

---

## 🛠️ Prerequisites

Before running the project, ensure your machine has the following tools installed:

- **Python 3.11+**
- **Docker Desktop** (Must be running in the background)
- **Git**

---

## 🚀 Setup Instructions

### 1. Clone & Navigate

```bash
git clone <your-repository-url>
cd github-mcp-server
```

### 2. Configure Virtual Environment

Create and activate an isolated virtual environment to prevent system package pollution:

```bash
python3 -m venv myenv --without-pip
source myenv/bin/activate
python3 -m ensurepip --default-pip
```

### 3. Install Dependencies

Install the slim, optimized top-level dependencies required for runtime operations:

```bash
pip install -r requirements.txt
```

### 4. Setup Secrets & Environment

Create a `.env` file in the root directory to store your secret tokens securely:

```bash
touch .env
```

Open the `.env` file and insert your API credentials exactly like this:

```env
MISTRAL_API_KEY=your_mistral_api_key_here
GITHUB_PERSONAL_ACCESS_TOKEN=your_fine_grained_github_token_here
```

> ⚠️ **Note:** Ensure your GitHub Fine-grained Personal Access Token has **Read-only** access granted for _Contents_, _Metadata_, and _Issues_ on your target repositories.

---

## 💻 Usage

1. Open Docker Desktop on your system.
2. Fire up the AI agent in your terminal:
   ```bash
   python agent.py
   ```
3. Type your query directly into the prompt box on demand:
   ```text
   💬 Your Query: summarize Readme of https://github.com
   ```

---

## 📁 Project Structure

```text
github-mcp-server/
│
├── myenv/               # Isolated Python virtual environment
├── .env                 # API Credentials & Token Secrets (Hidden)
├── .gitignore           # Safeguards secrets from being tracked by git
├── agent.py             # Core MCP Client & Mistral logic loop
└── requirements.txt     # Clean version-locked package list
```
