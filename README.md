# 📄 Automated Form Filling with Playwright

This Python script automates the registration and appointment booking on a Spanish government website using [Playwright](https://playwright.dev/python/). It simulates realistic user input and regularly checks for new available NIE appointment slots.

**NIE** stands for *Número de Identidad de Extranjero* (Foreigner Identification Number), which is required in Spain for many legal or economic activities (e.g., opening a bank account, rental agreements, official procedures). Appointments for NIE applications are very limited and quickly booked — this script helps detect free slots early.

---

## 🔧 Requirements

- Python 3.8 or higher  
- Required packages (see installation)  
- A `config.yaml` file (see below)  

---

## 📦 Installation

```bash
pip install playwright pyyaml
playwright install

## ⚙️ Configuration

Create a config.yaml file in the same directory as the script:

province: "Madrid"
document_type: "pasaporte"
name: "Max Mustermann"
id_number: "X1234567"
nationality: "Germany"  # or "random"
birth_year: 1990
headless: true

Note: Set nationality to "random" to select a random valid nationality.

## 🧠 Main Features

    Realistic typing and clicking simulation via randomized mouse movements and delays

    Form filling including dropdowns, text inputs, and radio buttons

    Change detection on the target page via SHA256 hash comparison

    Screenshot generation upon changes detected

    Saving cookies and logs for traceability

## 🚀 Running the Script

python scriptname.py

Note: Replace scriptname.py with the actual name of your Python file, e.g. nie_checker.py.
🗂️ Project Structure
File	Purpose
scriptname.py	Main script
config.yaml	User configuration
log.txt	Log file with info and errors
cookies.json	Stored browser cookies
screenshot_*.png	Screenshots on page changes
last_hash.txt	Last known page hash

## 🛠️ Tips

    Set headless: false in config.yaml to run the browser visibly

    Adjust the REALISM_FACTOR in the script to control typing and clicking speed

    Uses a persistent Chromium browser, so cookies & login sessions are preserved

## 🧾 License

This project is not under any official license. Use at your own risk — especially regarding usage on official websites.
