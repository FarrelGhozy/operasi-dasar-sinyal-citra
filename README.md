# Eksperimen Operasi Dasar pada Sinyal dan Citra

**Mata Kuliah:** Pengolahan Sinyal Digital

**Nama:** Farrel Ghozy Affifudin — **NIM:** 452024611053 — **Kelas:** TI 5 A2

**Link Repository:** [github.com/FarrelGhozy/operasi-dasar-sinyal-citra](https://github.com/FarrelGhozy/operasi-dasar-sinyal-citra.git)

**Topik:** Operasi penjumlahan, penggeseran, amplifikasi, superposisi, sistem linier, dan aplikasi nyata pada sinyal 1D dan citra 2D

## Deskripsi Project

Project ini berisi eksperimen berbasis Python untuk menerapkan operasi dasar pada sinyal 1D dan citra 2D. Setiap operasi dilengkapi dengan visualisasi, analisis efek, dan penjelasan konseptual.

### Operasi yang Dicakup:
1. **Sinyal 1D:** Penjumlahan, penggeseran, amplifikasi
2. **Citra 2D:** Penjumlahan, penggeseran (translasi), amplifikasi
3. **Uji Sistem Linier:** Homogenitas, additivitas, perbandingan linier vs non-linier
4. **Analisis HOTS:** Analisis konseptual, studi kasus (audio mixing), skenario keputusan

## Library yang Digunakan

- **NumPy** — Operasi numerik dan array
- **Matplotlib** — Visualisasi dan plotting
- **OpenCV (cv2)** — Operasi citra
- **PIL (Pillow)** — Input/output citra

## Cara Menjalankan Notebook

### 1. Install dependencies
```bash
pip install -r requirements.txt
```

### 2. Jalankan Jupyter Notebook
```bash
jupyter notebook notebook/operasi_sinyal_citra.ipynb
```

Atau via VS Code:
```bash
code notebook/operasi_sinyal_citra.ipynb
```

### 3. Compile ulang laporan (jika diperlukan)
```bash
cd report && pdflatex laporan.tex
```

## Struktur Folder Project

```
operasi-dasar-sinyal-citra/
├── notebook/
│   └── operasi_sinyal_citra.ipynb   # Jupyter Notebook utama
├── images/
│   ├── citra_asli.jpg               # Citra untuk operasi (shapes)
│   ├── citra1.jpg                   # Citra gradient
│   ├── citra2.jpg                   # Citra checkerboard
│   ├── various_plot_outputs.png     # Hasil plot dari notebook
├── report/
│   ├── laporan.pdf                  # Laporan PDF
│   └── laporan.tex                  # Source LaTeX laporan
├── README.md
└── requirements.txt
```

## Ringkasan Hasil Eksperimen

**Sinyal 1D:**
- Penjumlahan menyebabkan superposisi amplitudo (DC shift pada n >= 5)
- Penggeseran dengan k positif = delay, k negatif = advance
- Amplifikasi dengan alpha > 1 memperkuat, alpha < 1 memperlemah, alpha negatif membalik fasa

**Citra 2D:**
- Penjumlahan citra harus dengan ukuran sama; clipping vs normalisasi memberikan hasil berbeda
- Translasi menggeser posisi objek, menyisakan area kosong
- Amplifikasi meningkatkan brightness namun risiko saturasi pada alpha > 1.5

**Sistem Linier:**
- T1(x) = 2x: linier (memenuhi homogenitas dan additivitas)
- T2(x) = x^2: non-linier (gagal pada kedua uji karena suku alpha^2 dan suku silang)

## Kesimpulan

Operasi sederhana seperti penjumlahan, penggeseran, dan amplifikasi adalah blok bangunan fundamental dari konsep yang lebih besar dalam Pengolahan Sinyal Digital — superposisi, sistem linier, filtering, dan augmentasi citra. Sistem linier memungkinkan penggunaan prinsip superposisi untuk analisis yang lebih kompleks.

## Refleksi Pribadi

1. **Operasi mana yang paling mudah dipahami? Mengapa?** — Amplifikasi, karena hanya perkalian skalar yang intuitif — memperbesar/memperkecil nilai sinyal secara proporsional.

2. **Operasi mana yang paling sulit diimplementasikan? Mengapa?** — Penggeseran dengan zero-padding, karena perlu menangani batas sinyal dengan benar agar tidak terjadi wraparound yang salah.

3. **Apa perbedaan utama antara operasi pada sinyal 1D dan citra 2D?** — Citra memiliki dua dimensi spasial dan tiga channel warna (RGB), sehingga operasi dilakukan pada matriks 3D, bukan vektor 1D.

4. **Apa hal baru yang Anda pahami tentang sistem linier?** — Fungsi sesederhana x² saja sudah cukup untuk mematahkan sifat linier karena menghasilkan suku silang 2x₁x₂ yang melanggar additivitas.

5. **Jika konsep ini digunakan dalam aplikasi nyata, bagian mana yang menurut Anda paling penting?** — Konsep superposisi dan linieritas merupakan dasar dari filtering, kompresi, dan analisis spektrum dalam DSP.
