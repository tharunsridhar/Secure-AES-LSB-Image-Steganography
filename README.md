# 🔐 Secure AES + LSB Image Steganography

![Python](https://img.shields.io/badge/Python-3-3776AB?style=flat-square&logo=python&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-Image%20Processing-0C7BDC?style=flat-square&logo=opencv&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-CryptoJS-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![AES](https://img.shields.io/badge/Encryption-AES--CBC-critical?style=flat-square)

A secure steganography framework that combines AES encryption with Least Significant Bit (LSB) embedding in grayscale images.

This project demonstrates secure covert communication while quantitatively analyzing image distortion using PSNR and SSIM metrics.

---

## 🚀 Project Overview

This system enables:

- AES-encrypted message embedding into images
- Blind extraction (no original image required)
- Image quality evaluation using PSNR & SSIM
- Capacity vs Quality trade-off visualization
- CLI-based Python implementation
- Interactive browser-based web interface

The framework emphasizes both **cryptographic security** and **steganographic imperceptibility**.

---

## 🧠 System Workflow

```text
Plaintext Message
  ->
AES Encryption
  ->
Base64 Encoding
  ->
Binary Conversion
  ->
LSB Embedding into Image
  ->
Stego Image Output
```

Extraction reverses the entire pipeline.

---

## 🔒 Cryptographic Layer

### AES Implementation (Python)

- AES-CBC mode with a random IV
- PKCS-style padding
- Base64 encoding of IV + ciphertext
- Secure random key generation

An alternative version (`main2.py`) uses AES-ECB for experimentation and comparison.

### Browser Version

- AES encryption using CryptoJS
- Client-side encryption & decryption
- No server dependency

---

## 🖼 Steganography Layer

- Grayscale image conversion
- LSB replacement in pixel intensity values
- Sequential bit embedding
- Blind extraction using ciphertext length

Core embedding logic is implemented in Python (`main.py`), with an equivalent JavaScript implementation for the web version (`steganography_app.html`).

---

## 📊 Image Quality Evaluation

To measure imperceptibility, the following metrics are computed:

### PSNR (Peak Signal-to-Noise Ratio)

Higher values indicate minimal distortion.

- **PSNR ≈ 74 dB**

This indicates extremely low visible distortion.

### SSIM (Structural Similarity Index)

Measures structural similarity between images.

- **SSIM ≈ 1.000**

Indicates nearly identical perceptual quality.

---

## 📈 Capacity vs Quality Trade-Off

The project includes automated evaluation of:

- Message length vs PSNR
- Message length vs SSIM

The trade-off plot is generated programmatically and saved as `quality_tradeoff.png`, with an example shown in `main-output.pdf`. This demonstrates how increasing payload affects image fidelity.

---

## 🧪 Experimental Results

The report demonstrates:

- Successful encryption & embedding
- Accurate extraction and decryption
- Minimal visual difference between original and stego image
- High PSNR and SSIM values
- Trade-off plot saved as `quality_tradeoff.png`

Full experimental screenshots are available in `main-output.pdf`.

---

## 🛠 Tech Stack

### Python Version
- Python 3
- PyCryptodome
- NumPy
- OpenCV
- PIL
- scikit-image
- Matplotlib

### Web Version
- HTML5
- CSS3
- JavaScript
- CryptoJS

---

## 📂 Project Structure

```text
main.py                  -> Full CLI workflow (AES-CBC + Metrics)
main2.py                 -> Alternative experimental pipeline (AES-ECB)
main-output.pdf          -> Experimental results & plots
steganography_app.html   -> Interactive browser UI
requirements.txt         -> Dependencies
```

---

## ⚙️ How to Run (Python Version)

Install dependencies:

```bash
pip install -r requirements.txt
```

Run:

```bash
python main.py
```

Follow the prompts to:
- Enter message
- Select encryption type
- Provide cover image path
- Generate stego image
- Compute PSNR & SSIM
- Extract & decrypt message

---

## 🌐 How to Run (Web Version)

Open `steganography_app.html` directly in a browser.

Features:
- Hide message
- Reveal message
- AES encryption
- Key-based decryption
- Download stego image

---

## 🔐 Security Design Considerations

- Encryption before embedding
- No plaintext stored inside image
- Random IV generation (CBC mode)
- Blind extraction capability
- Separation of crypto & stego layers
- Quantitative distortion validation

---

## ⚠️ Limitations

- Sequential LSB embedding (not randomized)
- No steganalysis resistance testing
- AES key management left to user
- Not hardened against advanced steganographic detection tools

---

## 🎯 Learning Outcomes

This project demonstrates:

- Practical AES encryption implementation
- Understanding of cipher modes (CBC vs ECB)
- Bit-level image manipulation
- Signal quality metric computation
- Capacity-distortion trade-off analysis
- Client-side cryptography in browser
- Secure pipeline design

---

## 📘 Report

The complete experimental workflow and visual results are available in `main-output.pdf`.

---

## 👤 Author

Tharun Sridhar
