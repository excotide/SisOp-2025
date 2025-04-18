# Single Thread dan Multithread

## Single Thread
Single-threading merupakan metode pemrograman di mana suatu proses hanya memiliki satu jalur eksekusi yang berjalan secara berurutan. Dalam pendekatan ini, setiap tugas harus selesai terlebih dahulu sebelum tugas berikutnya dapat dimulai, yang berpotensi menyebabkan keterlambatan ketika berhadapan dengan operasi yang memakan waktu lama, seperti pemrosesan data dalam jumlah besar atau komunikasi jaringan. Keunggulan utama dari single-threading adalah kesederhanaan dalam implementasi serta kemudahan pengelolaan, karena tidak terdapat risiko kondisi balapan atau masalah sinkronisasi antar thread. Namun, dalam skenario yang menuntut eksekusi cepat atau pemrosesan paralel, metode ini kurang optimal dibandingkan alternatif yang lebih efisien.

## Multithread
Multithreading memungkinkan sebuah program menjalankan beberapa alur eksekusi secara simultan, sehingga berbagai komponen dapat bekerja secara paralel. Dengan pendekatan ini, efisiensi dan kecepatan pemrosesan meningkat karena tugas-tugas dapat diselesaikan tanpa harus menunggu satu sama lain. Contohnya, dalam aplikasi browser, satu thread dapat mengelola pemuatan halaman, sementara thread lainnya menangani input pengguna secara bersamaan. Teknik ini sangat efektif untuk mengoptimalkan kinerja sistem, terutama dalam lingkungan yang membutuhkan pemrosesan banyak tugas secara bersamaan.

![FotoSingle&Multi Thread](https://github.com/excotide/SisOp-25/blob/main/tugas7/thread.png)
