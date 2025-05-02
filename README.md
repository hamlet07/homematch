# HomeMatch

**HomeMatch** is an intelligent real estate matching system that leverages Large Language Models (LLMs) and vector databases to enhance the property search experience. This project demonstrates how natural language queries can be transformed into structured filters and used to retrieve relevant property listings using semantic search and metadata filtering.

---

## 📌 Overview

HomeMatch explores how prompt engineering and LLMs can:

* Generate realistic real estate listings.
* Parse user-friendly, natural language queries into structured search filters.
* Combine metadata filtering with semantic search using a vector database (ChromaDB).

---

## 📁 Project Structure

```
HomeMatch/
├── homematch.ipynb                  # Main notebook demonstrating the full pipeline
├── data
   ├── real_estates_listings.json    # Generated sample real estate data
   ├── chroma.sqlite3                # Local ChromaDB vector database with embeddings
   ├── 27b...(catalog)               # Local ChromaDB vector database with embeddings
├── requirements.txt                 # Required Python packages
```

---

## 🚀 Getting Started

1. **Install dependencies:**

   ```bash
   pip install -r requirements.txt
   ```

   It's recommended to use a virtual environment.

2. **Run the Jupyter Notebook:**

   Open and execute `homematch.ipynb`. The notebook walks through:

   * Generating synthetic real estate listings.
   * Loading data into ChromaDB.
   * Performing semantic and filtered queries using user input.

> ✅ You can skip directly to the query section if sample data is already generated — just ensure the earlier cells are executed.

---

## 🔧 Dependencies

* Python 3.x
* [OpenAI GPT-3.5 Turbo](https://platform.openai.com/)
* [ChromaDB](https://www.trychroma.com/) (Vector DB)
* [LangChain](https://www.langchain.com/) (optional for advanced LLM workflows)

**Note:** You must set your OpenAI API key:

```bash
export OPENAI_API_KEY="your-key"
```

Or inside Python:

```python
import os
os.environ["OPENAI_API_KEY"] = "your-key"
```

---

## 🔧 Main Components & Functions

| Function                                                          | Description                                                         |
| ----------------------------------------------------------------- | ------------------------------------------------------------------- |
| `generate_listing()` / `generate_multiple_listings(n=10)`         | Create synthetic real estate listings using GPT                     |
| `get_embeddings(texts)`                                           | Generate and store vector embeddings of listings                    |
| `collection.add(...)`                                             | Add listings to ChromaDB with metadata and embeddings               |
| `parse_query_into_features(query_text)`                           | Parse user query into structured filters like price, bedrooms, size |
| `personalized_query_results(query_text, tolerance=True, top_k=3)` | Semantic + metadata search with adjustable filtering                |
| `summarize_listing(description, neighborhood_description,query_text)`                                               | Creates personalized summary                                        |
| `display_results(results)`                                        | Nicely formats and displays the final matching listings             |

---

## 💡 Example Query

> *"Luxury estate with pool in Sunset Hills to 2 million dollars and not less than 1,500 sqft"*

> *"Modern house with 2 bedrooms for young man, active in business and looking for easy access to entertainment"*

> *"Modern house in prestigious place. No limitation on price. Seaside view. Home for family with 2 children"*

These would be parsed into structured filters and used to retrieve the most relevant listings.

---






