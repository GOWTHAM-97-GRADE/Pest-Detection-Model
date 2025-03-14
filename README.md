# Pest Detection Model

## Overview
This project focuses on **image classification** for detecting common agricultural pests using a deep learning model based on **InceptionV3**. The model is trained on a dataset of 5,494 images across **12 pest categories**.

## Dataset Information
### General Information
- **Type:** Agricultural Pest Image Dataset
- **Total Images:** 5,494
- **Format:** JPEG/PNG
- **Source:** Kaggle
- **Application:** Pest detection in agricultural settings

### Meta Information
| Attribute | Details |
|-----------|---------|
| Dimensions | 2D |
| Modality | Natural Images |
| Task Type | Classification |
| Number of Categories | 12 |
| Data Volume | 5,494 images |
| File Format | JPEG/PNG |

### Image Resolution
- **Minimum:** Variable
- **Median:** 300px (max width or height)
- **Maximum:** 300px (max width or height)

### Label Information
| # | Pest Type | Number of Images |
|---|----------|-----------------|
| 1 | Ants | 499 |
| 2 | Bees | 500 |
| 3 | Beetles | 416 |
| 4 | Caterpillars | 434 |
| 5 | Earthworms | 323 |
| 6 | Earwigs | 466 |
| 7 | Grasshoppers | 485 |
| 8 | Moths | 497 |
| 9 | Slugs | 381 |
| 10 | Snails | 500 |
| 11 | Wasps | 498 |
| 12 | Weevils | 485 |

### Pest Descriptions
- **Ants:** Can be both beneficial and harmful to crops.
- **Bees:** Essential pollinators but some species may be pests.
- **Beetles:** Damage crops by feeding on leaves, stems, or roots.
- **Caterpillars:** Larval stage of butterflies/moths; known for defoliating plants.
- **Earthworms:** Beneficial for soil aeration but may disrupt root structures.
- **Earwigs:** Nocturnal pests that feed on soft plant tissues.
- **Grasshoppers:** Cause significant foliage damage.
- **Moths:** Some larvae species are agricultural pests.
- **Slugs & Snails:** Soft-bodied pests that consume plant leaves and stems.
- **Wasps:** Some species prey on crops or disrupt farming.
- **Weevils:** Target stored grains and agricultural produce.

## Model Architecture
The **InceptionV3** model is used for classification, implemented using **PyTorch**. It consists of:
- Initial convolutional layers for feature extraction
- Two **Inception Modules** for multi-scale feature learning
- Fully connected layers for classification
- **Softmax output** for 12 pest categories

## Training & Evaluation
### Training Details
- **Dataset Split:**
  - Train: 80%
  - Validation: 10%
  - Test: 10%
- **Loss Function:** CrossEntropyLoss
- **Optimizer:** Adam (learning rate: 0.001)
- **Batch Size:** 32
- **Epochs:** 30

### Validation & Testing
- The model is validated after each epoch.
- **Accuracy & Loss** are tracked.
- Final testing is done on unseen data.

## File Structure
```
Project_ML/
|-- Pest/
|   |-- pestDataset/  # Contains training images
|   |-- Output/
|       |-- pth/  # Model checkpoints
|   |-- main.py  # Training & testing script
```

## Model Checkpoints
- **Checkpoints saved at:** `/content/drive/MyDrive/Project_ML/Pest/Output/pth`
- The model is loaded from the latest checkpoint (`inception_v3_70.pth`) if available.

## Classification Example
To classify a single image, run:
```python
image_path = '/content/drive/MyDrive/Project_ML/Pest/pestDataset/snail/snail (116).jpg'
true_label = 'snail'  # Optional
classify_image(image_path, model, device, train_dataset.dataset.classes, true_label)
```
This will display the image along with the predicted class label.

## Authors & Source
- **Dataset:** Kaggle (https://www.kaggle.com/datasets/vencerlanz09/agricultural-pests-image-dataset)
- **Project:** Open-source research for pest detection using deep learning.

## Future Enhancements
- Improve accuracy with **transfer learning** and **data augmentation**.
- Optimize for **edge devices** for real-time agricultural monitoring.
- Deploy as a **web or mobile application** for practical usage.

---
This project aims to enhance **pest detection** in agriculture using AI, providing farmers with a powerful tool to protect crops. 🌱🚜

