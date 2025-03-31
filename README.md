# VectorDB

A Jupyter notebook demonstration of using **LangChain** with **Chroma DB** for local document embedding and semantic search. This project walks through chunking text data, embedding it using OpenAI or Hugging Face models, and storing it in a persistent Chroma database for efficient similarity search.

Perfect for developers and students exploring practical applications of vector databases, semantic retrieval, and language model integration.

---

## Features

- **Document Chunking**: Splits text into manageable chunks using `RecursiveCharacterTextSplitter`.
- **Embeddings**: Generates vector representations with `HuggingFaceEmbeddings` or `OpenAIEmbeddings`.
- **Chroma DB Integration**: Stores and retrieves document embeddings locally using Chroma DB.
- **Semantic Search**: Enables natural language queries to retrieve relevant document segments.
- **LangChain Compatibility**: Designed using LangChain’s `VectorstoreIndexCreator` and `Chroma` utilities.

---

## How It Works

### 1. Load and Process Data
- Takes `.txt` documents as input. This demo uses:
  - `digital_privacy_in_the_modern_world.txt`
  - `benefits_of_reading_daily.txt`
  - `climate_change_and_its_effects.txt`
  - `impact_of_social_media.txt`
  - `importance_of_sleep.txt`
  - `remote_work_trends.txt`
- Uses `LangChain` tools to split them into overlapping text chunks.

### 2. Generate Embeddings
- Embeds text chunks using either:
  - **OpenAI GPT-based embeddings**, or
  - **HuggingFace Transformers** (e.g., `all-MiniLM-L6-v2`).

### 3. Store in Chroma DB
- Saves embeddings locally with persistent storage for reuse.
- You can perform similarity search without reprocessing every time.

### 4. Query Semantically
- Accepts user questions and returns matching chunks from the database.
- Useful for QA systems, chatbots, and document search tools.

---

## Installation & Setup

### 1. Clone the Repository
```bash
git clone https://github.com/yourusername/chroma-db-demo.git
cd chroma-db-demo
```

### 2. Create and Activate Environment
Using Conda:
```bash
conda create -n chroma-env python=3.10 -y
conda activate chroma-env
```

### 3. Install Dependencies
```bash
pip install langchain chromadb openai sentence-transformers tiktoken
```

> Optional (for Hugging Face embeddings):
```bash
pip install transformers
```

---

## Usage

1. Place your `.txt` files in the same directory.
2. Open the notebook:
```bash
jupyter notebook Chroma_DB_Demo.ipynb
```
3. Run the cells step-by-step to:
   - Load and split your data
   - Create and persist embeddings
   - Query the database semantically

---

## Example

```
query = "How would you say the narrative changes how people/what people do about an issue?"

The narrative can change people's perception and understanding of the issue, potentially leading to different actions or behaviors in response. For example, if the narrative shifts from viewing climate change as a distant threat to a present crisis, individuals may be more motivated to take action and support policies and behaviors that address the issue. Similarly, if the narrative around social media shifts from solely negative effects on mental health to also highlighting responsible usage and digital literacy, individuals may be more mindful of their online behavior and make changes to protect their well-being. 


Sources:
/content/Texts/climate_change_and_its_effects.txt
/content/Texts/impact_of_social_media.txt
/content/Texts/climate_change_and_its_effects.txt
/content/Texts/digital_privacy_in_the_modern_world.txt
```

---

## Notes

- This demo uses local storage via Chroma DB’s `persist_directory`.
- Swap between OpenAI and Hugging Face models by toggling the `embedding_function` setup.
- GPT-based models require an OpenAI API key.

---

## License

This project is open-source and licensed under the MIT License.  
For academic and experimental use.

