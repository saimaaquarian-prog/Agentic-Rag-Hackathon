# AI Research Agent

An AI-powered research assistant that allows users to interact through **text or voice** and receive research-based answers using information retrieved from the **web and uploaded documents**.

The system combines **Retrieval-Augmented Generation (RAG)**, web search, document analysis, and AI tools to help users perform research and obtain context-aware answers.

## Features

* 💬 **Text Queries** — Ask research questions by typing.
* 🎙️ **Voice Queries** — Speak questions using voice input.
* 🌐 **Web Search** — Search the web for relevant information using DuckDuckGo.
* 📄 **Document Analysis** — Upload PDF documents and ask questions about their content.
* 🔎 **RAG-Based Retrieval** — Retrieve relevant document information using vector similarity search.
* 🧮 **Calculator Tool** — Perform mathematical calculations when required.
* ✅ **Fact Checker** — Help verify information using external sources.
* 📑 **Document Analyzer** — Analyze and extract useful information from uploaded documents.
* 🤖 **AI-Generated Answers** — Generate responses using Groq-hosted Llama models.
* 🔊 **Text-to-Speech** — Convert generated responses into speech using gTTS.
* 🔗 **Multi-Source Research** — Combine information from uploaded documents and web sources.

---

## How It Works

The AI Research Agent follows an agentic research workflow:

```text
                         User
                           │
                ┌──────────┴──────────┐
                │                     │
           Text Query             Voice Query
                │                     │
                │                Speech Processing
                │                     │
                └──────────┬──────────┘
                           │
                           ▼
                  AI Research Agent
                           │
          ┌────────────────┼────────────────┐
          │                │                │
          ▼                ▼                ▼
     Web Search       Document RAG       AI Tools
          │                │                │
     DuckDuckGo          FAISS       ┌──────┼────────┐
          │                │         │      │        │
          │          Sentence      Calc  Fact     Doc
          │          Transformers       Checker  Analyzer
          │                │
          └────────────────┼────────────────┘
                           │
                           ▼
                    Relevant Context
                           │
                           ▼
                      Groq LLM
                           │
                           ▼
                  Generated Answer
                           │
                           ▼
                     gTTS (Optional)
                           │
                           ▼
                    Voice Response
```

---

## Research Workflow

### 1. User Input

The user can either:

* Type a research question.
* Speak a research question.

### 2. Query Processing

The research agent analyzes the user's query and determines what information or tools may be required.

### 3. Information Retrieval

Depending on the query, the agent can use:

* Uploaded PDF documents
* DuckDuckGo web search
* Calculator
* Fact Checker
* Document Analyzer

### 4. Document Retrieval

For uploaded PDFs, the system:

```text
PDF
 ↓
Text Extraction
 ↓
Text Chunking
 ↓
Sentence Transformer Embeddings
 ↓
FAISS Vector Index
 ↓
Similarity Search
 ↓
Relevant Document Context
```

### 5. Answer Generation

The retrieved information is provided to the **Groq API**, which uses Llama models to generate the final response.

### 6. Voice Response

The generated answer can be converted into speech using **gTTS**, allowing the user to receive an audio response.

---

## Technology Stack

| **Layer**            | **Technology**                                                     |
| -------------------- | ------------------------------------------------------------------ |
| UI / Frontend        | **Gradio**                                                         |
| Programming Language | **Python**                                                         |
| LLM                  | **Groq API (Llama 3.1 models)**                                    |
| Embeddings           | **Sentence Transformers**                                          |
| Vector Search        | **FAISS**                                                          |
| Document Parsing     | **PyPDF**                                                          |
| Tools                | **Calculator, Fact Checker, Document Analyzer, DuckDuckGo Search** |
| Web Search           | **DuckDuckGo API**                                                 |
| Text-to-Speech       | **gTTS**                                                           |
| Utilities            | **tqdm, requests, json, os**                                       |

---

## RAG Pipeline

The document-based research component uses Retrieval-Augmented Generation:

```text
                 Uploaded PDF
                      │
                      ▼
                PDF Parsing
                   PyPDF
                      │
                      ▼
                Text Extraction
                      │
                      ▼
                Text Chunking
                      │
                      ▼
           Sentence Transformers
                 Embeddings
                      │
                      ▼
                    FAISS
              Vector Search
                      │
                      ▼
              Relevant Context
                      │
                      ▼
                Groq Llama
                      │
                      ▼
             Generated Answer
```

This approach allows the LLM to generate answers using information retrieved from the uploaded document rather than relying only on its internal knowledge.

---

## Available Tools

### Calculator

The calculator tool handles mathematical calculations when a query requires numerical reasoning.

### Fact Checker

The fact-checking tool can retrieve external information to help verify claims and provide more reliable research responses.

### Document Analyzer

The document analyzer processes uploaded documents and extracts relevant information for the user's query.

### DuckDuckGo Search

The web-search tool retrieves relevant online information when the user's question requires external or current information.

---

## Voice Interaction

The application supports voice-based research.

```text
User Speaks
     ↓
Voice Input
     ↓
Speech Processing
     ↓
Research Query
     ↓
AI Research Agent
     ↓
Web / Document / Tools
     ↓
Groq Llama
     ↓
Generated Answer
     ↓
gTTS
     ↓
Audio Response
```

This makes the application useful when users prefer speaking rather than typing their research questions.

---

## Example Queries

### Web Research

```text
What are the recent developments in generative AI?
```

The agent can use web search to retrieve relevant online information.

### Document Research

```text
What methodology was used in this research paper?
```

The agent retrieves relevant information from the uploaded PDF and generates an answer.

### Mathematical Query

```text
Calculate the accuracy improvement from 82.7% to 89.6%.
```

The calculator tool can be used for the calculation.

### Combined Research

```text
Compare the approach used in this uploaded paper with recent
approaches available online.
```

The agent can use both the uploaded document and web search as information sources.

---

## Key Capabilities

| Capability            | Description                                     |
| --------------------- | ----------------------------------------------- |
| Text Interaction      | Ask questions through text                      |
| Voice Interaction     | Ask questions through voice                     |
| Web Research          | Retrieve information from the web               |
| PDF Research          | Query uploaded PDF documents                    |
| RAG                   | Retrieve relevant document context              |
| Vector Search         | Find semantically relevant content using FAISS  |
| AI Tools              | Calculator, fact checker, and document analyzer |
| LLM Generation        | Generate answers using Groq Llama               |
| Text-to-Speech        | Convert responses into audio                    |
| Multi-Source Research | Use documents and web information together      |

---

## Use Cases

The AI Research Agent can support:

* Academic research
* Research paper analysis
* Technical research
* Literature exploration
* Document question answering
* Web-based research
* AI/ML learning
* Research information gathering
* PDF analysis
* General knowledge exploration

---

## Project Objective

The objective of this project is to develop an **AI Research Agent** capable of interacting with users through both text and voice while retrieving information from multiple sources.

By combining **RAG, vector search, web search, AI tools, and LLM-based generation**, the system provides a flexible research environment where users can ask questions and receive answers grounded in retrieved information.

---

## Future Improvements

* Multi-document comparison
* Page-level PDF citations
* Automatic source citations
* Research report generation
* Literature review automation
* Conversation memory
* Multi-agent research workflow
* Improved fact verification
* Text-to-speech improvements
* Support for additional document formats
* Research paper metadata extraction

---


**Research Interests:** Generative AI, LLMs, Retrieval-Augmented Generation (RAG), Agentic AI, and AI Research Systems.
