# Local LLM Setup with Ollama

This project provides a containerized setup for running local LLM (Large Language Model) instances using Ollama, with a web interface and optional public access capability.

## Project Goals
- Run LLM models locally using GPU acceleration
- Provide user-friendly web interface for model interaction
- Enable secure public access for demonstrations

## Services

### Ollama
- Core LLM service running locally
- GPU-enabled for better performance
- Runs on port 11434
- Pre-configured with [Gemma3 1B model](https://ollama.com/library/gemma3:1b)
- Official website: https://ollama.com/

### Open WebUI
- User-friendly web interface for Ollama
- Runs on port 3000 (mapped to internal 8080)
- Provides chat interface and model management
- Depends on Ollama service
- Special thanks to the [Open WebUI team](https://github.com/open-webui/open-webui) for their amazing open source contribution

### Ngrok
- Enables secure public access to the web interface
- Runs on port 4040 (dashboard)
- Requires Ngrok authentication token
- Official website: https://ngrok.com/

## Prerequisites
- Docker and Docker Compose installed
- NVIDIA GPU with appropriate drivers (for GPU acceleration)
- Ngrok account and auth token (if public access is needed)

## Setup Instructions

1. Clone this repository:
```bash
git clone <repository-url>
cd <repository-name>
```

2. Set up environment variable (if using Ngrok):
```bash
export NGROK_TOKEN=your_ngrok_auth_token
```

3. Start the services:
```bash
docker-compose up -d
```

4. Access the services:
- Web UI: http://localhost:3000
- Ollama API: http://localhost:11434
- Ngrok Dashboard: http://localhost:4040

## Additional Notes
- All data is persisted using Docker volumes
- Ngrok service can be removed from docker-compose.yml if not needed