# Website Scraping and Querying with LangChain and FAISS

## Overview

This project demonstrates how to scrape text content from a website, process it into vector embeddings, and perform efficient query-based retrieval using FAISS and LangChain. The goal is to enable semantic search and question-answering over the scraped content using an LLM (Large Language Model) such as OpenAI's GPT.

---

## Features

1. **Website Scraping**: Extract text content from a given URL using `WebBaseLoader`.
2. **Text Chunking**: Split the scraped text into manageable chunks with optional overlap for better context retention.
3. **Embeddings Generation**: Convert text chunks into vector embeddings using Hugging Face's models.
4. **Vector Storage**: Store and query embeddings efficiently using FAISS, optimized for GPU.
5. **Question Answering**: Query the scraped data using a RetrievalQA chain powered by OpenAI's GPT API.
6. **GPU Optimization**: Leverages GPU for faster embeddings generation and FAISS similarity search.

---

## Prerequisites

### Software Requirements

- Python 3.8 or above
- GPU with CUDA support (if using GPU acceleration)

### API Keys

- OpenAI API Key: Obtain from [OpenAI](https://platform.openai.com/).
- LangChain API Key: Optional for advanced LangChain features.

---

## Installation

### Step 1: Clone the Repository

```bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
```

### Step 2: Set Up Virtual Environment

```bash
python -m venv langchainEnv
source langchainEnv/bin/activate  # On Windows: langchainEnv\Scripts\activate
```

### Step 3: Install Dependencies

Install PyTorch first with GPU support:

```bash
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118
```

Replace `cu118` with your CUDA version if needed.

Then install the other dependencies:

```bash
pip install -r requirements.txt
```

### Step 4: Configure Environment Variables

Create a `.env` file in the root directory and add your API keys:

```plaintext
OPENAI_API_KEY=your_openai_api_key_here
LANGCHAIN_API_KEY=your_langchain_api_key_here
```

---

## Usage

### Step 1: Run the Script

Run the main Python script:

```bash
python main.py
```

### Step 2: Enter Website URL

You’ll be prompted to enter a website URL:

```plaintext
Enter the website URL to scrape: https://example.com
```

The script will scrape the text content of the provided website.

### Step 3: Preview Scraped Text

The script displays a preview of the scraped text and splits it into chunks for processing.

### Step 4: Query the Content

Enter your query when prompted:

```plaintext
Enter your query: What is AI?
```

The script will process your query and provide an answer based on the scraped content.

### Example Output:

```plaintext
Response:
{'query': 'What is AI?', 'result': 'AI stands for Artificial Intelligence and is a field of research in computer science...'}
```

---

## Project Structure

```plaintext
.
├── main.py             # Main script to run the project
├── requirements.txt    # Python dependencies
├── .env                # Environment variables (not included in the repo)
├── README.md           # Project documentation
```

---

## Key Components

### `main.py`

- Handles website scraping, text processing, embeddings generation, vector storage, and querying.
- Interactive script prompts the user for input and displays outputs step-by-step.

### `requirements.txt`

- Lists all necessary Python packages for the project.

### `.env`

- Stores sensitive API keys. Excluded from version control.

---

## Advanced Features

### GPU Acceleration

The project is optimized for GPU usage:

- Uses `faiss-gpu` for faster vector similarity search.
- Leverages `torch` and `transformers` for efficient embeddings generation.

### Caching

- Optional: Implement caching for embeddings and FAISS indices to save time on repeated runs.

---

## Troubleshooting

### Common Issues

1. **CUDA Compatibility**:
   - Ensure the installed PyTorch version matches your CUDA version.
2. **API Key Errors**:
   - Verify that the `.env` file is properly configured.
3. **Scraping Issues**:
   - Some websites may block scraping. Consider using proxies or bypass techniques.

### Verify GPU Usage

Run the following Python code to ensure GPU is detected:

```python
import torch
print(f"Is GPU available: {torch.cuda.is_available()}")
print(f"CUDA version: {torch.version.cuda}")
print(f"Device name: {torch.cuda.get_device_name(0)}")
```

---

## Future Improvements

- Add support for multilingual scraping and querying.
- Enhance robustness with more sophisticated error handling.
- Deploy as a web service using Flask or FastAPI.

---

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

---

## Contact

For any issues or contributions, feel free to reach out:

- **Email**: [amangupta52001@gmail.com](mailto\:amangupta52001@gmail.com)
- **GitHub**: [amangupta05](https://github.com/amangupta05)

