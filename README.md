# ML Project Template

This repository provides a template for organizing machine learning projects using DVC for data versioning and reproducibility.

## Project Structure

```
.
├── config/           # Configuration files
├── data/             # Raw and processed data
├── models/           # Saved models
├── notebooks/        # Jupyter notebooks
├── reports/          # Generated reports
├── src/              # Source code
│   ├── data/         # Data loading and preprocessing
│   ├── evaluate/     # Model evaluation
│   ├── features/     # Feature engineering
│   ├── report/       # Report generation
│   ├── stages/       # Pipeline stages
│   └── train/        # Model training
├── requirements.txt  # List Python dependencies
├── .dvc/             # DVC files and cache
├── .gitignore        # Git ignore rules
├── .dvcignore        # DVC ignore rules
```

## Setup Instructions

1. **Clone the repository**
   ```bash
   git clone <repo-url>
   cd project_dir
   ```
2. **Create and activate virtual environment**
   ```bash
   python3 -m venv dvc-venv
   echo "export PYTHONPATH=$PWD" >> dvc-venv/bin/activate
   source dvc-venv/bin/activate
   ```

3. **Install dependencies**
   ```bash
   pip install --upgrade pip setuptools wheel
   pip install -r requirements.txt
   ```
   Add Virtual Environment to Jupyter Notebook

   ```bash
   python -m ipykernel install --user --name=dvc-venv
   ``` 

   Configure ToC for jupyter notebook (optional)

   ```bash
   jupyter contrib nbextension install --user
   jupyter nbextension enable toc2/main
   jupyter notebook #run notebook
   ```

4. **Install DVC**
   ```sh
   pip install dvc
   ```

5. **Initialize DVC (if not already initialized)**
   ```sh
   dvc init
   ```

6. **Add your data**
   Place your raw data in the `data/` directory and track it with DVC:
   ```sh
   dvc add data/<your-data-file>
   git add data/<your-data-file>.dvc .gitignore
   git commit -m "Add raw data"
   ```

7. **Run the pipeline**
   Use scripts in `src/` to preprocess data, train models, and generate reports. You can organize pipeline stages using DVC.

8. **Jupyter Notebooks**
   Store exploratory analysis and experiments in the `notebooks/` directory.

## Reproducibility

- Use DVC to version datasets and models.
- Track experiments and results in `reports/`.

## Contributing

Feel free to open issues or submit pull requests to improve this template.

## License

[None](LICENSE)