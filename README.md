# 🧠 Knowledge Graph Analysis & Question Answering using NetworkX, ArangoDB & LangChain

## 📌 Project Overview
This project demonstrates how to **build, store, analyze, visualize, and query a large-scale knowledge graph** using real-world scientific domain data.  
It integrates **NetworkX**, **ArangoDB (graph database)**, and **LangChain + OpenAI** to enable **natural language question answering over graph data**.

The dataset represents a **network of scientific fields extracted from Wikipedia**, where nodes represent disciplines and edges represent semantic similarity.

---

## 🎯 Objectives
- Construct a large graph from CSV data
- Analyze graph structure using NetworkX
- Store the graph in ArangoDB for scalability
- Visualize complex relationships
- Enable **LLM-powered natural language queries** over the graph

---
<img width="2166" height="1342" alt="image" src="https://github.com/user-attachments/assets/cb1a718b-de94-40ca-9b6b-bbf2b624b3bd" />

## 🧩 Dataset Description

| File | Description |
|----|----|
| `nodes.csv` | Scientific fields with metadata |
| `edges.csv` | Relationships with cosine similarity |
| `gprops.csv` | Graph-level properties |

Here is somthing by which you will understand in easy way : Its so simple , i asked query , it answered me correctly through the connections from graph !!!!!!!!!!!!!!!!!!!!!!! Its Super Awsome!
<img width="1054" height="1550" alt="image" src="https://github.com/user-attachments/assets/c1b493ec-747c-4264-8913-9c33d9a9baa5" />
<img width="1264" height="1036" alt="image" src="https://github.com/user-attachments/assets/7d0578b0-47ca-4a9c-896d-e9384191cbf6" />



**Graph Statistics**
- Nodes: **687**
- Edges: **6,523**

---

## 🛠️ Tech Stack
- Python 3.11  
- NetworkX  
- nx-arangodb  
- ArangoDB Cloud  
- LangChain  
- LangGraph  
- OpenAI API  
- Pandas, NumPy  
- Matplotlib  

---

## 📂 Project Workflow

### 1️⃣ Install Dependencies
```bash
pip install networkx nx-arangodb python-arango
pip install langchain langchain-community langchain-openai langgraph
