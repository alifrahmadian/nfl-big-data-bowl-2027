# Local datasets

Extract original Kaggle competition files into `raw/`.

Write derived datasets into `processed/` when preprocessing is introduced.

Both directories are ignored by Git except for their empty directory placeholders. The repository contains no competition data. The notebook recursively lists CSV and Parquet files, but its initial sample loader reads CSV only.
