The scripts (Seg_Eval_LISA_2025_BG.py and Seg_Eval_LISA_2025_hippo.py) evaluate segmentation (basal ganglia and hipocampus) accuracy between predicted and ground truth NIfTI masks using standard metrics (Dice, Hausdorff, ASSD, RVE). 
It supports multi-label inputs (e.g., left/right hippocampus) and automatically matches filenames based on similarity. 
Outputs include a CSV with per-scan scores and a JSON summary of overall performance.
There are some examples in the related folders to run the code.

Inputs:

Folder of ground truth masks

Folder of predicted masks

Outputs:

CSV and JSON files with evaluation metrics

Dependencies:

numpy, pandas, SimpleITK, surface-distance

Run it via command line using --gt_dir, --pred_dir, and --output.