# Ollama, DeepSeek, and Open WebUI Installation Guide

This guide walks you through installing Ollama, setting up DeepSeek, and deploying Open WebUI using Docker.

## Prerequisites

Ensure your system meets the following requirements:

- **Operating System:** macOS, Linux, or Windows
- **Docker:** Installed and running ([Install Docker](https://docs.docker.com/get-docker/))
- **Git:** Installed ([Install Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git))

---

## Step 1: Install Ollama

Ollama is a runtime for large language models.

1. Open your terminal and run the following commands:

```bash
# macOS (Homebrew)
brew install ollama

# Linux
curl -fsSL https://ollama.com/install.sh | bash

# Windows (via WSL)
wsl curl -fsSL https://ollama.com/install.sh | bash

```

2. Verify the installation:

```
ollama --version
```

## Step 2: Install DeepSeek

DeepSeek is an advanced LLM model you can run with Ollama.

1. Pull the DeepSeek model:

```
#ollama pull deepseek
```

2. Test if the model is working:

```
ollama run deepseek
```

##Step 3: Deploy Open WebUI with Docker

Open WebUI provides a user-friendly interface for interacting with LLMs.

1. Clone the Open WebUI repository:
```
docker run -d -p 3001:8080 --add-host=host.docker.internal:host-gateway -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:main
```

2. Open browser for Open WebUI:

http://localhost:3001/