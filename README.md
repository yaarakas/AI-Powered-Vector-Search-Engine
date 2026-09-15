# AI-Powered Semantic Retrieval Pipeline

A C# semantic retrieval application that integrates vector embeddings, document retrieval, and local LLM-generated responses.

This project was developed as part of an academic assignment and demonstrates how a natural-language query can be transformed into an embedding, passed through a vector-retrieval component, and combined with retrieved context to generate an AI-based response.

## How It Works

The application follows a retrieval-augmented generation (RAG) style pipeline:

1. The user provides a retrieval algorithm and a natural-language query through command-line arguments.
2. The query is converted into a vector embedding using Phi-3 through a locally running Ollama instance.
3. The embedding is passed to the course-provided vector-search component.
4. Search execution time is measured using C# `Stopwatch`.
5. The application retrieves the document corresponding to the search result.
6. The original query and retrieved document are sent to Phi-3 to generate a contextual response.

```text
User Query
    ↓
Ollama / Phi-3
    ↓
Query Embedding
    ↓
Vector Retrieval
    ↓
Relevant Document
    ↓
Query + Retrieved Context
    ↓
Phi-3
    ↓
Generated Response
```

## My Contribution

My implementation focused on the C# application layer that connects the different stages of the retrieval pipeline.

I implemented:

- Command-line input handling and validation
- Query embedding generation through the Ollama REST API
- Integration with the provided vector-search component
- Retrieval of the document corresponding to the search result
- Search execution-time measurement using `Stopwatch`
- Integration with Phi-3 for natural-language response generation
- Passing both the original query and retrieved context to the LLM
- Asynchronous HTTP communication using `HttpClient`
- JSON serialization and response parsing

## Technologies

- C#
- .NET
- Ollama
- Phi-3
- REST APIs
- Vector Embeddings
- Semantic Retrieval
- JSON
- File I/O
- Asynchronous Programming

## Course-Provided Components

The original academic assignment included:

- A vector-search implementation
- A movie-review dataset
- Precomputed document vectors

These components were provided as course infrastructure and are not included in this repository.

This repository focuses specifically on the application and integration layer that I implemented.

## Embedding Generation

The application communicates with a locally running Ollama instance using HTTP.

A user query is sent to the embedding endpoint and converted into a vector representation using Phi-3. The resulting embedding is then passed to the provided retrieval component.

## Retrieval and Response Generation

After the retrieval component identifies the most relevant document, the application loads the corresponding text from the dataset.

The retrieved document and the user's original query are then combined into a prompt and sent to Phi-3 through Ollama's generation API.

This creates an end-to-end flow from a natural-language query to semantic retrieval and an LLM-generated response.

## Performance Measurement

The application measures the execution time of the vector-search stage using C#'s `Stopwatch`.

The measurement focuses specifically on retrieval time, excluding embedding generation and LLM response generation.

## Repository Structure

```text
├── Program.cs
├── RagProject.csproj
├── .gitignore
└── README.md
```

`Program.cs` contains my implementation of the application and integration logic.

The course-provided search implementation, dataset, and precomputed vectors are intentionally excluded from this repository.

## Running the Project

The complete original academic environment requires the course-provided vector-search component, dataset, and precomputed vectors, which are not distributed in this repository.

The application also requires a locally running Ollama instance with the required Phi-3 model.

Because the course-provided components are excluded, this repository is intended primarily to demonstrate my implementation and integration work rather than serve as a standalone distribution of the full academic assignment.

## Key Takeaways

Through this project, I gained hands-on experience with:

- Integrating a local LLM into a C# application
- Working with vector embeddings and semantic retrieval
- Communicating with AI services through REST APIs
- Connecting retrieval and generation components
- Asynchronous programming in .NET
- File and network I/O
- Measuring retrieval performance
- Building a RAG-style application pipeline
