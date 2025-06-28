# UAS_PK - Ujian Akhir Semester Pemrograman Komputer

<div align="center">
  <img src="https://img.shields.io/badge/Language-Python-blue?style=for-the-badge&logo=python" alt="Python">
  <img src="https://img.shields.io/badge/Status-Active-green?style=for-the-badge" alt="Status">
  <img src="https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge" alt="License">
  
  ![CI/CD](https://github.com/YourUsername/UAS_PK/workflows/CI%2FCD%20Pipeline/badge.svg)
  ![Tests](https://github.com/YourUsername/UAS_PK/workflows/Tests/badge.svg)
  ![Coverage](https://codecov.io/gh/YourUsername/UAS_PK/branch/main/graph/badge.svg)
  ![Security](https://github.com/YourUsername/UAS_PK/workflows/Security/badge.svg)
</div>

## 📋 Deskripsi Proyek

**UAS_PK** adalah sebuah aplikasi yang dikembangkan untuk memenuhi tugas Ujian Akhir Semester (UAS) mata kuliah Pemrograman Komputer. Proyek ini bertujuan untuk mendemonstrasikan pemahaman dan penerapan konsep-konsep pemrograman yang telah dipelajari selama semester.

> 🎯 **Tujuan**: Mengimplementasikan solusi pemrograman yang efisien dan terstruktur untuk menyelesaikan permasalahan nyata dengan pipeline automation yang modern.

## ✨ Fitur Utama

- 🖥️ **Interface User-Friendly** - Antarmuka yang mudah digunakan
- 📊 **Pengolahan Data** - Sistem manajemen data yang efisien
- 🔒 **Validasi Input** - Validasi input dan error handling yang robust
- 📝 **Logging System** - Sistem pencatatan aktivitas aplikasi
- 🧪 **Unit Testing** - Testing otomatis untuk memastikan kualitas kode
- 🚀 **CI/CD Pipeline** - Automated testing, building, dan deployment
- 🐳 **Docker Support** - Containerized application untuk konsistensi environment

## 🛠️ Tech Stack

| Kategori | Teknologi |
|----------|-----------|
| **Language** | Python 3.9+ |
| **Framework** | Flask/Django |
| **Database** | SQLite/MySQL |
| **Frontend** | HTML, CSS, JavaScript |
| **Testing** | pytest, coverage |
| **CI/CD** | GitHub Actions |
| **Containerization** | Docker, Docker Compose |
| **Code Quality** | Black, Flake8, isort |
| **Security** | Bandit, Safety |
| **Version Control** | Git |

## 📂 Struktur Proyek

```
UAS_PK/
├── 📁 .github/
│   └── 📁 workflows/
│       ├── 📄 ci-cd.yml          # GitHub Actions pipeline
│       └── 📄 security.yml       # Security scanning
├── 📁 src/
│   ├── 📄 main.py                # File utama aplikasi
│   ├── 📁 models/                # Model data
│   ├── 📁 views/                 # View/Controller
│   ├── 📁 utils/                 # Utility functions
│   └── 📁 config/                # Konfigurasi aplikasi
├── 📁 tests/
│   ├── 📄 test_main.py           # Unit tests
│   ├── 📄 test_utils.py          # Test utilities
│   └── 📁 integration/           # Integration tests
├── 📁 scripts/
│   ├── 📄 pipeline.sh            # Pipeline runner script
│   ├── 📄 deploy.sh              # Deployment script
│   └── 📄 monitor-pipeline.sh    # Pipeline monitoring
├── 📁 docs/
│   ├── 📄 design.md              # Dokumentasi desain
│   ├── 📄 api.md                 # Dokumentasi API
│   └── 📄 deployment.md          # Deployment guide
├── 📁 assets/
│   ├── 📁 images/                # Gambar aplikasi
│   └── 📁 data/                  # Sample data
├── 📄 Dockerfile                 # Docker configuration
├── 📄 docker-compose.yml         # Docker Compose setup
├── 📄 Makefile                   # Build automation
├── 📄 .pre-commit-config.yaml    # Pre-commit hooks
├── 📄 requirements.txt           # Python dependencies
├── 📄 requirements-dev.txt       # Development dependencies
├── 📄 .gitignore                 # Git ignore rules
└── 📄 README.md                  # Dokumentasi ini
```

## 🚀 Quick Start

### Prerequisites

Sebelum menjalankan aplikasi, pastikan Anda memiliki:

- **Python 3.9+** installed
- **Docker** dan **Docker Compose**
- **Make** build tool
- **Git** for version control

### Installation

1. **Clone Repository**
   ```bash
   git clone https://github.com/YourUsername/UAS_PK.git
   cd UAS_PK
   ```

2. **Setup dengan Make (Recommended)**
   ```bash
   # Install semua dependencies dan setup environment
   make install
   
   # Atau setup development environment lengkap
   make setup-dev
   ```

3. **Manual Setup**
   ```bash
   # Create Virtual Environment
   python -m venv env
   
   # Windows
   env\Scripts\activate
   
   # Linux/Mac
   source env/bin/activate
   
   # Install Dependencies
   pip install -r requirements.txt
   pip install -r requirements-dev.txt
   ```

4. **Setup Database** (if applicable)
   ```bash
   python src/setup_db.py
   ```

### 🚀 Run End-to-End Pipeline

```bash
# Jalankan seluruh pipeline (install, lint, test, build, deploy)
make pipeline

# Atau step by step:
make install     # Install dependencies
make lint        # Code quality check
make test        # Run all tests
make build       # Build Docker image
make run         # Run application
```

### 🔧 Configuration

Buat file `.env` di root directory:

```env
# Database Configuration
DB_HOST=localhost
DB_PORT=5432
DB_NAME=uas_pk
DB_USER=your_username
DB_PASSWORD=your_password

# Application Settings
DEBUG=True
SECRET_KEY=your-secret-key-here
PORT=5000

# Pipeline Settings
ENVIRONMENT=development
DOCKER_REGISTRY=your-registry
```

## 📖 Usage Guide

### Basic Usage

1. **Menjalankan Aplikasi**
   ```bash
   # Local development
   make run
   
   # Atau dengan Docker
   make docker-run
   ```

2. **Akses Web Interface**
   - Buka browser dan kunjungi: `http://localhost:5000`

3. **Command Line Interface**
   ```bash
   # Contoh penggunaan CLI
   python src/main.py --mode cli --input data.csv --output result.json
   ```

### API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET    | `/api/health` | Health check endpoint |
| GET    | `/api/data` | Mengambil semua data |
| POST   | `/api/data` | Menambah data baru |
| PUT    | `/api/data/:id` | Update data |
| DELETE | `/api/data/:id` | Hapus data |

### Examples

**Example 1: Basic Data Processing**
```python
from src.models import DataProcessor

processor = DataProcessor()
result = processor.process_data('input.csv')
print(f"Processing complete: {result}")
```

**Example 2: API Call**
```bash
curl -X POST http://localhost:5000/api/data \
  -H "Content-Type: application/json" \
  -d '{"name": "Sample", "value": 123}'
```

## 🧪 Testing & Quality Assurance

### Run All Tests
```bash
# Run all tests dengan coverage
make test

# Atau manual
pytest --cov=src --cov-report=html --cov-report=term-missing

# Run specific test file
pytest tests/test_main.py

# Run integration tests
make test-integration
```

### Code Quality & Security
```bash
# Linting dan formatting
make lint         # Check code quality
make format       # Auto-format code

# Security scanning
make security     # Run security checks

# Pre-commit hooks
pre-commit run --all-files
```

### Test Coverage
```bash
# Generate coverage report
make test
# Open htmlcov/index.html in browser
```

## 🚀 CI/CD Pipeline & Automation

### GitHub Actions Workflow

Pipeline otomatis berjalan pada setiap push dan pull request dengan stages:

1. **🔍 Code Quality** - Linting, formatting, type checking
2. **🧪 Testing** - Unit tests, integration tests, coverage
3. **🔒 Security** - Vulnerability scanning, dependency check
4. **🏗️ Build** - Docker image build dan validation
5. **🚀 Deploy** - Automated deployment ke staging/production

### Local Pipeline Commands

```bash
# Full end-to-end pipeline
make pipeline

# Individual pipeline stages
make install      # Install dependencies
make lint         # Code quality checks
make security     # Security scanning
make test         # Run all tests
make build        # Build Docker image
make deploy-local # Deploy locally

# Pipeline dengan cleanup
make clean && make pipeline
```

### Docker Pipeline

```bash
# Build dan run dengan Docker
make docker-build
make docker-run

# Development dengan Docker Compose
docker-compose up -d

# Production deployment
make docker-deploy-prod
```

### Available Make Commands

```bash
make help                    # Show all available commands
make install                 # Install dependencies
make setup-dev              # Setup development environment
make lint                   # Run linting (flake8, black, isort)
make format                 # Format code automatically
make test                   # Run all tests with coverage
make test-integration       # Run integration tests
make security               # Run security checks (bandit, safety)
make build                  # Build Docker image
make run                    # Run application locally
make docker-run             # Run with Docker
make deploy-local           # Deploy to local environment
make deploy-staging         # Deploy to staging
make pipeline               # Run full end-to-end pipeline
make clean                  # Clean up build artifacts
make health-check           # Check application health
```

### Monitoring & Logging

```bash
# Monitor pipeline status
./scripts/monitor-pipeline.sh

# View application logs
make logs

# Health check
make health-check

# Performance monitoring
make monitor
```

## 📊 Performance & Metrics

### Benchmarks

| Operation | Time (ms) | Memory (MB) | CPU (%) |
|-----------|-----------|-------------|---------|
| Data Load | 245 | 12.5 | 15 |
| Processing | 1,230 | 45.2 | 65 |
| Export | 156 | 8.7 | 20 |
| API Response | 45 | 8.1 | 10 |

### System Requirements

- **RAM**: Minimum 512MB, Recommended 2GB
- **Storage**: 500MB free space (including Docker images)
- **OS**: Windows 10+, macOS 10.14+, Ubuntu 18.04+
- **Docker**: Version 20.10+
- **Python**: 3.9+

## 🐛 Troubleshooting

### Common Issues

**Issue**: `ModuleNotFoundError: No module named 'src'`
```bash
# Solution
export PYTHONPATH="${PYTHONPATH}:$(pwd)"
# Or run via make
make run
```

**Issue**: Docker permission denied
```bash
# Linux: Add user to docker group
sudo usermod -aG docker $USER
newgrp docker
```

**Issue**: Pipeline failure
```bash
# Check pipeline logs
make logs

# Reset environment
make clean
make setup-dev
```

**Issue**: Port already in use
```bash
# Find and kill process
make clean
# Or manually
lsof -i :5000
kill -9 <PID>
```

### Debug Mode

```bash
# Run in debug mode
DEBUG=true make run

# Verbose pipeline
make pipeline VERBOSE=1

# Check pipeline health
make health-check
```

## 📈 Development Workflow

### Contributing

1. Fork repository
2. Create feature branch: `git checkout -b feature/amazing-feature`
3. Run pre-commit hooks: `pre-commit install`
4. Make changes dan test: `make test`
5. Run full pipeline: `make pipeline`
6. Commit changes: `git commit -m 'Add amazing feature'`
7. Push branch: `git push origin feature/amazing-feature`
8. Create Pull Request

### Development Setup

```bash
# Setup development environment lengkap
make setup-dev

# Install pre-commit hooks
pre-commit install

# Run development server dengan hot reload
make run-dev

# Monitor file changes
make watch
```

### Code Standards

- **Python**: Follow PEP 8, use Black for formatting
- **Testing**: Minimum 80% code coverage
- **Documentation**: Docstrings untuk semua functions
- **Git**: Conventional commits format
- **Security**: No secrets in code, use environment variables

```bash
# Check code standards
make lint

# Auto-fix formatting issues
make format

# Run security audit
make security
```


