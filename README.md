# HEALTHCARE-PSMURO
1. Kerjakan materi latihan Sensor Suhu 18B20 + LCD
2. Kerjakan materi latihan Sensor Max 30102 + LCD
3. Kerjakan materi latihan Konfigurasi sensor Thingspeak

# IoT Healthcare Monitoring System

Proyek ini merupakan hasil dari workshop mikrokontroler bertema **"IoT Healthcare Monitoring System"** yang diselenggarakan oleh Pusat Studi Multimedia & Robotika (PSMURO) Universitas Gunadarma.

Proyek ini bertujuan untuk membangun sistem pemantauan kesehatan berbasis Internet of Things (IoT) yang mampu membaca data suhu tubuh dan detak jantung, kemudian mengirimkannya ke *cloud* untuk visualisasi *real-time*.

## 🛠️ Daftar Komponen & Pinout
Berikut adalah panduan koneksi kabel (*wiring*) antara WeMos D1 R2 dengan komponen lainnya:

| WeMos ESP8266 | LCD 1602 (I2C) | Sensor DS18B20 | Sensor MAX30102 | Sensor Easy Pulse |
| :--- | :--- | :--- | :--- | :--- |
| **5V** | VCC | - | - | - |
| **GND** | GND | Hitam (GND) | GND | GND |
| **D1** | SCL | - | SCL | - |
| **D2** | SDA | - | SDA | - |
| **D3** | - | Kuning (Data) | - | - |
| **3V3** | - | Merah (VCC) | VCC | 3V3 |
| **A0** | - | - | - | A0 |

> **Catatan:** Lepas jack DC power pada ESP8266 sebelum melakukan *upload* program untuk menghindari kerusakan perangkat.

## 🚀 Cara Menjalankan
1. **Persiapan:**
   - Pastikan Arduino IDE sudah terinstal.
   - Tambahkan URL board manager ESP8266 di `File > Preferences`: `http://arduino.esp8266.com/stable/package_esp8266com_index.json`.
   - Instal Library: `LiquidCrystal_I2C`, `DallasTemperature`, `MAX30105`, dan `ThingSpeak` melalui *Library Manager*.
2. **Konfigurasi:**
   - Buka file program utama (`.ino`).
   - Masukkan `ssid` dan `password` WiFi Anda.
   - Masukkan `myChannelNumber` dan `myWriteAPIKey` dari dashboard ThingSpeak.
3. **Upload:**
   - Hubungkan perangkat ke PC.
   - Pilih Board **WeMos D1 R2** atau **ESP8266 Board**.
   - Pilih port yang sesuai, lalu klik **Upload**.

## 📊 Visualisasi Data (ThingSpeak)
Sistem mengirimkan data ke platform ThingSpeak:
- **Field 1:** Beats Per Minute (BPM)
- **Field 2:** Average BPM
- **Field 3:** Temperatur Tubuh (°C)

---
*Proyek ini dikembangkan sebagai bagian dari modul workshop PSMURO Universitas Gunadarma.*
