# Semantic-Spotter-Assignment

## 1. Background

This project demonstrate "Build a RAG System" in insurance domain
using  [LangChain](https://python.langchain.com/docs/introduction/).

## 2. Problem Statement

The goal of the project is to build a robust generative search system capable of effectively and accurately
answering questions from a bunch of policy documents.

## 3. Document

1. The policy documents can be found [here](https://github.com/Ilovemom6666/Semantic-Spotter-Assignment/tree/main/Insurance%20Policy%20Documents)


## 4. Approach 

LangChain is a framework that simplifies the development of LLM applications LangChain offers a suite of tools,
components, and interfaces that simplify the construction of LLM-centric applications. LangChain enables developers to
build applications that can generate creative and contextually relevant content LangChain provides an LLM class designed
for interfacing with various language model providers, such as OpenAI, Cohere, and Hugging Face.

- LangChain's versatility and flexibility enable seamless integration with various data sources, making it a comprehensive
solution for creating advanced language model-powered applications.

LangChain framework consists of the following:

- *Components: Modular abstractions for different components required for language models.

- *Use-Case Specific Chains: Prebuilt chains tailored to specific applications.

- *Model I/O: Interfaces with language models, prompts, and output parsers.

- *Retrieval: Handles application-specific data, including document loaders, transformers, embeddings, vector stores, and retrievers.

- *Chains: Constructs sequences of LLM calls.

- *Memory: Persists application state.

- *Agents: Selects appropriate tools dynamically.

- *Callbacks: Logs and streams intermediate steps.

## 5. System Layers

**Reading & Processing PDF Files:** [PyPDFDirectoryLoader](https://python.langchain.com/api_reference/community/document_loaders/langchain_community.document_loaders.pdf.PyPDFDirectoryLoader.html)

- Used PyPDFDirectoryLoader from LangChain to process PDFs.

- Implemented page-wise splitting in addition to text splitting to enhance retrieval granularity.


**Document Chunking:**  [RecursiveCharacterTextSplitter](https://python.langchain.com/docs/how_to/recursive_text_splitter/)

Utilized RecursiveCharacterTextSplitter to ensure semantically meaningful text chunks.

Applied customized chunking strategies based on document structure.


**Generating Embeddings:** 

- Instead of ChromaDB, we used cosine similarity
- [cosine](https://api.python.langchain.com/en/latest/utils/langchain_community.utils.math.cosine_similarity.html)
- and FAISS [FAISS](https://python.langchain.com/docs/integrations/vectorstores/faiss/) for efficient vector search.
- Utilized OpenAIEmbeddings from LangChain for embedding generation.

**Storing Embeddings:

-  Switched from ChromaDB to FAISS, which offers efficient similarity search and scalable vector storage.
-  [Refernce]((https://python.langchain.com/api_reference/community/vectorstores/langchain_community.vectorstores.faiss.FAISS.html))

**Retrievers:** [VectoreStoreRetriever](https://api.python.langchain.com/en/latest/langchain_api_reference.html#module-langchain.retrievers).

- Implemented FAISS-based retrieval instead of ChromaDB's VectorStoreRetriever.
- Retrievers provide Easy way to combine documents with language models.A retriever is an interface that returns documents given an unstructured query.
- It is more general than a vector store. A retriever does not need to be able to store documents, only to return (or retrieve) them.
- Optimized similarity search with cosine similarity to improve retrieval precision.

**Re-Ranking with a Cross Encoder:**

- Integrated HuggingFaceCrossEncoder (model BAAI/bge-reranker-base) for re-ranking retrieved results.
- with [HuggingFaceCrossEncoder](https://python.langchain.com/api_reference/community/cross_encoders/langchain_community.cross_encoders.huggingface.HuggingFaceCrossEncoder.html)

**Enhancements in Query Handling:**
- Added new question sets to improve model performance.
- Improved the ranking logic to ensure more relevant results appear higher.

## Chains:

 - we can create a chain that takes user input, formats it with a PromptTemplate, and then passes the formatted response to an LLM.
- Leveraged the rlm/rag-promp from LangChain Hub.Constructed a custom RAG chain for better integration with FAISS and cosine similarity,retreivalQA 
- [reference](https://python.langchain.com/docs/versions/migrating_chains/retrieval_qa/)



## 6. System Architecture

![](./Images/arch1.png) 
![](./Images/arch2.png)

## 7. Prerequisites

- Python 3.7+
- langchain 0.3.13
- Please ensure that you add your OpenAI API key to the empty text file named "OpenAI_API_Key.txt" in order to access
  the
  OpenAI API.

## 8. Running

- Clone the github repository
  ```shell
  $ git clone https://github.com/Ilovemom6666/Semantic-Spotter-Assignment.git
  ```
- Open
  the [notebook](https://github.com/Ilovemom6666/Semantic-Spotter-Assignment/blob/main/Semantic-Spotter-Assignment.ipynb)
  in jupyter and run all cells.
