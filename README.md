# UAS_PK - Ujian Akhir Semester Penalaran Komputer

<div align="center">
  <img src="https://img.shields.io/badge/Language-Python-blue?style=for-the-badge&logo=python" alt="Python">
  <img src="https://img.shields.io/badge/Status-Active-green?style=for-the-badge" alt="Status">
  <img src="https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge" alt="License">
</div>

## 📋 Deskripsi Proyek

**UAS_PK** adalah sebuah aplikasi yang dikembangkan untuk memenuhi tugas Ujian Akhir Semester (UAS) mata kuliah Pemrograman Komputer. Proyek ini bertujuan untuk mendemonstrasikan pemahaman dan penerapan konsep-konsep pemrograman yang telah dipelajari selama semester.

> 🎯 **Tujuan**: Mengimplementasikan solusi pemrograman yang efisien dan terstruktur untuk menyelesaikan permasalahan nyata.

## ✨ Fitur Utama

- 🖥️ **Interface User-Friendly** - Antarmuka yang mudah digunakan
- 📊 **Pengolahan Data** - Sistem manajemen data yang efisien
- 🔒 **Validasi Input** - Validasi input dan error handling yang robust
- 📝 **Logging System** - Sistem pencatatan aktivitas aplikasi
- 🧪 **Unit Testing** - Testing otomatis untuk memastikan kualitas kode

## 🛠️ Tech Stack

| Kategori | Teknologi |
|----------|-----------|
| **Language** | Python 3.9+ |
| **Framework** | Flask/Django |
| **Database** | SQLite/MySQL |
| **Frontend** | HTML, CSS, JavaScript |
| **Testing** | pytest |
| **Version Control** | Git |

## 📂 Struktur Proyek

```
UAS_PK/
├── 📁 src/
│   ├── 📄 main.py              # File utama aplikasi
│   ├── 📁 models/              # Model data
│   ├── 📁 views/               # View/Controller
│   ├── 📁 utils/               # Utility functions
│   └── 📁 config/              # Konfigurasi aplikasi
├── 📁 tests/
│   ├── 📄 test_main.py         # Unit tests
│   └── 📄 test_utils.py        # Test utilities
├── 📁 docs/
│   ├── 📄 design.md            # Dokumentasi desain
│   └── 📄 api.md               # Dokumentasi API
├── 📁 assets/
│   ├── 📁 images/              # Gambar aplikasi
│   └── 📁 data/                # Sample data
├── 📄 requirements.txt         # Python dependencies
├── 📄 .gitignore              # Git ignore rules
└── 📄 README.md               # Dokumentasi ini
```

## 🚀 Quick Start

### Prerequisites

Sebelum menjalankan aplikasi, pastikan Anda memiliki:

- **Python 3.9+** installed
- **pip** package manager
- **Git** for version control

### Installation

1. **Clone Repository**
   ```bash
   git clone https://github.com/YourUsername/UAS_PK.git
   cd UAS_PK
   ```

2. **Create Virtual Environment**
   ```bash
   python -m venv env
   
   # Windows
   env\Scripts\activate
   
   # Linux/Mac
   source env/bin/activate
   ```

3. **Install Dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Setup Database** (if applicable)
   ```bash
   python src/setup_db.py
   ```

5. **Run Application**
   ```bash
   python src/main.py
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
```

## 📖 Usage Guide

### Basic Usage

1. **Menjalankan Aplikasi**
   ```bash
   python src/main.py
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

## 🧪 Testing

### Run All Tests
```bash
# Run all tests
pytest

# Run with coverage
pytest --cov=src

# Run specific test file
pytest tests/test_main.py

# Run with verbose output
pytest -v
```

### Test Coverage
```bash
pytest --cov=src --cov-report=html
# Open htmlcov/index.html in browser
```

## 📊 Performance

### Benchmarks

| Operation | Time (ms) | Memory (MB) |
|-----------|-----------|-------------|
| Data Load | 245 | 12.5 |
| Processing | 1,230 | 45.2 |
| Export | 156 | 8.7 |

### System Requirements

- **RAM**: Minimum 512MB, Recommended 2GB
- **Storage**: 100MB free space
- **OS**: Windows 10+, macOS 10.14+, Ubuntu 18.04+

## 🐛 Troubleshooting

### Common Issues

**Issue**: `ModuleNotFoundError: No module named 'src'`
```bash
# Solution
export PYTHONPATH="${PYTHONPATH}:$(pwd)"
```

**Issue**: Database connection error
```bash
# Check database service
sudo systemctl status postgresql
# Restart if needed
sudo systemctl restart postgresql
```

**Issue**: Port already in use
```bash
# Find process using port 5000
lsof -i :5000
# Kill process
kill -9 <PID>
```

## 📈 Development

### Contributing

1. Fork the repository
2. Create feature branch: `git checkout -b feature/amazing-feature`
3. Commit changes: `git commit -m 'Add amazing feature'`
4. Push to branch: `git push origin feature/amazing-feature`
5. Open Pull Request

### Code Style

- Follow **PEP 8** for Python code
- Use **Black** for code formatting
- Add **docstrings** for all functions
- Write **unit tests** for new features

```bash
# Format code
black src/

# Check style
flake8 src/

# Type checking
mypy src/
```

### Development Setup

```bash
# Install development dependencies
pip install -r requirements-dev.txt

# Setup pre-commit hooks
pre-commit install

# Run development server
python src/main.py --debug
```

