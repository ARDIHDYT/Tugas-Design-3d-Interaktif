# 🏢 3D Digital Twin: Smart Meeting Room Setpoint AC Controller
### Sistem Kendali Iklim Adaptif Berbasis Okupansi (ESP32 + DHT22 + IR Transmitter)

🌐 **Live Demo Website**: [https://ardihdyt.github.io/Tugas-Design-3d-Interaktif/](https://ardihdyt.github.io/Tugas-Design-3d-Interaktif/)

---

## 👨‍💻 Informasi Proyek
- **Nama Siswa**: Ardi Hidayat
- **Kelas**: XI TELK 4
- **Jurusan**: Teknik Telekomunikasi
- **Sekolah**: SMK Telkom
- **Guru Pembimbing**: Buk Decy

---

## 🌟 Fitur Utama Simulasi 3D
1. **Interactive 3D Meeting Room Architecture (Three.js)**:
   - Desain ruang rapat eksekutif modern (lantai parquet kayu ek, meja walnut marmer calacatta, 8 kursi ergonomis interaktif).
   - Animasi orang (3D Business Avatars) berjalan masuk/keluar dari pintu kaca geser otomatis.
   - Pintu kaca otomatis membuka saat ada peserta mendekat disertai sound effect sliding door.
   - Efek visual pencahayaan mewah, volumetric light downlight, pantulan lantai, dan partikel debu halus (dust motes).

2. **Aerodynamic AC Airflow & Particle System**:
   - Visualisasi pita angin dinamis (*Aerodynamic Streamlines*) langsung dari mulut AC Split menuju meja rapat.
   - Partikel kabut dingin (*Cold Air Mist*) yang intensitasnya menyesuaikan kecepatan blower kipas AC (LOW, MED, HIGH, TURBO).
   - Flap louver AC berosilasi secara halus menyesuaikan mode pendinginan.

3. **Closed-Loop Setpoint Adaptive Climate Control**:
   - Formula adaptif okupansi: saat ruangan kosong (0 orang), suhu stabil pada target **Setpoint** (misal 22.0°C) dengan putaran blower **LOW (650 RPM)**.
   - Setiap peserta rapat masuk menyumbang beban kalor (+0.85°C per orang).
   - ESP32 secara otonom mendeteksi kenaikan suhu melalui sensor DHT22 dan menaikkan kompensasi putaran kipas (hingga 1600 RPM TURBO) untuk menekan *steady-state error* tetap berada pada rentang presisi $\le 0.20^\circ\text{C}$.

4. **MATLAB / Simulink Dual-Subplot Oscilloscope**:
   - Grafik real-time respons loop tertutup:
     - **Subplot 1**: Target Setpoint vs Suhu Aktual Sensor DHT22 vs Suhu Tanpa Kompensasi.
     - **Subplot 2**: Kecepatan Putaran Blower Motor AC (RPM) dengan kurva area hijau.

5. **Panel IoT Industri & Komunikasi IR**:
   - Rangkaian ESP32 DevKit V1, Sensor DHT22 (GPIO 4), dan Modul IR TX 940nm (GPIO 14).
   - Layar OLED I2C 0.96" live telemetri suhu & kelembaban.
   - Sinyal pulsa inframerah 38kHz animasi gelombang ring saat ESP32 menembakkan perintah kompensasi ke unit indoor AC.

6. **Web Audio API Sound Engine**:
   - Suara hembusan angin blower AC dinamis (*bandpass filtered noise*) yang frekuensi dan volumenya berubah sesuai RPM motor.
   - Suara chirp modulasi IR & konfirmasi beep unit indoor AC.
   - Sound effect pintu geser dan langkah kaki peserta rapat.

---

## 🚀 Cara Menjalankan Secara Lokal
Cukup buka file `index.html` langsung di browser modern apa saja (Google Chrome, Microsoft Edge, Firefox, Safari) tanpa perlu menginstall server atau library tambahan! Seluruh dependensi (Three.js, Lucide Icons, Tailwind CSS) dimuat via CDN berkecepatan tinggi.

---
*Dibuat untuk memenuhi tugas mata pelajaran Teknik Telekomunikasi & Desain 3D Interaktif.*
