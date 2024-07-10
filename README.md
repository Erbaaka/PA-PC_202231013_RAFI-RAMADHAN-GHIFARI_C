# UAS Pengolahan Citra Digital
Assalamualaikum Warahmatullah Wabarakatuh

Perkenalkan saya rafi Ramadhan Ghifari dengan NIM 202231013 dan pada kesempatan ini, saya akan menjelaskan terkait pengerjaan Ujian Akhir Semester mata kuliah Pengolahan Citra Digital. Pengerjaan UAS ini berbentuk proyek dan proyeknya sudah dibagi per mahasiswa. Kebetulan saya mendapatkan materi Geometrik Citra

# Geometrik Citra/Geometric Image Transformation
Fungsi geometrik citra digunakan untuk melakukan berbagai transformasi geometris pada citra 2 dimensi. Fungsi tersebut tidak mengubah konten gambar, tetapi mengubah bentuk kisi piksel dan memetakan kisi yang berubah bentuk ini ke citra tujuan. Bahkan, untuk menghindari artefak pengambilan sampel, mapping dilakukan dalam urutan terbalik, dari tujuan ke sumber. Yaitu, untuk setiap piksel dari citra tujuan, fungsi menghitung koordinat piksel atau disebut "donor" yang sesuai di gambar sumber dan menyalin nilai piksel:

![image](https://github.com/Erbaaka/PA-PC_202231013_RAFI-RAMADHAN-GHIFARI_C/assets/88221760/92765c0e-b478-4d69-9b02-8192feb5e632)

Perhatikan ketika menentukan pemetaan maju (Gx,Gy): src -> dst, fungsi dari OpenCV akan menghitung pemetaan terbalik yang sesuai (Fx,Fy): dst -> src dan kemudian gunakan rumus di atas.

# Rotasi Citra
Proses rotasi citra dapat dicapai dengan mentransformasi matriks dari wujud citra. Library OpenCV menyediakan rotasi berskala dengan pusat rotasi yang dapat disesuaikan sehingga dapat diputar di lokasi mana pun yang diinginkan.

![image](https://github.com/Erbaaka/PA-PC_202231013_RAFI-RAMADHAN-GHIFARI_C/assets/88221760/1440d1c6-b25b-4671-b712-88d31e6e866c)

Berikut adalah bentuk matriks yang telah dimodifikasi :

![image](https://github.com/Erbaaka/PA-PC_202231013_RAFI-RAMADHAN-GHIFARI_C/assets/88221760/c502dcc1-7555-4f49-a2c8-9bea09103218)

![image](https://github.com/Erbaaka/PA-PC_202231013_RAFI-RAMADHAN-GHIFARI_C/assets/88221760/389d14e4-7b59-40b5-9842-101ea460c4a9)

## Penyelesaian Rotasi Citra
Dalam kasus ini, saya menggunakan fungsi cv2.getRotationMatrix2D sebagai fungsi rotasi citra. Sebelum itu, citra harus di-load terlebih dahulu menggunakan cv2.imread dan untuk menampilkannya saya menggunakan bantuan dari library matplotlib.pyplot dengan alias plt. Setelah di-load, citra perlu dideteksi terlebih dahulu warnanya dengan fungsi cv2.cvtColor dan cv2.COLOR_BGR2RGB. Selanjutnya, citra perlu diketahui bentuk matriksnya. Dikarenakan citra yang saya gunakan berukuran portrait, maka penentuan bentuknya menggunakan (h,w) yaitu h sebagai tinggi dan w sebagai lebar.  

Untuk hasil dari rotasinya akan disimpan oleh variabel bernama img_rotated.

# Resize Citra
Penskalaan hanyalah mengubah ukuran citra. Dengan kata lain, penskalaan atau scaling merupakan proses untuk mengubah ukuran citra. OpenCV dilengkapi dengan fungsi cv.resize() untuk tujuan ini. Ukuran citra dapat ditentukan secara manual, atau dapat ditentukan oleh faktor penskalaan. 

## Penyelesaian Resize Citra
Kasus ini cukup mudah untuk diselesaikan. Hanya diperlukan penentuan bentuk matriks dengan fungsi new_height dan new_width lalu gunakan fungsi cv2.resize() serta disimpan oleh variabel img_resized. 

# Crop Citra
Untuk meng-crop sebuah citra, diperlukan proses pemotongan secara perbandingan antara baris dan kolom. Disini saya mengatur perbandingannya dengan 50 banding 200(50:200)

# Flip Citra
Dalam OpenCV , citra dapat dibalik menggunakan fungsi cv2.flip(). Dengan menggunakan fungsi ini, citra dapat dibalik dengan melintasi sumbu X, sumbu Y, dan melintasi kedua sumbu. Terdapat flipcode untuk melakukan proses pembalikkan. Jika flipcodenya diatur 0, citra akan dibalik pada sumbu x dan jika flipcode diatur ke bilangan bulat positif (misalkan 1), citra akan dibalik pada sumbu Y. Namun, jika menggunakan bilangan negatif (misalkan -1), gambar akan dibalik pada kedua sumbu.

## Penyelesaian Flip Citra
Dalam kasus ini, saya menggunakan flipcode 1 untuk membalik citra pada sumbu Y.

# Translasi Citra
Translasi adalah perpindahan posisi suatu benda. Jika diketahui pergeseran pada arah (x,y) dan misalkan (Tx,Ty), matrik transformasi M sebagai berikut :

![image](https://github.com/Erbaaka/PA-PC_202231013_RAFI-RAMADHAN-GHIFARI_C/assets/88221760/09661b37-30ad-4d2e-8623-1fd85651d170)

Matriks diatas dapat diubah menjadi array Numpy bertipe np.float32 dan diberikan kepada fungsi cv.warpAffine().

## Penyelesaian Translasi Citra
Untuk menyelesaikan kasus ini, digunakan variabel dengan nama M untuk menyimpan nilai matriks dan fungsi Numpy np.float32 sebagai array translasi. Saya mengatur nilai array berupa (1,0,50) dan (0,1,100). Selanjutnya, proses matriksnya akan disimpan dalam variabel img_translated dengan fungsi cv2.warpAffine(). 

# Hasil Olahan Citra
Hasil dari pengolahannya akan sebagai berikut :

![image](https://github.com/Erbaaka/PA-PC_202231013_RAFI-RAMADHAN-GHIFARI_C/assets/88221760/6effa74d-2e06-4eca-8ba5-b5cab745424f)
