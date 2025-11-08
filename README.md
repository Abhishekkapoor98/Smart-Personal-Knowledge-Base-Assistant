# MCP Knowledge Base Assistant Server

A Model Context Protocol (MCP) server that provides AI assistants with access to a local knowledge base. This server enables AI agents to search, add, and manage documents in a vector database for efficient retrieval and context-aware responses.

## Features

- **Document Search**: Semantic search across your knowledge base using vector embeddings
- **Document Management**: Add and organize documents with metadata
- **Document Summaries**: Get quick overviews of documents in the knowledge base
- **RAG Integration**: Uses ChromaDB for efficient vector storage and retrieval

## Prerequisites

- Python 3.10 or higher
- OpenAI API key (for embeddings)

## Installation

1. Clone this repository
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Copy `.env.example` to `.env` and configure your settings:
   ```bash
   cp .env.example .env
   # Edit .env with your settings
   ```

## Usage

1. Start the server:
   ```bash
   python server.py
   ```

2. The server exposes the following MCP tools:

   - `search_documents`: Search for relevant documents using natural language queries
   - `add_document`: Add new documents to the knowledge base
   - `get_document_summary`: Get metadata and content previews for specific documents

## Development

### Project Structure

```
mcp-knowledge-base/
├── server.py             # Main MCP server implementation
├── requirements.txt      # Python dependencies
├── .env                 # Configuration settings
└── knowledge_base/      # Local storage for vector database
```

### Adding New Features

To add new tools or capabilities:

1. Add new methods to the `KnowledgeBaseServer` class
2. Register them as tools using the `@app.tool()` decorator
3. Update documentation as needed

## Security Notes

- The server is designed for local use and requires proper configuration for production deployments
- API keys should be kept secure and never committed to version control
- Consider implementing authentication if deploying in a multi-user environment

## License

MIT