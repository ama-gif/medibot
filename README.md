# medibot
This project is a Retrieval-Augmented Generation (RAG) chatbot designed to answer user queries using document-based context. It integrates OpenAI’s GPT-4 with a semantic vector search engine and is orchestrated via n8n.

Features
📄 Document Support: Ingests PDF, TXT, and Markdown files

🔍 Semantic Search: Uses ChromaDB and MiniLM embeddings

🤖 LLM Integration: GPT-4 for contextual, source-backed answers

🔁 Workflow Automation: n8n handles query-to-response pipeline

🔐 Secure & Scalable: Rate limiting, error handling, and API protection
Architecture
sql
Copy
Edit
User → Webhook → Vector Search → Context → GPT-4 → Response
Quick Start
Install dependencies:

bash
Copy
Edit
npm install openai pinecone-client
pip install -r requirements.txt
Process documents:

bash
Copy
Edit
python scripts/process_documents.py --input data/
Import and activate the rag-chatbot-workflow.json in n8n.

Test via:

bash
Copy
Edit
curl -X POST http://your-n8n/webhook/rag-chatbot \
  -H "Content-Type: application/json" \
  -d '{"query": "What is your refund policy?"}'
