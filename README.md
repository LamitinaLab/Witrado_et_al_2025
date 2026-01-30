Project code for analysis of ASH GCaMP6s data in Witrado et al., 2025.

## What you need
- Python 3.11+
- Input data (not stored in this repo). You must provide the raw CSVs under the paths specified in `config.yaml`.

## Setup
1. Create and activate a Python environment.
2. Install dependencies:
	- `pip install -r requirements.txt`

## Data layout
Place raw CSVs under the folder specified by `paths.raw_dir` in `config.yaml` (default: `data/raw`).
Use one subfolder per genotype (e.g., `data/raw/WT`, `data/raw/dr206`, `data/raw/dr206_dr180`).

Each raw CSV should contain the Mean1 and Mean2 columns expected by the pipeline.

## Configure the analysis
Edit `config.yaml` to set:
- `paths.*` (raw and processed directories)
- `wrangling.columns_to_extract` (Mean1/Mean2 column indices)
- `analysis.frame_rate_hz`
- `analysis.stim_window_s` or `analysis.stim_windows_s`
- `analysis.genotypes` and `analysis.palette`

## Run the notebooks
Run in order:
1. `01_data_wrangling.ipynb`
	- Combines per-genotype raw CSVs into processed files in `paths.combined_data_dir`.
2. `02_data_analysis.ipynb`
	- Computes % ΔF/F0 (background subtraction → F0 normalization → bleaching correction).
	- Generates mean traces, peak stats, and heatmaps.
	- Writes outputs to `paths.figure_data_dir`, `paths.figure_statistics_dir`, and `paths.figures_dir`.

## Notes
- All notebook parameters are read from `config.yaml`.
- If you add multiple stimulus windows in `analysis.stim_windows_s`, the first window is used for peak extraction.
