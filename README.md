Knowledge Graph Analysis & Question Answering using NetworkX, ArangoDB & LangChain
📌 Project Overview

This project demonstrates how to build, store, visualize, and query a large-scale knowledge graph using real-world scientific domain data.
It integrates NetworkX, ArangoDB (graph database), and LangChain + OpenAI to enable graph analytics and natural language question answering over graph data.

The dataset represents a network of scientific fields extracted from Wikipedia, where nodes are disciplines and edges represent semantic similarity.

🎯 Key Objectives

Load and preprocess graph data from CSV files

Construct and analyze a large graph using NetworkX

Store and manage the graph in ArangoDB

Visualize complex graph structures

Enable natural language Q&A over the graph using LangChain + LLMs

🧩 Dataset Description

The dataset contains three main components:

File	Description
nodes.csv	Scientific fields with metadata (class, Wikipedia URL, name)
edges.csv	Relationships between fields with cosine similarity
gprops.csv	Graph-level properties

📊 Final Graph Stats:

Nodes: 687

Edges: 6,523

🛠️ Tech Stack

Python 3.11

NetworkX – graph creation & analysis

nx-arangodb – NetworkX ↔ ArangoDB bridge

ArangoDB Cloud – persistent graph storage

LangChain – graph-based QA

LangGraph – memory & workflow management

OpenAI API – LLM-powered reasoning

Pandas / NumPy – data processing

Matplotlib – graph visualization

📂 Project Workflow
1️⃣ Install Dependencies
pip install networkx nx-arangodb python-arango
pip install langchain langchain-community langchain-openai langgraph

2️⃣ Load Graph Data

CSV files are extracted from a ZIP archive

Data is cleaned and loaded using pandas

Bad lines are safely skipped to avoid parsing errors

edges_df = pd.read_csv("edges.csv", on_bad_lines="skip")
nodes_df = pd.read_csv("nodes.csv", on_bad_lines="skip")

3️⃣ Build Graph using NetworkX
G = nx.from_pandas_edgelist(edges_df, "# source", " target")


✔ Graph successfully created with:

687 nodes

6,523 edges

4️⃣ Graph Analysis

Example:

print(G.degree(166))


➡️ Degree of node 166: 21

This enables:

Degree analysis

Centrality measures

Community detection (extendable)

5️⃣ Graph Visualization
pos = nx.spring_layout(G, iterations=15, seed=1721)
nx.draw_networkx(G, pos, node_size=10, with_labels=False, width=0.15)


✔ Visualizes large graph structure using force-directed layout

6️⃣ Store Graph in ArangoDB
G_adb = nxadb.Graph(name="mygraph", db=db)


✔ Graph persisted in ArangoDB Cloud
✔ Enables scalable graph queries and traversal

7️⃣ Enable Graph Question Answering (Graph QA)
arango_graph = ArangoGraph(db)
qa_chain = ArangoGraphQAChain.from_llm(llm, graph=arango_graph)


🧠 Users can ask natural language questions like:

“Which scientific fields are most connected?”

“What disciplines are related to Agriculture?”

“Find similar research domains”

🚀 Applications

Knowledge graph construction

Research field exploration

Scientific domain similarity analysis

AI-powered graph querying

Educational & recommendation systems

⚠️ Notes & Limitations

CUDA warnings may appear in Colab (safe to ignore)

OpenAI API key required for QA functionality

ArangoDB credentials must be secured before deployment

📌 Future Enhancements

Add centrality & community detection algorithms

Interactive graph visualization (PyVis / D3.js)

Web interface for graph Q&A

Multi-graph support

Explainable graph reasoning

👨‍💻 Author

Durva K
B.Tech – Artificial Intelligence & Data Science

“Graphs are not just data structures — they are how knowledge connects.”
