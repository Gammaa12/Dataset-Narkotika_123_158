# ⚖️ Dataset Narkotika – Pengadilan Negeri Malang

---

## 📘 Deskripsi Umum

Dokumen **putusan pengadilan** merupakan sumber pengetahuan terbuka yang sangat penting dalam pengembangan sistem **Temu Kembali Informasi (TKI)** pada domain hukum.  
Repositori ini menyajikan **50 putusan perkara pidana khusus Narkotika dan Psikotropika** yang diperoleh dari situs resmi  
👉 [Direktori Putusan Mahkamah Agung RI](https://putusan3.mahkamahagung.go.id/direktori.html).

Seluruh dataset diambil dari **Pengadilan Negeri Kota Malang** untuk rentang waktu **2023–2025**, dengan fokus pada perkara **Narkotika Golongan I (Sabu)**.  
Dataset ini digunakan sebagai bahan analisis dan implementasi sistem TKI berbasis **pencarian dokumen hukum**.

---

## 🗂️ Struktur Direktori Repository

Dataset-Narkotika
│
├── Dataset/
│ └── Narkotika.zip # Berisi 50 dokumen putusan (.pdf)
│
├── Overview/
│ └── Overview.xlsx # Ringkasan metadata dari seluruh putusan
│
└── README.md # Dokumentasi proyek


> 💡 Penamaan repository mengikuti format:  
> `Dataset-Narkotika_<3digit NIM Anggota1>_<3digit NIM Anggota2>`  
> Contoh: `Dataset-Narkotika_123_456`

---

## 🧾 Struktur Dataset (Overview.xlsx)

File `Overview.xlsx` berisi **ringkasan metadata** dari setiap putusan pengadilan.  
Struktur kolom mengikuti format berikut:

| No | No Putusan | Lembaga Peradilan | Barang Bukti | Amar Putusan |
|----|-------------|-------------------|---------------|---------------|
| 1  | 408/Pid.Sus/2021/PN Mlg | Pengadilan Negeri Malang | Narkotika jenis sabu-sabu dalam 4 plastik klip (berat bersih 7,42 gram); 1 timbangan digital; 1 HP Vivo hitam | Terdakwa terbukti secara sah dan meyakinkan bersalah melakukan tindak pidana narkotika. Dihukum 7 tahun penjara dan denda Rp1.000.000.000,-. |

> Seluruh kolom disusun untuk mempermudah pemrosesan metadata dalam sistem TKI (Information Retrieval System).

---

## 📊 Ringkasan Dataset

| Keterangan | Nilai |
|-------------|-------|
| **Jumlah Dokumen** | 50 putusan |
| **Sumber Data** | Direktori Putusan MA RI |
| **Lembaga Peradilan** | Pengadilan Negeri Kota Malang |
| **Jenis Perkara** | Narkotika dan Psikotropika |
| **Periode Tahun** | 2025 |
| **Format File** | PDF & XLSX |
| **Total Atribut Metadata** | 5 (No, Nomor Putusan, Lembaga, Barang Bukti, Amar Putusan) |

---

## ⚙️ Tahapan Akuisisi dan Pengolahan Data

1. **Pengumpulan Data**  
   - 50 putusan diunduh manual dari situs [putusan3.mahkamahagung.go.id](https://putusan3.mahkamahagung.go.id/direktori.html)  
   - Kategori: *Pidana Khusus → Narkotika dan Psikotropika*  
   - Pengadilan: **PN Kota Malang**  
   - Status perkara: *Belum Berkekuatan Hukum Tetap*

2. **Ekstraksi Metadata**  
   - Dilakukan dengan membaca file PDF dan mengekstrak bagian penting:  
     - Nomor Putusan  
     - Identitas Pengadilan  
     - Barang Bukti  
     - Amar Putusan  
   - Proses manual + semi-otomatis dengan Python (`pdfplumber`, `pandas`)

3. **Pembersihan dan Standarisasi Data**  
   - Penghapusan karakter tidak relevan  
   - Standarisasi penulisan nama lembaga dan format nomor putusan  
   - Penulisan amar putusan dalam bentuk **paragraf naratif** agar mudah dipahami

4. **Penyimpanan Dataset**  
   - Dataset akhir dikompresi menjadi file `Narkotika.zip`
   - Metadata disimpan di `Overview.xlsx`

---

## 🧠 Potensi Pemanfaatan

Dataset ini dapat digunakan untuk berbagai tujuan di bidang **Information Retrieval dan LegalTech**, di antaranya:
- Pembangunan **mesin pencari dokumen hukum** berbasis metadata.
- Pengembangan **chatbot hukum** untuk menjawab pertanyaan terkait putusan pengadilan.
- Pelatihan model **Natural Language Processing (NLP)** dalam domain hukum.
- Analisis pola **putusan narkotika** berdasarkan barang bukti dan lama hukuman.

---

## 🔬 Teknologi dan Tools yang Digunakan

| Kategori | Tools / Framework |
|-----------|------------------|
| **Bahasa Pemrograman** | Python 3.10 |
| **Library Pengolahan Data** | Pandas, OpenPyXL |
| **Library PDF Parsing** | pdfplumber, PyPDF2 |
| **Manajemen File** | Git & GitHub |
| **Dokumentasi & Visualisasi** | Markdown, Excel |

---

## 💡 Contoh Ringkasan Amar Putusan

> **Nomor:** 250/Pid.Sus/2025/PN Mlg  
> **Terdakwa:** HENDRA KURNIAWAN Als GENDUT Bin Alm SUGIONO  
> **Amar Putusan:**  
> Terdakwa terbukti secara sah dan meyakinkan bersalah melakukan tindak pidana *“tanpa hak menjadi perantara dalam jual beli Narkotika Golongan I”*.  
> Dihukum dengan **penjara 6 tahun 6 bulan** dan **denda Rp1.000.000.000,-** subsidiair **3 bulan kurungan**.  
> Barang bukti berupa sabu 1,93 gram, handphone, dan motor Honda Vario dirampas untuk dimusnahkan.  
> Biaya perkara dibebankan sebesar Rp5.000,-.

---

## 👥 Tim Penyusun

| Nama | NIM | Peran |
|------|-----|-------|
| [Maylani Kusuma Wardhani] | [202210370311123] | Pengumpulan Data & Pembersihan Metadata |
| [Garin Muhammad Akbar] | [202210370311158] | Dokumentasi & Pembuatan Dataset |

---

## 📜 Lisensi dan Etika Penggunaan

Dataset ini bersifat **terbuka (Open Data)** untuk kepentingan akademik dan penelitian.  
Sumber asli berasal dari situs resmi **Mahkamah Agung Republik Indonesia** dan tidak melanggar Hak Kekayaan Intelektual (HaKI).

> Mohon mencantumkan atribusi jika menggunakan dataset ini dalam publikasi ilmiah atau proyek penelitian.  

**Sumber resmi:** [putusan3.mahkamahagung.go.id](https://putusan3.mahkamahagung.go.id)


---

> — *Tim Dataset Narkotika PN Malang*
