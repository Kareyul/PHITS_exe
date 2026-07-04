# PHITS automation

This repository now contains a simple unattended runner for the PHITS input file [APXray_60_kV.inp](APXray_60_kV.inp).

## How it works

- The script [scripts/run_phits.ps1](scripts/run_phits.ps1) runs PHITS from the repository root.
- Each execution creates a timestamped folder under [results](results) and stores the log plus copied output files there.
- The GitHub Actions workflow [.github/workflows/phits.yml](.github/workflows/phits.yml) can run the simulation automatically on a self-hosted runner, so it can keep generating data even when your laptop is off.

## Setup

1. Push this repository to GitHub.
2. Add a self-hosted GitHub Actions runner on a machine that stays on and has PHITS installed.
3. Set a repository variable named `PHITS_EXE` to the full path of the PHITS executable on that runner.
4. Start the workflow manually from the Actions tab, or let the schedule run every six hours.

## Local test

Run the script locally with:

```powershell
./scripts/run_phits.ps1 -PhitsExe "C:\path\to\phits.exe"
```

The outputs will appear in the `results` folder.
