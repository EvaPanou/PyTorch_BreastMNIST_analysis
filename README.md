# Breast ultrasound classifier with PyTorch

A small PyTorch project on biomedical image data.

This project trains a small convolutional neural network (CNN) to classify breast ultrasound images as normal or benign versus malignant. It uses BreastMNIST, the breast ultrasound dataset from the MedMNIST collection, in its 28 by 28 pixel version. The model is evaluated on the standard test split using the area under the receiver operating characteristic curve, averaged over several random seeds.

## Dataset

- BreastMNIST, downloaded automatically through the `medmnist` package: https://medmnist.com/

## Setup

1. Create a virtual environment in the project folder:

   ```text
   python -m venv .venv
   ```

2. Activate it:

   ```text
   # Windows (PowerShell) - the one I used
   .venv\Scripts\Activate.ps1

   # macOS and Linux
   source .venv/bin/activate
   ```

3. Install the packages:

   ```text
   pip install -r requirements.txt
   ```

4. Open the notebook and select the `.venv` environment as its kernel:
   - **Visual Studio Code *(used for this project)*:** click *Select Kernel*, and choose `.venv`.

5. Run `BreastMNIST_analysis.ipynb` from top to bottom, to firstly download the BreastMNIST dataset into a `data` folder, and be able to move forward with the analysis


## Notes and versions

### Environment used

| Item | Version or detail |
|---|---|
| Operating system | Windows `<fill in, from the notebook output>` |
| Python | 3.12 `<fill in the full version, for example 3.12.x>` |
| Visual Studio Code | `<fill in, under Help, then About>` |
| Environment creation | Made with the Command Palette command "Python: Create Environment" (Venv, named `.venv`), which gives the same result as step 1 above |
| Date of setup | 2026-11-10 |

### Package versions

The exact versions are pinned in `requirements.txt`. They were taken from the working environment after the first successful run:

| Package | Version |
|---|---|
| torch | `<fill in>` |
| medmnist | `<fill in>` |
| numpy | `<fill in>` |
| pandas | `<fill in>` |
| scikit-learn | `<fill in>` |
| matplotlib | `<fill in>` |
| ipykernel | `<fill in>` |

### Notes and decisions

- Images that show the armpit region are kept in the analysis, because this region can show signs of breast cancer.
- Duplicate/Mislabeled images were handled xxx way
- `<add later: result of the check for copied images between the training, validation and test splits>`
- `<add later: how images with a biopsy needle, a doubtful label, or a place in two label groups were handled>`