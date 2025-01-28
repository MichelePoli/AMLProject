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
| DeepLabV2      **B4**     | LoveDA-urban     | 20         | 0.3217          |16.42 ms       |  11.535G       | 62.231M        |
| DeepLabV2      **B16**     | LoveDA-urban     | 20         |0.3342        | 13.42 ms        |  11.535G       | 62.231M        |
| PIDNet (Real-time) **B2** | LoveDA-urban     | 20         | 0.3590         | 17.43 ms        | 6.346G      | 7.718M       |
| PIDNet (Real-time) **B16** | LoveDA-urban     | 20         | 0.4867         | 288.70 ms        | 6.346G      | 7.718M       |


---

### Step 3: Domain Shift Analysis


| **Source → Target** | **Model**         | **Augmentation**   | **mIoU (%)** | **Road** | **Building** | **Water** | **Background** | **Barren** | **Forest** | **Agricultural** |
|---------------------|-------------------|--------------------|--------------|----------|--------------|-----------|----------------|------------|------------|------------------|
| Urban → Rural       | PIDNet           | x               | 0.2398       | 0.1941      | 0.2424          | 0.3546       | 0.5024             | 0.0695         | 0.1023         | 0.3182               |
| Urban → Rural       | PIDNet           | Aug. 1             | 0.2991          |  0.2875      | 0.3988          | 0.3671       | 0.5433            | 0.1118        | 0.1537        | 0.4357              |
| Urban → Rural       | PIDNet           | Aug. 2             | 0.3080          | 0.3164      | 0.3849          | 0.3866       |  0.5353            | 0.1403        | 0.1604        | 0.4332              |
| Urban → Rural       | PIDNet           | Aug. 1 + Aug. 2    | 0.2935          | 0.2883      | 0.3927          | 0.3681       | 0.5369            | 0.1363        | 0.1826        | 0.4266              |



---

### Step 4: Domain Adaptation Techniques
#### 4a) Adversarial Approach


| **Source → Target** | **Model** | **Method**      | **mIoU (%)** | **Road** | **Building** | **Water** | **Background** | **Barren** | **Forest** | **Agricultural** |
|---------------------|-----------|-----------------|--------------|----------|--------------|-----------|----------------|------------|------------|------------------|
| Urban → Rural       | PIDNet    | Discriminator   | 0.3059        | 0.5009    | 0.4833        | 0.7845    | 0.5446         | 	0.2517      | 0.5264      | 0.4077           |



#### 4b) Image-to-Image Approach
| **Source → Target** | **Model**         | **Method**      | **mIoU (%)** |**Road** | **Building** | **Water** | **Background** | **Barren** | **Forest** | **Agricultural** |
|---------------------|-----------|-----------------|--------------|----------|--------------|-----------|----------------|------------|------------|------------------|
| Urban → Rural       | PIDNet           | DACS            | 0.3063        | 0.3032   | 0.3935        | 0.4280     |0.5598          | 0.1615       | 0.0550      | 0.4449           |

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
