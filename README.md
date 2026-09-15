# AI-Powered Semantic Retrieval Pipeline

A C# semantic retrieval application that combines vector embeddings, similarity-based document retrieval, and local LLM-generated responses.

The project demonstrates how a natural-language query can be transformed into a vector embedding, used to retrieve a semantically relevant document, and combined with the retrieved context to generate an AI-based response.

## How It Works

The application follows a retrieval-augmented generation (RAG) style pipeline:

1. The user provides a search algorithm and a natural-language query through command-line arguments.
2. The query is converted into a vector embedding using a locally running Phi-3 model through Ollama.
3. The embedding is passed to the vector-search component to retrieve the most relevant document.
4. Search execution time is measured using `Stopwatch`.
5. The corresponding movie review is loaded from the document dataset.
6. The original query and retrieved review are sent to Phi-3 to generate a contextual response.

```text
User Query
    ↓
Ollama / Phi-3
    ↓
Query Embedding
    ↓
Vector Search
    ↓
Relevant Movie Review
    ↓
Query + Retrieved Context
    ↓
Phi-3
    ↓
Generated Response
```

## My Contribution

This project was developed as part of an academic assignment.

The vector-search implementation and dataset infrastructure were provided as course scaffolding.

My implementation focused on building the C# application layer that connects the different components of the retrieval pipeline, including:

- Processing command-line input
- Generating query embeddings through the Ollama REST API
- Integrating the provided vector-search component
- Retrieving the corresponding document
- Measuring search execution time
- Sending the query and retrieved context to the LLM
- Generating a contextual natural-language response
- Handling asynchronous HTTP communication in C#

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

## Vector Retrieval

The project uses a provided vector-search component that operates on 384-dimensional embeddings stored in a binary file.

The component supports different retrieval strategies and uses cosine similarity to compare the query embedding with stored document vectors.

My application integrates this component into the end-to-end retrieval and generation workflow.

## Dataset

The application works with a collection of movie reviews.

Each document is associated with a stored vector representation. After the vector-search component identifies the most relevant vector, the application retrieves the corresponding review from the document collection.

## Performance Measurement

The application measures the execution time of the vector-search stage using C#'s `Stopwatch`.

This makes it possible to observe the performance characteristics of different retrieval strategies while keeping embedding generation and LLM response generation outside the measured search interval.

## Running the Project

The application expects Ollama to be running locally with the required Phi-3 model available.

Example:

```bash
dotnet run <algorithm> "your search query"
```

The application will:

1. Generate an embedding for the query.
2. Perform vector retrieval.
3. Print the search execution time.
4. Retrieve the relevant movie review.
5. Generate an AI response using the retrieved context.

## Project Structure

```text
├── Program.cs
├── VectorSearch.cs
├── RagProject.csproj
├── documents.txt
└── vectors.bin
```

`Program.cs` contains the application and integration logic implemented as part of my work.

`VectorSearch.cs` and the dataset/vector infrastructure were provided as part of the academic assignment.

## Key Takeaways

This project provided hands-on experience with:

- Integrating local LLMs into a C# application
- Working with vector embeddings and semantic retrieval
- Communicating with AI services through REST APIs
- Building an end-to-end retrieval and generation pipeline
- Working with file and network I/O
- Measuring search performance
- Using asynchronous programming in .NET
