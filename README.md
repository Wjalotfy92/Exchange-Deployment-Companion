# Exchange Deployment Companion

**Exchange Deployment Companion** is a PowerShell-based GUI application designed to simplify, automate, and visualize the deployment of Microsoft Exchange Server. It replaces the complex command-line installation process with a modern, user-friendly interface.

## 🚀 Features

This tool covers the entire deployment lifecycle for **Mailbox** and **Edge Transport** roles:

### 1. Pre-Deployment Automation
* **Active Directory Prep:** GUI-based Schema, AD, and Domain preparation.
* **Prerequisites:** Automated installation of required Windows Features (RSAT, IIS, etc.) and dependencies (C++ Redistributables, UCMA 4.0).
* **Safety Checks:** Automatically detects and clears "Pending Reboot" registry keys that often block Exchange installations.

### 2. Exchange Installation
* **Visual Logs:** Real-time log tailing within the GUI (no need to open text files manually).
* **Flexible Setup:** Supports both "Typical" (Unattended) and "Custom" (GUI-based) installation modes.
* **Edge Transport Support:** Dedicated workflow for Edge server roles.

### 3. Post-Installation Configuration
* **Activation:** Bulk activate servers with Product Keys.
* **Namespace Configuration:** Configure Virtual Directory URLs (OWA, ECP, ActiveSync, etc.) and the Autodiscover Service Connection Point (SCP).
* **Certificate Management:** Securely import PFX certificates and assign them to IIS and SMTP services across multiple servers.

## 📋 Requirements

* **OS:** Windows Server 2016, 2019, or 2022.
* **PowerShell:** Version 5.1 (Run as Administrator).
* **Exchange Media:** The Exchange Server ISO mounted or extracted.

## 🛠️ Installation & Setup

1.  **Clone the Repository:**
    ```powershell
    git clone [https://github.com/YOUR-USERNAME/Exchange-Deployment-Companion.git](https://github.com/YOUR-USERNAME/Exchange-Deployment-Companion.git)
    ```

2.  **Download Dependencies:**
    Due to GitHub file size limits, please download the following installers and place them in the `\Installers` folder:
    * `IIS_rewrite.msi`
    * `vcRedist2012.exe`
    * `vcredist2013.exe`
    * `UcmaRuntimeSetup.exe`

3.  **Run the Tool:**
    * Open PowerShell as Administrator.
    * Navigate to the script directory.
    * Run the main script:
        ```powershell
        .\Start-ExchangeSetup.ps1
        ```

## 📂 Folder Structure

Ensure your directory looks like this for the script to function correctly:

```text
/Root
  ├── Start-ExchangeSetup.ps1
  ├── /XAML Files         (Contains all .xaml UI files)
  ├── /Scripts            (Contains helper .ps1 scripts)
  └── /Installers         (Place your .exe/.msi requirements here)
