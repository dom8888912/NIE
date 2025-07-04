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
