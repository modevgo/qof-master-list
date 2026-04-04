# QoF Call & Recall Master List — Setup Guide

## Option 1: Use Online (Recommended)

1. Open your browser (Chrome, Edge, or Firefox)
2. Go to: **https://modevgo.github.io/qof-master-list/**
3. That's it. Start uploading your QoF register files.

> **Data Privacy:** All processing happens in your browser. No patient data is sent to any server.

---

## Option 2: Run Locally (Offline)

### Step 1 — Download

1. Go to: https://github.com/modevgo/qof-master-list
2. Click the green **"Code"** button
3. Click **"Download ZIP"**
4. Save the ZIP file to your computer

### Step 2 — Extract

1. Find the downloaded file (usually in your Downloads folder)
2. Right-click → **Extract All** (Windows) or double-click (Mac)
3. Open the extracted folder

### Step 3 — Open

1. Find the file called **`index.html`**
2. Double-click it
3. It will open in your default web browser
4. The tool is now ready to use

---

## How to Use

### Step 1 — Upload Files

1. Click **"Upload Files"** or drag and drop your QoF register exports
2. Accepted formats: `.csv` or `.xlsx` (Excel)
3. Upload one file per disease register

### Step 2 — Assign Registers

1. For each uploaded file, select which QoF register it belongs to from the dropdown
2. Available registers:
   - Asthma
   - Atrial Fibrillation
   - Cancer
   - CKD (Chronic Kidney Disease)
   - COPD
   - CHD (Coronary Heart Disease)
   - Depression
   - Diabetes
   - Epilepsy
   - Heart Failure
   - Hypertension
   - Learning Disability
   - Mental Health
   - Stroke/TIA

### Step 3 — Column Mapping

1. The tool automatically detects your column headers
2. It looks for: NHS Number, EMIS Number, Patient Name, Date of Birth
3. If auto-detection is wrong, you can manually select the correct columns
4. Click **"Confirm Mapping"**

### Step 4 — Process

1. Click **"Build Master List"**
2. The tool will:
   - Cross-reference all registers by patient ID
   - Merge duplicate patients into one row
   - List all conditions per patient
   - Count conditions and sort by priority

### Step 5 — Review Results

The results table shows:

| Column | Description |
|--------|-------------|
| Patient ID | NHS or EMIS Number |
| Patient Name | If available in source data |
| Date of Birth | If available in source data |
| Known QoF Conditions | All registers the patient appears on |
| Condition Count | Number of conditions |

**Colour coding:**
- 🔴 **Red** — 4+ conditions (complex patient)
- 🟠 **Amber** — 2-3 conditions (multi-morbidity)
- 🟢 **Green** — 1 condition

**Features:**
- **Search** — Type a name or NHS number to find a patient
- **Filter** — Click the condition filter to show only specific registers
- **Sort** — Click any column header to sort

### Step 6 — Export

Click the export button for your preferred format:
- **CSV** — Opens in Excel, Google Sheets
- **Excel** — Native .xlsx file
- **JSON** — For backup or data transfer

Files are named: `QoF_Master_List_YYYY-MM-DD.csv`

---

## Testing with Sample Data

The tool includes test data to try before using real patient data:

1. Download the repo (see Option 2 above)
2. Open the `test-data/` folder
3. Upload these files:
   - `diabetes_register.csv` (50 patients)
   - `hypertension_register.csv` (40 patients)
   - `ckd_register.csv` (30 patients)
   - `asthma_register.csv` (25 patients)
4. Process and verify the results show overlapping patients with multiple conditions

---

## Troubleshooting

| Problem | Solution |
|---------|----------|
| File won't upload | Check it's .csv or .xlsx format |
| Columns not detected | Use manual column mapping |
| Missing patient names | Names are optional — patients still appear by ID |
| Excel file errors | Try saving as .csv from Excel first |
| Page is blank | Try a different browser (Chrome recommended) |

---

## Data Privacy Statement

- ✅ All processing happens **locally in your browser**
- ✅ **No patient data** is sent to any server
- ✅ **No internet connection** required (if running locally)
- ✅ No data is stored after you close the browser
- ✅ Suitable for NHS patient data handling

---

## System Requirements

- Any modern web browser (Chrome, Edge, Firefox, Safari)
- No installation required
- No admin rights needed
- Works on Windows, Mac, and tablets
