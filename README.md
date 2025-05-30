# <img src="https://github.com/user-attachments/assets/0ee677be-e7c0-40df-9aaa-9d078b5e3ce5" alt="streamlit" style="height: 50px; vertical-align: middle; margin-left: 10px;"> Knowledge Graph Generator

A Colab-based Streamlit application that extracts graph data (entities and relationships) from text input using **LangChain** and **OpenAI's GPT-4o** models, then visualizes it interactively as a dynamic knowledge graph.

![CleanShot 2025-05-28 at 13 11 46](https://github.com/user-attachments/assets/4fef9158-8dd8-432d-bb8a-b53953a82c6c)

---

## 🚀 Features

- 📂 Input support for both `.txt` uploads and direct text entry  
- 🧠 Automatic entity and relationship extraction using GPT-4o  
- 🕸️ Interactive knowledge graph with physics-based layout  
- 🔄 Real-time drag, zoom, and hover interactivity with PyVis  
- 🌐 Fully deployable via Streamlit within Colab using `%%writefile`  

---

## ⚙️ Installation

### ✅ Prerequisites

- Python 3.8+
- OpenAI API key

### 📦 Dependencies

The following Python packages are required:

- `langchain >= 0.1.0`
- `langchain-experimental >= 0.0.45`
- `langchain-openai >= 0.1.0`
- `python-dotenv >= 1.0.0`
- `pyvis >= 0.3.2`
- `streamlit >= 1.32.0`

Install all dependencies using:

```bash
pip install -r requirements.txt
````

> In Colab, you can also run:

```python
!pip install -r requirements.txt
```

---

## 🔐 API Key Setup

Create a `.env` file in the notebook with:

```python
%%writefile .env
OPENAI_API_KEY=your_openai_api_key_here
```

Or set it dynamically in the notebook:

```python
import os
os.environ["OPENAI_API_KEY"] = "your_openai_api_key_here"
```

---

## ▶️ Running the App in Colab

Since this app uses `%%writefile` to generate scripts:

1. Run each notebook cell to write required files like `app.py`
2. Launch the Streamlit app using:

```python
!streamlit run app.py
```

> Colab will give you a public URL to access the interface.

---

## 🧠 How to Use

1. Select input method in the sidebar:

   * 📄 Upload a `.txt` file, or
   * 📝 Enter text directly
2. Click **"Generate Knowledge Graph"**
3. Interact with the graph:

   * Drag nodes
   * Zoom in/out with mouse wheel
   * Hover to see details
   * Apply graph filters and layouts

---

## 🧪 How It Works

1. Your input text is sent through a LangChain `GraphTransformer`
2. GPT-4o identifies `(entity) - [relationship] → (entity)` triplets
3. A NetworkX graph is built from those triplets
4. PyVis visualizes the graph inside Streamlit

Example triplets:

```
(Isaac Newton) - [discovered] → (Laws of Motion)  
(Laws of Motion) - [published in] → (1687)
```

---

## 📁 Project Structure

All scripts are generated via Colab using `%%writefile`:

```
├── KnowledgeGraph.ipynb    # Main notebook
├── app.py                  # Streamlit app
├── utils.py                # Helper logic (if needed)
├── .env                    # API key
└── requirements.txt        # Dependencies
```

---

## 🧑‍💻 Author

© Aditya Saxena, 2025
Licensed under the MIT License.
See: [MIT License](https://opensource.org/licenses/MIT)

---

## 📚 Resources

* [LangChain Docs](https://docs.langchain.com/)
* [OpenAI API Docs](https://platform.openai.com/docs)
* [Streamlit](https://docs.streamlit.io/)
* [PyVis Docs](https://pyvis.readthedocs.io/)



