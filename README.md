# Classification of TATA-box promoter-like sequences

## Overview
This project explores the application of machine learning to nucleotide sequences.  
The objective is to classify DNA sequences containing a **TATA-box motif** (a core promoter element in many eukaryotic genes) versus randomly generated sequences without this motif.

## Methodology
- **Data generation**: Synthetic 100-bp DNA sequences are created. Positive samples contain a TATA-box motif placed within positions 25–40 (a biologically plausible promoter window). Negative samples are random sequences; a minority contain noisy or out-of-window motifs to form “hard negatives.”
- **Baseline**: A simple motif search detects the canonical TATAAA motif (allowing ≤1 mismatches). This establishes a performance reference and highlights how much additional value ML can provide.
- **Feature extraction**: sequences were represented using **k-mer counts**, a common approach to capture local nucleotide patterns.
- **Model**: a **logistic regression classifier** was trained on character k-mer counts (3–6 nt) and an additional binary positional feature indicating whether “TATA” occurs inside the promoter window.
- **Evaluation**: model performance was assessed through accuracy metrics, a precision–recall curve, and analysis of the most discriminative k-mers.

**Note:** The data generation process was updated to better reflect biological promoter architecture as TATA motifs are now inserted specifically within positions 25–40. Negatives may contain noisy or out-of-window motifs. This allows the model to use positional information in addition to sequence motifs.

## Results
- Logistic Regression reaches **~0.69** accuracy and **~0.77** PR-AUC on the updated dataset.
- Because the task is strongly driven by the presence of a known motif, machine learning provides only limited gains over a motif-search baseline — although it does successfully learn motif variants and positional preferences.
- The positional feature receives a strong positive weight, confirming that the model exploits the biological prior.
- The most discriminative k-mers correspond to TATAAA and close variants, showing that the model learns canonical TATA-box signatures.

## Perspectives
This project illustrates how machine learning can capture biologically meaningful patterns in DNA sequences.  
It also opens the way for further exploration of more advanced architectures (e.g., Transformers such as InstaDeep's Nucleotide Transformer) for biological sequence analysis.

## Repository structure
- `TATA_Box_project.ipynb`: main notebook with code, explanations, and results.
- `README.md`: project description.

