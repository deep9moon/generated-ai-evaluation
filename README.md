# MSc Individual Project: Evaluating Cultural Fidelity in AI-Generated Music

This repository contains all code and evaluation scripts for my MSc project, which investigates the cultural alignment of AI-generated music, particularly focusing on traditional Chinese prompts and real audio reconstruction using Stable Audio Small.

---

## 📁 Directory Structure

### `Colab_Generate/`
- Includes the Colab notebook (`Stable_Audio_Generate.ipynb`) used for audio reconstruction and generation using Stable Audio Small.
- The `stable-audio-tools-main/` subfolder contains the cloned official codebase for generation.
### ⚠️ Note on Google Drive Paths

Some Colab notebooks use `drive.mount()` to access model checkpoints stored in the author's Google Drive.  
These paths (e.g., `/content/drive/MyDrive/...`) are private and will not work outside the original environment.

To reproduce results:
- Either comment out `drive.mount()` and upload checkpoint files directly in Colab, or
- Download checkpoints from the `checkpoints/` folder in this repository and update the path accordingly.

### `evaluation/`
- Contains evaluation notebooks for computing MCD and MOS results:
  - `FineTune_MCD.ipynb`: Compares pre/post fine-tuned reconstructions.
  - `Murekavsudio_MCD_MOS.ipynb`: Evaluates Mureka and Udio outputs.
  - `UdioVsMureka_*`: Cross-model comparison notebooks.
- `data/`: Includes reference/real audio features.
- `outputs/`: Stores plots, CSVs, and evaluation results.

### `Kaggle_FineTune/`
- Contains the notebook used for fine-tuning Stable Audio Small on Kaggle (`finetune.ipynb`).
- `model_config.json` and `dataset_config.json`: Configuration files.
- `checkpoints/`: Includes selected `.ckpt` files (e.g., `epoch=99-step=800.ckpt`) used for evaluation.
- `stable-audio-tools-main/`: Training codebase.

---

## 🧪 How to Reproduce

1. **Fine-Tuning** (on Kaggle GPU):
   - Run `Kaggle_FineTune/finetune.ipynb`.
   - Adjust paths and config files as needed.

2. **Audio Generation**:
   - Use `Colab_Generate/Stable_Audio_Generate.ipynb` to load and evaluate reconstruction from different checkpoints.

3. **Evaluation**:
   - Run notebooks under `evaluation/` to reproduce MCD/MOS results and plots used in the dissertation.

---

## 📝 Notes

- All training and evaluation were performed across Colab, Kaggle, and local Jupyter environments.
- Some paths may need manual adjustment depending on the execution platform.
- Original real audio training data is not included due to licensing and storage constraints.

---

## 👩‍💻 Author

**Jiuyue Zhang**  
MSc Urban Informatics, King’s College London  
Email: [jiuyue.zhang@kcl.ac.uk]