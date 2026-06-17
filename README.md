# MediaSniffer Pro

MediaSniffer Pro is an intelligent media detection and processing application built with Python and FastAPI. It accepts a URL and automatically detects downloadable media, allows you to choose the quality, handles HLS streaming, and provides progress reporting while downloading.  The project is designed to be modular and extensible, supporting both a REST API and a command‑line interface.

## Features

- **Intelligent media detection** – Give MediaSniffer Pro a web page or streaming URL and it will analyse the content to locate downloadable media such as video, audio, and images.
- **Quality selection** – When multiple formats are available (e.g. 1080p, 720p, 480p), you can select your preferred resolution or bitrate before downloading.
- **HLS and streaming support** – The application understands HLS/playlist streaming formats and can assemble segment files into a single output.
- **Download and progress reporting** – Download selected media while receiving progress updates on file size, download speed, and estimated completion time.
- **REST API** – MediaSniffer Pro exposes a FastAPI web service so it can be integrated into other applications or used via HTTP requests.
- **Command‑Line Interface** – A CLI tool is provided for quick downloads directly from the terminal.
- **Extensible architecture** – The extraction pipeline is modular, making it easy to add support for new websites or streaming formats by creating custom extractor classes.

## Getting Started

### Installation

Clone the repository and install dependencies:

```bash
# Clone the repo
 git clone https://github.com/abubakar-r-salihawa/mediasniffer-pro.git
 cd mediasniffer-pro

# Install dependencies
 pip install -r requirements.txt
```

### Running the API Server

Launch the FastAPI server using Uvicorn:

```bash
uvicorn src.mediasniffer.api.main:app --reload
```

Visit `http://localhost:8000/docs` to view interactive API documentation powered by Swagger UI.

### Using the CLI

After installing the package, you can download media via the command line:

```bash
python src/cli.py --url "https://example.com/some-video" --quality 1080p
```

## Project Structure

```text
mediasniffer-pro/
├── README.md
├── LICENSE
├── requirements.txt
├── CHANGELOG.md
├── CONTRIBUTING.md
├── SECURITY.md
├── src/
│   ├── mediasniffer/
│   │   ├── __init__.py
│   │   ├── api/
│   │   │   ├── __init__.py
│   │   │   └── main.py
│   │   ├── extractor/
│   │   │   ├── __init__.py
│   │   │   └── base.py
│   │   ├── models.py
│   │   └── utils.py
│   └── cli.py
└── tests/
    ├── __init__.py
    └── test_basic.py
```

## Contributing

Contributions are welcome! Please see `CONTRIBUTING.md` for guidelines on how to report issues, propose features, or submit pull requests.

## License

This project is licensed under the MIT License – see the `LICENSE` file for details.

## Security

If you discover a security vulnerability, please see `SECURITY.md` for information on how to report it responsibly.
