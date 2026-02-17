# RAG-with-fiction-books
This project implements a simple Retrieval-Augmented Generation (RAG) pipeline using custom PDF books (e.g., Harry Potter series) as the knowledge source.  The goal is to build a question-answering system that answers queries strictly based on the uploaded documents instead of relying on general internet knowledge.

How It Works

1. PDF books are uploaded to Google Drive.
2. Google Colab notebook accesses the books from:

   ```
   /content/drive/MyDrive/books
   ```
3. The PDFs are loaded and split into smaller text chunks.
4. Each chunk is converted into vector embeddings using a sentence-transformer model.
5. The embeddings are stored in a FAISS vector database.
6. When a question is asked:

   * The question is converted into an embedding.
   * FAISS retrieves the most relevant text chunks.
   * Those chunks are passed to a language model (FLAN-T5).
   * The model generates an answer grounded in the retrieved context.


Technologies Used

* LangChain
* FAISS (Vector Database)
* Sentence-Transformers (Embeddings)
* HuggingFace Transformers
* Google Colab
* PyPDF
* Python


Key Concepts Demonstrated

* Vector embeddings
* Semantic similarity search
* Top-k retrieval
* Prompt grounding
* LLM-based answer generation
* Basic RAG architecture

Setup

1. Upload PDF books to Google Drive.
2. Mount Google Drive in Colab.
3. Run the notebook cells in order.
4. Ask questions about the uploaded books.


Example Query

```
How did Harry get his scar?
```

The system retrieves relevant passages and generates an answer strictly from the provided book content.

