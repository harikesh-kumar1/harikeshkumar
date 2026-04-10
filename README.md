# Chatbot 

## The Golden RAGtriever - Community Edition ✨

[![Weaviate](https://img.shields.io/static/v1?label=powered%20by&message=Weaviate%20%E2%9D%A4&color=green&style=flat-square)](https://weaviate.io/)
[![PyPi downloads](https://static.pepy.tech/personalized-badge/goldenverba?period=total&units=international_system&left_color=grey&right_color=orange&left_text=pip%20downloads)](https://pypi.org/project/goldenverba/) [![Docker support](https://img.shields.io/badge/Docker_support-%E2%9C%93-4c1?style=flat-square&logo=docker&logoColor=white)](https://docs.docker.com/get-started/) [![Demo](https://img.shields.io/badge/Check%20out%20the%20demo!-yellow?&style=flat-square&logo=react&logoColor=white)]

The Golden RAGtriever, an community-driven open-source application designed to offer an end-to-end, streamlined, and user-friendly interface for Retrieval-Augmented Generation (RAG) out of the box. In just a few easy steps, explore your datasets and extract insights with ease, either locally with Ollama and Huggingface or through LLM providers such as Anthrophic, Cohere, and OpenAI. This project is built with and for the community, please be aware that it might not be maintained with the same urgency as other Weaviate production applications. Feel free to contribute to the project and help us make Verba even better! <3

```
pip install goldenverba
```

![Demo of Verba](https://github.com/weaviate/Verba/blob/2.0.0/img/verba.gif)

- [Verba](#verba)
  - [🎯 What Is Verba?](#what-is-verba)
  - [✨ Features](#feature-lists)
- [✨ Getting Started with Verba](#getting-started-with-verba)
- [🔑 API Keys](#api-keys)
  - [Weaviate](#weaviate)
  - [Ollama](#ollama)
  - [Unstructured](#unstructured)
  - [AssemblyAI](#assemblyai)
  - [OpenAI](#openai)
  - [HuggingFace](#huggingface)
  - [Groq](#groq)
  - [Novita AI](#novitaai)
- [Quickstart: Deploy with pip](#how-to-deploy-with-pip)
- [Quickstart: Build from Source](#how-to-build-from-source)
- [Quickstart: Deploy with Docker](#how-to-install-verba-with-docker)
- [💾 Verba Walkthrough](#️verba-walkthrough)
- [💖 Open Source Contribution](#open-source-contribution)
- [🚩 Known Issues](#known-issues)
- [❔FAQ](#faq)




## Feature Lists

| 🤖 Model Support                  | Implemented | Description                                             |
| --------------------------------- | ----------- | ------------------------------------------------------- |
| Ollama (e.g. Llama3)              | ✅          | Local Embedding and Generation Models powered by Ollama |
| HuggingFace (e.g. MiniLMEmbedder) | ✅          | Local Embedding Models powered by HuggingFace           |
| Cohere (e.g. Command R+)          | ✅          | Embedding and Generation Models by Cohere               |
| Anthrophic (e.g. Claude Sonnet)   | ✅          | Embedding and Generation Models by Anthrophic           |
| OpenAI (e.g. GPT4)                | ✅          | Embedding and Generation Models by OpenAI               |
| Groq (e.g. Llama3)                | ✅          | Generation Models by Groq (LPU inference)               |
| Novita AI (e.g. Llama3.3)         | ✅          | Generation Models by Novita AI                          |
| Upstage (e.g. Solar)              | ✅          | Embedding and Generation Models by Upstage              |

| 🤖 Embedding Support | Implemented | Description                              |
| -------------------- | ----------- | ---------------------------------------- |
| Weaviate             | ✅          | Embedding Models powered by Weaviate     |
| Ollama               | ✅          | Local Embedding Models powered by Ollama |
| SentenceTransformers | ✅          | Embedding Models powered by HuggingFace  |
| Cohere               | ✅          | Embedding Models by Cohere               |
| VoyageAI             | ✅          | Embedding Models by VoyageAI             |
| OpenAI               | ✅          | Embedding Models by OpenAI               |
| Upstage              | ✅          | Embedding Models by Upstage              |

| 📁 Data Support                                          | Implemented | Description                                    |
| -------------------------------------------------------- | ----------- | ---------------------------------------------- |
| [UnstructuredIO](https://docs.unstructured.io/welcome)   | ✅          | Import Data through Unstructured               |
| [Firecrawl](https://www.firecrawl.dev/)                  | ✅          | Scrape and Crawl URL through Firecrawl         |
| [UpstageDocumentParse](https://upstage.ai/)              | ✅          | Parse Documents through Upstage Document AI    |
| PDF Ingestion                                            | ✅          | Import PDF into Verba                          |
| GitHub & GitLab                                          | ✅          | Import Files from Github and GitLab            |
| CSV/XLSX Ingestion                                       | ✅          | Import Table Data into Verba                   |
| .DOCX                                                    | ✅          | Import .docx files                             |
| Multi-Modal (using [AssemblyAI](https://assemblyai.com)) | ✅          | Import and Transcribe Audio through AssemblyAI |

| ✨ RAG Features         | Implemented     | Description                                                               |
| ----------------------- | --------------- | ------------------------------------------------------------------------- |
| Hybrid Search           | ✅              | Semantic Search combined with Keyword Search                              |
| Autocomplete Suggestion | ✅              | Verba suggests autocompletion                                             |
| Filtering               | ✅              | Apply Filters (e.g. documents, document types etc.) before performing RAG |
| Customizable Metadata   | ✅              | Free control over Metadata                                                |
| Async Ingestion         | ✅              | Ingest data asynchronously to speed up the process                        |
| Advanced Querying       | planned ⏱️      | Task Delegation Based on LLM Evaluation                                   |
| Reranking               | planned ⏱️      | Rerank results based on context for improved results                      |
| RAG Evaluation          | planned ⏱️      | Interface for Evaluating RAG pipelines                                    |
| Agentic RAG             | out of scope ❌ | Agentic RAG pipelines                                                     |
| Graph RAG               | out of scope ❌ | Graph-based RAG pipelines                                                 |

| 🗡️ Chunking Techniques | Implemented | Description                                             |
| ---------------------- | ----------- | ------------------------------------------------------- |
| Token                  | ✅          | Chunk by Token powered by [spaCy](https://spacy.io/)    |
| Sentence               | ✅          | Chunk by Sentence powered by [spaCy](https://spacy.io/) |
| Semantic               | ✅          | Chunk and group by semantic sentence similarity         |
| Recursive              | ✅          | Recursively chunk data based on rules                   |
| HTML                   | ✅          | Chunk HTML files                                        |
| Markdown               | ✅          | Chunk Markdown files                                    |
| Code                   | ✅          | Chunk Code files                                        |
| JSON                   | ✅          | Chunk JSON files                                        |

| 🆒 Cool Bonus            | Implemented     | Description                                             |
| ------------------------ | --------------- | ------------------------------------------------------- |
| Docker Support           | ✅              | Verba is deployable via Docker                          |
| Customizable Frontend    | ✅              | Verba's frontend is fully-customizable via the frontend |
| Vector Viewer            | ✅              | Visualize your data in 3D                               |
| Multi-User Collaboration | out of scope ❌ | Multi-User Collaboration in Verba                       |

| 🤝 RAG Libraries | Implemented | Description                        |
| ---------------- | ----------- | ---------------------------------- |
| LangChain        | ✅          | Implement LangChain RAG pipelines  |
| Haystack         | planned ⏱️  | Implement Haystack RAG pipelines   |
| LlamaIndex       | planned ⏱️  | Implement LlamaIndex RAG pipelines |

> Something is missing? Feel free to create a new issue or discussion with your idea!

![Showcase of Verba](https://github.com/weaviate/Verba/blob/2.0.0/img/verba_screen.png)

---

# Getting Started with Verba

You have three deployment options for Verba:

- Install via pip

```
pip install goldenverba
```

- Build from Source

```
git clone https://github.com/weaviate/Verba

pip install -e .
```

- Use Docker for Deployment

**Prerequisites**: If you're not using Docker, ensure that you have `Python >=3.10.0,<3.13.0` installed on your system.

```
git clone https://github.com/weaviate/Verba

docker compose --env-file <your-env-file> up -d --build
```

If you're unfamiliar with Python and Virtual Environments, please read the [python tutorial guidelines](./PYTHON_TUTORIAL.md).

# API Keys and Environment Variables

You can set all API keys in the Verba frontend, but to make your life easier, we can also prepare a `.env` file in which Verba will automatically look for the keys. Create a `.env` in the same directory you want to start Verba in. You can find an `.env.example` file in the [goldenverba](./goldenverba/.env.example) directory.

> Make sure to only set environment variables you intend to use, environment variables with missing or incorrect values may lead to errors.

Below is a comprehensive list of the API keys and variables you may require:

| Environment Variable   | Value                                                      | Description                                                                                                                   |
| ---------------------- | ---------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| WEAVIATE_URL_VERBA     | URL to your hosted Weaviate Cluster                        | Connect to your [WCS](https://console.weaviate.cloud/) Cluster                                                                |
| WEAVIATE_API_KEY_VERBA | API Credentials to your hosted Weaviate Cluster            | Connect to your [WCS](https://console.weaviate.cloud/) Cluster                                                                |
| ANTHROPIC_API_KEY      | Your Anthropic API Key                                     | Get Access to [Anthropic](https://www.anthropic.com/) Models                                                                  |
| OPENAI_API_KEY         | Your OpenAI Key                                            | Get Access to [OpenAI](https://openai.com/) Models                                                                            |
| OPENAI_EMBED_API_KEY         | Your OpenAI Key                                            | Use a different endpoint for embeddings                                                                            |
| OPENAI_BASE_URL        | URL to OpenAI instance                                     | Models                                                                                                                        |
| OPENAI_EMBED_BASE_URL        | URL to OpenAI instance                                     | Use a different endpoint for embeddings                                                                                                                        |
| OPENAI_MODEL        | The name of the model to be used when selecting OpenAI as a Generator                                    | Default: the first model in the list returned by the endpoint                                                                                                                        |
| OPENAI_EMBED_MODEL        | The name of the OpenAI embedding model to be used when selecting OpenAI as an Embedder                                    | Default: `text-embedding-3-small`                                                                                                                        |
| OPENAI_CUSTOM_EMBED        | `true` \| `false`                                    | Allow Verba to recognize custom embedding model names (not only OpenAI ones)                                                                            |
| COHERE_API_KEY         | Your API Key                                               | Get Access to [Cohere](https://cohere.com/) Models                                                                            |
| GROQ_API_KEY           | Your Groq API Key                                          | Get Access to [Groq](https://groq.com/) Models                                                                                |
| NOVITA_API_KEY         | Your Novita API Key                                        | Get Access to [Novita AI](https://novita.ai?utm_source=github_verba&utm_medium=github_readme&utm_campaign=github_link) Models |
| OLLAMA_URL             | URL to your Ollama instance (e.g. http://localhost:11434 ) | Get Access to [Ollama](https://ollama.com/) Models                                                                            |
| UNSTRUCTURED_API_KEY   | Your API Key                                               | Get Access to [Unstructured](https://docs.unstructured.io/welcome) Data Ingestion                                             |
| UNSTRUCTURED_API_URL   | URL to Unstructured Instance                               | Get Access to [Unstructured](https://docs.unstructured.io/welcome) Data Ingestion                                             |
| ASSEMBLYAI_API_KEY     | Your API Key                                               | Get Access to [AssemblyAI](https://assemblyai.com) Data Ingestion                                                             |
| GITHUB_TOKEN           | Your GitHub Token                                          | Get Access to Data Ingestion via GitHub                                                                                       |
| GITLAB_TOKEN           | Your GitLab Token                                          | Get Access to Data Ingestion via GitLab                                                                                       |
| FIRECRAWL_API_KEY      | Your Firecrawl API Key                                     | Get Access to Data Ingestion via Firecrawl                                                                                    |
| VOYAGE_API_KEY         | Your VoyageAI API Key                                      | Get Access to Embedding Models via VoyageAI                                                                                   |
| EMBEDDING_SERVICE_URL  | URL to your Embedding Service Instance                     | Get Access to Embedding Models via [Weaviate Embedding Service](https://weaviate.io/developers/wcs/embeddings)                |
| EMBEDDING_SERVICE_KEY  | Your Embedding Service Key                                 | Get Access to Embedding Models via [Weaviate Embedding Service](https://weaviate.io/developers/wcs/embeddings)                |
| UPSTAGE_API_KEY        | Your Upstage API Key                                       | Get Access to [Upstage](https://upstage.ai/) Models                                                                           |
| UPSTAGE_BASE_URL       | URL to Upstage instance                                    | Models                                                                                                                        |
| DEFAULT_DEPLOYMENT     | Local, Weaviate, Custom, Docker                            | Set the default deployment mode                                                                                               |
| SYSYEM_MESSAGE_PROMPT     | Prompt text value                            | Default value starts with: "You are Verba, a chatbot for..."                                                                                               |
| OLLAMA_MODEL           | Your Ollama Model                                          | Set the default Ollama model to use                                                                                           |
| OLLAMA_EMBED_MODEL     | Your Ollama Embedding Model                                | Set the default Ollama embedding model to use                                                                                 |

![API Keys in Verba](https://github.com/weaviate/Verba/blob/2.0.0/img/api_screen.png)

## Weaviate

Verba provides flexibility in connecting to Weaviate instances based on your needs. You have three options:

1. **Local Deployment**: Use Weaviate Embedded which runs locally on your device (except Windows, choose the Docker/Cloud Deployment)
2. **Docker Deployment**: Choose this option when you're running Verba's Dockerfile.
3. **Cloud Deployment**: Use an existing Weaviate instance hosted on WCD to run Verba

**💻 Weaviate Embedded**
Embedded Weaviate is a deployment model that runs a Weaviate instance from your application code rather than from a stand-alone Weaviate server installation. When you run Verba in `Local Deployment`, it will setup and manage Embedded Weaviate in the background. Please note that Weaviate Embedded is not supported on Windows and is in Experimental Mode which can bring unexpected errors. We recommend using the Docker Deployment or Cloud Deployment instead. You can read more about Weaviate Embedded [here](https://weaviate.io/developers/weaviate/installation/embedded).

**🌩️ Weaviate Cloud Deployment (WCD)**

If you prefer a cloud-based solution, Weaviate Cloud (WCD) offers a scalable, managed environment. Learn how to set up a cloud cluster and get the API keys by following the [Weaviate Cluster Setup Guide](https://weaviate.io/developers/wcs/guides/create-instance).

**🐳 Docker Deployment**
Another local alternative is deploying Weaviate using Docker. For more details, follow the [How to install Verba with Docker](#how-to-install-verba-with-docker) section.

![Deployment in chatbot](https://github.com/weaviate/chatbot
