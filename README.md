# HP Smart Sign-In & Scan Automation

This repository contains a Python automation script that opens the HP Smart desktop application, signs into an HP account, and triggers the Scan workflow. It is intended for automated Windows desktop testing and task execution using UI automation.

## Overview

The project uses:

- `pywinauto` to interact with the Windows desktop UI
- `selenium` for browser alert handling
- a JSON configuration file for credentials
- an HTML report generator for step-by-step execution logs

The script automates the following flow:

1. Launch the HP Smart application
2. Open the HP Account sign-in flow
3. Enter the configured email and password
4. Click the Sign In button
5. Trigger the Scan action
6. Save an automation report to `automation_report.html`

## Project Files

- `sas_test.py` — main automation logic and test entry point
- `config.json` — credentials and login configuration
- `automation_report.html` — generated execution report
- `pytest_report.html` — pytest test report

## Requirements

- Windows 10/11
- Python 3.9+
- HP Smart application installed and available on the machine
- Access to the HP account used for sign-in
- Chrome/Edge installed for Selenium-based browser interaction

## Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/mohantysasmita5056/HP_Smart_Sign_In_Scan.git
   cd HP_Smart_Sign_In_Scan


## What this is

This repo is a small Windows automation project for the HP Smart sign-in and scan flow. It uses desktop UI automation to launch the HP Smart app, sign into an HP account using credentials stored in a JSON file, trigger the scan flow, and generate an HTML report of each step.

### Stack
- **Language(s):** Python
- **Framework / runtime:** Windows desktop automation via `pywinauto`, with browser-side handling via `Selenium`
- **Notable libraries:** `pywinauto`, `selenium`, `pytest`, `logging`

## How it's organized

```text
/
├── config.json              credentials used by the automation
├── sas_test.py              main automation script and test entry point
├── automation_report.html   generated execution report
├── pytest_report.html       pytest-generated report
└── README*                 none present in this repo
```

**How it fits together:** The flow is driven by `sas_test.py`: it loads credentials from `config.json`, opens the HP Smart desktop app, waits for the right window, clicks through the sign-in UI, optionally accepts browser alerts, and then clicks the scan action. `HTMLReport` records each step and writes a simple HTML summary to `automation_report.html`. There is also a `pytest` entry point (`test_hp_account_sign_in`) that just calls the main workflow and asserts success.

## How to run it

This repo is not a web app; it is a local automation script intended to run on Windows with the HP Smart app installed and accessible.

```bash
# 1) edit config.json with your HP account email/password
python sas_test.py

# or
pytest -q sas_test.py
```

Required env/secrets:
- `config.json` must contain an `email` and `password`
- The script expects the HP Smart desktop app and HP account sign-in windows to be present and interactable on the machine

## Try asking

- “How do I make `sas_test.py` more resilient to HP Smart UI changes?”
- “Can this automation run in CI or only on a local Windows desktop?”
- “Where should I add retry logic or OCR-based fallback for the scan button?”
