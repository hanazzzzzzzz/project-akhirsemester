# SensorCraft - Smart Environment & Motion Activity Logger 🚀

**SensorCraft** adalah aplikasi Android berbasis **Kotlin Jetpack Compose** yang dirancang untuk memantau, menganalisis, dan mencatat data sensor fisik perangkat secara *real-time*. Aplikasi ini menerapkan arsitektur **MVVM (Model-View-ViewModel)** serta menggunakan **Database SQLite** untuk penyimpanan data snapshot sensor secara lokal.

---

## 📱 Fitur-Fitur Utama Aplikasi

1. **Real-Time Sensor Dashboard**:
   - Monitoring data sensor Motion (Accelerometer), Environment (Light Sensor), dan Position (Magnetometer/Compass) secara langsung.
   - Status indikator pergerakan (*Stationary*, *Walking*, *Active Shake*) dan perhitungan sudut Kemiringan (*Pitch & Roll*).
   - Pengukur tingkat pencahayaan (Lux) beserta kategori kondisi ruangan dan rekomendasi kenyamanan mata.
   - Pembacaan kompas 360° lengkap dengan 8 arah mata angin (N, NE, E, SE, S, SW, W, NW) dan kekuatan medan magnet (µT).

2. **Penyimpanan Snapshot Data ke Database SQLite**:
   - Tombol cepat **"Log to SQLite"** untuk menyimpan status sensor saat ini.
   - Input judul log, tag kategori (*Desk Work*, *Outdoor Walk*, *Gym / Active*, *Night Reading*, *Travel*), serta catatan/observasi.

3. **Manajemen & Analisis Riwayat (History Logs)**:
   - Menampilkan seluruh catatan snapshot sensor yang tersimpan di database SQLite.
   - Pencarian cerdas (*Search bar*) berdasarkan judul, catatan, atau kategori sensor.
   - Filter data berdasarkan Tag kategori.
   - Ringkasan statistik otomatis (Total logs, Rata-rata Lux, Puncak Akselerasi).
   - Fitur menghapus log individual maupun mengosongkan seluruh isi database SQLite.

4. **Alat Interaktif Sensor (Interactive Sensor Tools)**:
   - **Waterpass Digital (Spirit Level)**: Visualisasi gelembung air bergerak pada target lingkaran menggunakan *Canvas* Compose berbasis data Accelerometer.
   - **Kompas 360° Interaktif**: Dial kompas digital dengan jarum petunjuk arah utara (Merah) yang berputar halus berbasis Magnetometer.
   - **Lux Evaluator Bar**: Gauge visualisasi intensitas cahaya berbasis pencahayaan lingkungan.

5. **Halaman Info & Status Hardware (About App)**:
   - Rincian teknologi, arsitektur MVVM, dan status ketersediaan sensor hardware pada perangkat.

---

## 🛠️ Teknologi & Arsitektur

- **Bahasa Pemrograman**: Kotlin (Modern & Idiomatic)
- **UI Framework**: Jetpack Compose dengan Material 3 Design
- **Arsitektur**: MVVM (Model - View - ViewModel)
  - **Model**: `SensorLog`, `SensorDbHelper` (SQLite Database)
  - **View**: `DashboardScreen`, `HistoryScreen`, `ToolsScreen`, `AboutScreen`, `SaveSnapshotDialog`, `CompassDialView`, `SpiritLevelView`
  - **ViewModel**: `SensorViewModel` mengelola `StateFlow<SensorUiState>`
- **Database**: SQLite (`android.database.sqlite.SQLiteOpenHelper`)
- **Sensors API**: Android `SensorManager`, `SensorEventListener`
- **Asynchronous & Reactive**: Kotlin Coroutines & StateFlow
- **Navigation**: Jetpack Compose Navigation (`NavHost`)

---

## 📡 Sensor yang Digunakan & Fungsinya

Aplikasi ini mengintegrasikan **3 Sensor Hardware** dari 3 kategori berbeda:

| Kategori Sensor | Tipe Sensor | Fungsi & Penerapan dalam Aplikasi |
| :--- | :--- | :--- |
| **Motion Sensor** | `Sensor.TYPE_ACCELEROMETER` | Mengukur percepatan 3-aksis (X, Y, Z), menghitung total magnitudo akselerasi (m/s²), menentukan status aktivitas (*Stationary*, *Walking*, *Active Shake*), serta mengukur sudut kemiringan *Pitch* & *Roll* untuk alat Waterpass Digital (*Spirit Level*). |
| **Environment Sensor** | `Sensor.TYPE_LIGHT` | Mengukur tingkat intensitas pencahayaan lingkungan sekitar dalam satuan Lux (lx), mengklasifikasikan kondisi cahaya (Gelap, Dim, Kamar, Kantor Terang, Daylight), serta memberikan rekomendasi kesehatan mata. |
| **Position Sensor** | `Sensor.TYPE_MAGNETIC_FIELD` | Mengukur kekuatan medan magnet (µT) dan dikombinasikan dengan Accelerometer untuk menghitung derajat sudut kompas azimuth (0° - 360°) dan penentuan 8 arah mata angin utama. |

---

## 🎨 Tampilan Aplikasi (UI Screens)

Aplikasi memiliki 4 Navigasi Utama:
1. **Dashboard Tab**: Tampilan kartu monitor data sensor *real-time* & Floating Action Button simpan ke SQLite.
2. **History Tab**: Daftar log SQLite, ringkasan statistik, filter chip tag, dan bilah pencarian.
3. **Tools Tab**: Tampilan visualisasi Waterpass (Spirit Level), Kompas Dial 360°, dan Lux Meter.
4. **About Tab**: Informasi arsitektur MVVM, SQLite DB, dan daftar checklist kelengkapan proyek.

---

## 🚀 Cara Menjalankan Aplikasi

### Persyaratan Sistem:
- **Android Studio**: Ladybug / 2024.1+
- **JDK**: Version 11 atau 17
- **Min SDK**: Android 8.0 (API Level 26)
- **Target SDK**: Android 16 (API Level 36)

### Langkah-Langkah:
1. **Clone / Download Repository**:
   ```bash
   git clone <LINK_REPOSITORY_GITHUB_ANDA>
   ```
2. **Buka Proyek di Android Studio**:
   - Buka Android Studio -> `File` -> `Open` -> Pilih folder proyek `SensorCraft`.
3. **Sync Gradle Project**:
   - Tunggu proses Gradle Build & Dependencies Sync hingga selesai.
4. **Jalankan Proyek**:
   - Hubungkan HP Android asli via USB Debugging (Disarankan agar dapat mencoba sensor fisik) atau gunakan Android Emulator (Virtual Sensors di Extended Controls).
   - Tekan tombol **Run 'app'** (`Shift + F10`).
