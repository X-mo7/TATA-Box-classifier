# Classification of TATA-box promoter-like sequences

## Overview
This project explores the application of machine learning to nucleotide sequences.  
The objective is to classify DNA sequences containing a **TATA-box motif** (a core promoter element in many eukaryotic genes) versus randomly generated sequences without this motif.

## Methodology
- **Data generation**: synthetic DNA sequences were created, some embedding the canonical TATA-box motif, others being random.
- **Feature extraction**: sequences were represented using **k-mer counts**, a common approach to capture local nucleotide patterns.
- **Model**: a **logistic regression classifier** was trained to distinguish promoter-like sequences from random ones.
- **Evaluation**: model performance was assessed through accuracy metrics, a precision–recall curve, and analysis of the most discriminative k-mers.

## Results
- The logistic regression classifier reached an accuracy of around **74%** (seed-dependent).
- The precision–recall AUC was around **0.73**, confirming a clear separation between promoter-like and random sequences.
- The most discriminative k-mers identified by the model correspond to the expected TATA-box motif.

## Perspectives
This project illustrates how machine learning can capture biologically meaningful patterns in DNA sequences.  
It also opens the way for further exploration of more advanced architectures (e.g., Transformers such as Instadeep's Nucleotide Transformers) for biological sequence analysis.

## Repository structure
- `TATA_Box_project.ipynb`: main notebook with code, explanations, and results.
- `README.md`: project description.

