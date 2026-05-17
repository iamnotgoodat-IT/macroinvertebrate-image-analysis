# Macroinvertebrate Image Analysis System

A Python desktop application for exploratory data analysis and visualisation
of freshwater macroinvertebrate image data.

Built for Software Technology 1 (4483) — Group Project Assessment 3.

---

## Group Members
- u3320473 — Backend, Data Architect & Bug Tester
- u3218103 — Visualisation & Image Specialist
- u3313879 — GUI Developer & Integrator

---

## Stages Implemented
- Stage 1: Exploratory Data Analysis (EDA)
- Stage 3: Tkinter GUI Deployment

---

## Dataset
This project uses the **Stream Macroinvertebrates** dataset from Kaggle.

Download it here:
https://www.kaggle.com/datasets/kennethtm/stream-macroinvertebrates

After downloading, extract it so the folder structure looks like this:
macro_project_final/
└── data/
└── raw/
├── Asellus sp/
├── Baetidae sp/
├── Elmis sp/
├── Ephemerellidae/
├── Erpobdella sp/
├── Gammarus sp/
├── Hydropsychidae sp/
├── Leptophlebiidae sp/
├── Leuctra sp/
├── Limnius sp/
├── Lymnea sp/
├── Nemoura sp/
├── Oligochaeta sp/
├── Sericostomatidae sp/
├── Sialis sp/
├── Simuliidae sp/
└── Sphaerium sp/

The dataset is not included in this repository due to file size.

---

## Installation

Make sure Python 3.10 or later is installed with the **"Add to PATH"**
option ticked during installation.

Then install all required libraries:

```bash
pip install -r requirements.txt
```

---

## Requirements

All dependencies are listed in `requirements.txt`:
pandas
numpy
opencv-python
matplotlib
Pillow

---

## How to Run

### Option 1 — VS Code (recommended)
1. Open the `macro_project_final` folder in VS Code via **File → Open Folder**
2. Press `F5`
3. Select **Run App** from the dropdown

### Option 2 — Terminal
Navigate to the `macro_project_final` folder first:

```bash
cd "path/to/macro_project_final"
python -m src.App_SecondVer
```

---

## Species Selection

On startup, a **Species Selection** window will appear before the main app loads.

- All 17 species are listed with checkboxes, all selected by default
- Use **Select All** or **Deselect All** for quick selection
- A minimum of **3 species** must be selected before continuing
- Only the selected species are loaded and indexed — this keeps startup fast when you only need a subset of the data

---

## Features

- Species selection dialog on startup for targeted analysis
- Automatically scans and indexes images for selected species
- Summary statistics panel on startup (total images, species count, avg dimensions)
- Species dropdown to browse and view random sample images
- Generates 10 EDA charts and 1 CSV report saved to `outputs/eda/`
- View any generated chart directly inside the app via dropdown
- Species image count table in a scrollable popup window

---

## EDA Outputs

Clicking **Generate EDA Charts** inside the app produces:

| File | Description |
|---|---|
| `class_distribution.png` | Bar chart of images per species |
| `category_pie_chart.png` | Pie chart of species proportions |
| `width_distribution.png` | Histogram of image widths |
| `height_distribution.png` | Histogram of image heights |
| `aspect_ratio_distribution.png` | Histogram of width-to-height ratios |
| `channels_distribution.png` | Bar chart of colour channel counts |
| `width_vs_height.png` | Scatter plot of width vs height |
| `dimension_boxplot.png` | Boxplot of image dimensions |
| `sample_grid.png` | Grid of 9 random sample images |
| `top5_species.png` | Horizontal bar chart of top 5 species |
| `eda_summary_report.csv` | Exported summary statistics table |

The `outputs/eda/` folder is created automatically if it does not exist.

---

## Folder Structure
macro_project_final/
├── .vscode/
│   └── launch.json              ← VS Code run configuration
├── data/
│   └── raw/                     ← Kaggle dataset goes here (not included)
├── outputs/
│   └── eda/                     ← Generated charts saved here (auto-created)
├── src/
│   ├── config.py                ← Central paths and settings
│   ├── main.py                  ← Terminal test script
│   ├── App_SecondVer.py         ← Main Tkinter GUI
│   ├── species_selector.py      ← Startup species selection dialog
│   ├── models/
│   │   └── records.py           ← ImageRecord dataclass
│   └── services/
│       ├── dataset_indexer.py   ← Scans dataset, builds DataFrame
│       └── eda_service.py       ← Generates all EDA charts
├── MANUAL_TESTING.md            ← Testing evidence
├── README.md
└── requirements.txt

---

## Testing

Manual testing scenarios are documented in `MANUAL_TESTING.md`.

Scenarios tested include:

- Selecting fewer than 3 species at startup
- Closing the species selector without confirming
- Clicking View Chart before generating charts
- Missing dataset folder handling
- Full successful end-to-end run with selected species
