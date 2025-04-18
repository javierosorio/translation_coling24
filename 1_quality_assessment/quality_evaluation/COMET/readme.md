```markdown
# COMET Evaluation Script

## Overview

This script evaluates translation quality using **COMET** (Crosslingual Optimized Metric for Evaluation of Translation). COMET is a neural-based metric that provides more accurate and context-aware evaluation of machine translation outputs compared to traditional metrics like **BLEU**.

The script dynamically loads input files, processes them using pre-trained COMET models, and saves the evaluation results with corresponding filenames.

## Prerequisites

Ensure you have the necessary dependencies installed before running the script.

### Installation

```bash
pip install unbabel-comet pandas torch matplotlib seaborn statsmodels
```

## Usage

Follow these step-by-step instructions to use the script.

### 1. Input Files

The script processes **CSV** files located in the `input_data` directory. Each input file should have the following columns:

- **Source**: Original text
- **Translation**: Machine-translated text
- **Reference**: Human reference translation

#### Example format:

```csv
Source,Translation,Reference
"Hello world","Hola mundo","Hola mundo"
"How are you?","¿Cómo estás?","¿Cómo estás?"
```

### 2. Run the Script

Execute the script using:

```bash
python comet_evaluation.py
```

### 3. Output Files

The script generates evaluation results in the `comet_outputs` directory. The output files are named based on the **COMET model** used, e.g., `COMET_Evaluation_Results_wmt20-comet-da.csv`.

Each output file is a **CSV** containing the following columns:

- **Source**: Original text
- **Reference**: Human reference translation
- **Translation**: Machine-translated text
- **COMET Score**: Evaluation score given by COMET
- **Model**: The COMET model used for evaluation
- **Filename**: The original input filename

#### Example output format:

```csv
Source,Reference,Translation,COMET Score,Model,Filename
"Hello world","Hola mundo","Hola mundo",0.95,"wmt20-comet-da","input_file.csv"
"How are you?","¿Cómo estás?","¿Cómo estás?",0.92,"wmt20-comet-da","input_file.csv"
```

### 4. Interpreting Results

- **Higher COMET scores indicate better translation quality.**
- Use the output files for further analysis or visualization.

### 5. Logging

- The script logs all progress in `comet_evaluation.log`.
- Errors and skipped models are recorded in the log file.

## Notes

- Ensure your `input_data` folder contains properly formatted **CSV** files.
- The script will process all files in `input_data` automatically.
- If a model fails to load, it will be **skipped and logged**.

## Contact

For questions or issues, please open an **issue** on the repository.

**Happy Evaluating!**
```

