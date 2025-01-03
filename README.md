# AMLProject

# Real-time Domain Adaptation in Semantic Segmentation

## Overview
| **Step**                     | **Description**                                                                                                                                               |
|------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Step 1: Related Works        | Familiarize with the tasks of semantic segmentation, domain adaptation, and real-time semantic segmentation by reading the recommended papers.                |
| Step 2: Testing Networks     | Train and evaluate classic and real-time semantic segmentation networks using LoveDA-urban dataset.                                                          |
| Step 3: Domain Shift         | Train on LoveDA-urban (source) and evaluate on LoveDA-rural (target) to analyze domain shift effects.                                                        |
| Step 4: Domain Adaptation    | Implement adversarial and image-to-image translation techniques to address domain shift.                                                                      |
| Step 5: Extensions           | Explore additional techniques like style transfer, alternative networks, segmentation losses, or hyperparameter tuning to improve domain adaptation.         |

---

## Training and Evaluation Results

### Step 2: Testing Semantic Segmentation Networks
| **Model**           | **Dataset**       | **Training Epochs** | **mIoU (%)** | **Latency** | **FLOPs** | **Params** |
|----------------------|-------------------|------------|--------------|-------------|-----------|------------|
| DeepLabV2           | LoveDA-urban     | 20         | TBD          | TBD         | TBD       | TBD        |
| PIDNet (Real-time)  | LoveDA-urban     | 20         | 0.2665          | 10.16 ms         | 5.960G       | 7.624M        |


## Userfull links
a)  **Classic semantic segmentation network -  Backbone: R101 (pre-trained on ImageNet)**

    - link

b) **Real-time semantic segmentation network - Backbone:  PIDNet-S (pre-trained on ImageNet)**

    - link





---

### Step 3: Domain Shift Analysis
| **Source → Target** | **Model**         | **Augmentation** | **mIoU (%)** | **Road** | **Building** | **Water** | ... |
|---------------------|-------------------|------------------|--------------|----------|--------------|-----------|-----|
| Urban → Rural       | PIDNet           | None             | TBD          | TBD      | TBD          | TBD       |     |
| Urban → Rural       | PIDNet           | Aug. 1           | TBD          | TBD      | TBD          | TBD       |     |
| Urban → Rural       | PIDNet           | Aug. 2           | TBD          | TBD      | TBD          | TBD       |     |
| Urban → Rural       | PIDNet           | Aug. 1 + Aug. 2   | TBD          | TBD      | TBD          | TBD       |     |

---

### Step 4: Domain Adaptation Techniques
#### 4a) Adversarial Approach
| **Source → Target** | **Model**         | **Method**      | **mIoU (%)** | **Road** | **Building** | **Water** | ... |
|---------------------|-------------------|-----------------|--------------|----------|--------------|-----------|-----|
| Urban → Rural       | PIDNet           | Discriminator   | TBD          | TBD      | TBD          | TBD       |     |

#### 4b) Image-to-Image Approach
| **Source → Target** | **Model**         | **Method**      | **mIoU (%)** | **Road** | **Building** | **Water** | ... |
|---------------------|-------------------|-----------------|--------------|----------|--------------|-----------|-----|
| Urban → Rural       | PIDNet           | DACS            | TBD          | TBD      | TBD          | TBD       |     |

---

### Extensions
| **Technique**                | **Description**                                                                                  |
|-------------------------------|--------------------------------------------------------------------------------------------------|
| Style Transfer               | Preprocess source images to match the target domain appearance using a style-transfer model.     |
| Alternative Networks         | Explore other real-time networks such as STDC or PEM.                                           |
| Alternative Loss Functions   | Experiment with different segmentation losses to improve performance.                           |
| Hyperparameter Tuning        | Optimize learning rates, batch sizes, and augmentation probabilities.                           |

---

## Useful Links
- **Dataset**: [LoveDA](https://zenodo.org/records/5706578)
- **Model**: [PIDNet GitHub](https://github.com/XuJiacong/PIDNet)
