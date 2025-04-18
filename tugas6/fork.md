# FORK: PARENT - CHILD PROCESS

## **Tugas:**  
- Akses dan cloning repo: [github.com/ferryastika/operatingsystem.git](https://github.com/ferryastika/operatingsystem.git)  
- Deskripsikan dan visualisasikan pohon proses hasil eksekusi dari kode berikut:
  - `fork01.c`
  - `fork02.c`
  - `fork03.c`
  - `fork04.c`
  - `fork05.c`
  - `fork06.c`

---

## **1. fork01.c**
Program ini mengimplementasikan **First-Come, First-Served (FCFS) Scheduling** untuk menghitung waktu tunggu (*waiting time*) dan waktu penyelesaian (*turnaround time*) berdasarkan *burst time* yang diberikan pengguna.

### **Visualisasi Pohon Proses:**  
```
Main()
│
├── Input Jumlah Proses
│
├── Loop Input Burst Time
│   ├── P1: Burst Time
│   ├── P2: Burst Time
│   ├── P3: Burst Time
│
├── Hitung Waiting Time (WT)
│   ├── P1: WT = 0
│   ├── P2: WT = BT[P1]
│   ├── P3: WT = BT[P1] + BT[P2]
│
├── Hitung Turnaround Time (TAT)
│   ├── P1: TAT = BT[P1] + WT[P1]
│   ├── P2: TAT = BT[P2] + WT[P2]
│   ├── P3: TAT = BT[P3] + WT[P3]
│
└── Hitung rata-rata WT dan TAT → Output Data → Selesai
```
---

## **2. fork02.c**
Program ini menggunakan *system call* `fork()` untuk menciptakan proses anak dari proses induk yang sedang berjalan.

### **Visualisasi Pohon Proses:** 
```
Proses Induk (PID X) 
│
├── Fork() → Membuat Proses Anak (PID Y)
│
├── Proses Induk: Menampilkan PID X dan nilai x
│    ├── x = 5, x = 6, x = 7, ...
│
├── Proses Anak: Menampilkan PID Y dan nilai x
│    ├── x = 5, x = 6, x = 7, ...
│
└── Kedua proses berjalan **selamanya** dalam loop while(1)
```
> **Catatan:** Kedua proses berjalan **selamanya** dalam loop `while(1)`. Mereka berjalan bersamaan tetapi independen.

---

## **3. fork03.c**
Program ini membuat proses anak dari induk, di mana setiap proses mencetak ID-nya selama lima iterasi dengan jeda dua detik.

### **Visualisasi Pohon Proses:** 
```
Proses Induk (PID X) 
│
├── Fork() → Membuat Proses Anak (PID Y)
│
├── Proses Induk: Menampilkan PID X
│    ├── Iterasi 1: "This is process X"
│    ├── Iterasi 2: "This is process X"
│    ├── Iterasi 3: "This is process X"
│    ├── Iterasi 4: "This is process X"
│    ├── Iterasi 5: "This is process X"
│
├── Proses Anak: Menampilkan PID Y
│    ├── Iterasi 1: "This is process Y"
│    ├── Iterasi 2: "This is process Y"
│    ├── Iterasi 3: "This is process Y"
│    ├── Iterasi 4: "This is process Y"
│    ├── Iterasi 5: "This is process Y"
│
└── **Selesai setelah 5 iterasi**
```
> **Catatan:** Tidak ada sinkronisasi, sehingga urutan output bisa acak tergantung pada *CPU scheduling*.

---

## **4. fork04.c**
Program ini menggunakan `fork()` untuk membuat proses anak, lalu induk menunggu anak selesai menggunakan `wait()`.

### **Visualisasi Pohon Proses:**  
```
Proses Induk (PID X)
│
├── Fork() → Membuat Proses Anak (PID Y)
│
├── Proses Anak (PID Y)
│    ├── Cetak: "Saya anak, PID saya Y"
│    ├── Cetak: "Induk saya adalah X"
│    ├── Keluar
│
├── Proses Induk (PID X)
│    ├── Cetak: "Saya induk, PID saya X"
│    ├── Cetak: "Anak saya memiliki PID Y"
│    ├── Menunggu anak selesai dengan `wait()`
│    ├── Keluar setelah anak selesai
```
---

## **5. fork05.c**
Program ini membuat proses anak, yang kemudian menjalankan perintah menggunakan `execl()` untuk menggantikan eksekusi proses.

### **Visualisasi Pohon Proses:**  
```
Proses Induk (PID X)
│
├── Fork() → Membuat Proses Anak (PID Y)
│
├── Proses Anak (PID Y)
│    ├── Cetak: "Saya anak, PID saya Y"
│    ├── Eksekusi `/bin/ls -l /home`
│    ├── Keluar setelah eksekusi selesai
│
├── Proses Induk (PID X)
│    ├── Cetak: "Saya induk, PID saya X"
│    ├── Cetak: "Anak saya memiliki PID Y"
│    ├── Menunggu anak selesai dengan `wait()`
│    ├── Keluar setelah anak selesai

```
---

## **6. fork06.c**
Program ini mencoba mengeksekusi program eksternal menggunakan `execl()`, dan jika gagal, mencetak pesan error.

### **Visualisasi Pohon Proses:** 
```
Proses Induk (PID X)
│
├── Fork() → Membuat Proses Anak (PID Y)
│
├── Proses Anak (PID Y)
│    ├── Cetak: "Saya anak, PID saya Y"
│    ├── Eksekusi `execl("fork03", "goose", NULL)`
│    ├── Jika gagal, cetak "Could not execl file fork3" lalu keluar
│
├── Proses Induk (PID X)
│    ├── Cetak: "Saya induk, PID saya X"
│    ├── Cetak: "Anak saya memiliki PID Y"
│    ├── Menunggu anak selesai dengan `wait()`
│    ├── Keluar setelah anak selesai

```
