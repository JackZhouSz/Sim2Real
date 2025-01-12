
# From Sim-to-Real: Toward General Event-based Low-Light Frame Interpolation with Per-scene Optimization

[Ziran Zhang](https://naturezhanghn.github.io)<sup>1,2</sup>, 
[Yongrui Ma](https://scholar.google.com/citations?user=JwQLEocAAAAJ&hl=en)<sup>3,2</sup>, 
[Yueting Chen](https://scholar.google.com/citations?user=gS-0tfAAAAAJ&hl=en)<sup>1</sup>, 
Feng Zhang<sup>2</sup>, 
[Jinwei Gu](https://www.gujinwei.org)<sup>3</sup>, 
[Tianfan Xue](https://tianfan.info)<sup>3</sup>, 
[Shi Guo](https://guoshi28.github.io)<sup>2</sup>

<sup>1</sup> Zhejiang University, <sup>2</sup> Shanghai AI Laboratory, <sup>3</sup> The Chinese University of Hong Kong

[🌐 Project Page](https://openimaginglab.github.io/Sim2Real/) | [🎥 Video](https://www.youtube.com/watch?v=PiYEh_zcG88) | [📄 Paper](https://arxiv.org/pdf/2406.08090) | [📊 Data](https://opendatalab.com/ziranzhang/EVFI-LL) | [🛠️ Weights](https://drive.google.com/file/d/1KjFf3vgxhpS6-RnrYM5ctOUqXVEocvzo/view?usp=sharing) | [🔖 PPT](https://github.com/OpenImagingLab/Sim2Real/blob/main/PPT.pdf)

---

## 🔔 Overview

This repository hosts the implementation of **"From Sim-to-Real: Toward General Event-based Low-Light Frame Interpolation with Per-scene Optimization"** (SIGGRAPH Asia 2024). Our approach leverages **event cameras** and enhances **Video Frame Interpolation (VFI)** in **low-light conditions** via a **per-scene optimization** strategy. This method adapts the model to specific lighting and camera settings, solving issues like trailing artifacts and signal degradation common in low-light environments.

![Visual Comparison](Sim2Real_code/image.png)

---
## 🔑 Key Features

- **Per-Scene Optimization**: Fine-tunes a pre-trained model for each scene, significantly improving interpolation results in varied lighting conditions.
- **Low-Light Event Correction**: Effectively mitigates event-based signal latency and noise under low-light conditions.
- **EVFI-LL Dataset**: Provides challenging RGB+Event sequences captured in low-light environments for benchmarking.

---

## 🚀 Quick Start: Per-Scene Optimization

Follow these steps to apply per-scene optimization with pre-trained models:

### 1. Clone the repository:

```bash
git clone https://github.com/OpenImagingLab/Sim2Real.git
cd Sim2Real/Sim2Real_code
```

### 2. Download and place the required weights:

- **Main model weights**: Place in `pretrained_weights/`
- **DISTS loss function weights**: Place in `losses/DISTS/weights/`

[Download Weights Here](https://drive.google.com/file/d/1KjFf3vgxhpS6-RnrYM5ctOUqXVEocvzo/view?usp=sharing)

### 3. Install dependencies:

```bash
pip install -r requirements.txt
```

### 4. Run per-scene optimization:

```bash
bash perscene.sh
```

This will fine-tune the pre-trained model on specific scenes, performing frame interpolation optimized for each setting.

---

## 🛠️ Optional: Pretraining the Model

To pretrain the model from scratch using simulated data:

1. **Pretrain the model**:

```bash
bash pretrain.sh
```

2. After pretraining, proceed with **per-scene optimization** as described above.

---

## 📂 Directory Structure

- `dataset/`: Utilities for dataset preparation and loading.
- `losses/`: Custom loss functions and weights for training.
- `models/`: Neural network models for Sim2Real frame interpolation tasks.
- `params/`: Configuration files for training and evaluation.
- `tools/`: Scripts for preprocessing and postprocessing.
- `pretrained_weights/`: Directory for storing pre-trained models.
- `run_network.py`: Main script for training and evaluation.
- `pretrain.sh`: Script for model pretraining.
- `perscene.sh`: Script for per-scene optimization.
- `requirements.txt`: Required Python dependencies.

---

## 📊 EVFI-LL Dataset

The **EVFI-LL** dataset includes RGB+Event sequences captured under low-light conditions, offering a challenging benchmark for evaluating event-based VFI performance. Download and place the dataset in the `dataset/` directory.

[Download Dataset Here](https://opendatalab.com/ziranzhang/EVFI-LL)

---

## 📜 License Information
The code in this repository is licensed under the [MIT License](LICENSE).

---

## 📝 Citation

If you find this work helpful in your research, please cite:

```bibtex
@article{zhang2024sim,
  title={From Sim-to-Real: Toward General Event-based Low-light Frame Interpolation with Per-scene Optimization},
  author={Zhang, Ziran and Ma, Yongrui and Chen, Yueting and Zhang, Feng and Gu, Jinwei and Xue, Tianfan and Guo, Shi},
  journal={arXiv preprint arXiv:2406.08090},
  year={2024}
}
```

---

## 🙏 Acknowledgements

This project builds upon the exceptional work of **[TimeLens-XL](https://github.com/OpenImagingLab/TimeLens-XL)**. We extend our sincere thanks to the original authors for their outstanding contributions.
