# Running Backtests

## Setup

Navigate to the backtester directory first:
```powershell
cd C:\Users\Riyan\Documents\backtester_kevin
```

If you get `No module named 'datamodel'`, set PYTHONPATH:
```powershell
$env:PYTHONPATH = "C:\Users\Riyan\Documents\backtester_kevin\prosperity4bt"
```

---

## Basic Commands

Run against all days in a round:
```powershell
python -m prosperity4bt "C:\Users\Riyan\Documents\IMC_Prosperity4\round1\osmium.py" 1
```

Run against a specific day:
```powershell
python -m prosperity4bt "C:\Users\Riyan\Documents\IMC_Prosperity4\round1\osmium.py" 1-0
python -m prosperity4bt "C:\Users\Riyan\Documents\IMC_Prosperity4\round1\osmium.py" 1--1
python -m prosperity4bt "C:\Users\Riyan\Documents\IMC_Prosperity4\round1\osmium.py" 1--2
```

Run against multiple specific days:
```powershell
python -m prosperity4bt "C:\Users\Riyan\Documents\IMC_Prosperity4\round1\osmium.py" 1-0 1-1
```

---

## Useful Flags

| Flag | Purpose |
|---|---|
| `--print` | Print your `print()` / `logger.print()` output live while running |
| `--no-vis` | Skip auto-opening the visualizer (use when browser blocks it) |
| `--no-out` | Don't save a `.log` file |
| `--out myresult.log` | Save log to a custom path |

Recommended command for debugging (skips broken auto-visualizer, shows live output):
```powershell
python -m prosperity4bt "C:\Users\Riyan\Documents\IMC_Prosperity4\round1\osmium.py" 1 --no-vis --print
```

---

## Viewing Results in the Visualizer

The auto-open visualizer fails with a Network Error due to browser Mixed Content restrictions (https site fetching from http localhost).

**Workaround:**
1. Run with `--no-vis` — the log is saved to `backtests\<timestamp>.log`
2. Open https://kevin-fu1.github.io/imc-prosperity-4-visualizer/ manually
3. Drag and drop the `.log` file onto the page
