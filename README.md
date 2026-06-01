# INR-Tracker Web Decoder

This repository contains the source code for the **INR-Tracker Web Decoder**. This tool allows medical professionals to view INR data exported from the INR-Tracker iOS app in a secure, privacy-focused manner.


## 🔒 Privacy & Security

The safety of patient data is our top priority. This web application operates on a **strictly local, client-side** basis:

- **No Server Processing:** This page does not communicate with any backend server. No medical data is sent, stored, or logged anywhere on the internet.
- **Local Decryption:** All decryption (AES-GCM) happens directly within the memory (RAM) of your browser.
- **Time-Limited Access:** Each QR code contains an embedded, encrypted timestamp. During decryption, the web tool validates this timestamp against the current system time. **If the code is older than 24 hours, the tool automatically refuses to decrypt the data.** This security feature works entirely offline and client-side, ensuring that access expires after 24 hours without requiring any server-side database or tracking.
- **GDPR Compliant:** Since no data leaves the browser, this tool is fully compliant with GDPR/DSGVO standards.


## 🚀 How to use

There are two ways to decrypt and view the patient's INR data:

1. **Option A: Scanning the QR Code (Direct)**
   - Scan the patient's QR code (e.g., directly from the app screen).
   - The web tool will automatically recognize the code and display an input field for the 10-digit PIN.
   - Enter the PIN provided by the patient to decrypt and view the data.

2. **Option B: Manual Input (Remote)**
   - Open this web tool manually in your browser.
   - If the patient has provided the encrypted data text (ID), paste the text into the designated input field.
   - Enter the 10-digit PIN and click the decrypt button to view the data.

*Note: For security reasons, every QR code includes an encrypted timestamp and is valid for 24 hours only. After this period, the data cannot be decrypted.*


## 🛠 Technical Implementation

To ensure the highest level of security, the data is encrypted using industry-standard protocols:

- **Algorithm:** AES-GCM (256-bit)
- **Key Derivation:** PBKDF2 with SHA-256
  

## ⚖️ Transparency

This project is open-source. I believe in transparency, especially regarding health data. By keeping this repository public, medical professionals and developers can verify that the code performs only the promised functions without any hidden network activity.

---
*Disclaimer: This tool is intended for medical professionals to view patient-provided data. Please verify patient data with official lab reports if necessary.*

<p align="center">
  <a href="https://apps.apple.com/de/app/inr-tracker/id6747362112">
    <img src="Badge Apple.svg" 
         alt="Download on the App Store" 
         width="180">
  </a>
</p>
