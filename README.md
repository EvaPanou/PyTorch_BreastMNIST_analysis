# Breast ultrasound classifier with PyTorch

A small PyTorch project on biomedical image data:

MedMNIST is a collection of standardized, lightweight biomedical image datasets with fixed training, validation and test splits, designed so that results can be compared across studies.<sup>1,2</sup> 

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
| Operating system | Windows 11 Pro, version 10.0.26300 (build 26300) |
| Python | 3.12 |
| Visual Studio Code | `<fill in, under Help, then About>` |
| Environment creation | Made with the Command Palette command "Python: Create Environment" (Venv, named `.venv`), which gives the same result as step 1 above |
| Date of setup | 2026-11-10 |

### Package versions

The exact versions are pinned in `requirements.txt`. They were taken from the working environment after the first successful run:

| Package | Version |
|---|---|
| torch | 2.15.0 (CPU build) |
| medmnist | 3.0.2 |
| numpy | 2.5.4 |
| pandas | 3.1.1 |
| scikit-learn | 1.9.1 |
| matplotlib | 3.11.2 |
| ipykernel | 7.4.0 |

### Notes and decisions

- Images that show the armpit region are kept in the analysis, because this region can show signs of breast cancer.
- Duplicate/Mislabeled images were handled xxx way
- `<add later: result of the check for copied images between the training, validation and test splits>`
- `<add later: how images with a biopsy needle, a doubtful label, or a place in two label groups were handled>`

## References

1. Yang J, Shi R, Wei D, et al. MedMNIST v2—a large-scale lightweight benchmark for 2D and 3D biomedical image classification. *Sci Data*. 2023;10(1):41. doi:10.1038/s41597-022-01721-8
2. Yang J, Shi R, Ni B. MedMNIST classification decathlon: a lightweight AutoML benchmark for medical image analysis. In: *IEEE 18th International Symposium on Biomedical Imaging (ISBI)*. IEEE; 2021:191-195. doi:10.1109/ISBI48211.2021.9434062
3. Al-Dhabyani W, Gomaa M, Khaled H, Fahmy A. Dataset of breast ultrasound images. *Data Brief*. 2020;28:104863. doi:10.1016/j.dib.2019.104863
4. MedMNIST. MedMNIST: 18x standardized datasets for 2D and 3D biomedical image classification. GitHub. Accessed `<fill in the date you downloaded the metadata file>`. https://github.com/MedMNIST/MedMNIST
5. Pawłowska A, Karwat P, Żołek N. Letter to the Editor. Re: "Dataset of breast ultrasound images by W. Al-Dhabyani, M. Gomaa, H. Khaled & A. Fahmy, Data in Brief, 2020, 28, 104863." *Data Brief*. 2023;48:109247. doi:10.1016/j.dib.2023.109247
6. Pawlowska A, Karwat P, Zolek N. Supplementary files DIB-D-23-00350. Dataset. Mendeley Data; 2023. doi:10.17632/k8t3gnx9h6.1
7. Paszke A, Gross S, Massa F, et al. PyTorch: an imperative style, high-performance deep learning library. *arXiv*. Preprint posted online December 3, 2019. doi:10.48550/arXiv.1912.01703