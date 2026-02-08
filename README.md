# MONIC - Modern Aquaponic Monitoring System 🐟🌱

**Sistem Monitoring Aquaponik Berbasis IoT** menggunakan Raspberry Pi, sensor DHT22, Ultrasonic, dan integrasi cloud Ubidots.

Proyek ini adalah sistem monitoring real-time untuk instalasi aquaponik modern. Sensor membaca suhu udara, kelembaban udara, dan level air secara otomatis, kemudian data dikirim ke platform Ubidots untuk visualisasi dashboard dan notifikasi.

Proyek ini pernah saya ikutkan dalam **kompetisi IoT** dan berhasil menjadi **juara** 🏆.

![Aquaponic Setup](assets/setup.jpg) <!-- Ganti dengan foto hardware kamu -->
![Ubidots Dashboard](assets/dashboard.png) <!-- Ganti dengan screenshot dashboard Ubidots -->

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

### 📦 Instalasi & Setup
1. **Siapkan Raspberry Pi**
   - Install Raspberry Pi OS (Lite atau Desktop).
   - Update sistem:
     ```bash
     sudo apt update && sudo apt upgrade -y

Install dependenciesBashsudo apt install python3-pip -y
pip3 install RPi.GPIO Adafruit_DHT requests
Clone repositoryBashgit clone https://github.com/hilman-devop/monic-modern-aquaponik.git
cd monic-modern-aquaponik
Konfigurasi Ubidots
Buat akun di Ubidots Industrial
Buat device baru dengan label monic-modern-aquaponik
Salin TOKEN dan ganti di file utama:PythonTOKEN = "BBFF-XXXXXXXXXXXXXXXXXXXXXXXXXXXX"

Hubungkan hardware
DHT22 → GPIO 4 (atau sesuaikan di dht22.py)
HC-SR04 Trigger → GPIO 17, Echo → GPIO 27 (sesuaikan di ultrasonic.py)


▶️ Cara Menjalankan
Bashpython3 main.py
Script akan berjalan loop terus-menerus dan mengirim data setiap detik.
Untuk menjalankan otomatis saat boot (opsional):
Bashcrontab -e
Tambahkan baris:
text@reboot python3 /home/pi/monic-modern-aquaponik/main.py &
📸 Screenshot & Demo

Foto rangkaian hardware: (upload ke folder assets/ dan link di sini)
Dashboard Ubidots: (screenshot grafik suhu/kelembaban/level air)

🏆 Achievement
Proyek ini berhasil menjadi juara kompetisi IoT dengan fokus pada solusi pertanian berkelanjutan melalui aquaponik otomatis.
🔮 Future Improvements (Ide Pengembangan)

Tambah relay untuk kontrol pompa otomatis berdasarkan level air
Integrasi notifikasi Telegram/Email saat parameter kritis
Dashboard web custom dengan Flask/Laravel
Tambah sensor pH, TDS, dan nutrisi air

📝 Catatan

Pastikan Raspberry Pi terkoneksi internet stabil.
Jika ada error baca sensor, cek wiring dan GPIO pin.
Untuk produksi, tambahkan error handling lebih robust dan logging.
