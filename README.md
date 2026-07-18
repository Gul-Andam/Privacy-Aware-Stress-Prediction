<img width="1444" height="1446" alt="_- visual selection (1)" src="https://github.com/user-attachments/assets/7620e78e-00dd-445c-9b54-c4552d29b266" /># 🔐 A Privacy-Aware Framework for Stress Prediction Based on Secure Computational Intelligence

<p align="center">
  <img src="https://img.shields.io/badge/Status-Preprint-orange?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Python-3.8+-blue?style=for-the-badge&logo=python"/>
  <img src="https://img.shields.io/badge/Encryption-BFV%20%7C%20LWE-purple?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Accuracy-91%25-brightgreen?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/ResearchGate-Published-00CCBB?style=for-the-badge&logo=researchgate"/>
</p>

<p align="center">
  <b>Hafiz Gulfam Ahmad Umar¹ · Gul Andam² · Qahtan M. Yas¹* · Aymen Mudheher Badr³</b><br/>
  ¹ Ghazi University, Dera Ghazi Khan, Pakistan &nbsp;|&nbsp; ³ University of Diyala, Iraq
</p>

<p align="center">
  <a href="https://www.researchgate.net/publication/404834665">📄 Read on ResearchGate</a> &nbsp;|&nbsp;
  <a href="https://gul-andam.github.io/">🌐 Author Portfolio</a> &nbsp;|&nbsp;
  <a href="https://www.linkedin.com/in/gull-andam-48a2a1331/">💼 LinkedIn</a>
</p>

---

## 📌 Abstract

> Stress prediction is a critical component of mental health assessment — enabling early intervention before stress negatively impacts wellbeing. This paper presents a **privacy-preserving framework** for stress prediction using machine learning combined with **homomorphic encryption (BFV + LWE)**. Models including **Linear Regression, Random Forest, and XGBoost** are trained and evaluated on real-world demographic, behavioral, and mental health data. Inference is performed directly on **ciphertext**, with decryption occurring only post-prediction. 10-fold cross-validation yields **91% accuracy** (Linear Regression, MSE = 0.721) with only **1–2% accuracy loss** from encryption overhead — demonstrating that privacy and performance can coexist.

**Keywords:** `Stress Prediction` · `Mental Health AI` · `Homomorphic Encryption` · `BFV` · `LWE` · `Privacy-Preserving ML` · `Lattice-based Cryptography`

---

## 🎯 Key Results at a Glance

| Metric | Value |
|---|---|
| 🏆 Best Accuracy | **91.0%** (Linear Regression) |
| 📉 Best MSE | **0.721** (Linear Regression) |
| 🔐 Encryption Accuracy Loss | **Only 1–2%** |
| ⏱️ Encryption Overhead (BFV) | **10–20 ms/sample** |
| 📊 Dataset Size | **5,000 records** |
| 🔁 Validation | **10-Fold Cross-Validation** |
| 🛡️ Security Level | **128-bit post-quantum** |

---

## 🧠 Problem Statement

Existing stress detection systems face a critical gap:

- ✅ Machine learning models can predict stress accurately
- ❌ But they require **raw, unencrypted access** to sensitive personal health data
- ❌ This violates **GDPR, HIPAA**, and patient confidentiality norms
- ❌ Fully Homomorphic Encryption (FHE) is too slow for real-time use

**Our solution:** A hybrid framework using **Somewhat Homomorphic Encryption (SHE)** — specifically BFV and LWE — that enables secure inference on encrypted data with minimal computational overhead and negligible accuracy loss.

---

## 🏗️ Framework Architecture

### How Homomorphic Encryption Works

<p align="center">
  <img src="images/image1.png" width="650" alt="Homomorphic Encryption Overview"/>
</p>
<p align="center"><i><img width="892" height="769" alt="napkin 1" src="https://github.com/user-attachments/assets/04c7f150-c482-4278-a29f-d2aa8cdaeddd" />
</i></p>

### Encryption Process Workflow

<p align="center">
  <<img width="1444" height="1446" alt="_- visual selection (1)" src="https://github.com/user-attachments/assets/7f398748-071c-4e95-8c42-2cad6f69e0c5" />
/>
</p>
<p align="center"><i>Fig 2. End-to-end encryption workflow: Input → Encrypt → Predict → Decrypt → Output</i></p>

### The Core Mathematical Flow

```
ε(X) = X_encrypted          → Encrypt input features
f(X_encrypted; θ) → Ŷ_encrypted   → Predict on ciphertext
D(Ŷ_encrypted) = Ŷ          → Decrypt output only
```

### Somewhat Homomorphic Encryption (SHE)

<p align="center">
  <img src="images/image4.png" width="650" alt="Somewhat Homomorphic Encryption"/>
</p>
<p align="center"><i>Fig 4. BFV-based Somewhat Homomorphic Encryption scheme for secure ML inference</i></p>

---

## 📊 Dataset

- **Source:** Mental Health and Lifestyle Indicators Dataset (Kaggle, 2022–2023)
- **Size:** 5,000 anonymized individual records
- **Collection:** Anonymous online survey, adults aged 18–65
- **Label:** Stress Level (Low / Moderate / Severe) — self-reported via PSS-3 scale

| Feature | Description | Type |
|---|---|---|
| Age | Age of the individual | Numerical |
| Gender | Gender of the individual | Categorical |
| Occupation | Occupation category | Categorical |
| Country | Country of residence | Categorical |
| Mental_Health_Condition | Binary mental health indicator | Categorical |
| Sleep_Hours | Average daily sleep hours | Numerical |
| Work_Hours | Average daily work hours | Numerical |
| Physical_Activity_Hours | Daily physical activity hours | Numerical |
| **Stress_Level** | **Target: Low / Moderate / Severe** | **Ordinal** |

**Label Distribution:** ~30% Low · ~44% Moderate · ~26% Severe

### Age Distribution in Dataset

<p align="center">
  <img src="images/image3.png" width="600" alt="Age Distribution"/>
</p>
<p align="center"><i>Fig 3. Age distribution across dataset — well-balanced across 20–65 age range</i></p>

---

## ⚙️ Encryption Parameters

| Scheme | Parameter | Value | Description |
|---|---|---|---|
| BFV | Polynomial Modulus Degree | 2¹⁴ | Polynomial size for encrypted arithmetic |
| BFV | Plaintext Modulus | 2²⁰ | Controls precision of plaintext representation |
| LWE | Noise Standard Deviation | 3.2 | Controls noise level for encryption |
| Lattice-based | Security Level | **128-bit** | Ensures post-quantum cryptographic security |

---

## 🤖 Machine Learning Models

Four models were trained and evaluated under the encrypted framework:

| Algorithm | Key Parameters | Role |
|---|---|---|
| **Linear Regression** | LR: 0.01 | Numerical baseline, ordinal modeling |
| **Random Forest** | Trees: 100, Max Depth: 10 | Ensemble learning |
| **XGBoost** | Trees: 100, Max Depth: 5 | Gradient-boosted trees |
| **Neural Network** | Layers: [64, 32, 1], ReLU | Non-linear pattern capture |

---

## 📈 Results & Visualizations

### Model Performance Comparison (MSE + Accuracy)

<p align="center">
  <img src="images/image16.png" width="650" alt="Model Performance Comparison"/>
</p>
<p align="center"><i>Fig 16. MSE vs Accuracy across all four models — Linear Regression leads on both metrics</i></p>

### Final Performance Table

| Model | MSE ↓ | Accuracy ↑ | MAE | RMSE | R² | Enc. Time | Dec. Time |
|---|---|---|---|---|---|---|---|
| **Linear Regression** | **0.721** | **91.0%** | 0.42 | 0.63 | 0.76 | 10ms | 6ms |
| Random Forest | 0.756 | 90.2% | 0.34 | 0.52 | 0.87 | 12ms | 8ms |
| Neural Network | 0.946 | 88.3% | 0.27 | 0.45 | 0.92 | 20ms | 12ms |
| XGBoost | 0.994 | 87.5% | 0.29 | 0.47 | 0.90 | 15ms | 10ms |

### Model Comparison (MSE Bar Chart)

<p align="center">
  <img src="images/image7.png" width="650" alt="Model Comparison Chart"/>
</p>
<p align="center"><i>Fig 7. MSE comparison — Linear Regression achieves lowest error (0.721)</i></p>

### Cross-Validation Model Performance

<p align="center">
  <img src="images/image8.png" width="650" alt="Model Performance Statistical"/>
</p>
<p align="center"><i>Fig 8. Statistical significance testing — Linear Regression vs. other models (10-fold CV)</i></p>

### MSE Distribution Across Folds

<p align="center">
  <img src="images/image19.png" width="650" alt="Distribution of MSE"/>
</p>
<p align="center"><i>Fig 19. MSE distribution across 10-fold cross-validation folds for all models</i></p>

### Computation Time by Model

<p align="center">
  <img src="images/image18.png" width="650" alt="Computation Time"/>
</p>
<p align="center"><i>Fig 18. Computation time — Neural Network (~300s) vs Linear Regression (~90s)</i></p>

---

## 🔐 Encryption Results

### Prediction Before vs. After Decryption

<p align="center">
  <img src="images/image10.png" width="650" alt="Prediction Before and After Decryption"/>
</p>
<p align="center"><i>Fig 10. Original vs. decrypted predictions — encryption has negligible impact on output</i></p>

### Original vs. Decrypted Predictions (Scatter Plot)

<p align="center">
  <img src="images/image13.png" width="650" alt="Original vs Decrypted Predictions Scatter"/>
</p>
<p align="center"><i>Fig 13. Scatter plot — points cluster tightly along diagonal, confirming prediction integrity</i></p>

### Distribution of Prediction Differences

<p align="center">
  <img src="images/image6.png" width="650" alt="Distribution of Prediction Differences"/>
</p>
<p align="center"><i>Fig 6. Histogram of prediction differences — minimal deviation between original and decrypted</i></p>

### Absolute Errors Across Samples

<p align="center">
  <img src="images/image9.png" width="650" alt="Absolute Error"/>
</p>
<p align="center"><i>Fig 9. Absolute errors across 20 samples — all within 0.00–0.10 range</i></p>

### Error Distribution (Box Plot)

<p align="center">
  <img src="images/image14.png" width="650" alt="Error Distribution Box Plot"/>
</p>
<p align="center"><i>Fig 14. Error distribution per prediction range — errors remain low across all bins</i></p>

### BFV vs. LWE Encryption MSE Comparison

<p align="center">
  <img src="images/image12.png" width="650" alt="Comparison of MSE BFV vs LWE"/>
</p>
<p align="center"><i>Fig 12. BFV MSE (~0.0030) vs LWE MSE (~0.0035) — both schemes maintain prediction fidelity</i></p>

### Encryption Scheme Trade-Off

| Scheme | Enc. Time | Dec. Time | Accuracy Loss |
|---|---|---|---|
| **BFV** | 1.3s | 0.9s | 0.02 (2%) |
| **LWE** | 1.6s | 1.1s | 0.01 (1%) |

### Time Overhead Comparison

<p align="center">
  <img src="images/image15.png" width="650" alt="Time Overhead Comparison"/>
</p>
<p align="center"><i>Fig 15. Encryption (~0.8s) dominates overhead; Prediction (~0.2s) is highly efficient</i></p>

---

## 📋 Classification Results by Stress Level

| Stress Level | Precision | Recall | F1-Score | Samples |
|---|---|---|---|---|
| **Low** | 0.91 | 0.88 | 0.89 | 150 |
| **Moderate** | 0.87 | 0.85 | 0.86 | 220 |
| **Severe** | 0.83 | 0.90 | 0.86 | 130 |

### Stress Level by Mental Health Condition

<p align="center">
  <img src="images/image11.png" width="650" alt="Stress Level by Mental Health Condition"/>
</p>
<p align="center"><i>Fig 11. Stress level distribution — individuals with mental health conditions show elevated severity</i></p>

---

## 🔍 Additional Analysis

### Residual Plot (Random Forest)

<p align="center">
  <img src="images/image5.png" width="650" alt="Residual Plot"/>
</p>
<p align="center"><i>Fig 5. Residual plot — no systematic bias pattern, confirming good model fit</i></p>

### Anomaly Detection (Isolation Forest)

<p align="center">
  <img src="images/image17.png" width="650" alt="Anomaly Detection 3D Scatter"/>
</p>
<p align="center"><i>Fig 17. 3D scatter — red anomalies highlight outliers with unusual stress/sleep/work patterns</i></p>

---

## 📐 Statistical Significance Testing

| Comparison | t-statistic | t-test p-value | Wilcoxon p-value | Significant? |
|---|---|---|---|---|
| RF vs. Linear Regression | 3.43 | 0.0075 | 0.0019 | ✅ Yes (p < 0.01) |
| XGB vs. Linear Regression | 5.87 | 0.0002 | 0.0019 | ✅ Yes (p < 0.01) |
| NN vs. Linear Regression | 0.25 | 0.8058 | 0.8457 | ❌ No (similar performance) |

> Linear Regression and Neural Network perform **statistically equivalently**, but Linear Regression wins on simplicity, speed, and privacy overhead.

---

## 🛠️ Tech Stack

```
Python 3.8+
├── Data: Pandas, NumPy
├── ML: Scikit-learn, XGBoost, Keras/TensorFlow
├── Encryption: BFV (SEAL-compatible), LWE
├── Visualization: Matplotlib, Seaborn
└── Environment: Jupyter Notebook / Google Colab
```

**Hardware:** Intel Core i7 · 16GB RAM · 512GB SSD · Optional NVIDIA GPU

---

## 🚀 How to Use

```bash
# Clone the repository
git clone https://github.com/Gul-Andam/Privacy-Aware-Stress-Prediction.git
cd Privacy-Aware-Stress-Prediction

# Install dependencies
pip install -r requirements.txt

# Run the notebook
jupyter notebook stress_prediction_encrypted.ipynb
```

---

## 🌍 Why This Matters

| Challenge | Our Solution |
|---|---|
| ML needs raw data → privacy risk | BFV encryption → inference on ciphertext only |
| FHE too slow for real-time use | SHE (BFV+LWE) → millisecond-level overhead |
| GDPR/HIPAA compliance gaps | Full pipeline encryption → regulatory compliant |
| Binary stress detection | Ordinal 3-class (Low/Moderate/Severe) prediction |
| Single model comparison papers | 4-model unified encrypted framework evaluated |

---

## 📚 Citation

```bibtex
@article{umar2025privacy,
  title     = {A Privacy-Aware Framework for Stress Prediction Based on Secure Computational Intelligence},
  author    = {Umar, Hafiz Gulfam Ahmad and Andam, Gul and Yas, Qahtan M. and Badr, Aymen Mudheher},
  journal   = {Preprint},
  year      = {2025},
  month     = {November},
  url       = {https://www.researchgate.net/publication/404834665}
}
```

---

## 👤 Author — Gul Andam

**AI & ML Engineer | NLP · Healthcare AI · Privacy-Preserving ML**

📍 Dera Ghazi Khan, Pakistan · 🎓 MS IT, Ghazi University

[![Portfolio](https://img.shields.io/badge/Portfolio-gul--andam.github.io-00D4FF?style=flat-square)](https://gul-andam.github.io/)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0077B5?style=flat-square&logo=linkedin)](https://www.linkedin.com/in/gull-andam-48a2a1331/)
[![ResearchGate](https://img.shields.io/badge/ResearchGate-Profile-00CCBB?style=flat-square&logo=researchgate)](https://www.researchgate.net/profile/Gul-Andam-2)
[![GitHub](https://img.shields.io/badge/GitHub-Gul--Andam-181717?style=flat-square&logo=github)](https://github.com/Gul-Andam)
[![Fiverr](https://img.shields.io/badge/Hire%20Me-Fiverr-1DBF73?style=flat-square)](https://www.fiverr.com/gul_andam_8)

---

> *"AI doesn't replace your judgment. It scales it — securely."*
