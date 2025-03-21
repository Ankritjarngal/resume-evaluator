# Resume Parser & Evaluator

## Overview
This project is a **Resume Parser and Evaluator** that extracts structured information from resumes and assesses their quality. It integrates **Natural Language Processing (NLP)**, **Named Entity Recognition (NER)**, and **vector-based semantic search** using **Pinecone**.

## Features
- Extracts **emails, phone numbers, skills, education, work experience, projects, and certifications** from resumes.
- Uses **Named Entity Recognition (NER)** for structured data extraction.
- Evaluates resumes based on **predefined scoring criteria**.
- Provides an **overall score** along with scores for different sections.
- Stores resume embeddings in **Pinecone** for efficient retrieval.
- Enables **semantic search** to find resumes similar to a query.

## Pinecone Integration (Vector Database)(only backend for pinecone stuff is done yet)

### **Uploading Resumes to Pinecone**
1. **Resume Parsing**: Extracts structured data (skills, experience, education, etc.) and generates a text summary.
2. **Embedding Generation**: Converts the extracted text into a numerical vector (1024-dimension) using an embedding model.
3. **Data Cleaning**: Removes unnecessary characters (e.g., `\n`, extra spaces) for better metadata storage.
4. **Upsert to Pinecone**: Stores the vector along with structured metadata in Pinecone for future searches.

*

### **Searching Resumes in Pinecone**
1. **Query Embedding Generation**: Converts the search query into a numerical vector.
2. **Pinecone Query**: Searches the vector database for the most similar resumes.
3. **Filtering Results**: Filters results based on a similarity threshold.
4. **Returning Matches**: Returns the most relevant resumes along with metadata.



This setup ensures **efficient storage and retrieval** of resumes based on their **semantic similarity**, allowing for a smarter and faster search process.

