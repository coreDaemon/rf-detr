# RF-DETR Basketball Player Detection

This project fine-tunes the **RF-DETR-Small (RF-DETR-S)** model on a **custom basketball dataset** from [Roboflow](https://app.roboflow.com/coredaemonml/basketball-13eae/1) to detect basketball players and related entities on the court.

## Overview

**RF-DETR (Refined DETR)** is a transformer-based object detection model that improves on standard DETR with better convergence, refined predictions, and stronger generalization — especially in complex visual scenes with occlusions and motion blur.

In this project, we fine-tuned **RF-DETR-S**, a smaller and faster version of the model that offers the best balance of **speed and accuracy**, outperforming larger models like YOLO11-L on the COCO benchmark while maintaining higher inference speed.

---

## Dataset

**Source:** [Roboflow Basketball Dataset](https://app.roboflow.com/coredaemonml/basketball-13eae/1)  
**Classes:**  
1. ball  
2. ball-in-basket  
3. number  
4. player  
5. player-in-possession  
6. player-jump-shot  
7. player-layup-dunk  
8. player-shot-block  
9. referee  
10. rim  

This dataset contains diverse basketball scenes with motion blur, overlaps, and small jersey numbers, making it ideal for training a robust player detection model.

---

## Objective

The primary goal of this fine-tuning project is to **detect basketball players** effectively.  
We mainly use the following classes for player recognition:

- `player`  
- `player-in-possession`  
- `player-jump-shot`  
- `player-layup-dunk`  
- `player-shot-block`  
- `number` (for potential jersey number recognition)

Other classes like `ball`, `rim`, and `referee` are included for future extensions such as:
- Detecting when a basket is made  
- Identifying specific plays or player actions  

---

## Model Details

- **Base Model:** RF-DETR-Small (`rfdetr_small`)
- **Framework:** PyTorch
- **Training Setup:** Fine-tuned on custom basketball dataset using RF-DETR training pipeline.
- **Task:** Object detection (bounding boxes)
- **Purpose:** Player and play recognition in basketball footage.

---

## Performance and Insights

RF-DETR-S demonstrates strong performance on this task, handling:
- **Motion blur** during fast plays  
- **Overlapping players** in tight formations  
- **Small details** like jersey numbers

Its transformer backbone allows it to model spatial relationships between players and objects effectively, making it ideal for sports analysis.

---

## Future Work

- Extend fine-tuning for **player identification** via jersey number recognition.  
- Add post-processing for **event detection** (e.g., shots, dunks, blocks).  
- Integrate with a tracking pipeline for **player movement analysis**.

---

## Reference

This project follows the approach described in the blog post:

> **"Detect Players with RF-DETR"**  
> *The first step is object detection. We use RF-DETR-S because it offers the best balance of speed and accuracy for our task...*  

For more details about RF-DETR and fine-tuning methods, visit the [official RF-DETR GitHub repository](https://github.com/coreDaemon/rf-detr).

---

## License

This project is distributed under the same license as the original RF-DETR repository. Refer to the upstream repository for more details.
