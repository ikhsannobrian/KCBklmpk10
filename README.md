# Jenis Kelamin


Memprediksi jenis kelamin dari nama bahasa Indonesia menggunakan Machine Learning.

Data set yang digunakan berasal dari data pengunjung perpustakaan UPN "Veteran" Jawa Timur pada tanggal 07 Juni 2023 pukul 12.00 WIB yang didapat dari penelusuran secara langsung. Saya telah menyiapkan data set yang telah di scrape dalam bentuk csv, terdiri dari 2 kolom, nama dan jenis kelamin [disini](./data/data-pengunjung-perpustakaan.csv).

Tampilan dataset, teridiri dari 38 nama

| Nama | Jenis Kelamin |
|------|---------------|
|Sekar Ningrum Puspitasari|Perempuan|
|Putri Cahyani Nabilla|Perempuan|
|Bisma Putra|Laki-laki|
|Keiza Citra Sari|Perempuan|
|Dhinda Kurniasari|Perempuan|


Metode klasifikasi yang digunakan adalah Logistic Regression, Naive Bayes dan Random Forest Tree dengan bantuan library Python [Scikit Learn](http://scikit-learn.org).  

### Setup program
1. Clone repository ini `git clone git@github.com:irfani/Jenis-Kelamin.git`
2. Masuk ke direktori project `cd Jenis-Kelamin`
3. Buat Python virtual environment `python3 -m venv venv`
4. Aktifkan virtual environment `source venv/bin/activate`
5. Install dependency `pip3 install -r requirements.txt`

### Menjalankan program

```bash
python jenis-kelamin.py -h
usage: jenis-kelamin.py [-h] [-ml {NB,LG,RF}] [-t TRAIN] nama

Menentukan jenis kelamin berdasarkan nama Bahasa Indonesia

positional arguments:
  nama                  Nama

optional arguments:
  -h, --help            show this help message and exit
  -ml {NB,LG,RF}        NB=Naive Bayes(default); LG=Logistic Regression;
                        RF=Random Forest
  -t TRAIN, --train TRAIN
                        Training ulang dengan dataset yang ditentukan
```

Tebak jenis kelamin sekar ? 
```bash
python jenis-kelamin.py sekar
Prediksi jenis kelamin dengan Naive Bayes :
sekar  :  wanita
```

Menjalankan program dengan metode Logistic Regression dan dataset yg ditentukan ulang
```bash
python jenis-kelamin.py -t "./data/data-pengunjung-perpustakaan.csv" -ml LG "Bisma Putra"
Akurasi : 93.5135135135 %
Prediksi jenis kelamin dengan Logistic Regression :
Bisma Putra  :  Pria
```
