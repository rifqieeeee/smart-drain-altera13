SURABAYA SMART DRAINAGE AI + WATER LEVEL

Fungsi:
1. TensorFlow.js / Teachable Machine mengklasifikasi penyebab gangguan drainase.
2. JavaScript membaca tanda warna pada dinding drainase untuk menentukan ketinggian air.
3. Status ketinggian air: BLUE = AMAN, GREEN = SIAGA, RED = DARURAT.
4. Peta dan prioritas petugas memakai status ketinggian air; hasil AI ditampilkan sebagai penyebab.

LOGIKA MARKER FISIK
Pasang marker vertikal dari bawah ke atas:
- BLUE (paling bawah)
- GREEN (tengah)
- RED (paling atas)

Ketika air naik, marker tertutup dari bawah ke atas:
- Blue terlihat -> AMAN
- Blue tidak terlihat, Green terlihat -> SIAGA
- Blue + Green tidak terlihat, Red terlihat -> DARURAT
- Tidak ada marker terbaca -> BELUM TERBACA (cek posisi/ROI/pencahayaan)

ROI dan threshold HSV mengikuti kode Python yang diberikan pengguna.
MIN_COLOR_PERCENTAGE = 3.0%.

JALANKAN
Buka terminal pada folder ini:
  python -m http.server 8000
Lalu buka:
  http://localhost:8000

CATATAN
- Jangan buka index.html melalui file:// karena browser dapat memblokir kamera/model.
- Jika posisi kamera berubah, edit POLYGON_RATIO di index.html.
- Jika marker SIAGA nantinya menggunakan kuning, rentang HSV GREEN perlu diganti dengan HSV kuning.
