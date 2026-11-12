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
