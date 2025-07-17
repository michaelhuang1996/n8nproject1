# n8n RAG Chatbot for Company Documents 

A low-code Retrieval‑Augmented Generation (RAG) chatbot built with n8n to help employees easily query internal company documents (SOPs, policy manuals, product guides, etc.). Powered by Pinecone for vector search and OpenAI for intelligent responses.

---

## Features

- **Automatic ingestion from Google Drive**: New or updated files are indexed in Pinecone via text chunking and embeddings.  
- **Semantic search**: Retrieves the most relevant document segments using vector similarity.  
- **Conversational feedback**: Users ask questions in a chat UI, and the AI agent pulls context + responses via the RAG pipeline.  
- **Commit & version control**: This workflow’s JSON is stored here for easy updates and reuse.

---

## Stack

- **n8n**: Workflow automation (Google Drive trigger, Chat UI, Pinecone integrations)
- **Pinecone**: Vector database for semantic search
- **OpenAI**: Generates embeddings & responses (`gpt-4.1-mini`, `text-embedding-3-small`)
- **Chat Trigger**: Provides web-based chat interface with optional embed via widget

---

## Usage

### 1. Import the workflow

- In n8n Cloud or self-hosted: `Workflows → Import from file → select JSON`

### 2. Set up credentials

- Create credentials in n8n for:
  - Google Drive OAuth
  - Pinecone API
  - OpenAI API

### 3. Configure nodes

- **Google Drive Trigger**: Watch your internal documents folder  
- **Pinecone Vector Store**: Ensure index dimension matches embeddings (e.g. 1536 & `text-embedding-3-small`)  
- **AI Agent**: Connect Pinecone as a Tool, set “Return metadata” for source tracing  
- (Optional) Use Chat Trigger → embed into your website with n8n chat widget

### 4. Run and test

- Upload/update a document in Drive → it’s automatically indexed  
- Open chat UI or embedded widget → ask questions (e.g., “What’s the reimbursement policy?”)  
- The chatbot returns answers with contextual documents and metadata sources

---

## Tips & Next Steps

- **Customize chunk size & metadata tags** (page number, file name) for better citation  
- **Switch models**: e.g., `gpt-4o-mini` for multilingual/text + image context  
- **Viz> Add reranking**: Use Cohere or other reranker nodes to fine-tune retrieval  
- **Enhance UX**: Embed chat UI in your intranet or internal portal for staff access

---

## References & Templates

- [Build a custom knowledge RAG chatbot using n8n](https://n8n.io/blog/rag-chatbot) — in-depth tutorial :contentReference[oaicite:1]{index=1}  
- [Chat with GitHub API docs (template)](https://n8n.io/workflows/2705-chat-with-github-api-documentation-rag-powered-chatbot-with-pinecone-and-openai) :contentReference[oaicite:2]{index=2}  
- [PDF-based RAG system (template)](https://n8n.io/workflows/5734-build-a-pdf-based-rag-system-with-openai-pinecone-and-cohere-reranking) :contentReference[oaicite:3]{index=3}  

---

## License

This project is open-source and MIT licensed — feel free to adapt or integrate into your internal systems!

---

## Contribution

Issues, improvements, or templates welcome!
