# QoF Call & Recall Master List

A local-first browser tool for NHS GP practices to consolidate QoF (Quality and Outcomes Framework) disease register exports into a single master patient list.

## What It Does

Upload your QoF register exports (CSV or Excel), and the tool will:

- **Auto-detect** NHS Number, Patient Name, and DOB columns
- **Cross-reference** patients across all 14 QoF disease registers
- **Consolidate** into a single master list — one row per patient
- **Prioritise** by condition count (complex patients first)
- **Export** as CSV, Excel, or JSON

## How to Use

1. **Open `index.html`** in any browser (just double-click it)
2. **Upload** your QoF register CSV/Excel files
3. **Assign** each file to its QoF register
4. **Review** auto-detected column mappings
5. **Process** to generate the master list
6. **Export** in your preferred format

No installation. No server. No internet required.

## QoF Registers Supported

Asthma, Atrial Fibrillation, Cancer, CKD, COPD, CHD, Depression, Diabetes, Epilepsy, Heart Failure, Hypertension, Learning Disability, Mental Health, Stroke/TIA

## Data Privacy

- **100% local** — all processing happens in your browser
- **No data leaves your computer** — zero network calls
- **No storage** — refreshing the page clears all data
- **No tracking** — no analytics, no cookies, no telemetry
- Safe for use with NHS patient identifiable data

## Export Formats

| Format | Filename |
|--------|----------|
| CSV | `QoF_Master_List_YYYY-MM-DD.csv` |
| Excel | `QoF_Master_List_YYYY-MM-DD.xlsx` |
| JSON | `QoF_Master_List_YYYY-MM-DD.json` |

## Requirements

- Any modern browser (Chrome, Edge, Firefox, Safari)
- That's it

## License

MIT
