# InvoiceSync

**Automate your invoicing process with ease!**  
InvoiceSync is a Python application that monitors a folder for PDF invoices, uploads them to Google Drive, and sends download links to clients via WhatsApp—all from a user-friendly GUI.

---

## Features
- **Folder Monitoring**: Automatically detects new PDF invoices in a specified directory.
- **Google Drive Integration**: Uploads invoices to a dedicated "Invoice PDFs" folder on your Google Drive.
- **WhatsApp Notifications**: Sends invoice links instantly to clients using WhatsApp.
- **Duplicate Prevention**: Uses file hashing to avoid reprocessing identical invoices.
- **GUI Interface**: Built with PyQt5 for easy control and real-time logs.
- **Cross-Platform**: Runs on Windows (with potential for macOS/Linux).

---

## Prerequisites
Before running InvoiceSync, ensure you have:
- **Python 3.7+** installed.
- A **Google Cloud Project** with Drive API enabled and OAuth 2.0 credentials (`credentials.json`).
- **WhatsApp** installed and logged in on your default browser.
- A Windows PC (tested on Windows; other OSes may require tweaks).

---

## Installation

### Option 1: Run from Source
1. **Clone the Repository**:
   ```bash
   git clone https://github.com/yourusername/InvoiceSync.git
   cd InvoiceSync
   ```
2. **Install Dependencies**:
   ```bash
   pip install -r requirements.txt
   ```
3. **Run the App**:
   ```bash
   python gui_app.py
   ```

### Option 2: Use the Executable
1. Download `InvoiceApp.exe from the [Releases]() page.
2. Place it in a folder and run it.

---

## Setup
1. **Google Drive Credentials**:
  - Go to [Google Cloud Console](https://console.cloud.google.com/).
  - Create a Project and enable the Drive API
  - Generate OAuth 2.0 credentials (Desktop App) and download as `credentials.json`.
  - Place `credentials.json` in the same folder as `InvoiceApp.exe` or the source files.
  - On first run, authenticate via the browser to generate `token.json`.
2. **Folder Configuration**:
    - Default monitored folder: `D:\Lynn\Python\automation\pdf_folder`.
    - Change it via the GUI's "Browse" button if needed.
   
---

## Usage

1. Launch `InvoiceApp.exe` or `python gui_app.py`.
2. If prompted, select `credentials.json` and complete Google Drive authentication.
3. Click **"بدء المراقبة" (Start Monitoring)** to watch the folder.
4. Save a PDF invoice to the monitored folder:
   - The app extracts a phone number (e.g., "جوال: 201234567891").
   - Uploads the PDF to Google Drive.
   - Sends a WhatsApp message with the link.
5. View logs in the GUI or `invoice_logs.txt`.

---

## Requirements
Create a `requirements.txt` with:

   ```txt
    PyQt5==5.15.9
    PyMuPDF==1.23.5
    watchdog==4.0.0
    pywhatkit==5.4
    pyautogui==0.9.54
    google-auth-oauthlib==1.2.0
    google-auth-httplib2==0.2.0
    google-api-python-client==2.126.0
   ```

---

## Building from Source
### To create your own execuatable**:
1. **Install `PyInstaller`**:
   ```bash
   pip install pyinstaller
   ```
2. **Generate a `.spec` file**:
   ```bash
   pyinstaller --onefile --windowed --icon=invoice.ico --name=InvoiceApp --add-data "main.py;." gui_app.py
   ```
3. **Edit `invoice_app.spec` as needed and build**:
   ```bash
   pyinstaller invoice_app.spec
   ```
4. **Find `InvoiceApp.exe` in `dist/`.

---

## Contributing
Feel free to fork this repo, submit issues, or send pull requests to enhance InvoiceSync!

---

# License
his project is licensed under the MIT License - see  for details.










