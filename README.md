
# BCMID: Breast Cancer Multimodal Imaging Dataset

**BCMID** is the first publicly available multimodal breast cancer imaging dataset from Egypt, collected at *Ayady Almostakbal Hospital* in Alexandria. It supports the development of advanced Computer-Aided Diagnosis (CAD) systems by providing paired **Ultrasound** and **Mammogram** images for each patient, annotated with **BI-RADS** category labels.

## 📊 Dataset Overview

- **Population**: 323 adult female patients  
- **Age Range**: 26 to 82 years  
- **Modalities**: Ultrasound + Mammography  
- **Annotations**: BI-RADS categories, derived from expert clinical reports  
- **License**: Creative Commons Attribution (CC BY)  
- **Download**: [Zenodo Record](https://zenodo.org/records/14970848)

Researchers and developers are encouraged to use this dataset for academic and research purposes. Please cite the dataset when using it in publications or derivative works.

### 📌 Citation
```bibtex
@dataset{seddik_tawfik_2025_14970848,
  author       = {Seddik Tawfik, Noha and
                  Ghatwary, Noha and
                  Elgendy, Ahmed and
                  Nasr, Omar and
                  Ye, Xujiong},
  title        = {BCMID: Breast Cancer Multimodal Imaging Dataset},
  month        = mar,
  year         = 2025,
  publisher    = {Zenodo},
  doi          = {10.5281/zenodo.14970848},
  url          = {https://doi.org/10.5281/zenodo.14970848}
}
```

---

## 🧪 Technical Validation

To validate the dataset's utility, we performed **three multiclass classification experiments** using imaging modalities individually and in combination, predicting BI-RADS categories based on medical report labels.

### 🧠 Model Architecture

We adopted the **Vision Transformer (ViT)**  as a baseline model due to its effectiveness in medical image analysis. The pipeline includes:

- **Modality-Specific Training**:  
  Independent ViT models were trained on mammogram and ultrasound images to extract complementary features.
  
- **Feature Fusion**:  
  Features from each modality were concatenated and passed through a **shared classification head**, implemented as a multi-layer perceptron (MLP).

### ⚙️ Training Details

- **Optimizer**: ADAM  
- **Learning Rate Tuning**: Bayesian Optimization 
- **Split**: 80% training, 20% validation with **stratified sampling** to maintain class balance

