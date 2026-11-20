# SensorCraft - Smart Environment & Motion Activity Logger 🚀

**SensorCraft** merupakan aplikasi Android yang dibuat menggunakan Kotlin dan Jetpack Compose untuk membaca serta memantau data sensor yang ada di perangkat secara langsung. Aplikasi ini bisa digunakan untuk melihat kondisi lingkungan sekitar, pergerakan perangkat, dan arah kompas.

Selain menampilkan data sensor, SensorCraft juga memiliki fitur untuk menyimpan hasil pembacaan sensor ke database SQLite, sehingga data yang sudah dicatat bisa dilihat kembali kapan saja.

Aplikasi ini dibuat dengan menggunakan arsitektur MVVM agar kode program lebih terstruktur dan mudah dikembangkan.

---

## 📱 Fitur Aplikasi

### 1. Dashboard Sensor Real-Time
Pada halaman Dashboard, pengguna dapat melihat data sensor secara langsung, meliputi:
- **Accelerometer** untuk membaca pergerakan perangkat.
- **Light Sensor** untuk mengetahui tingkat pencahayaan sekitar dalam satuan Lux.
- **Magnetometer** untuk mengetahui arah dan kekuatan medan magnet.

Dashboard juga menampilkan status aktivitas perangkat seperti Stationary, Walking, dan Active Shake, serta sudut kemiringan perangkat berupa Pitch dan Roll.

### 2. Menyimpan Data Sensor
Pengguna dapat menyimpan hasil pembacaan sensor menggunakan tombol **Log to SQLite**. Sebelum menyimpan data, pengguna bisa mengisi beberapa informasi, seperti:
- Judul catatan.
- Kategori aktivitas.
- Catatan tambahan.

Data yang disimpan akan masuk ke database SQLite dan bisa dilihat kembali melalui halaman History.

### 3. History dan Pengelolaan Data
Halaman History digunakan untuk melihat data sensor yang sudah pernah disimpan. Beberapa fitur yang tersedia antara lain:
- Menampilkan seluruh data log.
- Mencari data berdasarkan judul, catatan, atau kategori.
- Memfilter data berdasarkan tag.
- Menampilkan statistik jumlah log, rata-rata Lux, dan akselerasi tertinggi.
- Menghapus data tertentu atau menghapus seluruh data log.

### 4. Tools Sensor Interaktif
Aplikasi juga menyediakan beberapa alat yang menggunakan data sensor perangkat secara langsung.

- **Digital Waterpass (Spirit Level)**: Menampilkan posisi kemiringan perangkat melalui visualisasi gelembung pada layar.
- **Kompas Digital**: Menampilkan arah mata angin dengan dial 360° yang bergerak mengikuti perubahan arah perangkat.
- **Lux Meter**: Menampilkan tingkat pencahayaan sekitar dalam bentuk indikator visual.

### 5. About App
Halaman About berisi informasi mengenai aplikasi, teknologi yang digunakan, arsitektur program, serta status sensor yang tersedia pada perangkat.

---

## 🛠️ Teknologi yang Digunakan

Dalam pembuatan aplikasi SensorCraft, beberapa teknologi yang digunakan yaitu:

- **Kotlin** sebagai bahasa pemrograman.
- **Jetpack Compose** untuk membuat tampilan aplikasi.
- **Material 3** sebagai desain antarmuka.
- **MVVM** untuk mengatur struktur aplikasi.
- **SQLite** untuk menyimpan data sensor secara lokal.
- **SensorManager** untuk mengakses sensor perangkat Android.
- **Coroutines dan StateFlow** untuk mengelola data secara asynchronous dan real-time.
- **Jetpack Compose Navigation** untuk berpindah antarhalaman.

### Struktur Arsitektur

Aplikasi menggunakan arsitektur MVVM yang terdiri dari tiga bagian utama:

- **Model**: Berisi data sensor dan pengelolaan database, seperti `SensorLog` dan `SensorDbHelper`.
- **View**: Bagian tampilan aplikasi, seperti Dashboard, History, Tools, About, dan beberapa komponen visual sensor.
- **ViewModel**: Mengatur data yang ditampilkan pada aplikasi dan menghubungkan Model dengan View melalui `SensorViewModel`.

---

## 📡 Sensor yang Digunakan

SensorCraft menggunakan tiga jenis sensor utama yang tersedia pada perangkat Android.

| Sensor | Fungsi |
|---|---|
| Accelerometer | Mengukur percepatan pada sumbu X, Y, dan Z. Digunakan untuk mendeteksi gerakan, menghitung magnitudo akselerasi, serta mengetahui sudut kemiringan perangkat. |
| Light Sensor | Mengukur intensitas cahaya di sekitar perangkat dalam satuan Lux. Data digunakan untuk menentukan kondisi pencahayaan dan memberikan rekomendasi penggunaan. |
| Magnetometer | Mengukur kekuatan medan magnet. Data sensor ini digunakan bersama Accelerometer untuk menentukan arah kompas. |

---

## 🎨 Tampilan Aplikasi

SensorCraft memiliki empat halaman utama yang dapat diakses melalui navigasi aplikasi.

1. **Dashboard**  
   Menampilkan data sensor secara real-time, status pergerakan, tingkat cahaya, arah kompas, dan tombol untuk menyimpan data.

2. **History**  
   Menampilkan data sensor yang sudah tersimpan, dilengkapi fitur pencarian, filter kategori, statistik, dan penghapusan data.

3. **Tools**  
   Berisi alat interaktif seperti Digital Waterpass, Kompas Digital, dan Lux Meter.

4. **About**  
   Berisi informasi mengenai aplikasi, teknologi yang digunakan, struktur arsitektur, serta ketersediaan sensor perangkat.

---

## 🚀 Cara Menjalankan Aplikasi

### Persyaratan
- Android Studio Ladybug atau versi terbaru.
- JDK 11 atau 17.
- Minimum Android 8.0 (API 26).
- Target SDK Android 16 (API 36).

### Langkah Instalasi

1. Download atau clone repository proyek SensorCraft.
   ```bash
   git clone <LINK_REPOSITORY_GITHUB_ANDA>
   ```

2. Buka Android Studio, lalu pilih **File → Open**.

3. Pilih folder proyek SensorCraft yang sudah di-download.

4. Tunggu proses Gradle Sync sampai selesai.

5. Hubungkan perangkat Android menggunakan USB Debugging atau jalankan melalui emulator yang mendukung virtual sensor.

6. Klik tombol **Run** atau tekan `Shift + F10` untuk menjalankan aplikasi.

---

SensorCraft dibuat sebagai proyek pembelajaran Android yang menggabungkan penggunaan sensor perangkat, tampilan data secara real-time, penyimpanan database lokal, dan pengembangan aplikasi menggunakan Kotlin serta Jetpack Compose.
