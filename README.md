# shoulder-xray-data-volume-impact

**Impact of training data volume on the detection and external generalization of rotator cuff calcifications.**

This repository contains the full experimental pipeline (Jupyter notebooks) used to develop and evaluate Deep Learning models for the detection of **calcific tendinopathy of the rotator cuff (CTRC)**. The core of this research is a systematic analysis of how incremental training data volumes (25%, 50%, 75%, and 100%) affect diagnostic performance and model robustness in both internal and external clinical cohorts.

---

## Project summary

The study utilizes a unified CNN-based framework (VGG19) to identify the **data saturation point** in musculoskeletal radiology. By isolating data volume as the primary independent variable, we demonstrate where additional training samples yield diminishing returns for external generalization, supporting a shift toward more efficient "Smart Data" strategies.

---

## Repository structure

### Subfolders (Simulation)
- **Databases/**: Placeholder for dataset metadata.
- **Images_X_rays/**: Placeholder for representative ROI examples.
- **Models/**: Weights and architecture definitions.
- **Subsets_v0/**: Logic for data partitioning and incremental splits.

### Notebooks (Execution order)

1. **00_environment_setup.ipynb** Environment preparation, library checks, and global configuration.

2. **01_Unet_training_models.ipynb** Training of the U-Net architecture for automated humeral segmentation.

3. **02_preprocess_dicom_luts.ipynb** DICOM standardization, LUT application, and intensity normalization.

4. **03_data_merge_dicom_clinical.ipynb** Integration of image data with associated clinical and demographic metadata.

5. **04_eda_dataset_statistics.ipynb** Exploratory data analysis and descriptive statistics of the study population.

6. **05_train_cnn_models_example_M100.ipynb** Standardized training pipeline (baseline M100 model) with 5-fold cross-validation.

7. **06_eval_internal_validation.ipynb** Performance metrics and scaling laws for the internal cohort (HURJC).

8. **07_eval_external_generalization.ipynb** Transferability and saturation analysis on the external cohort (HGV).

---

## Ethics and Privacy
This repository provides **code and workflow only**. To ensure compliance with institutional ethical standards and data protection regulations (GDPR/Helsinki), **no patient data or original DICOM files are included**.

---

## Environment
- Python 3.10
- Key libraries: PyTorch, TensorFlow/Keras, Scikit-learn, OpenCV, Matplotlib, Pydicom.
