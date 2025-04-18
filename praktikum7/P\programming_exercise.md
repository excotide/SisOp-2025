# Implementasi Thread di Berbagai Platform

## 1. **Thread di Java (`SumTask.java`)**

Program `SumTask.java` memanfaatkan **Fork/Join Framework** untuk mengeksekusi tugas secara paralel di Java. Pendekatan ini membagi pekerjaan besar menjadi beberapa bagian kecil yang dapat berjalan bersamaan pada beberapa thread.

### **Struktur Kelas**
```java
public class SumTask extends RecursiveTask<Integer>
```
Kelas `SumTask` merupakan turunan dari `RecursiveTask<Integer>`, yang memungkinkan pemecahan tugas secara rekursif serta eksekusi paralel.

### **Pembagian Tugas**
```java
if (end - begin < THRESHOLD) {
} else {
}
```
Jika jumlah data yang diproses lebih kecil dari nilai batas (`THRESHOLD`), maka penjumlahan dilakukan langsung (**conquer**). Namun, jika lebih besar, array dipecah menjadi dua bagian yang masing-masing dibuat sebagai subtask (**divide**) untuk dieksekusi secara paralel.

### **Eksekusi Paralel**
```java
leftTask.fork();
rightTask.fork();
return rightTask.join() + leftTask.join();
```
Setelah tugas dibagi, dua subtask (`leftTask` dan `rightTask`) dieksekusi secara paralel, dan hasilnya digabung setelah semua thread selesai bekerja.

### **Penggunaan ForkJoinPool**
```java
ForkJoinPool pool = new ForkJoinPool();
int sum = pool.invoke(task);
```
Di fungsi `main()`, sebuah array berisi 10.000 elemen acak dibuat dan diproses oleh objek `SumTask` menggunakan `ForkJoinPool`, yang secara otomatis mengelola thread-thread yang diperlukan.

Dengan pendekatan Fork/Join, proses penjumlahan dapat dibagi menjadi subproses yang berjalan paralel, meningkatkan efisiensi pemrosesan terutama dalam sistem multi-core.

---

## 2. **Thread di Linux (`thrd-posix.c`)**

Program `thrd-posix.c` menggunakan **POSIX Thread** (pthreads) untuk mengelola eksekusi paralel di sistem operasi Linux. Program ini menjalankan thread tambahan untuk menghitung jumlah angka dari 0 hingga batas tertentu.

### **Membuat Thread Baru**
```c
pthread_t tid;
pthread_create(&tid, NULL, runner, argv[1]);
```
Fungsi `pthread_create()` digunakan untuk membuat thread baru. Parameter `runner` menentukan fungsi yang dijalankan oleh thread, sementara `argv[1]` berisi batas angka untuk perhitungan.

### **Fungsi Eksekusi oleh Thread**
```c
void *runner(void *param) {
    int i, upper = atoi(param);
    sum = 0;
    for (i = 1; i <= upper; i++)
        sum += i;
    pthread_exit(0);
}
```
Thread yang dibuat menjalankan fungsi `runner`, yang mengubah parameter menjadi integer (`upper`), lalu menjumlahkan angka dari 1 hingga `upper`.

### **Menunggu Eksekusi Selesai**
```c
pthread_join(tid, NULL);
```
Thread utama tidak akan dilanjutkan hingga thread tambahan selesai bekerja, menggunakan `pthread_join()` untuk memastikan hasilnya siap digunakan.

Pendekatan ini memungkinkan pemrosesan lebih responsif dan fleksibel, karena pekerjaan berat dapat dibagi ke thread terpisah tanpa mengganggu eksekusi utama.

---

## 3. **Thread di Windows (`thrd-win32.c`)**

Program `thrd-win32.c` menerapkan **thread di sistem operasi Windows** menggunakan API `CreateThread()`. Fungsinya sama dengan versi POSIX, yaitu melakukan penjumlahan angka hingga batas tertentu yang dimasukkan dari command line.

### **Membuat Thread Baru**
```c
DWORD ThreadId;
HANDLE ThreadHandle;
ThreadHandle = CreateThread(NULL, 0, Summation, argv[1], 0, &ThreadId);
```
`CreateThread()` digunakan untuk membuat thread baru. Fungsi `Summation` akan dieksekusi, dengan argumen yang ditentukan oleh `argv[1]`.

### **Eksekusi oleh Thread**
```c
DWORD WINAPI Summation(LPVOID Param) {
    int upper = atoi(Param);
    Sum = 0;
    for (int i = 1; i <= upper; i++)
        Sum += i;
    return 0;
}
```
Thread akan menjalankan fungsi `Summation`, yang mengubah parameter menjadi integer lalu melakukan penjumlahan angka dari 1 hingga batas tertentu.

### **Menunggu Thread Selesai**
```c
WaitForSingleObject(ThreadHandle, INFINITE);
```
Agar thread utama tidak lanjut sebelum perhitungan selesai, `WaitForSingleObject()` digunakan untuk memastikan eksekusi sudah lengkap sebelum hasil diakses.

Manajemen thread di Windows menggunakan `CreateThread()` lebih fleksibel tetapi juga lebih eksplisit dibandingkan dengan pthreads di Linux, karena setiap thread memiliki identifikasi tersendiri (`HANDLE`), dan fungsi eksekusi harus mengikuti format tertentu.
