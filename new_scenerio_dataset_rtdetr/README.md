# New Scenario Dataset for RT-DETR

This dataset is structured and formatted for training object detection models, particularly intended for RT-DETR (Real-Time DEtection TRansformer) within the NVIDIA TAO Toolkit or similar frameworks. It follows the standard COCO (Common Objects in Context) dataset format.

## Dataset Structure

The dataset directory is organized as follows:

```
new_scenerio_dataset_rtdetr/
│
├── annotations/
│   ├── instances_train.json    # COCO-formatted annotations for the training set
│   └── instances_val.json      # COCO-formatted annotations for the validation set
│
├── train/
│   └── images/                 # Directory containing all training images
│
├── val/
│   └── images/                 # Directory containing all validation images
│
└── classes.txt                 # A plain text file listing all class names
```

## Dataset Format

### Annotations
The annotations are provided in standard **COCO JSON format**. 
- `instances_train.json`: Contains metadata, categories, image paths, and bounding box annotations for the training dataset.
- `instances_val.json`: Contains metadata, categories, image paths, and bounding box annotations for the validation dataset.

### Classes
The dataset includes the following **3 classes**, as defined in `classes.txt` and the `categories` section of the JSON annotation files:

1. `Person` (ID: 0)
2. `Pallet` (ID: 1)
3. `Forklift` (ID: 2)

### Images
- The images are divided into `train` and `val` splits.
- Inside both `train/` and `val/` directories, the actual image files are stored within an `images/` subdirectory.

## Usage

When configuring a training pipeline (e.g., TAO Toolkit for RT-DETR), you can map the paths to these directories and files:
- **Train Images Directory**: `train/images/`
- **Train Annotations File**: `annotations/instances_train.json`
- **Val Images Directory**: `val/images/`
- **Val Annotations File**: `annotations/instances_val.json`
