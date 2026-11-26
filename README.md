# Python Batch Image Resizer

A production-ready Python automation utility built to recursively scan directories and batch-resize images by a configurable percentage scale. Engineered with OS-agnostic path resolution, structured logging, and defensive error handling.

## Key Engineering Features
* **Environment-Agnostic Pathing:** Uses `pathlib` anchored to `__file__` so the script executes reliably across Windows, macOS, and Linux cloud environments regardless of the working directory.
* **Structured Observability:** Implements Python's `logging` module with dual handlers (`FileHandler` and `StreamHandler`) to output timestamped logs to both the console and `app.log`.
* **Fault Tolerance & Guard Clauses:** Validates directory existence, filters out subdirectories, and safely skips corrupted or unsupported files (`None` checks) without interrupting batch execution.
* **Modular Architecture:** Separates dimension calculation, single-batch processing, and execution orchestration behind a clean `if __name__ == "__main__":` entry point.

## Project Structure
```text
python-batch-image-resizer/
├── images/             # Input directory containing source images
├── Resized-Images/     # Auto-generated output directory for processed images
├── main.py             # Core automation script
├── requirements.txt    # Project dependencies
├── .gitignore          # Ignored local artifacts and logs
└── README.md           # Project documentation
```

## Setup & Usage

1. **Clone the repository**
   ```bash
   git clone https://github.com/itsloni/python-batch-image-resizer.git
   cd python-batch-image-resizer
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Add source images**
   Place the images you want to resize inside the `images/` folder (nested subfolders are supported).

4. **Run the automation script**
   ```bash
   python main.py
   ```
   Processed images will be saved to `Resized-Images/`, and execution logs will be recorded in `app.log`.
