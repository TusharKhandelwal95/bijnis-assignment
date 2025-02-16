## 📌 Approach Overview

### 1️⃣ Data Preprocessing  
- **Cleaning:** Used 3000 records for demonstration. Converts queries to lowercase and removes non-alphanumeric characters.  
- **Spell Correction:** Applies spell correction (using PySpellChecker) to generate a corrected query.   

### 2️⃣ Embedding & FAISS Indexing  
- **Embedding:** Uses `all-MiniLM-L6-v2` from SentenceTransformer to convert queries into vector representations.  
- **Indexing:** Builds a FAISS index for fast similarity search and stores it for efficient retrieval.  

### 3️⃣ Clustering  
- **KMeans Clustering:** Groups query embeddings into clusters based on semantic similarity.  
- **Caching:** Saves clustered data in `clustered_data.csv`.  

### 4️⃣ Topic Modeling  
- **LDA (Latent Dirichlet Allocation):** Extracts topics from each cluster using Gensim’s LDA model.  
- **JSON Output:** Saves topics per cluster in `topics.json` (ensuring valid JSON keys).  

### 5️⃣ Insights & Visualization  
- **Error Analysis:** Compares original and corrected queries, flags spelling errors, and calculates error percentages per cluster.  
- **Visualization:**  
  - Generates a **bar chart** showing query distribution across clusters.  
  - Displays **sample queries per cluster** for further analysis.  
