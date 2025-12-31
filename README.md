# SanTOK - Advanced Text Tokenization Framework

A comprehensive text tokenization system with mathematical analysis, statistical features, and semantic embeddings. SanTOK provides multiple tokenization methods, embedding generation, and a full-featured API server.

[![Ask DeepWiki](https://deepwiki.com/badge.svg)](https://deepwiki.com/chavalasantosh/SanTOK)

## Features

- **Multiple Tokenization Methods**: Word, character, subword, byte-level, grammar-based, and more
- **Semantic Embeddings**: Generate embeddings using multiple strategies (feature-based, hash-based, semantic, hybrid)
- **RESTful API**: FastAPI-based server with interactive documentation
- **WebSocket Support**: Real-time tokenization and streaming
- **Vector Database Integration**: Support for ChromaDB, FAISS, and Weaviate
- **Training Capabilities**: Train custom semantic models on your data
- **CLI Interface**: Command-line tools for all operations
- **Cross-Platform**: Works on Windows, Linux, and macOS

## Quick Start

Choose one of three methods to get started:

### Method 1: Automated Setup (Recommended)

**Linux/Mac:**
```bash
git clone <repository-url>
cd SanTOK
chmod +x setup.sh
./setup.sh
./run.sh
```

**Windows:**
```powershell
git clone <repository-url>
cd SanTOK
.\setup.bat
.\run.bat
```

### Method 2: Docker (Easiest)

```bash
git clone <repository-url>
cd SanTOK
docker-compose up
```

The server will be available at `http://localhost:8000`

### Method 3: Manual Installation

See [INSTALLATION.md](INSTALLATION.md) for detailed step-by-step instructions.

## System Requirements

- **Python**: 3.11 or higher
- **Node.js**: 18+ (optional, for frontend)
- **RAM**: 4GB minimum, 8GB recommended
- **Disk Space**: 2GB free space

## Installation

### Prerequisites

1. **Python 3.11+**
   - Check version: `python --version` or `python3 --version`
   - Download from [python.org](https://www.python.org/downloads/) if needed

2. **pip** (usually comes with Python)
   - Upgrade: `pip install --upgrade pip`

3. **Virtual Environment** (recommended)
   - Python venv module (included with Python 3.3+)

### Quick Installation

Run the automated setup script for your platform:

- **Linux/Mac**: `./setup.sh`
- **Windows**: `setup.bat`

Or follow the detailed guide in [INSTALLATION.md](INSTALLATION.md)

## Usage

### Start the Server

**Linux/Mac:**
```bash
./run.sh
```

**Windows:**
```powershell
.\run.bat
```

**Cross-platform:**
```bash
python run.py
```

The API server will start on `http://localhost:8000`

### Access API Documentation

Once the server is running:
- **Interactive Docs**: http://localhost:8000/docs
- **Alternative Docs**: http://localhost:8000/redoc

### CLI Usage

```bash
# Tokenize text
python santok_cli.py tokenize --text "Hello world" --method word

# Train a model
python santok_cli.py train --file corpus.txt --model-path model.pkl

# Generate embeddings
python santok_cli.py embed --text "Hello" --model-path model.pkl
```

See [CLI_USAGE.md](CLI_USAGE.md) for complete CLI documentation.

### API Examples

**Tokenize text:**
```bash
curl -X POST "http://localhost:8000/api/v1/tokenize" \
  -H "Content-Type: application/json" \
  -d '{"text": "Hello world", "method": "word"}'
```

**Generate embeddings:**
```bash
curl -X POST "http://localhost:8000/api/v1/embed" \
  -H "Content-Type: application/json" \
  -d '{"text": "Hello world", "strategy": "semantic"}'
```

## Project Structure

```
SanTOK/
├── src/                    # Core source code
│   ├── core/              # Tokenization engines
│   ├── embeddings/        # Embedding generation
│   ├── servers/           # API servers
│   └── utils/             # Utility functions
├── backend/               # Backend-specific code
├── frontend/              # Frontend application (optional)
├── requirements.txt       # Python dependencies
├── setup.sh / setup.bat  # Setup scripts
├── run.sh / run.bat      # Run scripts
└── docker-compose.yml    # Docker configuration
```

## Documentation

- **[QUICK_START.md](QUICK_START.md)** - Fast setup reference
- **[INSTALLATION.md](INSTALLATION.md)** - Detailed installation guide
- **[CLI_USAGE.md](CLI_USAGE.md)** - Command-line interface guide
- **API Docs** - Available at `/docs` when server is running

## Verification

After installation, verify everything works:

```bash
python verify_installation.py
```

This will check:
- Python version
- Installed dependencies
- File structure
- Basic functionality

## Troubleshooting

### Common Issues

**Port already in use:**
```bash
# Change port in run.sh/run.bat or use:
PORT=8001 python run.py
```

**Python version too old:**
- Install Python 3.11+ from [python.org](https://www.python.org/downloads/)

**Dependencies fail to install:**
- Upgrade pip: `pip install --upgrade pip`
- Use virtual environment: `python -m venv venv`

**Import errors:**
- Ensure you're in the project root directory
- Activate virtual environment if using one
- Run `python verify_installation.py` to check setup

### Getting Help

1. Check [INSTALLATION.md](INSTALLATION.md) for detailed troubleshooting
2. Run `python verify_installation.py` to diagnose issues
3. Check server logs for error messages

## Development

### Setting up Development Environment

```bash
# Clone repository
git clone <repository-url>
cd SanTOK

# Create virtual environment
python -m venv venv
source venv/bin/activate  # Linux/Mac
# or
venv\Scripts\activate  # Windows

# Install dependencies
pip install -r requirements.txt

# Install development dependencies
pip install pytest pytest-cov black flake8
```

### Running Tests

```bash
pytest tests/
```

## Docker

### Build and Run

```bash
docker-compose up
```

### Build Only

```bash
docker-compose build
```

### Run in Background

```bash
docker-compose up -d
```

### View Logs

```bash
docker-compose logs -f
```

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Run tests: `pytest tests/`
5. Submit a pull request

## License

[Add your license here - Soon Going to Placed]

## Authors

- Santosh Chavala

## Acknowledgments

[Add acknowledgments if any - Soon Going to Placed]
