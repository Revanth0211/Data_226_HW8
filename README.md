# Data_226_HW8
Overview

This project builds a semantic search engine using Apache Airflow, Sentence Transformers, and Pinecone.
The Airflow DAG automates a full pipeline — downloading data, processing it, generating embeddings, creating a Pinecone index, and running semantic search queries.

It follows the class assignment “Run Pinecone as an Airflow job” (Data 226 / Data Warehouse).

| Tool                      | Purpose                                       |
| ------------------------- | --------------------------------------------- |
| **Apache Airflow**        | Orchestrates all ETL and indexing steps       |
| **Sentence-Transformers** | Converts text into numerical embeddings       |
| **Pinecone**              | Vector database to store and query embeddings |
| **Docker Compose**        | Runs the entire Airflow environment locally   |


Tool	Purpose
Apache Airflow	Orchestrates all ETL and indexing steps
Sentence-Transformers	Converts text into numerical embeddings
Pinecone	Vector database to store and query embeddings
Docker Compose	Runs the entire Airflow environment locally
 DAGs Implemented
Medium_to_Pinecone

Builds a semantic search index using Medium article data.

Tasks:

download_data – Downloads the Medium dataset CSV.

preprocess_data – Cleans data and generates input for Pinecone.

create_pinecone_index – Creates the Pinecone index (semantic-search-fast).

generate_embeddings_and_upsert – Embeds text and upserts to Pinecone.

test_search_query – Runs a test query and logs top matches.

 build_pinecone_search

An alternate DAG using Romeo & Juliet text to demonstrate the same workflow.

Tasks:

download_data – Downloads text from Project Gutenberg.

process_data – Splits into paragraphs and prepares a CSV.

create_index – Creates the Pinecone index (PINECONE_INDEX_NAME variable).

embed_and_upsert – Embeds paragraphs and inserts into Pinecone.

run_search – Executes a semantic search query.
