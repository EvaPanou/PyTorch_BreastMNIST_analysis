# Breast ultrasound classifier with PyTorch

**A small PyTorch project on biomedical image data:**

MedMNIST is a collection of standardized, lightweight biomedical image datasets with fixed training, validation and test splits, designed so that results can be compared across studies<sup>1,2</sup>. 

This project trains a *small convolutional neural network (CNN)* to classify breast ultrasound images as normal or benign versus malignant. It uses `BreastMNIST`, the **breast ultrasound dataset** from the `MedMNIST collection`, in its 28 by 28 pixel version. The model is evaluated on the standard test split using the area under the receiver operating characteristic curve, averaged over several random seeds.

A `convolutional neural network (CNN)` is a type of neural network designed for pictures. Instead of looking at every pixel on its own, it slides small windows, called filters, across the picture and measures how strongly each small region matches a pattern, such as an edge or a bright or dark area. The filters' values are learned during training, so the network discovers patterns on its own. As a result, early layers pick up simple patterns, later layers combine them into more complex ones, and pooling steps shrink the picture so that the network keeps the strongest responses and needs fewer numbers, while, at the end, the remaining values are combined into a single score per picture, which is turned into a probability<sup>3</sup>. 

`PyTorch` is a machine learning library for Python. Using it, you can write a model as ordinary Python code, so it can be run fast and effectively, line by line, and debugged like any other program. The library carries out the calculations on tensors and works out the gradients that training needs automatically<sup>4</sup>.

## Repository structure and data sources

| Path | What it is | Source and how it was obtained |
|---|---|---|
| `README.md` | Description, setup, notes and references | |
| `requirements.txt` | Pinned package versions | |
| `.gitignore` | Files that Git should not track | |
| `BreastMNIST_analysis.ipynb` | The analysis notebook | |
| `metadata/breastmnist_split_info.csv` | Table giving each image's split, its position in that split, and its name in the original dataset | MedMNIST GitHub repository<sup>5</sup>, link behind "here" in the "Data Files" section of its README. Officially provided CSV file for BreastMNIST. Downloaded manually from [here](https://drive.google.com/drive/folders/1A_99qH_c-J0p_SatwSiaP_i1CvLUOzVo) |
| `data/breastmnist.npz` | The image and label arrays | Downloaded automatically from Zenodo, in the notebook, by the `medmnist` [package](https://medmnist.com/). 

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

## RESULTS & CONCLUSIONS



## Documentation and versions

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
- Two images out of the 780 in the arrays, disagree with the metadata file, and are misaligned on the labels nd benign vs malignant categories

## References

1. Yang J, Shi R, Wei D, et al. MedMNIST v2—a large-scale lightweight benchmark for 2D and 3D biomedical image classification. *Sci Data*. 2023;10(1):41. doi:10.1038/s41597-022-01721-8
2. Yang J, Shi R, Ni B. MedMNIST classification decathlon: a lightweight AutoML benchmark for medical image analysis. In: *IEEE 18th International Symposium on Biomedical Imaging (ISBI)*. IEEE; 2021:191-195. doi:10.1109/ISBI48211.2021.9434062
3. Krizhevsky A, Sutskever I, Hinton GE. ImageNet classification with deep convolutional neural networks. Commun ACM. 2017;60(6):84-90. doi:10.1145/3065386
4. Paszke A, Gross S, Massa F, et al. PyTorch: an imperative style, high-performance deep learning library. In: Wallach H, Larochelle H, Beygelzimer A, d’Alché-Buc F, Fox E, Garnett R, eds. Advances in Neural Information Processing Systems 32. Curran Associates, Inc.; 2019:8024-8035.
5. MedMNIST. MedMNIST: 18x standardized datasets for 2D and 3D biomedical image classification. GitHub. https://github.com/MedMNIST/MedMNIST