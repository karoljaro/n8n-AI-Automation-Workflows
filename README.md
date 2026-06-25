# n8n AI Automation Workflows

A collection of practical n8n workflows for AI-powered automation, agentic systems, RAG pipelines and media processing.

The repository includes exported workflows, setup instructions, architecture notes and examples covering:

- AI email agents
- RAG-based knowledge assistants
- AutoLektor media automation
- API integrations
- Error handling and retry strategies
- Local and external AI model providers

Each workflow is stored in a separate directory with its own documentation, required environment variables and example inputs.

## Requirements

Some workflows use local AI models through **Ollama**. Those workflows expect the Ollama API to be available on the default port **11434**.

Start the Ollama server before importing or running AI-based workflows:

```bash
OLLAMA_HOST=0.0.0.0:11434 ollama serve
```

Alternatively, on Windows (PowerShell):

```powershell
$env:OLLAMA_HOST="0.0.0.0:11434"
ollama serve
```

After the server is running, make sure the required models are available, for example:

```bash
ollama pull llama3.2
ollama pull nomic-embed-text
```

> **Note:** Only workflows that use local AI models require Ollama. Workflows using external providers (such as OpenAI or Anthropic) do not require a local Ollama instance.
