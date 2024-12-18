# **Analisis Sentimen Menggunakan Caikit dan Hugging Face**

## **Pendahuluan**

Proyek ini menunjukkan cara melakukan analisis sentimen menggunakan toolkit AI open-source **Caikit** dan model pre-trained dari **Hugging Face**. Model yang digunakan adalah **DistilBERT base uncased fine-tuned SST-2** dari Hugging Face, yang dirancang untuk mengklasifikasikan sentimen teks menjadi positif atau negatif.

Proyek ini mencakup:
- Server gRPC yang menyajikan model menggunakan runtime Caikit.
- Aplikasi klien untuk melakukan analisis sentimen dengan berinteraksi melalui runtime Caikit.

### **Apa itu Caikit?**
[Caikit](https://github.com/Caikit) adalah toolkit AI open-source yang menyediakan API ramah pengembang untuk mengelola model AI di berbagai domain data dan tugas. Caikit menyederhanakan integrasi model AI ke dalam aplikasi, sehingga pengembang dapat fokus menggunakan model tanpa perlu memahami detail internal yang kompleks.

---

## **Ringkasan Proyek**

### **Struktur Repository**

```
text-sentiment/
├── start_runtime.py                # Skrip untuk memulai runtime Caikit sebagai server gRPC.
├── client.py                       # Skrip klien untuk melakukan inferensi menggunakan runtime Caikit.
├── requirements.txt                # Dependensi pustaka Python.
├── models/                         # Direktori yang berisi metadata dan artefak model Caikit.
│   └── text_sentiment/
│       └── config.yml              # Metadata untuk model analisis sentimen.
├── text_sentiment/                 # Direktori yang mendefinisikan modul dan implementasi Caikit.
│   ├── config.yml                  # Konfigurasi untuk input dan output model.
│   ├── __init__.py                 # Membuat paket data_model dan runtime_model terlihat.
│   ├── data_model/                 # Mendefinisikan kelas data untuk model AI.
│   │   ├── classification.py       # Merepresentasikan atribut model AI dalam kode.
│   │   └── __init__.py             # Membuat kelas data model terlihat dalam proyek.
│   └── runtime_model/              # Mendefinisikan modul runtime untuk model.
│       ├── hf_module.py            # Mengintegrasikan model Hugging Face ke Caikit.
│       └── __init__.py             # Membuat modul runtime terlihat dalam proyek.
```

---

## **Tujuan Pembelajaran**

Dengan menyelesaikan proyek ini, Anda akan mempelajari cara:
1. Menginstal dan mengatur lingkungan runtime Caikit.
2. Membuat dan menjalankan aplikasi klien Python yang memanggil model analisis sentimen Hugging Face melalui runtime Caikit.
3. Melakukan inferensi sentimen dari teks dan menganalisis output yang dihasilkan.

---

## **Petunjuk Instalasi**

### **1. Clone Repository**
```bash
git clone https://github.com/<nama-repo-anda>/Sentiment-Analysis-using-Caikit-and-Hugging-Face.git
cd Sentiment-Analysis-using-Caikit-and-Hugging-Face
```

### **2. Instal Dependensi**
Pastikan Python 3.8+ sudah terinstal di sistem Anda. Kemudian, instal pustaka yang diperlukan:
```bash
pip install -r requirements.txt
```

---

## **Penggunaan**

### **1. Memulai Runtime Caikit**
Jalankan skrip **`start_runtime.py`** untuk memulai server gRPC yang menyajikan model analisis sentimen:
```bash
python start_runtime.py
```
- Skrip ini akan memuat model dan membuatnya tersedia untuk inferensi melalui antarmuka gRPC.

---

### **2. Menjalankan Klien untuk Inferensi**
Gunakan skrip **`client.py`** untuk mengirim teks ke server gRPC dan mendapatkan hasil analisis sentimen:
```bash
python client.py
```

#### **Contoh Input:**
```text
"Saya sangat menyukai produk ini! Hasilnya luar biasa dan melebihi ekspektasi saya."
```

#### **Contoh Output:**
```json
{
    "teks": "Saya sangat menyukai produk ini! Hasilnya luar biasa dan melebihi ekspektasi saya.",
    "sentimen": "positif",
    "kepercayaan": 0.95
}
```

---

## **Penjelasan File Utama**

### **1. `start_runtime.py`**
- Memulai runtime Caikit dan memuat model saat server dijalankan.
- Runtime ini menyediakan server gRPC untuk menangani permintaan inferensi.

### **2. `client.py`**
- Klien yang terhubung ke server gRPC yang dijalankan oleh runtime.
- Mengirimkan input teks dan mendapatkan hasil analisis sentimen.

### **3. `models/text_sentiment/config.yml`**
- Metadata yang mendefinisikan model Caikit, termasuk lokasi artefak model Hugging Face.

### **4. `text_sentiment/runtime_model/hf_module.py`**
- Mengintegrasikan model Hugging Face agar kompatibel dengan runtime Caikit.

---

## **Alur Pembelajaran**

1. Jalankan runtime Caikit dengan model Hugging Face yang sudah dikonfigurasi.
2. Gunakan aplikasi klien Python untuk mengirim teks input dan menerima hasil analisis sentimen.
3. Kembangkan proyek ini lebih lanjut dengan mengganti model Hugging Face atau menambahkan fungsionalitas baru pada runtime Caikit.

---

## **Kontribusi**

Kontribusi sangat diterima! Untuk berkontribusi:
1. Fork repository ini.
2. Buat branch baru: `git checkout -b nama-branch-fitur`.
3. Commit perubahan Anda: `git commit -m "Tambah fitur"`.
4. Push branch ke repository Anda: `git push origin nama-branch-fitur`.
5. Buat pull request.

---

## **Referensi**
- [Dokumentasi Caikit](https://github.com/Caikit)
- [Hugging Face](https://huggingface.co)
