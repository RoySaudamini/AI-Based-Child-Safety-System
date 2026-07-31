<div align="center">

# 🛡️ AI-Based Child Safety System

> **Intelligent RFID & Facial Recognition for Child Safety**

![Python](https://img.shields.io/badge/Python-3.8+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-4.8+-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white)
![Arduino](https://img.shields.io/badge/Arduino-Compatible-00979D?style=for-the-badge&logo=arduino&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green.svg)

<br/>

An intelligent attendance and safety system that combines **RFID authorization**, **AI-powered facial recognition**, and **guardian verification** to ensure children's safety during check-in and check-out procedures. It keeps parents updated in real-time via WhatsApp and syncs logs securely to Google Sheets.

</div>

<hr/>

## 🚀 Quick Setup

### 1️⃣ Clone & Install Requirements
```bash
git clone https://github.com/somesh-opps/AI-Based-Child-Safety-System.git
cd AI-Based-Child-Safety-System

# Install core dependencies
pip install cmake dlib face-recognition
pip install -r requirements.txt
```

### 2️⃣ Hardware & Cloud Setup
- 🔌 **Arduino:** Upload the MFRC522 RFID sketch to your Arduino and connect it via USB.
- ☁️ **Google Cloud:** Enable **Google Sheets & Drive APIs** in the Google Cloud Console and download your service account `key.json`.
- 💬 **WhatsApp:** Make sure **WhatsApp Web** is logged in on your primary Chrome browser.

### 3️⃣ Configure Environment
```bash
cp .env.example .env
```
Open `.env` and fill in your details:
- **Arduino COM port**
- **Authorized RFID card IDs**
- **Paths** to your Google credentials and `STUDENTS/` directory

### 4️⃣ Prepare Student Data
Create a folder structure for each student to hold their photos and their guardian's photos for recognition:
```text
STUDENTS/
├── Student_Name/
│   ├── photo1.jpg
│   ├── phone.txt (Parent's WhatsApp number)
│   └── guardian/
│       └── mother.jpg
```

### 5️⃣ Start the System
```bash
python main_rfid_control.py
```
> *🎉 Your safety system is now live! Simply scan an RFID card to begin the check-in or check-out process.*

<hr/>

## 🏗️ How It Works

<div align="center">

```mermaid
graph TD
    A[🎴 RFID Scan] -->|Mode 1| B[📷 Student Face Check-in]
    A -->|Mode 2| C[📷 Student + Guardian Check-out]
    
    B & C --> D{Face Recognized?}
    
    D -->|Yes| E[✅ Access Granted]
    D -->|No| F[❌ Access Denied]
    
    E --> G[📊 Log to Google Sheets]
    E --> H[💬 WhatsApp Alert to Parent]
    E --> I[🖥️ Display on LCD]
    
    style A fill:#00979D,stroke:#333,stroke-width:2px,color:#fff
    style B fill:#3776AB,stroke:#333,stroke-width:2px,color:#fff
    style C fill:#3776AB,stroke:#333,stroke-width:2px,color:#fff
    style E fill:#4CAF50,stroke:#333,stroke-width:2px,color:#fff
    style F fill:#F44336,stroke:#333,stroke-width:2px,color:#fff
    style G fill:#95E1D3,stroke:#333,stroke-width:1px,color:#000
    style H fill:#25D366,stroke:#333,stroke-width:1px,color:#fff
```

</div>

<hr/>

## 📄 License

This project is licensed under the **MIT License**.

> Copyright (c) 2026 Somesh Kumar Sahoo
> 
> Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files... *(See the [LICENSE](LICENSE) file for the full text.)*

<br/>

<div align="center">
<b>Made with ❤️ for Child Safety</b>
</div>
