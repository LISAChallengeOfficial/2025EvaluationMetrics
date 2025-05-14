README - How to Run the QC Evaluation Script

This script evaluates predicted quality control (QC) labels for MRI images by comparing them to a ground truth file. It computes performance metrics like F1 score, accuracy, precision, and recall.

How to Run the Script:
----------------------
In the terminal, run the script using:

    python Evaluation_QA.py

By default, it will look for the following files in the same folder:

- predicted_output.csv
- LISA_LF_QC_goldstandard.csv

To use custom file names, run:

    python Evaluation_QA.py --predictions_file your_predictions.csv --goldstandard_file your_groundtruth.csv --output your_results.json

Input Files:
------------
1. Prediction File (e.g., predicted_output.csv):
   - Must be a CSV file with a "Subject ID" column.
   - Should contain these QC category columns:
     - Noise
     - Zipper
     - Positioning
     - Banding
     - Motion
     - Contrast
     - Distortion
   - Values in these columns must be class labels: 0, 1, or 2.

2. Ground Truth File (e.g., LISA_LF_QC_goldstandard.csv):
   - Must also be a CSV file with a "Subject ID" column.
   - If subject IDs include ".nii.gz", this will be removed automatically.
   - Must contain the same QC category columns with labels 0, 1, or 2.

Output Files:
-------------
1. results.json:
   - A JSON file containing the calculated evaluation metrics.

2. all_scores_qc.csv:
   - A CSV file with the same metrics, readable in Excel.

Metrics Computed:
-----------------
The script calculates the following metrics:
- F1 Score
- F2 Score
- Precision
- Recall
- Accuracy

Each metric is calculated using:
- Micro average
- Macro average
- Weighted average

Other Notes:
------------
- Subject IDs must match in both files.
- Only matching rows are evaluated.
- Make sure column names are consistent across files.

