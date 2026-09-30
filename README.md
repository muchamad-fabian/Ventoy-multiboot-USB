# Ventoy Multiboot USB

Panduan membuat flashdisk 16 GB menjadi USB multiboot menggunakan Ventoy untuk Windows 10 Maupun SystemBOOT lain.

Flashdisk juga dapat digunakan untuk menyimpan file pribadi.

---

## Target

Struktur flashdisk yang digunakan:

```text
Ventoy (E:)
├── DATA
│   ├── Skripsi
│   ├── Dokumen
│   ├── Software
│   └── Backup
│
└── ISO
    ├── Win10_22H2_English_x64v1.iso
    └── Linux.iso
```

---

## 1. Perangkat dan File yang Dibutuhkan

- Komputer Windows 11 64-bit
- Flashdisk 16 GB
- Ventoy
- Windows 10 ISO
- Linux ISO

> **Peringatan:** Instalasi Ventoy akan menghapus seluruh isi flashdisk.

Pastikan flashdisk yang digunakan memang flashdisk yang ingin diproses.

---

## 2. Download Ventoy

Gunakan halaman resmi Ventoy:

**Official Website:**

https://www.ventoy.net/en/download.html

Pada panduan ini digunakan Ventoy untuk Windows.

Contoh file:

```text
ventoy-1.1.17-windows.zip
```

---

## 3. Download Windows 10 ISO

Windows 10 ISO yang digunakan:

https://drive.google.com/file/d/14bDetBitELUgBwHpBSvDbkGkxUXdM4MG/view?usp=sharing

File yang digunakan:

```text
Win10_22H2_English_x64v1.iso
```

Informasi file:

```text
Win10      = Windows 10
22H2       = Version 22H2
English    = Bahasa Inggris
x64        = 64-bit
.iso       = Disk Image
```

Ukuran file sekitar:

```text
5.7 GB
```

### Catatan

Windows dapat menampilkan ikon WinRAR pada file ISO jika WinRAR terasosiasi dengan ekstensi `.iso`.

Hal tersebut normal.

Pastikan nama file tetap:

```text
Win10_22H2_English_x64v1.iso
```

Jangan mengubahnya menjadi `.rar` dan jangan melakukan extract.

---

## 4. Extract Ventoy

Setelah download Ventoy:

1. Klik kanan file ZIP.
2. Pilih **Extract All**.
3. Buka folder hasil extract.
4. Cari:

```text
Ventoy2Disk.exe
```

---

## 5. Colokkan Flashdisk

Colokkan flashdisk 16 GB ke komputer.

Kemudian jalankan:

```text
Ventoy2Disk.exe
```

Gunakan:

```text
Run as administrator
```

---

## 6. Periksa Device

Setelah Ventoy terbuka, perhatikan bagian:

```text
Device
```

Pastikan device yang dipilih adalah flashdisk 16 GB.

Contoh:

```text
Device: USB Flashdisk (~16 GB)
```

### Sangat penting

Jangan memilih:

```text
C:
D:
SSD Internal
HDD Internal
```

Karena instalasi Ventoy akan memformat device yang dipilih.

---

## 7. Pengaturan Ventoy

Untuk komputer modern dengan UEFI gunakan:

```text
Partition Style: GPT
Secure Boot Support: Enabled
```

Konfigurasi:

```text
Device        : Flashdisk 16 GB
Partition     : GPT
Secure Boot   : ✓
```

Setelah memastikan device benar, klik:

```text
Install
```

Konfirmasi peringatan yang muncul.

Tunggu sampai instalasi selesai.

---

## 8. Membuat Folder

Setelah Ventoy selesai di-install, buka flashdisk.

Contoh:

```text
Ventoy (E:)
```

Buat dua folder:

```text
DATA
ISO
```

Hasilnya:

```text
Ventoy (E:)
├── DATA
└── ISO
```

---

## 9. Memasukkan Windows 10 ISO

Buka:

```text
E:\ISO
```

Kemudian copy file:

```text
Win10_22H2_English_x64v1.iso
```

ke folder tersebut.

Hasil:

```text
Ventoy (E:)
├── DATA
└── ISO
    └── Win10_22H2_English_x64v1.iso
```

### Jangan extract ISO

File harus tetap dalam bentuk:

```text
.iso
```

Jangan mengubah ISO menjadi folder.

---

## 10. Memasukkan Linux ISO

Download ISO Linux yang ingin digunakan.

Kemudian copy ISO Linux ke:

```text
E:\ISO
```

Contoh:

```text
Ventoy (E:)
├── DATA
└── ISO
    ├── Win10_22H2_English_x64v1.iso
    └── Linux.iso
```

Ventoy akan mendeteksi ISO tersebut secara otomatis ketika USB digunakan untuk boot.

---

## 11. Menyimpan File Pribadi

Folder:

```text
DATA
```

digunakan untuk menyimpan file biasa.

Contoh:

```text
Ventoy (E:)
├── DATA
│   ├── Skripsi
│   ├── Dokumen
│   ├── Software
│   └── Backup
│
└── ISO
    ├── Win10_22H2_English_x64v1.iso
    └── Linux.iso
```

File yang dapat disimpan:

- PDF
- DOCX
- ZIP
- Foto
- Video
- Software
- File skripsi
- File backup

---

## 12. Cara Boot

Colokkan flashdisk ke komputer.

Restart komputer dan masuk ke **Boot Menu**.

Tombol Boot Menu berbeda tergantung motherboard atau laptop.

Contoh tombol yang umum digunakan:

```text
F12
F11
F9
ESC
```

Pilih USB atau flashdisk sebagai perangkat boot.

Setelah berhasil boot, Ventoy akan menampilkan daftar ISO.

Contoh:

```text
Ventoy Boot Menu

> Win10_22H2_English_x64v1.iso
  Linux.iso
```

Pilih ISO yang ingin dijalankan.

---

## 13. Cara Kerja

Alur penggunaan:

```text
Flashdisk
    ↓
Ventoy
    ↓
Boot Menu
    ↓
┌─────────────────────────┐
│ Windows 10 ISO          │
│ Linux ISO               │
└─────────────────────────┘
    ↓
Pilih sistem
```

Ventoy memungkinkan beberapa file ISO disimpan dalam satu USB tanpa harus membuat USB bootable terpisah untuk setiap ISO.

---

## 14. Keterbatasan Flashdisk 16 GB

Flashdisk yang digunakan hanya memiliki kapasitas 16 GB.

Windows 10 ISO pada panduan ini berukuran sekitar:

```text
5.7 GB
```

Linux ISO biasanya membutuhkan beberapa GB tambahan.

Contoh:

```text
16 GB Flashdisk
│
├── Ventoy
├── Windows 10 ISO    ~5.7 GB
├── Linux ISO         ~2-4 GB
└── DATA              Sisa kapasitas
```

Karena kapasitas terbatas, jangan menyimpan terlalu banyak ISO atau file berukuran besar.

Untuk penggunaan yang lebih luas, kapasitas berikut lebih nyaman:

```text
32 GB   = penggunaan ringan
64 GB   = lebih nyaman
128 GB  = cocok untuk banyak ISO + file pribadi
```

---

## 15. Catatan Penting

### Jangan salah memilih Device

Saat menggunakan:

```text
Ventoy2Disk.exe
```

pastikan device yang dipilih adalah flashdisk 16 GB.

### Jangan extract ISO

Tetap gunakan:

```text
Windows10.iso
Linux.iso
```

### Tidak perlu Rufus

Setelah Ventoy terpasang, tidak perlu menggunakan Rufus untuk membuat masing-masing ISO menjadi bootable.

Cukup:

```text
Download ISO
      ↓
Copy ISO ke E:\ISO
      ↓
Boot dari USB
      ↓
Pilih ISO
```

---

## 16. Hasil Akhir

Flashdisk 16 GB dapat digunakan sebagai:

```text
USB Multiboot
│
├── Windows 10
├── Linux
└── File Pribadi
```

Struktur akhir:

```text
Ventoy (E:)
├── DATA
│   ├── Skripsi
│   ├── Dokumen
│   ├── Software
│   └── Backup
│
└── ISO
    ├── Win10_22H2_English_x64v1.iso
    └── Linux.iso
```

---

## Download

### Ventoy

https://www.ventoy.net/en/download.html

### Windows 10 ISO

https://drive.google.com/file/d/14bDetBitELUgBwHpBSvDbkGkxUXdM4MG/view?usp=sharing
