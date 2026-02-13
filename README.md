# DVC Wine Dataset Project

A Data Version Control (DVC) project for managing and tracking the Wine dataset with proper versioning and reproducibility.

## 📋 Project Overview

This project demonstrates the use of **DVC (Data Version Control)** to manage data files, ensure reproducibility, and maintain version control for machine learning workflows. It includes the Wine dataset, a classic dataset used for classification tasks in machine learning.

### Key Features
- **Data Version Control**: Track large data files with DVC instead of Git
- **Reproducibility**: Ensure consistent data management across different environments
- **Version Tracking**: Keep history of dataset changes
- **Collaboration**: Share data efficiently without storing large files in Git

## 📁 Project Structure

```
DVC_TEST/
├── README.md              # Project documentation
├── ScriptsActivate        # Script initialization file
├── data/
│   ├── wine.csv          # Wine dataset
│   └── wine.csv.dvc      # DVC metadata file for wine.csv
├── .dvc/                 # DVC configuration directory
├── .dvcignore            # DVC ignore patterns
├── .gitignore            # Git ignore patterns
└── .venv/                # Python virtual environment (local)
```

## 🍇 About the Dataset

The Wine dataset contains:
- **Size**: 2,051 bytes
- **Format**: CSV (Comma-Separated Values)
- **Content**: Wine classification data with chemical properties and quality ratings
- **Use Case**: Classification tasks, machine learning model training

## 🚀 Getting Started

### Prerequisites
- Python 3.7 or higher
- Git
- DVC (Data Version Control)

### Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd DVC_TEST
   ```

2. **Create and activate a Python virtual environment**
   ```bash
   python -m venv .venv
   source .venv/bin/activate  # On Windows: .venv\Scripts\activate
   ```

3. **Install DVC**
   ```bash
   pip install dvc
   ```

4. **Pull the data from DVC** (if data is tracked remotely)
   ```bash
   dvc pull
   ```

### Usage

#### Browse the Dataset
```bash
# View the wine dataset
head -20 data/wine.csv
```

#### Check DVC Status
```bash
# Show DVC status
dvc status

# Show data file information
dvc dag
```

#### Track New Data Files with DVC
```bash
# Add a new file to DVC tracking
dvc add data/newfile.csv

# Push changes
dvc push
```

#### Update Your Changes
```bash
# After making changes, commit everything
git add .gitignore data/wine.csv.dvc
git commit -m "Update wine dataset"

# Push to remote storage (if configured)
dvc push

# Push code to Git
git push
```

## 🔧 Configuration

### DVC Configuration
DVC settings are stored in `.dvc/config`. For remote storage setup:

```bash
# Add a remote storage location
dvc remote add -d myremote /remote/storage/path

# Set up cloud storage (S3, GCS, Azure, etc.)
dvc remote add -d mystorage s3://my-bucket/path
```

## 📚 Useful DVC Commands

| Command | Description |
|---------|-------------|
| `dvc init` | Initialize DVC in a repository |
| `dvc add <file>` | Track a file with DVC |
| `dvc remove <file>.dvc` | Stop tracking a file |
| `dvc push` | Push data to remote storage |
| `dvc pull` | Pull data from remote storage |
| `dvc status` | Check if local data matches tracked versions |
| `dvc dag` | Display the data pipeline DAG |
| `dvc diff` | Show differences in data between commits |

## 🔄 Workflow

1. **Develop**: Make changes to your code and data
2. **Track**: Use `dvc add` to track large files
3. **Commit**: Commit the `.dvc` files to Git (not the data)
4. **Push**: Push code to Git and data to DVC remote
5. **Collaborate**: Team members can pull the latest code and data

## 🌐 Virtual Environment Setup

The `.venv/` directory contains the Python virtual environment. To activate it:

```bash
# On Linux/macOS
source .venv/bin/activate

# On Windows
.venv\Scripts\activate
```

To deactivate:
```bash
deactivate
```

## 📖 Learn More About DVC

- [DVC Official Documentation](https://dvc.org/doc)
- [DVC Tutorial](https://dvc.org/doc/start)
- [DVC on GitHub](https://github.com/iterative/dvc)

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 Notes

- Large data files are not stored in Git; they are managed by DVC
- Team members should run `dvc pull` after cloning to get the dataset
- Always commit `.dvc` files but not the actual large data files

## 📧 Support

For issues or questions, please refer to DVC documentation or contact the project maintainer.

---

**Happy Data Versioning! 🚀**