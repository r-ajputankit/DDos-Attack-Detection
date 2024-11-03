# RBNF-Augmented DDoS Detection with CNN-GRU Fusion
## Overview
This project implements a DDoS detection system augmented by Radial Basis Neural Functions (RBNF) and utilizes a CNN-GRU fusion model for enhanced detection accuracy. The system leverages convolutional neural networks (CNN) for feature extraction and gated recurrent units (GRU) for sequential data processing, aiming to improve the real-time detection of distributed denial-of-service (DDoS) attacks on network traffic.

## Dataset
This project utilizes a NSL-KDD Dataset containing features like:
- Source and destination IPs
- Protocols
- Packet sizes
- duration
- flag SF
- dst_host_srv_count

## Proposed Method - Overview
![image](https://github.com/user-attachments/assets/9bd85057-107c-4c26-8c04-5cfc8e638699)

## Data Preprocessing
- Data Balancing: Downsampling to address class imbalance
- Feature Selection: mRMR algorithm
- Selected Features: flag SF, dst_host_srv_count, logged_in, same_srv_rate, dst_host_srv_serror_rate, srv_error_rate, count

## Model Architecture
- CNN: 32 filters, size 3, for local pattern extraction
- GRU Layer 1: 64 units, returns sequences
- GRU Layer 2: 32 units, returns final state
- RBFN Layer: For function approximation
<p align="">
  <img src="https://github.com/user-attachments/assets/47de3be5-8548-4db9-be8b-58e0d13121e3" alt="Image 1" width="70%" style="display: inline-block;"/>
  <img src="https://github.com/user-attachments/assets/fca5d1cb-bdea-4d68-9833-11c0d721cf39" alt="Image 2" width="20%" style="display: inline-block;"/>
</p>



## Experimental Setup
- Training: Binary cross-entropy loss, Adam optimizer
- Evaluation Metrics: Accuracy, Precision, Recall, F1-score
- Visualization: ROC curves, Confusion matrices
- Threshold Optimization: Fine-tuning sensitivity and specificity

## Results
- Training Dataset:
  - F1-score: 94%
  - Precision: 93%
  - Recall: 96%
  - Accuracy: 94%
- Testing Dataset:
  - F1-score: 83%
  - Precision: Class 0 - 82%, Class 1 - 83%
  - Recall: Class 0 - 76%, Class 1 - 88%
  - Accuracy: 83%









