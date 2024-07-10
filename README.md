# UAS Pengolahan Citra Digital
Assalamualaikum Warahmatullah Wabarakatuh

Perkenalkan saya rafi Ramadhan Ghifari dengan NIM 202231013 dan pada kesempatan ini, saya akan menjelaskan terkait pengerjaan Ujian Akhir Semester mata kuliah Pengolahan Citra Digital. Pengerjaan UAS ini berbentuk proyek dan proyeknya sudah dibagi per mahasiswa. Kebetulan saya mendapatkan materi Geometrik Citra

# Geometrik Citra/Geometric Image Transformation
Fungsi geometrik citra digunakan untuk melakukan berbagai transformasi geometris pada citra 2 dimensi. Fungsi tersebut tidak mengubah konten gambar, tetapi mengubah bentuk kisi piksel dan memetakan kisi yang berubah bentuk ini ke citra tujuan. Bahkan, untuk menghindari artefak pengambilan sampel, mapping dilakukan dalam urutan terbalik, dari tujuan ke sumber. Yaitu, untuk setiap piksel dari citra tujuan, fungsi menghitung koordinat piksel atau disebut "donor" yang sesuai di gambar sumber dan menyalin nilai piksel:
![image](https://github.com/Erbaaka/PA-PC_202231013_RAFI-RAMADHAN-GHIFARI_C/assets/88221760/92765c0e-b478-4d69-9b02-8192feb5e632)

Perhatikan ketika menentukan pemetaan maju (Gx,Gy): src -> dst, fungsi dari OpenCV akan menghitung pemetaan terbalik yang sesuai (Fx,Fy): dst -> src dan kemudian gunakan rumus di atas.

# Rotasi Citra
