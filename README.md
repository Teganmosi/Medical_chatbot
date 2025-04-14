# Medical Chatbot

This project implements a **Medical Chatbot** designed to provide general medical information and guidance using a combination of natural language processing and retrieval-augmented generation. Built with **LlamaIndex**, **Hugging Face models**, and a web interface via **Gradio** or **Streamlit**, the chatbot answers queries about symptoms, conditions, and healthy habits, while emphasizing the importance of consulting licensed healthcare professionals.

**Note**: This is a demo project and not a substitute for professional medical advice.

## Features
- **Conversational Q&A**: Answers general medical questions using a fine-tuned language model.
- **Document-Based Retrieval**: Leverages PDF documents stored in Google Drive for context-aware responses.
- **Hugging Face Integration**: Uses `Llama-2-7b-chat-hf` for language modeling and `all-mpnet-base-v2` for embeddings.
- **Interactive Interface**: Supports Gradio or Streamlit for user-friendly interaction.
- **Colab Compatibility**: Optimized for Google Colab with GPU support.

## Getting Started

### Prerequisites
- A Google Colab account with **GPU runtime** enabled.
- A [Hugging Face](https://huggingface.co/) account and **access token** for model access.
- PDF documents for fine-tuning or context, stored in your **Google Drive**.
- Basic familiarity with Python and Colab.

### Setup in Google Colab
1. **Open the Notebook**:
   - Click the "Open in Colab" badge (add link if available) or upload the `.ipynb` file to Colab.
   - Ensure the runtime is set to **GPU**: Go to `Runtime > Change runtime type > Select GPU`.

2. **Mount Google Drive**:
   - Run the cell to mount your Drive:
     ```python
     from google.colab import drive
     drive.mount('/content/drive')
     ```
   - Authenticate and ensure your data is in `/content/drive/MyDrive/Data`.

3. **Log in to Hugging Face**:
   - Obtain your Hugging Face access token from [Hugging Face Settings](https://huggingface.co/settings/tokens).
   - Uncomment and run:
     ```bash
     !huggingface-cli login
     ```
     Paste your token when prompted.

4. **Install Dependencies**:
   - Run the following commands in Colab cells to install required libraries:
     ```bash
     !pip install pypdf python-dotenv gradio==4.5.0
     !pip install -q transformers einops accelerate langchain==0.0.208 bitsandbytes
     !pip install sentence_transformers
     !pip install llama-index==0.9.4
     !pip install streamlit
     ```
   - **Note**: If you encounter `pydantic` errors (e.g., `ModuleNotFoundError: No module named 'pydantic.v1'`), install a compatible version:
     ```bash
     !pip install pydantic==1.10.13
     ```

5. **Run the Notebook**:
   - Click `Runtime > Run all` to execute all cells.
   - Ensure your data path (`/content/drive/MyDrive/Data`) is correct for loading documents.

### Local Setup (Optional)
To run outside Colab:
1. Clone the repository:
   ```bash
   git clone https://github.com/teganmosi/Medical_chatbot.git
   cd Medical_chatbot
