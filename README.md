# Recommendation Anime System

## Project Overview
Dunia hiburan sekarang menjadi momok utama para masyarakat untuk menjadi pengisi waktu dalam waktu liburan. Salah satu hiburan tersebut adalah anime. Anime adalah animasi dari Jepang yang digambar dengan tangan maupun mengugnakan teknologi komputer. Kata anime merupakan singkatan dari "animation" dalam Bahasa Inggris, yang merujuk pada semua jenis animasi. Persebaran anime sendiri sangatlah besar, menurut gambar dibawah ini bisa dilihat permintaan anime pada April - Juni 2018 diluar Jepang sangatlah banyak.

![ss0](https://res.cloudinary.com/hafidhsoekma/image/upload/v1633679142/Random/ss0_new_qgyvuq.png)

Dengan adanya machine learning ini diharapkan kita, bisa mendapatkan rekomendasi anime yang mirip dengan nilai masukkan anime yang kita inginkan. Supaya kita bisa mendapatkan rekomendasi anime yang mirip dengan anime yang kita masukkan.

## Business Understanding

### Problem Statements
Permasalah yang ingin saya selesaikan adalah, banyak sekali anime yang tersebar diluas sana tetapi kita bingung untuk mencari anime yang mirip dengan anime yang disukai. Seperti contoh saya suka anime Sword Art Online, tetapi saya bingung untuk mencari anime yang mirip dengan Sword Art Online.

### Goals
Tujuan dari projek ini adalah untuk memberikan rekomendasi anime yang memiliki kesamaan genre kepada pengguna.

### Solution approach
Solusi kali ini adalah dengan menggunakan metode machine learning yaitu Content Based Filtering.
- **Content Based Filtering**. Content based filtering adalah salah satu metode machine learning yang konsep idenya dengan merekomendasikan item yang mirip dengan item yang disukai pengguna masa lalu. Kelebihan dari metode ini ialah, model tidak perlu menggunakan data pengguna lain, karena rekomendasi khusus untuk pengguna ini dan juga model dapat lebih spesifik mengetahui minat pengguna. Kekurangannya adalah karena ini model lebih mengarah ke rekomendasi kepentingan pengguna, model ini terbatas jika untuk memperluas kepentingan pengguna yang lain.

![ss1](https://res.cloudinary.com/hafidhsoekma/image/upload/v1633680830/Random/ss1_new_a7e3y8.jpg)

## Data Understanding
Dataset ini saya ambil dari situs kaggle yang berjudul [**Anime Database for Recommendation system**](https://www.kaggle.com/vishalmane109/anime-recommendations-database). Dataset ini dibuat oleh seseorang dengan nama *vishal mane* dan sudah diunggah ke situs kaggle pada bulan juni 2020. Dalam dataset tersebut terdapat beberapa fitur, diantaranya adalah:

- Anime_id: Identifikasi unik untuk judul anime tersebut
- Title: Judul dari anime
- Genre: Genre dari anime tersebut
- Synopsis: Deskripsi singkat dari anime tersebut
- Type: Tipe dari anime tersebut
- Producer: Producer dari anime tersebut
- Studio: Studio dari anime tersebut
- Rating: Rating dari anime tersebut
- ScoredBy: Total user yang memberikan rating dari anime tersebut
- Popularity: Ranking anime berdasarkan popularitasnya
- Members: Jumlah member yang mengikuti anime tersebut
- Episodes: Jumlah keseluruhan episode pada anime tersebut
- Source: Sumber anime tersebut
- Aired: Rentang anime itu dirilis mulai kapan dari kapan
- Link: Sumber link untuk melihat anime tersebut

#### Deskripsi Variabel
![Deskripsi Variabel](https://res.cloudinary.com/hafidhsoekma/image/upload/v1634009609/Random/sistem_rekomendasi_0_nt5xhc.png)

#### Deskripsi Statistik
![Deskripsi Statistik](https://res.cloudinary.com/hafidhsoekma/image/upload/v1634009616/Random/sistem_rekomendasi_1_rppal5.png)

## Data Preparation
1. Pertama saya menangani data yang missing dengan menghapus data missing tersebut karena kita tidak akan menggunakan data tersebut. Dengan menggunakan `dropna()` pada dataframe yang tersedia.
2. Setelah itu saya menghapus data yang sama, supaya model kita dapat lebih bervariasi dalam menerima data dari kita. Dengan menggunakan `drop_duplicates()` pada dataframe yang tersedia.

## Modeling
Disini saya membuat model dengan metode Content Based Filtering. Content based filtering adalah salah satu metode machine learning yang konsep idenya dengan merekomendasikan item yang mirip dengan item yang disukai pengguna masa lalu. Saya menggunakan model tersebut karena metode tersebut karena hanya menerima masukkan nilai dari judul anime saja dan tidak membutuhkan banyak resource data. Berikut adalah contoh keluaran dari model ini

![contoh_output_model](https://res.cloudinary.com/hafidhsoekma/image/upload/v1634009975/Random/sistem_rekomendasi_2_nxr8bd.png)

## Evaluation
Disini saya menggunakan precision sebagai evaluasi metrik saya. Precision adalah salah satu evaluasi metrik pada pembelajaran mesin yang meminta ketepatan antara informasi yang diminta oleh pengguna dengan jawaban yang diberikan oleh sistem.  

![precision](https://res.cloudinary.com/hafidhsoekma/image/upload/v1634716723/Random/precision_anime_rznewk.png)  

Bisa dilihat dari foto diatas, dibuktikan untuk setiap judul anime yang saya testing, ketiga judul anime tersebut memiliki hasil precision yang sangat bagus. Bisa disimpulkan model yang saya buat dapat memberikan rekomendasi anime yang begitu tepat ke pengguna.
