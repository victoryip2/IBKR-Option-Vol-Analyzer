Volatility Crush Analyzer — quick start

This folder contains `IBKR Option Vol Analyzer.py`, a small Tkinter GUI that prices option straddles and does scenario analysis. The steps below will create or use a project virtual environment, install dependencies, and run the script.

Prerequisites
- macOS with Python 3.10+ (your workspace Python is fine).
- Interactive Brokers TWS or IB Gateway if you want live market/historical data. Enable API access in TWS/IB Gateway settings.

Recommended (create an isolated venv for this analyzer)

1) Create and activate a virtual environment (from this folder):

```zsh
python3 -m venv ".venv"
source ".venv/bin/activate"
```

2) Install dependencies

```zsh
# Install pinned deps from requirements.txt
python -m pip install --upgrade pip setuptools wheel
python -m pip install -r "requirements.txt"
```

Notes about `requirements.txt`:
- This repository's `requirements.txt` may contain packages from your workspace. The analyzer needs at least:
  - numpy
  - pandas
  - scipy
  - ibapi
  - tkinter (stdlib; on macOS it relies on system Tcl/Tk)
- If you only want the minimal set, you can create a short file with the four packages above and install that instead.

3) Run the GUI

```zsh
# with venv active
python "IBKR Option Vol Analyzer.py"

# or directly with the venv python without activating
"$(pwd)/.venv/bin/python" "IBKR Option Vol Analyzer.py"
```

Connecting to Interactive Brokers
- Default host: 127.0.0.1
- Default port: 7497 (TWS paper/live) or 7496/4002 depending on your setup
- Ensure TWS/IB Gateway is running and API access is enabled (Configure > API > Settings)
- The script uses clientId 0 by default when connecting; change it in code if you need a different client id.

Troubleshooting
- If you see path/permission errors when running commands, wrap paths that contain spaces in double quotes (examples above use quoted paths).
- If tkinter import fails on macOS, install/update Tcl/Tk (e.g., Homebrew tcl-tk) and ensure your Python was built/linked with it.


