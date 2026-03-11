These train/val/test split files define the fixed, reproducible dataset partition used in our IDSC2026 Brugada-HUCA project.
Each CSV contains a single column: patient_id.
We first created an index table from the official metadata.csv, saved as results/data_summary.csv (patient_id and brugada label, where 1=Brugada and 0=Normal).
We then shuffled all subjects with a fixed seed (random_state=42) and split them by ratio 70%/15%/15% into train.csv, val.csv, and test.csv.
The three splits are non-overlapping and together cover all subjects.
In Kaggle, the ECG records are located under /kaggle/input/datasets/chanceyguo/idsc2026-brugada-huca-raw, stored as ROOT/files/files/<patient_id>/<patient_id>.hea and .dat.
