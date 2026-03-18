# Clinical-RAG: MedGemma Interpreter with Hierarchical Tree Retrieval

### 🏥 Project Overview
This project showcases a specialized **Retrieval-Augmented Generation (RAG)** pipeline designed for clinical decision support. The system moves beyond standard vector search by implementing a **Hierarchical Clinical Tree**, which categorizes medical knowledge into structured dimensions (State, Emotion, Concern, Risk) to provide grounded, empathetic context to the **MedGemma** model.

### 🛠 Technical Architecture
* **LLM Core:** MedGemma (Specialized Medical LLM).
* **Vector Engine:** Chaturya Vector Engine (Custom 512-dimension embeddings).
* **Indexing:** FAISS (Facebook AI Similarity Search) for high-performance semantic retrieval.
* **Data Structure:** Multi-branch tree architecture with **53,789 indexed clinical nodes**.
* **Environment:** Python 3.12, PyTorch, Pandas, Pickle.

### 📂 Notebook Breakdown
* **`medgemma-builder-notebook.ipynb`**: **[The Data Engineering Layer]**
    * Covers the end-to-end pipeline of embedding generation and FAISS indexing.
    * Implements the logic to construct the four-branch clinical tree (STATE, EMOTION, CONCERN, RISK).
* **`medgemma-app-notebook.ipynb`**: **[The Application Layer]**
    * Features the inference engine and the RAG-grounding logic.
    * Includes a stateful conversation handler and prompt engineering for MedGemma.

### 🚀 Key Technical Contributions
* **Dimensional Knowledge Retrieval:** Instead of a flat search, the system retrieves context across four distinct clinical "branches," ensuring a holistic understanding of the patient's physical and emotional state.
* **Optimized Retrieval:** Engineered a scalable FAISS index capable of handling tens of thousands of clinical parameters with sub-millisecond latency.
* **Medical Grounding:** Developed a custom prompt-building logic that integrates retrieved anchors to significantly reduce LLM hallucinations in sensitive clinical scenarios.

### 📊 Tree Distribution
The retrieval tree is structured as follows:
* **STATE:** 11,554 nodes (Clinical status/Vitals)
* **EMOTION:** 12,825 nodes (Psychological context)
* **CONCERN:** 14,429 nodes (Patient-reported issues)
* **RISK:** 14,981 nodes (Safety and clinical risk factors)

---
*Developed as a demonstration of advanced RAG techniques and clinical AI integration.*
