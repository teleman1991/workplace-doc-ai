# Workplace Document AI Assistant

A practical AI-powered document processing and analysis tool for workplace environments. This tool helps automate document analysis tasks and extract valuable insights from various document formats.

## Features

- Document text extraction (PDF, DOCX, TXT)
- Automatic document summarization
- Key points extraction
- Question answering capabilities
- Document metadata analysis

## Installation

1. Clone this repository:
```bash
git clone https://github.com/teleman1991/workplace-doc-ai.git
cd workplace-doc-ai
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

## Usage

1. Start the server:
```bash
python main.py
```

2. The API will be available at `http://localhost:8000`

### API Endpoints

- `POST /process/`: Process a document and get summary, key points, and metadata
- `POST /query/`: Ask specific questions about a document

## Example

```python
import requests

# Process a document
with open('document.pdf', 'rb') as f:
    response = requests.post('http://localhost:8000/process/', files={'file': f})
    results = response.json()
    print(results['summary'])

# Query a document
with open('document.pdf', 'rb') as f:
    response = requests.post(
        'http://localhost:8000/query/',
        files={'file': f},
        data={'query': 'What is the main conclusion?'}
    )
    answer = response.json()['answer']
    print(answer)
```

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.