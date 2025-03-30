Repository Structure Summary
Project Overview
This appears to be a backend service for an LLM-based graph builder system that processes documents, creates relationships, and performs QA operations.
Core Components
1. Main Application (src/main.py)
The primary entry point of the application
Contains the main application logic and API endpoints
2. Document Processing
src/document_sources/ - Handles different document source types
web_pages.py - Processes web pages using WebBaseLoader
diffbot_transformer.py - Integration with Diffbot service
3. Graph Operations
src/graphDB_dataAccess.py - Database operations for graph storage
src/make_relationships.py - Logic for creating relationships between entities
src/neighbours.py - Handles neighbor-related operations in the graph
src/graph_query.py - Query operations on the graph
4. LLM Integration
src/llm.py - LLM integration and operations
src/QA_integration.py - QA system integration
src/ragas_eval.py - Evaluation using RAGAS framework
5. Entity Management
src/entities/ - Entity-related operations
src/chunkid_entities.py - Entity chunking operations
src/create_chunks.py - Document chunking functionality
6. Community Analysis
src/communities.py - Community detection and analysis
7. Shared Components (src/shared/)
common_fn.py - Common utility functions
constants.py - System-wide constants
llm_graph_builder_exception.py - Custom exception handling
schema_extraction.py - Schema extraction utilities
8. Testing
test_commutiesqa.py - Community QA testing
test_integrationqa.py - Integration QA testing
Performance_test.py - Performance testing
dbtest.py - Database testing
9. Deployment
Dockerfile - Container configuration
requirements.txt - Python dependencies
example.env - Environment variable template
10. Performance Monitoring
locustperf.py - Load testing using Locust
score.py - Scoring and evaluation
Key Features
Document processing from various sources
Graph database operations
LLM integration for processing
QA system integration
Community detection and analysis
Performance monitoring and testing
Containerized deployment support
Technology Stack
Python-based backend
Graph database integration
LLM integration
Docker containerization
Testing frameworks (including Locust for performance testing)
This structure suggests a sophisticated system for processing documents, building knowledge graphs, and performing QA operations with LLM integration. The codebase is well-organized with clear separation of concerns and comprehensive testing coverage.