# Recipe Retrieval and Scaling Assistant

An AI-powered recipe assistant that uses semantic search to retrieve relevant recipes and dynamically scale ingredient quantities based on the desired serving size. Built with Python, LangChain, LangGraph, FAISS, HuggingFace embeddings, and OpenAI.

## Features

- **Semantic Recipe Retrieval:** Finds relevant recipes using FAISS vector search and HuggingFace embeddings.
- **Dynamic Recipe Scaling:** Adjusts ingredient quantities according to the requested serving size using a custom `scaler_tool`.
- **LLM Integration:** Uses OpenAI GPT-4.1-mini to interpret queries and generate responses.
- **Workflow Orchestration:** Uses LangGraph to coordinate retrieval, model execution, and tool calling.
- **Conversation Memory:** Uses LangGraph's `MemorySaver` to maintain conversation state across interactions.
- **Interactive Chat:** Allows users to request recipes and serving-size adjustments through a conversational interface.

## Tech Stack

- Python
- LangChain
- LangGraph
- OpenAI GPT-4.1-mini
- FAISS
- HuggingFace Sentence Transformers
- `sentence-transformers/all-MiniLM-L6-v2`
- Jupyter Notebook

## Project Structure

```text
recipe-retrieval-and-scaling-assistant/
├── recipe_assistant.ipynb
├── spaghetti_carbonara.txt
├── classic_pancakes.txt
├── chicken_curry.txt
└── README.md
```

## How It Works

1. **Load Recipes:** Reads recipe text files into LangChain documents.
2. **Generate Embeddings:** Converts recipes into vector representations using HuggingFace embeddings.
3. **Retrieve Relevant Recipes:** Searches the FAISS vector store for the most relevant recipe based on the user's query.
4. **Process the Query:** LangGraph passes the retrieved recipe context to the language model.
5. **Scale Ingredients:** When required, the model invokes `scaler_tool` to adjust ingredient quantities for the requested number of servings.
6. **Generate a Response:** The model uses the retrieved recipe and tool results to generate a natural-language answer.
7. **Maintain State:** `MemorySaver` preserves conversation state across turns.

## Included Recipes

- **Spaghetti Carbonara**
- **Classic Pancakes**
- **Chicken Curry**

Additional recipes can be added as text files following the existing recipe format.

## Installation and Setup

### Prerequisites

- Python 3.10+
- An OpenAI API key

### 1. Clone the Repository

```bash
git clone https://github.com/nofelmahmoodsubhani/recipe-retrieval-and-scaling-assistant.git
cd recipe-retrieval-and-scaling-assistant
```

### 2. Install Dependencies

```bash
pip install langchain langchain-openai langgraph langchain-community langchain-huggingface sentence-transformers faiss-cpu jupyter
```

### 3. Configure the API Key

Set your OpenAI API key as an environment variable.

**Windows PowerShell:**

```powershell
$env:OPENAI_API_KEY="your_api_key_here"
```

**macOS/Linux:**

```bash
export OPENAI_API_KEY="your_api_key_here"
```

Keep your API key private and never commit it to GitHub.

### 4. Run the Notebook

```bash
jupyter notebook
```

Open `recipe_assistant.ipynb` and execute the cells in order.

**Note:** Ensure the recipe filenames referenced in the notebook match the files in the repository before running it.
