# 🛡️ Batch MAC Address Changer (Decrypted Edition)

<p align="center">
  <img src="https://img.shields.io/badge/OS-Windows%2010%20%2F%2011-blue?style=for-the-badge&logo=windows" alt="Windows">
  <img src="https://img.shields.io/badge/Language-Batch%20(.bat)-orange?style=for-the-badge&logo=windows-terminal" alt="Batch">
  <img src="https://img.shields.io/badge/Status-Fully%20Decrypted-success?style=for-the-badge" alt="Status">
  <img src="https://img.shields.io/badge/Type-Driverless-critical?style=for-the-badge" alt="Driverless">
</p>

---

## 📌 Overview

This decrypted Windows batch script, created by **vizu1234**, automates the process of spoofing network interface card (NIC) MAC addresses. Instead of relying on third-party software or kernel drivers, it directly updates the Windows registry class keys for physical adapters and forces an interface restart to apply the changes immediately.

---

## ⚙️ How the Script Works

1. **MAC Generation Subroutine (`:MAC`):** Builds a randomized 12-character hexadecimal string using custom character pools (`GEN` and `GEN2`) to ensure a valid locally administered address format.
2. **Registry Injection (`NetworkAddress`):** Queries active physical network adapters via `wmic` to locate their specific registry class path under `{4D36E972-E325-11CE-BFC1-08002bE10318}` and injects the spoofed MAC into the `NetworkAddress` registry key.
3. **Power Saving Optimization (`PnPCapabilities`):** Automatically writes a value of `24` to disable power management features on the target adapters, preventing Windows from putting the card to sleep or resetting power states.
4. **Instant Interface Reset (`netsh`):** Cycles each active network connection off and back on using `netsh interface set interface` commands, forcing Windows to load the new MAC address instantly without requiring a PC restart.

---

## ✨ Key Features

* **⚡ 100% Driverless:** Zero kernel-level files, external binaries, or third-party dependencies required.
* **⏱️ Instant Application:** Automatically disables and re-enables network interfaces so the new MAC takes effect immediately.
* **🔋 Power State Tweaking:** Disables adapter power-saving settings to maintain stable connection performance.
* **🔓 Fully Decrypted Source:** Clean, unencrypted Windows Batch (`.bat`) code for complete transparency and auditing.

---

## 📋 System Requirements

| Component | Requirement |
| :--- | :--- |
| **Operating System** | Windows 10 / Windows 11 (`x64` architecture) |
| **Permissions** | Full Administrator privileges (`cmd.exe`) |

---

## 🚀 Usage Guide

> [!IMPORTANT]
> **Pre-requisite:** Disable Windows Defender real-time protection or third-party antivirus software temporarily to prevent false-positive script blocking.

1. Save your script code into a file named `mac_changer.bat`.
2. Place the file into a local working directory.
3. Right-click `mac_changer.bat` and select **Run as Administrator**.
4. Allow the script to generate the random MAC, update the registry keys, and reset your network adapters.
5. Verify your new MAC address by running `getmac` or `ipconfig /all` in your command prompt.

---

## 🛠️ Troubleshooting & FAQ

* **Q: Do I need to reboot my PC after running this?**
  * **A:** No. The script automatically resets the network adapters via `netsh`, applying the changes instantly.
* **Q: The script closes immediately or throws access errors.**
  * **A:** Make sure you are launching the script with full administrator rights and that your antivirus software hasn't quarantined the process.

---

## ⚖️ Credits & Disclaimer

* **Developer:** [vizu1234 (GitHub)](https://github.com/vizu1234)
* **Disclaimer:** This software and its contents are shared for educational, informational, and archival research purposes only. The user assumes full responsibility for any consequences arising from the usage of this script.
