# Medical Assistant - ChatBot (GenAI)

## Overview

The **Medical Assistant ChatBot (GenAI)** is an AI-driven conversational application designed to assist users in exploring medical knowledge. Users can ask questions about diseases, diagnoses, causes, symptoms, and more, while the bot provides accurate responses based on the context of a medical textbook provided in PDF format. This application combines cutting-edge AI technologies, such as **OpenAI GPT**, **Flask**, and **Retrieval-Augmented Generation (RAG)**, ensuring contextually relevant and reliable interactions.

---

## 🌟 Features

- **Interactive Medical Query Handling**: Users can ask questions related to diseases, symptoms, diagnoses, causes, and treatments.
- **PDF Knowledge Integration**: The bot processes a provided medical textbook in PDF format to create a knowledge base.
- **Context-Aware Responses**: The bot retrieves relevant information using a **RAG** framework for precise and factual answers.
- **Scalable and Efficient**: Uses a **vector database** for fast and efficient embedding search.
- **Secure and Lightweight**: Built on Flask for a lightweight yet secure web interface.
- **Dynamic and Customizable**: Easily extendable to other medical domains or knowledge bases.

---

## 🛠️ Tech Stack

### Backend:
- **Python**: Core programming language.
- **Flask**: Lightweight framework to build the web application.
- **LangChain**: Framework for managing conversational AI chains and memory.
- **OpenAI GPT**: Language model to generate human-like, context-aware responses.

### Database:
- **Pinecone**: Vector database for efficient storage and retrieval of embeddings.

### Embedding and Search:
- **RAG (Retrieval-Augmented Generation)**: Combines GPT’s generative capabilities with a knowledge retrieval system for fact-based and context-aware answers.

### Others:
- **dotenv**: Secure environment variable management.
- **PDF Processing**: For extracting data and knowledge from the provided PDF.

---

## 📂 Folder Structure

```plaintext
├── src/                   # Backend logic and helper functions
│   ├── helper.py          # Handles PDF ingestion, document chunking, and embedding creation
│   ├── prompt.py          # Prompts used for GPT responses
├── templates/             # HTML templates for the web interface
│   ├── chat.html          # Chat UI
├── static/                # Static assets (CSS, JS, images)
│   ├── style.css          # Custom styles for the chat interface
├── .env                   # Environment variables (API keys, etc.)
├── app.py                 # Main Flask application
├── requirements.txt       # Python dependencies
├── store_index.py         # Script for processing the PDF and storing embeddings in the vector DB
├── LICENSE                # License for the project
└── README.md              # Project documentation
```

---

## ⚙️ Application Workflow

1. **PDF Ingestion**:
   - The provided medical textbook (PDF) is processed and split into manageable chunks.
   - Text data is extracted, cleaned, and embedded using OpenAI's embedding API.

2. **Embedding Storage**:
   - These embeddings are stored in **Pinecone**, a vector database for fast and efficient retrieval.

3. **User Interaction**:
   - Users interact with the bot via a user-friendly web interface built using **Flask**.
   - Users input questions related to diseases, diagnoses, causes, symptoms, etc.

4. **RAG Framework**:
   - When a question is asked:
     1. The bot retrieves relevant chunks from the vector database using similarity search.
     2. These chunks are passed to the GPT model along with the user’s question.
     3. The model generates a context-aware response based on both the retrieved data and the input query.

5. **Response Delivery**:
   - The response is displayed in the chat interface for the user.

---

## 🔄 Code Flow

1. **PDF Preprocessing**:
   - `store_index.py` processes the PDF, splits it into sections, generates embeddings using OpenAI, and stores these in **Pinecone**.

2. **Web Application**:
   - `app.py` manages:
     - Routes for the application.
     - User input handling.
     - Communication between the vector database and the GPT model.
     - Rendering the chat interface.

3. **Query Handling**:
   - The user’s query is handled via a **Conversational Retrieval Chain**, ensuring accurate and context-aware responses.

4. **Frontend**:
   - `chat.html` provides a dynamic chat interface.
   - JavaScript ensures seamless interaction and updates to the chat flow.

---

## 🔧 How to Run

### Prerequisites

1. **Python 3.10 or above**  
2. **Conda** (optional but recommended)

### Steps

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/
   cd Medical-ChatBot-GenAI
   ```

2. **Create a Conda Environment**:
   ```bash
   conda create -n medBot python=3.10 -y
   conda activate medBot
   ```

3. **Install Dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

4. **Set Up API Keys**:
   - Create a `.env` file in the root directory and add:
     ```ini
     PINECONE_API_KEY=your_pinecone_api_key
     OPENAI_API_KEY=your_openai_api_key
     ```

5. **Process the PDF**:
   - Place the medical textbook (PDF) in the root directory.
   - Run the following command to generate and store embeddings:
     ```bash
     python store_index.py
     ```

6. **Start the Application**:
   ```bash
   python app.py
   ```

7. **Open in Browser**:
   Navigate to:
   ```bash
   http://127.0.0.1:5000/
   ```

---

## 🚀 Future Enhancements

1. **Voice Interaction**: Enable users to interact with the bot using voice commands.
2. **Multi-PDF Support**: Allow processing of multiple medical textbooks for a broader knowledge base.
3. **Enhanced UI**: Improve the chat interface with animations and a mobile-friendly design.
4. **Authentication**: Add user authentication for secure and personalized experiences.
5. **Multi-language Support**: Expand the bot to handle questions in various languages.

---

## 🤝 Contributing

We welcome contributions! Here’s how you can help:
1. Fork the repository.
2. Create a new branch for your feature.
3. Submit a pull request with a detailed description.

---

## 📜 License

This project is licensed under the [MIT License](LICENSE).

---

Enjoy using the **Medical Assistant ChatBot (GenAI)** and feel free to reach out for suggestions or feedback! 🚀
