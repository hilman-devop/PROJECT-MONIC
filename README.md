# MONIC - Modern Aquaponic Monitoring System 🐟🌱

**Sistem Monitoring Aquaponik Berbasis IoT** menggunakan Raspberry Pi, sensor DHT22, Ultrasonic, dan integrasi cloud Ubidots.

Proyek ini adalah sistem monitoring real-time untuk instalasi aquaponik modern. Sensor membaca suhu udara, kelembaban udara, dan level air secara otomatis, kemudian data dikirim ke platform Ubidots untuk visualisasi dashboard dan notifikasi.

Proyek ini pernah saya ikutkan dalam **kompetisi IoT** dan berhasil menjadi **Best 25 Project**.

![Monic Image 1](assets/monic1.jpeg)
![MONIC Image 2](assets/monic2.jpeg)

### 🚀 Fitur Utama
- Pengukuran real-time:
  - Suhu udara (°C)
  - Kelembaban udara (%)
  - Level air tangki (cm)
- Pengiriman data otomatis ke cloud Ubidots setiap detik
- Struktur kode modular (sensor terpisah di file `dht22.py`, `ultrasonic.py`, `ldr.py`)
- Error handling dasar untuk koneksi internet/API
- Siap dikembangkan lebih lanjut (tambah relay pompa, notifikasi Telegram, dll.)

### 🛠 Hardware yang Digunakan
- Raspberry Pi (3/4/Zero W rekomendasi)
- Sensor DHT22 (suhu + kelembaban)
- Sensor Ultrasonic HC-SR04 (level air)
- Jumper wires & breadboard
- Power supply stabil

### 💻 Tech Stack & Library
- Python 3
- RPi.GPIO
- Adafruit_DHT
- Requests (untuk API Ubidots)
- Modul custom: `dht22.py`, `ultrasonic.py`, `ldr.py`
