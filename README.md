# cfd_flow_image_analysis

About Dataset

The dataset comprises images generated using computational fluid dynamics (CFD) simulations for two cases: flow past an elliptic cylinder and flow past an aerofoil. Here are the details:

Elliptic Cylinder Dataset:

Images: 124 for low speed flow and 124 for high speed flow.
Conditions: Simulated for Reynolds numbers of 200 (low speed) and 5000 (high speed).

Aerofoil Dataset:

Images: 250 for low speed flow and 250 for high speed flow.
Conditions: Simulated under similar Reynolds number settings of 200 and 5000 for low speed and high speed flows, respectively.

The datasets were generated and captured via CFD simulations using OpenFOAM software. Images were post-processed with ParaView to standardize resolution.

Kaggle Link to the dataset: <https://www.kaggle.com/datasets/palanithanarajk/cfd-fluid-flow-images>

# Experimentation
This section includes an explanation of the purpose, environment setup, and how the code works.

---

# Fluid Flow Image Classification

This repository contains a Jupyter Notebook (`main_file.ipynb`) that classifies fluid flow images as either **low-speed (Laminar)** or **high-speed (Turbulent)** using Local Binary Pattern (LBP) features and several machine learning classifiers.

## Project Overview

- **Objective**: To classify fluid flow images into low-speed or high-speed categories using computer vision and machine learning.
- **Data Source**: The data is sourced from the Kaggle dataset available at `Kaggle dataset`.
- **Features**: Extracted using the Local Binary Pattern (LBP) method.
- **Classifiers**: k-NN, SVM (linear), and Random Forest.

## Environment Setup

- **Python Version**: `3.10.12`
- **Key Libraries**:
  - `numpy`
  - `pandas`
  - `skimage`
  - `scikit-learn`
  - `matplotlib`
  - `time`

Ensure you have these libraries installed. You can install them using pip if necessary:

```bash
pip install numpy pandas scikit-image scikit-learn matplotlib
```

## Data Organization

Directories are structured as follows:

- **Elliptic Data**:
  - Path: `cfd_flow_image_analysis\data\elliptic\`
- **Aerofoil Data**:
  - Path: `cfd_flow_image_analysis\data\aerofoil\`

## Code Description

### Feature Extraction Process

1. **Load Images**:
   - Iterates over all images in Laminar and Turbulent folders.
   - Converts images to grayscale.

2. **Local Binary Pattern (LBP)**:
   - Calculates LBP for each image with 8 points and radius 1.
   - Generates a histogram of LBP values for feature vector.

3. **Collect Features**:
   - Appends LBP histograms to feature list `X`.
   - Appends labels (0 for low-speed, 1 for high-speed) to `y`.

### Model Training and Evaluation

1. **Classifiers**:
   - k-NN
   - SVM (linear)
   - Random Forest

2. **Grid Search**:
   - Performs hyperparameter tuning using cross-validation.
   - Selects optimal parameters based on cross-validation score.

3. **Performance Metrics**:
   - Accuracy, Precision, Recall, F1 Score, Specificity, and AUC are calculated.
   - Confusion matrices are plotted with enhanced readability.

4. **Output**:
   - Prints evaluation metrics and best hyperparameters for each classifier.
   - Generates confusion matrix plots.

### Considerations

- Ensure the Kaggle environment is properly set up to access the dataset.
- The code is optimized for execution in environments that support Jupyter Notebooks, such as Kaggle Notebooks or Google Colab.

## Execution

1. Run the Jupyter Notebook (`main_file.ipynb`).
2. Review the printed metrics and saved plots in the output files.

## Future Improvements
- Experiment with different LBP parameters or alternative feature extraction techniques.

## Citation
If you use this code in your research, please cite the following paper: 

```
Palani Thanaraj K. (2023). Fluid Flow Image Classification Using LBP Features. GitHub repository. 
<https://github.com/palanithanarajk/cfd_flow_image_analysis>
```


# Repository Information

- **GitHub Link**: [GitHub Repository](https://github.com/palanithanarajk/cfd_flow_image_analysis)

# License

This project is distributed under the terms of the **GNU General Public License v3.0** (or any later version).

You can find a copy of the GNU GPL v3.0 [here](https://www.gnu.org/licenses/gpl-3.0.html).

By using, modifying, or distributing this project, you agree to be bound by the terms of the GPL v3.0.

---

This documentation provides a comprehensive overview of the project, ensuring clarity and usability for anyone interested in using or contributing to the codebase.