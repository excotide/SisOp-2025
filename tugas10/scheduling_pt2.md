## Kasus Algoritma Penjadwalan

### 1. Shortest-Job-First (SJF) without Arrival Time (Non-Preemptive)

Kasus ini mengasumsikan semua proses tiba pada waktu yang sama (waktu 0). Data proses diambil dari contoh di **Bagian 5.3.2 (Shortest-Job-First Scheduling)** dalam S10-Ch05.

**Proses dan Burst Time:**
* P1: 6 ms [cite: 147]
* P2: 8 ms [cite: 147]
* P3: 7 ms [cite: 147]
* P4: 3 ms [cite: 147]

**Cara Kerja SJF Non-Preemptive (Semua tiba di waktu 0):**
1.  Scheduler memilih proses dengan *burst time* terpendek.
2.  P4 (3 ms) dieksekusi pertama. [cite: 148]
3.  Kemudian P1 (6 ms). [cite: 148]
4.  Selanjutnya P3 (7 ms). [cite: 148]
5.  Terakhir P2 (8 ms). [cite: 148]

**Gantt Chart:**
| P4  | P1  | P3  | P2  |
0     3     9     16    24

*(Gantt chart berdasarkan [cite: 148])*

---

### 2. Shortest-Job-First (SJF) with Arrival Time (Non-Preemptive)

Kasus ini menggunakan proses yang memiliki waktu kedatangan berbeda, diambil dari **Practice Exercise 5.3** dalam S10-Ch05. [cite: 903]

**Proses, Arrival Time, dan Burst Time:**
* P1: Waktu Tiba = 0.0, Burst Time = 8 [cite: 904]
* P2: Waktu Tiba = 0.4, Burst Time = 4 [cite: 904]
* P3: Waktu Tiba = 1.0, Burst Time = 1 [cite: 904]

**Cara Kerja SJF Non-Preemptive (Dengan Waktu Tiba, sesuai Practice Exercise 5.3b):**
Scheduler membuat keputusan berdasarkan informasi yang ada pada saat keputusan tersebut harus dibuat.
1.  **Waktu 0.0:** Hanya P1 yang tersedia. P1 dieksekusi dan berjalan hingga selesai (selama 8 ms). [cite: 907]
2.  **Selama P1 berjalan (0.0 hingga 8.0):**
    * Pada waktu 0.4, P2 tiba.
    * Pada waktu 1.0, P3 tiba.
3.  **Waktu 8.0 (P1 selesai):** P2 (Burst 4) dan P3 (Burst 1) menunggu. P3 memiliki *burst time* lebih pendek, jadi P3 dieksekusi (selama 1 ms).
4.  **Waktu 9.0 (P3 selesai):** Hanya P2 yang tersisa. P2 dieksekusi (selama 4 ms).
5.  **Waktu 13.0 (P2 selesai):** Semua proses selesai.

**Gantt Chart (untuk Practice Exercise 5.3b):**
| P1 (selesai 8.0) | P3 (selesai 9.0) | P2 (selesai 13.0) |
0                  8.0                9.0                 13.0

---

### 3. Shortest Remaining Time First (SRTF) (SJF Preemptive)

Kasus ini menggunakan waktu kedatangan dan sifat preemptive, diambil dari contoh di **Bagian 5.3.2** yang menjelaskan SJF Preemptive.

**Proses, Arrival Time, dan Burst Time:**
* P1: Waktu Tiba = 0, Burst Time = 8 [cite: 173]
* P2: Waktu Tiba = 1, Burst Time = 4 [cite: 173]
* P3: Waktu Tiba = 2, Burst Time = 9 [cite: 173]
* P4: Waktu Tiba = 3, Burst Time = 5 [cite: 173]

**Cara Kerja SRTF (Preemptive):**
1.  **Waktu 0:** P1 tiba, mulai dieksekusi (Sisa P1 = 8). [cite: 175]
2.  **Waktu 1:** P2 tiba (Burst 4). Sisa P1 = 7. Burst P2 (4) < Sisa P1 (7), P1 di-*preempt*, P2 dieksekusi. [cite: 176]
3.  **Waktu 2:** P3 tiba (Burst 9). P2 berjalan (Sisa P2 = 3). Sisa P2 (3) < Burst P3 (9), P2 lanjut.
4.  **Waktu 3:** P4 tiba (Burst 5). P2 berjalan (Sisa P2 = 2). Sisa P2 (2) < Burst P4 (5), P2 lanjut.
5.  **Waktu 5:** P2 selesai. Tersedia: P1 (Sisa 7), P3 (Burst 9), P4 (Burst 5). P4 dipilih (sisa/burst terpendek). [cite: 174]
6.  **Waktu 10:** P4 selesai. Tersedia: P1 (Sisa 7), P3 (Burst 9). P1 dipilih. [cite: 174]
7.  **Waktu 17:** P1 selesai. Tersedia: P3 (Burst 9). P3 dipilih. [cite: 174]
8.  **Waktu 26:** P3 selesai. [cite: 174]

**Gantt Chart:**
| P1  | P2  | P4  | P1  | P3  |
0     1     5     10    17    26

*(Gantt chart berdasarkan [cite: 174])*
