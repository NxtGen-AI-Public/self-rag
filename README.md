# Self-RAG

## Overview
Self-RAG is an advanced implementation of Retrieval-Augmented Generation (RAG) that incorporates self-reflection and self-grading mechanisms. This approach improves the relevance and accuracy of retrieved information and generated responses by integrating structured decision-making and evaluation.

This repository implements Self-RAG from scratch using [LangGraph](https://langchain-ai.github.io/langgraph/), a framework for building reasoning and retrieval workflows.

## Features
- **Retrieval**: Fetches relevant documents from a ChromaDB vector store.
- **Relevance Grading**: Evaluates if retrieved documents are relevant to the query.
- **Generation**: Produces responses using a custom LLM.
- **Hallucination Detection**: Checks if the response is grounded in retrieved documents.
- **Answer Quality Grading**: Assesses whether the generated response sufficiently answers the question.
- **Query Rewriting**: Refines the query to improve retrieval quality.

## Installation
### Prerequisites
- Python 3.8+
- [LangChain](https://python.langchain.com/)
- [LangGraph](https://github.com/langchain-ai/langgraph)
- [ChromaDB](https://github.com/chroma-core/chroma)
- [Hugging Face Transformers](https://huggingface.co/docs/transformers/)

### Setup
1. Clone this repository:
   ```sh
   git clone https://github.com/yourusername/self-rag.git
   cd self-rag
   ```
2. Create a virtual environment and activate it:
   ```sh
   python -m venv env
   source env/bin/activate  # On Windows use: env\Scripts\activate
   ```
3. Install dependencies:
   ```sh
   pip install -r requirements.txt
   ```
4. Set up Hugging Face authentication:
   ```sh
   export HUGGINGFACE_TOKEN=your_huggingface_token  # On Windows use: set HUGGINGFACE_TOKEN=your_huggingface_token
   ```

## Usage
### Running the Self-RAG Workflow
```sh
python self_rag.py
```

## How It Works
1. **Load Documents & Create Vector Store**: Uses `ChromaDB` to store document embeddings.
2. **Retrieve Relevant Chunks**: Fetches the most relevant document sections.
3. **Grade Relevance**: Determines if retrieved documents are useful.
4. **Generate Responses**: Uses an LLM to generate answers.
5. **Validate Responses**: Checks for hallucinations and assigns an answer quality score.
6. **Iterate with Query Refinement**: Improves retrieval with better queries.

## Configuration
Modify file to adjust parameters like chunk size, retrieval count, and model selection.

## Contributing
Pull requests are welcome! If you find a bug or have suggestions, open an issue.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments
- [Self-RAG Paper](https://arxiv.org/abs/2310.11511)
- [LangGraph](https://langchain-ai.github.io/langgraph/)
- [Hugging Face](https://huggingface.co/)

