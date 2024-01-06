# Morse Code to Speech Based on Gesture Detection

 ![Computer Vision](https://github.com/mharits-s/morse-object-detection/blob/main/assets/computervision.svg?raw=true)
 
Sistem yang menggunakan pengenalan gerakan tangan (gesture detection) untuk mengonversi pola gerakan tangan ke dalam kode Morse, dan selanjutnya mengubahnya menjadi ucapan suara menggunakan teknologi Text-to-Speech (TTS).

## Collect Dataset
Pengkoleksian dataset menggunakan kode program `collect.py`.  Program pengumpulan dataset untuk melatih model pengenalan gestur tangan dibuat. Program ini menggunakan kamera untuk mendeteksi tangan dalam citra. Setiap tangan yang terdeteksi akan dicrop dan diresize agar sesuai dengan kebutuhan dataset. Saat tombol "s" ditekan, program mulai merekam citra tangan yang telah diproses dan menyimpannya dalam folder dataset. Proses rekaman berlanjut hingga jumlah maksimum citra tercapai, memberikan pengguna dataset yang beragam untuk melatih dan meningkatkan akurasi model pengenalan gestur tangan. Dataset yang dikoleksi terbagi menjadi 6 kelas yaitu: Dit, Dash, Enter, New, Next, Space.

## Training Model
Dalam tahap pelatihan model, pengenalan gestur tangan dilatih menggunakan platform "Teachable Machine." Proses pelatihan dilakukan sebanyak 50 epoch (siklus pelatihan), dengan setiap batch (kelompok data) berukuran 16 citra. Adapun learning rate yang digunakan adalah 0,001, yang mengontrol sejauh mana model mengupdate bobotnya berdasarkan gradien kesalahan. Melalui 50 epoch tersebut, model secara iteratif memperbarui parameter-parameternya untuk memahami dan mengenali berbagai gestur tangan yang telah diakuisisi sebelumnya dalam tahap pengumpulan dataset.