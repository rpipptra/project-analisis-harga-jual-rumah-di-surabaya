# project-analisis-harga-jual-rumah-di-surabaya

**Berdasarkan Karakteristik Properti, Aksesibilitas Sekolah ABK, dan Kepadatan Penduduk**

Project ini merupakan tugas akhir mata kuliah **Data Wrangling** yang bertujuan untuk menganalisis faktor-faktor yang memengaruhi harga jual rumah di Surabaya. Penelitian ini menggabungkan tiga sumber data utama, melakukan pembersihan data secara menyeluruh, serta menghasilkan sebuah dataset final yang siap digunakan untuk analisis dan pemodelan prediksi.

**Latar Belakang**

Kota Surabaya memiliki pertumbuhan penduduk dan kebutuhan hunian yang terus meningkat. Harga rumah di tiap kecamatan sangat bervariasi karena dipengaruhi banyak faktor—mulai dari karakteristik fisik bangunan, kondisi lingkungan, hingga keberadaan fasilitas publik seperti sekolah anak berkebutuhan khusus (ABK). Oleh karena itu, diperlukan pengolahan data yang tepat agar hubungan antar variabel dapat dianalisis secara akurat.

**Tujuan Project**

* Membuat dataset bersih hasil penggabungan data dari tiga sumber berbeda.
* Menganalisis pengaruh karakteristik properti, aksesibilitas sekolah ABK, dan kepadatan penduduk terhadap harga rumah.
* Melakukan Exploratory Data Analysis (EDA) untuk melihat pola hubungan antar variabel.
* Menyediakan dataset final yang siap digunakan untuk pemodelan machine learning.

**Dataset yang Digunakan**

1. **Data Properti Surabaya** — memuat harga rumah, luas bangunan, luas tanah, jumlah kamar, dan kecamatan.
2. **Data Sekolah & Siswa Inklusi (2025)** — berisi jumlah sekolah inklusi dan siswa inklusi per kecamatan.
3. **Data Kepadatan Penduduk Surabaya (2024)** — diperoleh dari BPS Surabaya.

Semua dataset memiliki struktur berbeda sehingga membutuhkan proses wrangling yang cukup kompleks sebelum dapat dianalisis.

---

**Tahapan Data Wrangling**

Proses wrangling dilakukan melalui beberapa tahap besar:

**1. Memuat Dataset**

Ketiga dataset dimuat menggunakan `pandas.read_excel()`.

**2. Pembersihan Data**

* Menghapus header rusak dan baris kosong.
* Standarisasi nama kecamatan menggunakan format uppercase + strip.
* Mengonversi kolom numerik yang masih berupa teks.
* Membersihkan simbol, spasi, dan karakter non-angka pada kolom kepadatan.
* Mengisi nilai hilang (missing value) menggunakan median untuk numerik dan `"Tidak Ada"` untuk non-numerik.

**3. Integrasi Dataset (Merging)**

Proses penggabungan dilakukan berdasarkan kolom *Kecamatan* menggunakan metode `pandas.merge()`. Setelah merge, dilakukan validasi untuk memastikan tidak ada kecamatan yang hilang atau duplikat.

**4. Final Cleaning**

* Konversi ulang semua kolom numerik.
* Mengisi ulang nilai hilang yang tersisa.
* Menyimpan dataset sebagai file CSV:
  **`data_rumah_wrangled.csv`**

 **Exploratory Data Analysis (EDA)**

Analisis eksploratif dilakukan untuk memahami:

* Distribusi harga rumah.
* Hubungan harga dengan luas bangunan dan kepadatan penduduk.
* Korelasi antar variabel utama menggunakan heatmap.

Visualisasi dibuat menggunakan **Matplotlib** dan **Seaborn**.

**Kendala yang Dihadapi**

* Perbedaan format penulisan kecamatan antar dataset.
* Kolom numerik berisi teks, tanda baca, atau simbol.
* Banyak nilai hilang pada dataset sekolah dan properti.
* Struktur dataset tidak seragam sehingga proses merge perlu pengecekan berulang.

**Kesimpulan**

Hasil analisis menunjukkan bahwa:

* Karakteristik properti seperti luas bangunan dan luas tanah memiliki pengaruh paling kuat terhadap harga rumah.
* Kepadatan penduduk berpengaruh namun tidak sepenuhnya linear.
* Aksesibilitas terhadap sekolah ABK dapat menjadi nilai tambah bagi pembeli tertentu.
* Data wrangling sangat penting untuk memastikan dataset bersih dan siap dianalisis.

**Tim Penyusun**

* **Hulwah Fatin Fathinah (24031554007)**
* **Rafif Fadhillah Putra Zainuri (24031554185)**
*  **Prodi S1 Sains Data, Universitas Negeri Surabaya.**

Tinggal bilang saja!
