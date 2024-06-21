# INFO7375-mini-assignemnt-local-llm-deployment
## Introduction

This repository contains all the necessary files and instructions for setting up and running the `ollma3` model locally. `ollma3` is designed for [specific model applications or tasks]. This README provides clear instructions on how to set up the environment, configure the model, and execute the scripts included in this repository.

Ollama now runs as a native Windows application, including NVIDIA and AMD Radeon GPU support.
After installing Ollama Windows Preview, Ollama will run in the background and the `ollama` command line is available in `cmd`, `powershell` or your favorite terminal application. As usual the Ollama api will be served on`http://localhost:11434`.

## Setup

### Download Windows preview and install
```
https://ollama.com/download/OllamaSetup.exe
```
## QuickStart

To run and chat with [Llama 3](https://ollama.com/library/llama3):

```
ollama run llama3
```
### Deploy Local server

```
ollama serve
```

## check model list

```
ollama list
```

### Generate a response

Ollama has a REST API for running and managing models.

```
curl -X POST "http://127.0.0.1:11434/api/generate" -H "Content-Type: application/json" -d "{\"model\": \"llama3\", \"prompt\": \"Why is the sky blue?\", \"stream\": false}"
```

Example answer

```
aasd
```

