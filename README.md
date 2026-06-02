# INR-Tracker Web Decoder

This repository contains the source code for the **INR-Tracker Web Decoder**. This tool allows medical professionals to view INR data exported from the INR-Tracker iOS app in a secure, privacy-focused manner.


## 🔒 Privacy & Security

This web decoder is designed to process INR share data locally in the browser.

- **No backend for patient data:** This is a static GitHub Pages viewer. The application code does not send decrypted INR data or patient data to a backend server.
- **Local decryption:** Decryption is performed in the user's browser using AES-GCM. The access code is used locally to derive the decryption key with PBKDF2/SHA-256.
- **URL fragment handling:** Encrypted QR data is read from the URL fragment (`#...`) where possible. The viewer removes this fragment from the visible address bar after loading.
- **Time-limited viewer access:** Each share may contain an encrypted expiry timestamp. The official viewer checks this timestamp after decryption and refuses to display expired data.
- **Open source transparency:** The source code is public so users, clinicians, and developers can verify how the viewer works.

This project is privacy-focused by design, but it should not be understood as a legal certification or guarantee of GDPR/DSGVO compliance. GDPR compliance depends on the full processing context, including who uses the tool, for what purpose, and under which legal basis.


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
