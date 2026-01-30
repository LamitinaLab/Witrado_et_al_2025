Project code for analysis of ASH GCaMP6s data in Witrado et al, 2025.

## Workflow (local VS Code)
- Place raw CSVs in `data/raw`.
- Update settings in `config.yaml` (paths, columns, frame rate, stimulus windows, and plot outputs).
- Run `01_data_wrangling.ipynb` to combine ROI CSVs into a single processed file (defaults to columns 3 and 7) saved in `data/processed/combined_output.csv`.
- Run `02_data_analysis.ipynb` to plot % dF/F0 traces, compute stimulus-window peaks, and export plots/tables to `data/processed`.

Notes:
- Use the `Python (ash-calcium)` kernel for the notebooks.
- All notebook settings are read from `config.yaml`.
- Use `analysis.stim_windows_s` for multiple stimulus periods; the first window is used for peak extraction.
