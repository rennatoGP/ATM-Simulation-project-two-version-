[![Releases](https://img.shields.io/badge/Download-Releases-blue?logo=github)](https://github.com/rennatoGP/ATM-Simulation-project-two-version-/releases)

# Python ATM Simulation Desktop App — Banking System Guide Tutorial

![ATM Banner](https://images.unsplash.com/photo-1519861534301-3b2f7b7f7b04?auto=format&fit=crop&w=1400&q=80)

ATM Simulation desktop app that demonstrates core banking flows. The project shows account login, balance checks, withdrawals, deposits, transfers, and basic admin actions. It targets learners who build GUI apps with Python.

Repository: ATM-Simulation-project-two-version-

Releases: https://github.com/rennatoGP/ATM-Simulation-project-two-version-/releases  
Download the release file from the Releases page and execute it on your machine. The release bundle contains a packaged executable for the matching platform. Execute the file to run the app.

Table of contents
- About
- Key features
- Screenshots
- Tech & architecture
- Requirements
- Install and run
  - Run the packaged release (recommended)
  - Run from source
- File structure
- Data model
- Testing
- How to extend
- Contributing
- License
- FAQ
- Contact

About
This repo holds a desktop ATM simulator written in Python. It uses a GUI to mimic an ATM. The UI shows screens for PIN entry, account menu, and simple transactions. The project aims to teach GUI design, event handling, and simple state management.

Key features
- Login with account number and PIN
- View account balance
- Cash withdrawal with balance checks
- Cash deposit (simulated)
- Internal transfer between accounts
- Transaction history list
- Simple admin mode for seeding accounts
- Local data storage using JSON (no external DB)
- Cross-platform build via PyInstaller (release bundle)

Badges
[![Python](https://img.shields.io/badge/Python-3.8%2B-blue)](https://www.python.org)
[![GUI](https://img.shields.io/badge/GUI-Tkinter-orange)](https://docs.python.org/3/library/tkinter.html)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)

Screenshots
![Login screen](https://images.unsplash.com/photo-1503376780353-7e6692767b70?auto=format&fit=crop&w=900&q=60)
![ATM UI example](https://images.unsplash.com/photo-1515165562835-cf8f3e80f2f4?auto=format&fit=crop&w=900&q=60)

Tech & architecture
- Language: Python 3.8+
- GUI: Tkinter (core GUI toolkit included with Python)
- Packaging: PyInstaller for release builds
- Storage: JSON file for accounts and transactions
- Pattern: Simple MVC-like separation (ui, models, controller)
- Concepts: OOP, event-driven UI, file I/O, basic validation

Requirements
- Windows, macOS, or Linux
- Python 3.8 or higher (if running from source)
- For running packaged release: matching platform executable included in Releases
- Optional: Virtual environment for source install

Install and run

Run the packaged release (recommended)
1. Visit the Releases page: https://github.com/rennatoGP/ATM-Simulation-project-two-version-/releases
2. Download the file that matches your platform (filename includes the platform and version).
3. Execute the downloaded file:
   - Windows: double-click the .exe file.
   - macOS: open the .dmg or .app bundle and run the app.
   - Linux: give execute permission and run, for example:
     - chmod +x ATM_Simulation_v1.0.AppImage
     - ./ATM_Simulation_v1.0.AppImage
4. The app opens a window. Use the seeded accounts to log in or seed new accounts via the admin menu.

Because the Releases link contains a path, you must download the release file and execute it on your device.

Run from source
1. Clone the repo:
   - git clone https://github.com/rennatoGP/ATM-Simulation-project-two-version-.git
2. Create and activate a virtual environment.
3. Install dependencies:
   - pip install -r requirements.txt
4. Run the main script:
   - python main.py
5. The app should open as a Tkinter window.

Dependencies (example)
- tkinter (bundled with Python)
- pyinstaller (for building a release)
- optional: pytest (for tests)

File structure
- main.py — app entry point
- app/
  - ui.py — UI screens and widgets
  - controller.py — event handlers and app logic
  - models.py — account and transaction classes
  - storage.py — JSON store functions
- data/
  - accounts.json — seeded accounts and transactions
- assets/
  - icons/ — UI icons and images
- tests/
  - test_models.py — unit tests for model logic
- requirements.txt
- LICENSE
- README.md

Data model
Account
- id: unique number
- name: account holder name
- pin: 4-digit PIN (stored as hashed or plain for demo)
- balance: float
- transactions: list of transaction records

Transaction
- id: unique id
- type: deposit, withdrawal, transfer
- amount: positive float
- date: ISO timestamp
- meta: optional details (target account for transfer)

Storage
- The app reads and writes JSON in data/accounts.json
- The storage layer serializes model objects and writes atomic files
- Backups: a timestamped file saves before writes

Common flows
Login and session
- The UI prompts for account number and PIN.
- The controller validates credentials against stored accounts.
- On success, the session loads the account object into memory.

Withdraw
- User requests an amount.
- Controller checks balance and minimum withdrawal rules.
- If allowed, controller creates a withdrawal transaction and updates balance.
- Storage persists the change.

Deposit
- User enters deposit amount.
- Controller creates deposit transaction, updates balance, and persists.

Transfer
- User picks target account.
- Controller checks both accounts. It debits source and credits target in a single flow.
- Controller writes both account states to storage.

Admin
- Admin mode seeds accounts, resets storage, and shows logs.
- Use admin only for demos and learning.

Testing
- Unit tests cover models and core logic.
- Run tests:
  - pytest tests/
- Focus tests on:
  - balance updates
  - transaction creation
  - edge cases (insufficient funds, invalid transfer)

How to extend
- Add encryption for stored PIN values.
- Replace JSON storage with SQLite for multi-user scenarios.
- Add networked mode for server-client tests.
- Switch GUI from Tkinter to PyQt or Kivy for richer UI.
- Implement print receipts or export CSV for transactions.
- Add localization and date formatting.

Contributing
- Fork the repo.
- Create a new branch per feature or bugfix.
- Keep changes small and focused.
- Add tests for new logic.
- Open a pull request with a clear description.

License
This project uses the MIT license. See the LICENSE file.

FAQ
Q: Where do I find the release files?
A: The release files live on the Releases page:
https://github.com/rennatoGP/ATM-Simulation-project-two-version-/releases

Q: Can I run this on macOS?
A: Yes. Download the macOS release or run from source with Python 3.8+.

Q: Is this safe to use with real accounts?
A: This app stores demo data locally in JSON. Do not enter real banking credentials.

Contact
- Repo owner: rennatoGP (GitHub)
- Issues: Use the GitHub Issues tab for bug reports and feature requests.

Topics and tags
atm, atmsimulation, bank-app, banking-system, beginner-project, coding, desktop-application, developer, gui, learning, learning-python, python, python-language, python-programing, simulation

Development notes
- The app focuses on clarity and hands-on learning.
- Keep UI code separate from business logic.
- Keep tests simple and deterministic.
- Use PyInstaller to create platform bundles.

Build a release (developer)
- Install PyInstaller.
- Run:
  - pyinstaller --onefile --windowed main.py
- Copy the output executable to the release archive.
- Update the Releases page with the new archive.

Release page reminder
Visit the Releases page to download the packaged app and run the file on your platform: https://github.com/rennatoGP/ATM-Simulation-project-two-version-/releases