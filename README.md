# Deep Research AI System

## Overview
This project implements a Deep Research AI system that automates online research, processes gathered information, and generates structured answers using AI models. The system is designed to efficiently gather and summarize information from various sources, making it useful for students, researchers, and professionals.

## Features
- **Web Crawling**: Uses Tavily to search the web for the most relevant and recent information related to a given query.
- **Data Processing and Storage**:
  - Splits large amounts of gathered text into smaller chunks using LangChain's `RecursiveCharacterTextSplitter`.
  - Stores processed text using FAISS, a vector database that allows efficient retrieval of similar information.
- **AI Agents**:
  - **Research Agent**: Queries the web using Tavily and stores the retrieved data.
  - **Answer Drafting Agent**: Extracts relevant stored data, processes it, and formulates a coherent response using GPT-4.
  - **Quality Control Agent**: Enhances the answer by refining language, improving clarity, and ensuring coherence.
- **Automated Workflow with LangGraph**:
  - Organizes the execution of the AI agents sequentially.
  - Ensures smooth data flow from one stage to another.
  - Implements structured decision-making in processing responses.

## Requirements
To run this AI research system, ensure you have the following:
- **Python 3.8+**
- **Required Python Libraries**:
  - `langchain` (for AI model interactions and data processing)
  - `langgraph` (for designing the workflow structure)
  - `faiss-cpu` (for efficient similarity search and information retrieval)
  - `openai` (for using GPT-4 to generate answers)
  - `tavily` (for web searching and gathering online information)

## Setup Instructions
### 1. Install Required Dependencies
Run the following command in your terminal or command prompt:
   ```sh
   pip install langchain langgraph faiss-cpu openai tavily
   ```

### 2. Set Up API Keys
This project requires API keys for Tavily (for web searching) and OpenAI (for text generation). Set them as environment variables:
   ```sh
   export TAVILY_API_KEY="your_tavily_api_key"
   export OPENAI_API_KEY="your_openai_api_key"
   ```

For Windows, use:
   ```sh
   set TAVILY_API_KEY="your_tavily_api_key"
   set OPENAI_API_KEY="your_openai_api_key"
   ```

### 3. Run the Program
Execute the script by running:
   ```sh
   python deep_research_ai.py
   ```

## Usage Guide
- Modify the `query` variable in the script to search for different topics. Example:
   ```python
   query = "Latest advancements in quantum computing"
   ```
- The AI system will:
  1. Search for relevant web content.
  2. Extract and store useful information.
  3. Generate a structured response.
  4. Refine and present the final answer.

## Future Improvements
- **Enhanced Accuracy**: Improve filtering mechanisms to remove irrelevant data.
- **Multi-Source Search**: Integrate additional search APIs beyond Tavily for a broader knowledge base.
- **User Interface**: Develop a web or mobile UI for interactive querying and result visualization.
- **Context-Aware Answering**: Implement memory-based answering to provide more contextual responses over multiple queries.
- **Better Summarization Models**: Use advanced summarization techniques to create more concise and accurate responses.

This project serves as a foundation for building an AI-driven research assistant capable of automating knowledge gathering and processing tasks efficiently.

