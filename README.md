# pinetoken

**pinetoken** adalah aplikasi Command Line Interface (CLI) untuk mengelola token rahasia (seperti GitHub Token, API Key, dsb) secara aman dan terenkripsi di komputer lokal.

## Fitur

- Inisialisasi penyimpanan dan proteksi dengan master password
- Menambahkan token baru dengan enkripsi
- Menampilkan daftar semua token
- Melihat detail token tertentu
- Menghapus token berdasarkan nama
- Mengekspor data token ke file eksternal

---

## Instalasi

### 1. Clone Repository

```bash
$ git clone https://github.com/username/pinetoken.git
$ cd pinetoken
```

### 2. Buat Virtual Environment (Opsional tapi Direkomendasikan)

```bash
$ python -m venv venv
$ source venv/bin/activate      # Untuk Linux/macOS
$ .\venv\Scripts\activate       # Untuk Windows
```

### 3. Install Dependency

```bash
$ pip install -r requirements.txt
```

Jika tidak ada file `requirements.txt`, Anda bisa langsung install:

```bash
$ pip install cryptography tabulate
```

---

## Cara Menggunakan

### 1. Inisialisasi Penyimpanan

```bash
$ python main.py --init
```

Ini akan membuat file `pinetokeninit.opine` dan meminta Anda membuat password master.

### 2. Menambahkan Token

```bash
$ python main.py --add \
  -s github \
  -n "GitHub Token" \
  -d "Token untuk akses API GitHub" \
  -t ghp_xxx123 \
  -e 2025-12-31 \
  -l "https://github.com"
```

### 3. Menampilkan Semua Token

```bash
$ python main.py --list
```

### 4. Melihat Detail Token

```bash
$ python main.py --show "GitHub Token"
```

### 5. Menghapus Token

```bash
$ python main.py --del "GitHub Token"
```

### 6. Mengekspor Token ke File JSON

```bash
$ python main.py --export
```

---

## Struktur Proyek

```
pinetoken/
├── main.py
├── requirements.txt
├── README.md
├── pinetokeninit.opine
└── function/
    ├── __init__.py
    ├── utils.py
    ├── add.py
    ├── delete.py
    ├── export.py
    ├── init.py
    ├── list.py
    ├── show.py
```

---

## Catatan Keamanan

- Token disimpan dalam file lokal `pinetokeninit.opine` dalam bentuk terenkripsi menggunakan password master.
- Simpan backup password Anda dengan aman, karena jika lupa, data tidak bisa didekripsi kembali.
- File `.opine` tidak boleh dibagikan atau dikirim melalui jaringan publik.

---

## Lisensi

MIT License - bebas digunakan, dimodifikasi, dan didistribusikan.

```

Kalau kamu mau versi yang support markdown untuk GitHub (dengan badge, link navigasi, dsb), tinggal bilang aja, nanti aku bantu tambahkan.