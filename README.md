# Project Overview
Welcome to our project! This project is built using FastAPI framework to create a fast and modern API with Python.

## Features
API Endpoint : This project provides various API endpoint to perform specific tasks.
Data Validation : Utilize FastAPI data validation and serialization feature.
Interactive Documentation : Access Swagger UI and ReDoc for interactive API documentation.

## API Documentation

### Core APIs

#### 1. Chat Bot
- **Endpoint**: `/chat_bot`
- **Method**: POST
- **Description**: Performs RAG-based question answering
- **Parameters**:
  - `uri`: Neo4j database URI
  - `model`: Model to use for chat
  - `userName`: Neo4j username
  - `password`: Neo4j password
  - `database`: Database name
  - `question`: User's question
  - `document_names`: Optional document filter
  - `session_id`: Chat session ID
  - `mode`: Search mode (vector/graph)
  - `email`: Optional email for logging

#### 2. Search Context
- **Endpoint**: `/search_context`
- **Method**: POST
- **Description**: Retrieves relevant context based on query
- **Parameters**:
  - `query`: Search query
  - `uri`: Neo4j database URI
  - `database`: Database name
  - `userName`: Neo4j username
  - `password`: Neo4j password
  - `document_names`: Optional document filter
  - `mode`: Search mode (default: "vector")
  - `top_k`: Number of results to return
  - `score_threshold`: Similarity threshold
  - `email`: Optional email for logging

#### 3. Graph Query
- **Endpoint**: `/graph_query`
- **Method**: POST
- **Description**: Performs graph-based queries
- **Parameters**:
  - `uri`: Neo4j database URI
  - `database`: Database name
  - `userName`: Neo4j username
  - `password`: Neo4j password
  - `document_names`: Optional document filter
  - `email`: Optional email for logging

### Document Management APIs

#### 1. Upload
- **Endpoint**: `/upload`
- **Method**: POST
- **Description**: Uploads and processes large files
- **Parameters**:
  - `file`: File to upload
  - `chunkNumber`: Current chunk number
  - `totalChunks`: Total number of chunks
  - `originalname`: Original file name
  - `model`: Processing model
  - `uri`: Neo4j database URI
  - `userName`: Neo4j username
  - `password`: Neo4j password
  - `database`: Database name
  - `email`: Optional email for logging

#### 2. Extract
- **Endpoint**: `/extract`
- **Method**: POST
- **Description**: Extracts knowledge graph from files
- **Parameters**:
  - `uri`: Neo4j database URI
  - `userName`: Neo4j username
  - `password`: Neo4j password
  - `model`: Extraction model
  - `database`: Database name
  - `source_url`: Source URL
  - `file_name`: File name
  - `allowedNodes`: Allowed node types
  - `allowedRelationship`: Allowed relationship types
  - `token_chunk_size`: Chunk size for processing
  - `chunk_overlap`: Chunk overlap size
  - `chunks_to_combine`: Number of chunks to combine
  - `language`: Processing language
  - `email`: Optional email for logging

### Graph Management APIs

#### 1. Schema
- **Endpoint**: `/schema`
- **Method**: POST
- **Description**: Retrieves graph schema information
- **Parameters**:
  - `uri`: Neo4j database URI
  - `userName`: Neo4j username
  - `password`: Neo4j password
  - `database`: Database name
  - `email`: Optional email for logging

#### 2. Schema Visualization
- **Endpoint**: `/schema_visualization`
- **Method**: POST
- **Description**: Generates graph schema visualization
- **Parameters**:
  - `uri`: Neo4j database URI
  - `userName`: Neo4j username
  - `password`: Neo4j password
  - `database`: Database name

### Utility APIs

#### 1. Health Check
- **Endpoint**: `/health`
- **Method**: GET
- **Description**: Checks application health status

#### 2. Backend Connection Configuration
- **Endpoint**: `/backend_connection_configuration`
- **Method**: POST
- **Description**: Tests backend database connection

#### 3. Document Status
- **Endpoint**: `/document_status/{file_name}`
- **Method**: GET
- **Description**: Retrieves document processing status
- **Parameters**:
  - `file_name`: Name of the document
  - `url`: Neo4j database URL
  - `userName`: Neo4j username
  - `password`: Neo4j password
  - `database`: Database name

## Getting Started 

Follow these steps to set up and run the project locally:

1. Clone the Repository:

> git clone https://github.com/neo4j-labs/llm-graph-builder.git

> cd llm-graph-builder

2. Install Dependency :

> pip install -t requirements.txt

## Run backend project using unicorn
Run the server:
> uvicorn score:app --reload

## Run project using docker
## prerequisite 
Before proceeding, ensure the following software is installed on your machine

Docker: https://www.docker.com/

1. Build the docker image
   > docker build -t your_image_name .
   
   Replace `your_image_name` with the meaningful name for your Docker image

2. Run the Docker Container
   > docker run -it -p 8000:8000 your_image_name
   
   Replace `8000` with the desired port.

## Access the API Documentation
Open your browser and navigate to
http://127.0.0.1:8000/docs for Swagger UI or
http://127.0.0.1:8000/redocs for ReDoc.

## Project Structure
`score.py`: Score entry point for FastAPI application

## Configuration

Update the environment variable in `.env` file. Refer example.env in backend folder for more config.

`OPENAI_API_KEY`: Open AI key to use incase of openai embeddings

`EMBEDDING_MODEL` : "all-MiniLM-L6-v2" or "openai" or "vertexai"

`NEO4J_URI` : Neo4j URL

`NEO4J_USERNAME` : Neo4J database username

`NEO4J_PASSWORD` : Neo4j database user password

`AWS_ACCESS_KEY_ID` : AWS Access key ID

`AWS_SECRET_ACCESS_KEY` : AWS secret access key

## Contact
For questions or support, feel free to contact us at christopher.crosbie@neo4j.com or michael.hunger@neo4j.com
