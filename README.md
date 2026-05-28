# INR-Tracker Web Decoder

This repository contains the source code for the **INR-Tracker Web Decoder**. This tool allows medical professionals to view INR data exported from the INR-Tracker iOS app in a secure, privacy-focused manner.

## 🔒 Privacy & Security (Zero-Knowledge)

The safety of patient data is our top priority. This web application operates on a **strictly local, client-side** basis:

- **No Server Processing:** This page does not communicate with any backend server. No medical data is sent, stored, or logged anywhere on the internet.
- **Local Decryption:** All decryption (AES-GCM) happens directly within the memory (RAM) of your browser.
- **GDPR Compliant:** Since no data leaves the browser, this tool is fully compliant with GDPR/DSGVO standards.

## 🚀 How to use

1. **Input:** Paste the text derived from the QR code (provided by the patient) into the decoder input field.
2. **Decrypt:** Enter the 4-digit PIN set by the patient in the app.
3. **View:** The data is decrypted instantly and displayed directly in the browser.

## 🛠 Technical Implementation

To ensure the highest level of security, the data is encrypted using industry-standard protocols:

- **Algorithm:** AES-GCM (256-bit)
- **Key Derivation:** PBKDF2 with SHA-256 (100,000 iterations)
- **Structure:** `[12 Bytes Nonce] + [Ciphertext] + [16 Bytes Tag]`

## ⚖️ Transparency

This project is open-source. We believe in transparency, especially regarding health data. By keeping this repository public, medical professionals and developers can verify that the code performs only the promised functions without any hidden network activity.

---
*Disclaimer: This tool is intended for medical professionals to view patient-provided data. Please verify patient data with official lab reports if necessary.*

<p align="center">
  <a href="https://apps.apple.com/de/app/inr-tracker/id6747362112">
    <img src="Badge Apple.svg" 
         alt="Download on the App Store" 
         width="180">
  </a>
</p>
