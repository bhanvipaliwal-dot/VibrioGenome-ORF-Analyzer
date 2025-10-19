# Bacterial Genome Analysis — VibrioGenome-ORF-Analyzer

### Author
**Bhanvi Paliwal**

---

## Project Overview
This project provides a **Python-based genome analysis pipeline** designed to examine the genome of *Vibrio natriegens*, a marine bacterium recognized for its **exceptionally fast growth rate** and rising importance in **synthetic biology**.

The workflow identifies **open reading frames (ORFs)**, translates them into protein sequences, and computes fundamental **protein properties** such as molecular weight, isoelectric point (pI), and an estimated solubility score.  
It also includes a framework for **BLAST-based annotation** of the predicted proteins (optional, depending on internet and Biopython setup).

---

## Pipeline Overview
Below is the high-level flow of the computational pipeline implemented in the Jupyter notebook:
1. **Genome Input** — Load the *Vibrio natriegens* genome FASTA file using Biopython.  
2. **ORF Detection** — Scan both forward and reverse strands for potential ORFs ≥ 50 codons.  
3. **Translation** — Convert each detected ORF into its corresponding amino acid sequence.  
4. **Protein Feature Analysis** —  
   - Compute **molecular weight (kDa)** using `ProteinAnalysis`.  
   - Estimate **isoelectric point (pI)**.  
   - Predict **protein solubility** using a simple amino acid–based scoring function.  
5. **BLAST Annotation (Optional)** —  
   - Submit up to 5 protein sequences (<1000 aa) to NCBI BLAST.  
   - Retrieve the **top alignment hit** and associated **E-value**.  
6. **Data Export** — Save analyzed protein data and BLAST results as a combined CSV file (`final_results_with_blast.csv`).

---

## Features
- Scans both DNA strands for **ORFs ≥ 50 codons**
- Translates ORFs into protein sequences
- Calculates:
  - Molecular weight (kDa)
  - Isoelectric point (pI)
  - Estimated solubility score
- (Optional) Performs **BLAST search** for up to 5 short protein sequences (<1000 aa)

---

## Repository Contents
| File | Description |
|------|--------------|
| `VibrioGenome-ORF-Analyzer.ipynb` | Main Jupyter Notebook containing the full analysis pipeline |
| `vibrionatriegens_genome.fasta` | Input genome file used for ORF scanning |
