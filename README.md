# Histopathology Datasets

![GitHub last commit](https://img.shields.io/github/last-commit/MindLab-DP/Datasets?style=flat)

![GitHub](https://img.shields.io/github/license/MindLab-DP/Datasets?style=flat)

This repository contains useful information of the most recent datasets in Digital Pathology.

## Datasets


| Name        | Size      | Link      | Cancer Type | Image Type  |
| ----------- |-----------|-----------|-----------  |-----------  |
| PANDA       |    `383 GB`       | Kaggle API: `kaggle competitions download -c prostate-cancer-grade-assessment` or [Kaggle](https://www.kaggle.com/c/prostate-cancer-grade-assessment/data) | Prostate Cancer | WSI and Masks|
| CAMELYON17  |  `600 GB `        | [Google Drive](https://drive.google.com/drive/folders/0BzsdkU4jWx9BaXVHSXRJTnpLZU0?resourcekey=0-tyfGzeoOMAWlP_ogPt_4pw) or [Baidu Pan](https://pan.baidu.com/s/1mIzSewImtEisclPtTHGSyw#list/path=%2F) | Breast Cancer | WSI |
| TCGA-PRAD   | `~600 GB` | [NCI GDC Portal](https://portal.gdc.cancer.gov/projects/TCGA-PRAD) | Prostate Cancer | WSI, WXS, RNA-Seq, miRNA-Seq, ATAC-Seq, Genotyping Array | 
| Breast Cancer Semantic Segmentation | `NA` | [GitHub](https://github.com/PathologyDataScience/CrowdsourcingDataset-Amgadetal2019) | Breast Cancer | ROI/WSI and Masks |
| Gleason 2019 | `1.5 GB` | [Grand Challenge](https://gleason2019.grand-challenge.org/Register/) | Prostate Cancer | TMA and masks |

### PANDA (Prostate cANcer graDe Assessment)

11,000 WSI with Gleason/ISUP labels and segmentation masks

The labels are imperfect.

*Files*

\[train/test\].csv

`image_id`: ID code for the image.

`data_provider`: The name of the institution that provided the data. Both the Karolinska Institute and Radboud University Medical Center contributed data. They used different scanners with slightly different maximum microscope resolutions and worked with different pathologists for labeling their images.

`isup_grade`: The target variable. The severity of the cancer on a 0-5 scale.

`gleason_score`: An alternate cancer severity rating system with more levels than the ISUP scale.

\[train/test\]_images: The images. Each is a large multi-level tiff file. Some of the training set images have stray pen marks on them.

`train_label_masks`: Segmentation masks showing which parts of the image led to the ISUP grade. Not all training images have label masks, and there may be false positives or false negatives in the label masks for a variety of reasons. These masks are provided to assist with the development of strategies for selecting the most useful subsamples of the images. The mask values depend on the data provider:

*Radboud*: Prostate glands are individually labelled. Valid values are:
0: background (non tissue) or unknown
1: stroma (connective tissue, non-epithelium tissue)
2: healthy (benign) epithelium
3: cancerous epithelium (Gleason 3)
4: cancerous epithelium (Gleason 4)
5: cancerous epithelium (Gleason 5)

*Karolinska*: Regions are labelled. Valid values are:
0: background (non tissue) or unknown
1: benign tissue (stroma and epithelium combined)
2: cancerous tissue (stroma and epithelium combined)


### CAMELYON17

The data contains whole-slide images (WSI) of hematoxylin and eosin (H&E) stained lymph node sections.

Depending on the particular data set, ground truth is provided:

* *On a lesion-level*: with detailed annotations of metastases in WSI.
* *On a patient-level*: with a pN-stage label per patient.

All ground truth annotations were carefully prepared under supervision of expert pathologists.

The data set for CAMELYON17 is collected from 5 medical centres in the Netherlands. WSI are TIFF images. Lesion-level annotations are provided as XML files.


### TCGA-PRAD

To-Do

### Breast Cancer Semantic Segmentation

To-Do

### Gleason 2019

Data used in this dataset consists of a set of tissue micro-array (TMA) images. Each TMA image is annotated in detail by several expert pathologists.

![alt text](https://grand-challenge-public-prod.s3.amazonaws.com/i/2020/01/21/f9f06df6.png, "Gleason 2019")

Objective:

* Pixel-level Gleason grade prediction
* Core-level Gleason score prediction

### References:

* Nir G, Hor S, Karimi D, Fazli L, Skinnider BF, Tavassoli P, Turbin D, Villamil CF, Wang G, Wilson RS, Iczkowski KA. Automatic grading of prostate cancer in digitized histopathology images: Learning from multiple experts. Medical image analysis. 2018 Dec 1;50:167-80.

* Karimi D, Nir G, Fazli L, Black PC, Goldenberg L, Salcudean SE. Deep Learning-Based Gleason Grading of Prostate Cancer From Histopathology Images—Role of Multiscale Decision Aggregation and Data Augmentation. IEEE journal of biomedical and health informatics. 2019 Sep 30;24(5):1413-26.

* Geert Litjens, Peter Bandi, Babak Ehteshami Bejnordi, Oscar Geessink, Maschenka Balkenhol, Peter Bult, Altuna Halilovic, Meyke Hermsen, Rob van de Loo, Rob Vogels, Quirine F Manson, Nikolas Stathonikos, Alexi Baidoshvili, Paul van Diest, Carla Wauters, Marcory van Dijk, Jeroen van der Laak. 1399 H&E-stained sentinel lymph node sections of breast cancer patients: the CAMELYON dataset. GigaScience, giy065, DOI: 10.1093/gigascience/giy065

* Babak Ehteshami Bejnordi; Mitko Veta; Paul Johannes van Diest; Bram van Ginneken; Nico Karssemeijer; Geert Litjens; Jeroen A. W. M. van der Laak; and the CAMELYON16 Consortium. Diagnostic Assessment of Deep Learning Algorithms for Detection of Lymph Node Metastases in Women With Breast Cancer. JAMA. 2017;318(22):2199–2210. DOI: 10.1001/jama.2017.14585

* Peter Bandi, Oscar Geessink, Quirine Manson, Marcory van Dijk, Maschenka Balkenhol, Meyke Hermsen, Babak Ehteshami Bejnordi, Byungjae Lee, Kyunghyun Paeng, Aoxiao Zhong, Quanzheng Li, Farhad Ghazvinian Zanjani, Svitlana Zinger, Keisuke Fukuta, Daisuke Komura, Vlado Ovtcharov, Shenghua Cheng, Shaoqun Zeng, Jeppe Thagaard, Anders B. Dahl, Huangjing Lin, Hao Chen, Ludwig Jacobsson, Martin Hedlund, Melih Cetin, Eren Halici, Hunter Jackson, Richard Chen, Fabian Both, Jorg Franke, Heidi Kusters-Vandevelde, Willem Vreuls, Peter Bult, Bram van Ginneken, Jeroen van der Laak, and Geert Litjens. From detection of individual metastases to classification of lymph node status at the patient level: the CAMELYON17 challenge. IEEE-TMI (Early Access) DOI: 10.1109/TMI.2018.2867350

* PANDA Challenge, organizers: Wouter Bulten, Geert Litjens, Hans Pinckaers, Peter Ström, Martin Eklund, Lars Egevad, Henrik Grönberg, Kimmo Kartasalo, Pekka Ruusuvuori, Tomi Häkkinen, Sohier Dane, Maggie Demkin.
