## welding-void-defect-dnn
Welding Void Defect Prediction — DNN

Professional project that builds a Keras Sequential DNN to predict welding void (void / void-free)
from welding process parameters.

This repo preserves your original dataset file (`data/Welding_process_parameters.csv`) exactly as provided.
The preprocessing step automatically detects the first numeric row and builds a clean modeling table from it.

## Features
- Robust ingestion of the supplied CSV (keeps units row intact)
- Automatic detection of numeric data start row
- Text cleaning (removes unit markers such as `*`, commas, non-numeric characters)
- Feature selection & scaling
- Keras Sequential DNN (train / validate / test)
- Confusion matrix, classification report and ROC curve saved to `outputs/`
- Model saved to `saved_model/welding_dnn.h5`
- CLI-friendly: single script `model.py`

## Files
- `model.py` — full pipeline: load → preprocess → train → evaluate → save
- `data/Welding_process_parameters.csv` — keep your original file here (already present)
- `outputs/` — plots & reports saved here by the script
- `saved_model/welding_dnn.h5` — trained model (created after running)
- `requirements.txt` — Python dependencies

## How to run (recommended)
1. Create virtual environment and install requirements:
   ```bash
   python -m venv venv
   source venv/bin/activate      # Windows: venv\Scripts\activate
   pip install -r requirements.txt

2. Put your original CSV at:
welding-void-defect-dnn/data/Welding_process_parameters.csv
(do not edit the file — the code keeps it intact)

3. Run training:
python model.py --data data/Welding_process_parameters.csv --epochs 80 --batch 32

4. After run you will find:outputs/training_history.png — loss/accuracy curves.

                           outputs/confusion_matrix.png — confusion matrix.

                           outputs/roc_curve.png — ROC curve.

                           outputs/classification_report.txt — precision/recall/F1.

                           saved_model/welding_dnn.h5 — trained model.
   

## Notes & tips

The script auto-detects where numeric rows start (so the units row and any header rows remain unchanged).

If you'd like a reproducible split, pass --seed argument.

To tune architecture, edit the build_model() function (currently a simple, robust DNN).

## requirements
pandas>=1.3
numpy>=1.21
matplotlib>=3.4
seaborn>=0.11
scikit-learn>=1.0
tensorflow>=2.9
