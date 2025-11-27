## What I ran

Loaded your CSV without editing it (units/header row preserved).

Auto-detected the numeric data start row and parsed numeric columns.

Cleaned common non-numeric markers (stars *, commas, units).

Built features and target (Void-1 void free-0) and removed rows with missing numbers.

Scaled features and trained a DNN-like classifier:

TensorFlow was not available in this environment, so I used scikit-learn's MLPClassifier as a robust fallback (architecturally similar: 64-64-32).

Evaluated model on a held-out test set.

## Key results (test-set)

Accuracy: 86.36%

Precision / Recall / F1 (per class) included in the saved classification_report.txt.

AUC: 0.966 (very good separation on test set)
