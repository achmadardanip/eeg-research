# Struktur dan Deskripsi Dataset EEG Kecanduan Pornografi

## Latar Belakang

Dataset ini berasal dari artikel *Data in Brief* yang berjudul **“Electroencephalogram (EEG) dataset with porn addiction and healthy teenagers under rest and executive function task”**. Data dikumpulkan di Yayasan Kita dan Buah Hati (YKBH), Jakarta, Indonesia menggunakan perangkat **Brain Maker EEG** dengan **19 kanal** dan laju sampel **250 Hz**. Tiga belas hingga 15 tahun (14 peserta; 5 perempuan, 9 laki‑laki) mengikuti eksperimen ini. Seorang psikolog menggunakan **Youth Pornography Addiction Screening Tool (YPAST)** untuk menentukan apakah seorang peserta mengalami kecanduan pornografi atau tidak. Tujuh subjek diklasifikasikan sebagai kecanduan pornografi dan tujuh sebagai remaja sehat.

Dataset ini terdiri dari tiga tahap eksperimen: tahap dasar (baseline), tahap keadaan emosional, dan tahap utama (main). Setiap peserta menyelesaikan sembilan tugas (mata tertutup, mata terbuka, happy, calm, sad, fear, memorize 15 words, executive tasks, recall 15 words) dengan durasi total 10 menit. Dataset ini dapat digunakan untuk menganalisis pola sinyal otak pada kecanduan pornografi, menganalisis emosi melalui EEG, serta mengevaluasi kapasitas memori kerja.

## Perangkat dan Kanal

* **Perangkat pencatat**: Brain Maker EEG, 19 kanal.

* **Laju sampel**: 250 Hz (250 sampel per detik).

* **Kanal EEG**: P4, O2, P8, T8, C4, Cz, Fz, F4, Fp2, F8, Fp1, F7, F3, C3, T7, P7, P3, O1, Pz. Kanal tersebut ditempatkan mengikuti sistem 10–20 internasional.

* **Format data**: Setiap file dalam format CSV berisi matriks **sampel × kanal**; satu baris mewakili satu sampel (250 Hz) dan setiap kolom berisi amplitudo mikrovolt untuk kanal yang sesuai.

## Struktur Direktori

Folder utama dataset bernama data\_porn\_addiction. Di dalamnya terdapat 14 subfolder, satu untuk setiap peserta, dengan nama **S1** sampai **S14**. Masing‑masing subfolder berisi sembilan file data mentah (format .csv) yang sesuai dengan tugas yang dikerjakan subjek. Selain itu terdapat beberapa file metadata:

| Berkas | Deskripsi |
| :---- | :---- |
| Channels.jpeg | Gambar yang menunjukkan posisi dan nomor kanal pada topi EEG. |
| Device.jpeg | Foto perangkat Brain Maker yang digunakan untuk akuisisi data. |
| Participants.xlsx | Spreadsheet dengan kolom **Subject ID**, **Jenis Kelamin**, dan **Label (Addicted/Not Addicted)**. |
| Protocols\_details.xlsx | Lembar kerja yang menjelaskan rincian protokol eksperimen, urutan tugas, durasi, dan instruksi. |

### Contoh Struktur Folder

data\_porn\_addiction/  
├── S1/  
│   ├── EC.csv    \# eyes closed  
│   ├── EO.csv    \# eyes open  
│   ├── H.csv     \# happy  
│   ├── C.csv     \# calm  
│   ├── S.csv     \# sad  
│   ├── F.csv     \# fear  
│   ├── M.csv     \# memorize 15 words  
│   ├── ET.csv    \# executive tasks (menonton pornografi)  
│   └── R.csv     \# recall 15 words  
├── S2/  
│   ├── EC.csv  
│   ├── ...       \# format sama seperti S1  
├── ...  
└── S14/  
    └── ...

## Deskripsi Setiap File Tugas

Tabel berikut merangkum nama file, nama tugas, durasi rekaman, dan jumlah sampel (dengan 19 kanal) untuk setiap tugas. Dalam dataset, setiap subjek memiliki sembilan file CSV dengan struktur yang sama.

| No | Tugas (Task) | Nama file | Durasi (detik) | Bentuk data (sampel × kanal) | Keterangan |
| :---- | :---- | :---- | :---- | :---- | :---- |
| 1 | **Eyes Closed** | EC.csv | 60 detik | 15.000 × 19 | Subjek menutup mata untuk merekam keadaan dasar tanpa rangsangan visual. |
| 2 | **Eyes Open** | EO.csv | 60 detik | 15.000 × 19 | Subjek membuka mata, tetap rileks sambil menatap layar kosong. |
| 3 | **Happy** | H.csv | 60 detik | 15.000 × 19 | Subjek menonton gambar dari *International Affective Picture System (IAPS)* yang memicu emosi bahagia. |
| 4 | **Calm** | C.csv | 60 detik | 15.000 × 19 | Subjek menonton gambar IAPS yang menimbulkan rasa tenang. |
| 5 | **Sad** | S.csv | 60 detik | 15.000 × 19 | Subjek menonton gambar IAPS yang menimbulkan rasa sedih. |
| 6 | **Fear** | F.csv | 60 detik | 15.000 × 19 | Subjek menonton gambar IAPS yang menimbulkan rasa takut (fearful). |
| 7 | **Memorize 15 Words** | M.csv | 60 detik | 15.000 × 19 | Peserta melihat 15 kata yang ditampilkan secara berurutan di layar dan diminta untuk mengingat semuanya. |
| 8 | **Executive Tasks** | ET.csv | 120 detik | 30.000 × 19 | Peserta menonton rangkaian gambar pornografi yang telah divalidasi oleh psikolog selama 2 menit. |
| 9 | **Recall 15 Words** | R.csv | 60 detik | 15.000 × 19 | Peserta diminta menyebutkan kembali 15 kata yang dipelajari sambil melihat layar putih kosong. |

### Detail Format CSV

Setiap file CSV berisi 19 kolom yang mewakili kanal P4, O2, P8, T8, C4, Cz, Fz, F4, Fp2, F8, Fp1, F7, F3, C3, T7, P7, P3, O1, dan Pz. Baris pertama biasanya merupakan header. Baris selanjutnya berisi nilai amplitudo EEG (dalam mikrovolt) per sampel. Misalnya, file EC.csv memiliki 15.000 baris data (60 detik × 250 Hz) dan 19 kolom kanal. Nilai-nilai tersebut dapat dikonversi menjadi pita frekuensi tertentu (delta, theta, alpha, beta, gamma) untuk analisis lanjutan. Jika diperlukan, file .tdms asli tersedia dalam dataset dan dapat dikonversi dengan aplikasi QtiPlot.

## Detil Peserta

Data peserta disediakan dalam Participants.xlsx dan dirangkum dalam Tabel berikut berdasarkan informasi pada artikel. Kolom “Label” menunjukkan apakah subjek termasuk kategori *Addicted* (kecanduan pornografi) atau *Not Addicted* (remaja sehat).

| No | ID Subjek | Jenis Kelamin | Label |
| :---- | :---- | :---- | :---- |
| 1 | S1 | L (Male) | Kecanduan |
| 2 | S2 | P (Female) | Tidak kecanduan |
| 3 | S3 | P | Tidak kecanduan |
| 4 | S4 | L | Tidak kecanduan |
| 5 | S5 | L | Kecanduan |
| 6 | S6 | L | Kecanduan |
| 7 | S7 | L | Tidak kecanduan |
| 8 | S8 | L | Tidak kecanduan |
| 9 | S9 | P | Kecanduan |
| 10 | S10 | P | Kecanduan |
| 11 | S11 | P | Kecanduan |
| 12 | S12 | L | Tidak kecanduan |
| 13 | S13 | L | Tidak kecanduan |
| 14 | S14 | L | Kecanduan |

## Rincian Protokol

Eksperimen dilakukan dalam tiga tahap dengan total sembilan tugas:

1. **Baseline (2 menit)** – peserta dalam kondisi mata tertutup (1 menit) lalu mata terbuka (1 menit) tanpa rangsangan eksternal.

2. **Keadaan emosional (4 menit)** – peserta menonton gambar dari *International Affective Picture System (IAPS)* untuk menimbulkan emosi **happy**, **calm**, **sad** dan **fear**, masing‑masing selama 1 menit. Gambar IAPS terdiri dari foto‑foto berwarna yang telah dinormalkan sebagai stimulus emosional.

3. **Tahap utama (4 menit)**:

4. **Memorize 15 words (1 menit)** – 15 kata tampil satu per satu; peserta diminta mengingat seluruh kata.

5. **Executive Tasks (2 menit)** – peserta menonton rangkaian gambar pornografi yang telah divalidasi oleh psikolog untuk memicu respons eksekutif dan emosi.

6. **Recall 15 words (1 menit)** – peserta diminta mengucapkan 15 kata yang telah mereka hapal sambil melihat layar putih kosong.

Urutan dan durasi tugas dicatat dalam Protocols\_details.xlsx, sehingga peneliti dapat mengidentifikasi segmen waktu tertentu untuk analisis. Tugas‑tugas tersebut dirancang untuk mempelajari aktivitas otak remaja saat mengalami rangsangan emosional dan tugas kognitif terkait pornografi.

## Penggunaan Dataset

Dataset ini berguna bagi peneliti neuroscience, psikologi, dan ilmu data untuk:

* Mengidentifikasi perbedaan pola EEG antara remaja kecanduan dan tidak kecanduan pornografi dalam kondisi dasar maupun selama tugas eksekutif.

* Menganalisis respons emosional melalui sinyal EEG ketika subjek menonton gambar IAPS atau rangsangan pornografi.

* Mengevaluasi kapasitas memori kerja melalui tugas menghafal dan mengingat kembali kata‑kata.

* Melakukan analisis frekuensi (pita delta, theta, alfa, beta, gamma) atau analisis spatio‑temporal pada 19 kanal EEG.

* Mengembangkan model machine learning atau deep learning untuk klasifikasi kecanduan pornografi berdasarkan sinyal EEG.

## Akses Dataset

Dataset tersedia di Mendeley Data dengan DOI: **10.17632/4r8hp2hmb4.5**. Pengguna dapat mengunduh arsip ZIP melalui tautan yang disediakan (misalnya https://prod-dcd-datasets-cache-zipfiles.s3.eu-west-1.amazonaws.com/4r8hp2hmb4-5.zip) untuk mendapatkan semua file. Pastikan untuk memeriksa file Participants.xlsx dan Protocols\_details.xlsx untuk metadata tambahan.

## Kesimpulan

Dataset EEG ini menyediakan rekaman multi‑kanal berkualitas tinggi dari remaja yang kecanduan pornografi dan sehat dengan beberapa kondisi emosional dan tugas kognitif. Struktur folder yang terorganisir, file CSV per subjek dan per tugas, serta metadata lengkap (jenis kelamin, label kecanduan, uraian protokol) memudahkan penggunaan dataset untuk analisis neuroscientific atau pengembangan model klasifikasi kecanduan. Dengan laju sampel 250 Hz dan 19 kanal, dataset ini memungkinkan analisis frekuensi tinggi serta eksplorasi aktivitas otak di berbagai area seperti frontal, temporal, parietal, dan oksipital.