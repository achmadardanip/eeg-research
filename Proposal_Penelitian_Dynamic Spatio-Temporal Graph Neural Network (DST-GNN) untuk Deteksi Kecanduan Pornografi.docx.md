# **IDE PENELITIAN INOVATIF**

**Jusul: Dynamic Spatio-Temporal Graph Neural Network (DST-GNN) untuk Deteksi Kecanduan Pornografi**

## **1.1 Latar Belakang & Gap Penelitian**

Penelitian sebelumnya menggunakan metode konvensional seperti SVM, Random Forest, dan MLP untuk klasifikasi kecanduan pornografi dari sinyal EEG. Namun, metode-metode ini memiliki keterbatasan fundamental: mereka tidak mampu memodelkan ***dynamic functional connectivity*** antar region otak yang berubah sepanjang waktu. Otak adalah sistem dinamis kompleks di mana konektivitas antar region berfluktuasi, terutama saat terpapar stimulus yang memicu respons adiktif.

**Novelty:** Belum ada penelitian yang menggunakan Graph Neural Network (GNN) dengan pendekatan spatio-temporal untuk menganalisis kecanduan pornografi berdasarkan sinyal EEG. Penelitian GNN untuk EEG baru diterapkan pada epilepsi, emotion recognition, dan motor imagery \- bukan behavioral addiction seperti pornografi.

## **1.2 Metodologi Inovatif**

### **A. Dynamic Brain Graph Construction**

* **Phase Lag Index (PLI):** Mengukur konektivitas fungsional antar electrode dengan meminimalkan volume conduction effect  
* **Weighted Phase Lag Index (wPLI):** Versi weighted untuk mengurangi noise pada weak coupling  
* **Sliding Window Analysis:** Membuat sequence of graphs untuk menangkap dinamika temporal konektivitas otak

### **B. Arsitektur DST-GNN**

* **Input Layer:** Node features dari 19 channel EEG (power spectral density pada band Delta, Theta, Alpha, Beta, Gamma)  
* **Spatial Graph Convolution:** Graph Attention Network (GAT) untuk mempelajari weighted importance antar brain regions  
* **Temporal Modeling:** Gated Recurrent Units (GRU) atau Temporal Convolutional Network untuk memodelkan evolusi graph sepanjang waktu  
* **Multi-Task Output:** Classification head untuk deteksi adiksi \+ Attention visualization untuk interpretability

### **C. Explainable AI Component**

Menggunakan GNNExplainer atau Integrated Gradients untuk mengidentifikasi: (1) Brain regions mana yang paling diskriminatif antara adiksi vs sehat, (2) Koneksi antar region mana yang paling berubah, (3) Pada band frekuensi mana perubahan paling signifikan.

## **1.3 Eksperimen & Analisis**

**Multi-Condition Analysis:** Analisis pada berbagai kondisi yang tersedia dalam dataset:

* **Baseline:** Eyes Closed & Eyes Open \- mengidentifikasi baseline brain state differences  
* **Emotional:** Happy, Calm, Sad, Fear \- menganalisis emotional dysregulation pada adiksi  
* **Cognitive:** Executive Task & Memory \- mengukur dampak pada fungsi eksekutif

## **1.4 Dampak & Kontribusi**

1. **Objektif Diagnosis:** Menyediakan biomarker objektif berbasis brain connectivity untuk screening kecanduan pornografi, menggantikan metode subjektif seperti kuesioner  
2. **Early Detection:** Memungkinkan deteksi dini sebelum dampak psikologis parah  
3. **Neurobiological Insight:** Memberikan pemahaman baru tentang mekanisme neurologis kecanduan pornografi pada remaja  
4. **Transferable Framework:** Arsitektur dapat diadaptasi untuk behavioral addiction lainnya (gaming, social media)

# **ANALISIS FEASIBILITY**

## **4.1 Ketersediaan Data**

* **Dataset:** 14 subjek (7 adiksi, 7 sehat), 19 channel EEG, 9 task berbeda, 250 Hz sampling rate  
* **Link Download Dataset: [https://prod-dcd-datasets-cache-zipfiles.s3.eu-west-1.amazonaws.com/4r8hp2hmb4-5.zip](https://prod-dcd-datasets-cache-zipfiles.s3.eu-west-1.amazonaws.com/4r8hp2hmb4-5.zip)**   
* **Durasi:** 10 menit per subjek dengan berbagai kondisi eksperimental  
* **Format:** CSV files yang mudah diproses dengan Python/PyTorch

## **4.2 Tools & Libraries**

* **EEG Processing:** MNE-Python untuk preprocessing, filtering, dan feature extraction  
* **Deep Learning:** PyTorch Geometric untuk Graph Neural Networks  
* **Connectivity:** MNE-Connectivity untuk Phase Lag Index computation  
* **Explainability:** Captum atau GNNExplainer untuk interpretability

## **4.3 Timeline Estimasi**

| Minggu | Aktivitas |
| :---: | ----- |
| 1-2 | Data preprocessing, filtering, artifact removal |
| 3-4 | Feature extraction, connectivity computation (PLI/wPLI) |
| 5-6 | Model development, training, hyperparameter tuning |
| 7-8 | Explainability analysis, result interpretation, article writing |

## **4.4 Handling Small Dataset**

Strategi untuk mengatasi keterbatasan jumlah subjek:

* **Data Augmentation:** Sliding window, time-shifting, noise injection pada sinyal EEG  
* **Leave-One-Subject-Out Cross-Validation:** Robust evaluation strategy  
* **Transfer Learning:** Pre-training pada dataset EEG publik yang lebih besar  
* **Multiple Task Analysis:** Memanfaatkan 9 kondisi berbeda untuk meningkatkan sample size

# **KEUNGGULAN & NOVELTY**

## **5.1 Perbandingan dengan Penelitian Sebelumnya**

| Aspek | Penelitian Sebelumnya | Penelitian Ini |
| ----- | ----- | ----- |
| **Metode** | SVM, MLP, Random Forest | **DST-GNN** |
| **Brain Connectivity** | Tidak dianalisis | **Dynamic PLI/wPLI** |
| **Temporal Dynamics** | Static features | **Spatio-temporal modeling** |
| **Interpretability** | Black-box | **Explainable AI (XAI)** |
| **Clinical Relevance** | Classification only | **Biomarker \+ Intervention** |

## **5.2 Poin-Poin Novelty**

* **Pertama** menerapkan Graph Neural Network untuk deteksi kecanduan pornografi berbasis EEG  
* **Kedua** menganalisis dynamic brain connectivity pada behavioral addiction remaja  
* **Ketiga** mengintegrasikan analisis emosi-kognisi pada dataset kecanduan pornografi  
* **Keempat** menyediakan explainable biomarker untuk kecanduan pornografi remaja

# **KESIMPULAN & REKOMENDASI**

Dari ketiga ide yang diajukan, **IDE UTAMA: Dynamic Spatio-Temporal Graph Neural Network (DST-GNN)** direkomendasikan sebagai fokus utama karena:

* Memiliki novelty tertinggi dengan pendekatan yang belum pernah diterapkan sebelumnya  
* Feasible dengan dataset yang tersedia melalui strategi data augmentation  
* Menghasilkan insight yang actionable untuk praktisi klinis  
* Memiliki potensi publikasi tinggi di jurnal impactful (IEEE TBME, NeuroImage, etc.)  
* Dapat dikembangkan lebih lanjut menjadi sistem screening berbasis mobile EEG

**Langkah Selanjutnya:**

* Download dan eksplorasi dataset untuk memahami karakteristik sinyal  
* Setup environment dengan MNE-Python dan PyTorch Geometric  
* Implementasi preprocessing pipeline  
* Develop baseline models sebelum implement DST-GNN

# **REFERENSI UTAMA**

**\[1\]** Kang, X., et al. (2021). Electroencephalogram (EEG) dataset with porn addiction and healthy teenagers. Data in Brief, 39, 107467\.

**\[2\]** Kipf, T. N., & Welling, M. (2017). Semi-supervised classification with graph convolutional networks. ICLR 2017\.

**\[3\]** Veličković, P., et al. (2018). Graph attention networks. ICLR 2018\.

**\[4\]** Stam, C. J., et al. (2007). Phase lag index: Assessment of functional connectivity. Human Brain Mapping, 28(11), 1178-1193.

**\[5\]** Gramfort, A., et al. (2013). MEG and EEG data analysis with MNE-Python. Frontiers in Neuroscience, 7, 267\.

**\[6\]** Ying, R., et al. (2019). GNNExplainer: Generating explanations for graph neural networks. NeurIPS 2019\.

**\[7\]** Klepl, D., et al. (2024). Graph Neural Network-based EEG Classification: A Survey. arXiv:2310.02152.

**\[8\]** Sun, S., et al. (2022). EEG signals based internet addiction diagnosis using CNNs. Applied Sciences, 12(13), 6297\.