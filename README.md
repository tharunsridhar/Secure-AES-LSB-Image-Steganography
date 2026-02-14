# 🔐 Secure AES + LSB Image Steganography

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

Plaintext Message  
        ↓  
AES Encryption  
        ↓  
Base64 Encoding  
        ↓  
Binary Conversion  
        ↓  
LSB Embedding into Image  
        ↓  
Stego Image Output  

Extraction reverses the entire pipeline.

---

## 🔒 Cryptographic Layer

### AES Implementation (Python)

- AES-CBC mode (with random IV) :contentReference[oaicite:4]{index=4}  
- PKCS-style padding  
- Base64 encoding of IV + ciphertext  
- Secure random key generation  

Alternative version includes AES-ECB for experimentation :contentReference[oaicite:5]{index=5}  

### Browser Version

- AES encryption using CryptoJS :contentReference[oaicite:6]{index=6}  
- Client-side encryption & decryption  
- No server dependency  

---

## 🖼 Steganography Layer

- Grayscale image conversion
- LSB replacement in pixel intensity values
- Sequential bit embedding
- Blind extraction using ciphertext length

Core embedding logic implemented in Python :contentReference[oaicite:7]{index=7}  
Equivalent JavaScript implementation for web version :contentReference[oaicite:8]{index=8}  

---

## 📊 Image Quality Evaluation

To measure imperceptibility, the following metrics are computed:

### PSNR (Peak Signal-to-Noise Ratio)

Higher values indicate minimal distortion.  
Observed result:

- **PSNR ≈ 74 dB** :contentReference[oaicite:9]{index=9}  

This indicates extremely low visible distortion.

### SSIM (Structural Similarity Index)

Measures structural similarity between images.

- **SSIM ≈ 1.000** :contentReference[oaicite:10]{index=10}  

Indicates nearly identical perceptual quality.

---

## 📈 Capacity vs Quality Trade-Off

The project includes automated evaluation of:

- Message length vs PSNR
- Message length vs SSIM

Plot generated programmatically :contentReference[oaicite:11]{index=11}  
Example visualization shown in report :contentReference[oaicite:12]{index=12}  

This demonstrates how increasing payload affects image fidelity.

---

## 🧪 Experimental Results

The report demonstrates:

- Successful encryption & embedding
- Accurate extraction and decryption
- Minimal visual difference between original and stego image
- High PSNR and SSIM values
- Trade-off plot saved as `quality_tradeoff.png`

Full experimental screenshots available in:
```
main-output.pdf
```
:contentReference[oaicite:13]{index=13}  

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

```
main.py                  → Full CLI workflow (AES-CBC + Metrics)
main2.py                 → Alternative experimental pipeline
main-output.pdf          → Experimental results & plots
steganography_app.html   → Interactive browser UI
requirements.txt         → Dependencies
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

Follow prompts to:
- Enter message
- Select encryption type
- Provide cover image path
- Generate stego image
- Compute PSNR & SSIM
- Extract & decrypt message

---

## 🌐 How to Run (Web Version)

Simply open:

```
steganography_app.html
```

in a browser.

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

Complete experimental workflow and visual results available in:

```
main-output.pdf
```

---

## 👤 Author

Tharun Sridhar  
