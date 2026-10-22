# NASA POWER Climate Analysis (2016–2025)

Proyek ini menyediakan workflow lengkap untuk:

- mendownload data harian NASA POWER untuk rentang 2016–2025
- menyimpan satu file CSV per tahun dalam folder `data/raw/`
- menggabungkan semua CSV menjadi satu data master
- melakukan validasi data (nilai kosong, tidak valid, tanggal duplikat)
- menghitung ringkasan bulanan dan tahunan
- menyimpan hasil dalam folder `data/processed/`
- menjelaskan pola cuaca dan keterbatasan data di notebook `.ipynb`

## Koordinat yang digunakan

Koordinat yang digunakan untuk semua tahun adalah:

- latitude: -7.250445
- longitude: 112.768845

Koordinat ini dipilih sebagai contoh lokasi yang tetap untuk seluruh periode analisis.

## Parameter yang diunduh

- T2M: average temperature at 2 meters (°C)
- T2M_MAX: maximum temperature at 2 meters (°C)
- T2M_MIN: minimum temperature at 2 meters (°C)
- QV2M: specific humidity at 2 meters (g/kg)
- PRECTOTCORR: corrected precipitation (mm/day)

## Struktur folder

- `download_nasa_power.py` – script otomatis untuk mengunduh dan memproses data
- `notebooks/nasa_power_analysis.ipynb` – notebook dengan penjelasan, kode, dan interpretasi
- `data/raw/` – hasil unduhan per-tahun (`power_daily_2016.csv` sampai `power_daily_2025.csv`)
- `data/processed/` – hasil gabungan, ringkasan bulanan, ringkasan tahunan, dan laporan validasi

## Cara menjalankan

1. Instal dependensi:
   ```bash
   pip install -r requirements.txt
   ```

2. Jalankan script:
   ```bash
   python download_nasa_power.py
   ```

3. Buka notebook:
   ```bash
   jupyter notebook notebooks/nasa_power_analysis.ipynb
   ```

## Catatan

Data NASA POWER bersifat publik dan dapat diakses melalui API resmi. Karena API terkadang membatasi permintaan, proses download mungkin memerlukan beberapa saat. Jika ada kesalahan koneksi atau rate limit, ulangi eksekusi script.

