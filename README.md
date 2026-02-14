# ChatwithPDF

A simple Streamlit app collection for chatting with PDF files using [Embedchain](https://github.com/embedchain/embedchain) and either:

- **OpenAI** (`chat_pdf.py`)
- **Ollama + Llama 3** (`chat_pdf_llama3.py`)
- **Ollama + Llama 3.2** with improved chat UI (`chat_pdf_llama3.2.py`)

## Features

- Upload a PDF and index it into a vector database
- Ask questions in natural language about the PDF
- Retrieval-augmented responses powered by Embedchain
- Multiple model backends (cloud and local)

## Project Files

- `chat_pdf.py` — OpenAI-based version (requires API key)
- `chat_pdf_llama3.py` — Local Ollama version using `llama3:instruct`
- `chat_pdf_llama3.2.py` — Local Ollama version using `llama3.2:latest` with chat history and PDF preview
- `requirements.txt` — Python dependencies

## Requirements

- Python 3.9+
- `pip`
- (Optional, for local models) [Ollama](https://ollama.com/) running on `http://localhost:11434`

## Installation

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

## Run the App

Choose one of the variants below.

### 1) OpenAI variant

```bash
streamlit run chat_pdf.py
```

In the app:
1. Enter your OpenAI API key.
2. Upload a PDF.
3. Ask questions.

### 2) Ollama + Llama 3 variant

First, ensure Ollama is running and model is available:

```bash
ollama pull llama3:instruct
```

Then run:

```bash
streamlit run chat_pdf_llama3.py
```

### 3) Ollama + Llama 3.2 variant (enhanced UI)

First, ensure Ollama is running and model is available:

```bash
ollama pull llama3.2:latest
```

Then run:

```bash
streamlit run chat_pdf_llama3.2.py
```

## Notes

- The app uses a temporary Chroma DB path, so indexed data is not persisted long-term by default.
- Local variants expect Ollama at `http://localhost:11434`.
- If answers are poor, try uploading cleaner PDFs and asking focused questions.

## Troubleshooting

- **`Connection refused` for Ollama**
  - Start Ollama and confirm it is reachable at `http://localhost:11434`.
- **Model not found**
  - Pull the required model with `ollama pull <model-name>`.
- **Dependency issues**
  - Recreate your virtual environment and reinstall from `requirements.txt`.

## License

Add your preferred license information here.
