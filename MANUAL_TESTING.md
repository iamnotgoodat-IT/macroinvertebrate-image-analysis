# Manual Testing Evidence

## Testing Summary
All scenarios were tested manually by running the application and 
recording the result of each input condition.

---

## Test Scenarios

| # | Scenario | Input / Action | Expected Result | Actual Result |
|---|---|---|---|---|
| 1 | Select fewer than 3 species | Tick only 2 checkboxes → click Confirm | Warning popup: "Please select at least 3 species" | Passed |
| 2 | Close selector without confirming | Click X on species selector window | App closes cleanly, no crash | Passed |
| 3 | View chart before generating | Click View Chart with empty dropdown | Warning popup: "Generate EDA charts first" | Passed |
| 4 | Missing dataset folder | Remove data/raw/ and launch app | Startup error popup with clear message | Passed |
| 5 | Select all species and run | Click Select All → Confirm | All 17 species load, stats panel populates | Passed |
| 6 | Select 3 specific species | Tick 3 species → Confirm | Only those 3 species appear in dropdown | Passed |
| 7 | Show sample image | Select species → click Show Sample Image | Random image from that species displayed | Passed |
| 8 | Generate EDA charts | Click Generate EDA Charts | 10 charts + 1 CSV saved to outputs/eda/ | Passed |
| 9 | View a generated chart | Select chart from dropdown → View Chart | Chart displayed inside the app window | Passed |
| 10 | Show species count table | Click Show All Species Counts | Scrollable popup with counts per species | Passed |
| 11 | Full end-to-end run | Select 5 species → run all features | All features work without errors | Passed |
