<div align="center">
  <h1>TUGAS SISTEM OPERASI</h1>
  <h2><strong>SISTEM BILANGAN</strong></h2>
  <img src="https://belajargiat.id/wp-content/uploads/2020/10/logo-PENS.png" alt="Pens Logo" width="350"><br>
  <h3><strong>Dosen Pengampu:</strong><br>
  Dr. Ferry Astika Saputra, S.T., M.Sc.</h3>
  <h3><strong>Disusun Oleh:</strong><br>
  Muhammad Labiq Jazli (3124521029)</h3><br>
  <h2><strong>PROGRAM STUDI D3 TEKNIK INFORMATIKA PSDKU LAMONGAN</strong><br>
  DEPARTEMEN TEKNIK INFORMATIKA DAN KOMPUTER<br>
  POLITEKNIK ELEKTRONIKA NEGERI SURABAYA<br>
  2025</h2>
</div>

## 1. Basis Bilangan
```
1. bilangan yang dipakai biner adalah bilangan yang berbasis 2
```

## 2. Konversi Bilangan Desimal ke Biner
  |Langkah-langkah:      |
  |:--------------------:|
  |1234 ÷ 2 = 617 sisa 0 |
  |617 ÷ 2 = 308 sisa 1  |
  |308 ÷ 2 = 154 sisa 0  |
  |154 ÷ 2 = 77 sisa 0  |
  |77 ÷ 2 = 38 sisa 1  |
  |38 ÷ 2 = 19 sisa 0  |
  |19 ÷ 2 = 9 sisa 1  |
  |9 ÷ 2 = 4 sisa 1  |
  |4 ÷ 2 = 2 sisa 0  |
  |2 ÷ 2 = 1 sisa 0  |
  |1 ÷ 2 = 0 sisa 1 |
  ```
  Hasil: 1234 (10) = 10011010010 (a)
  ```

## 3. Konversi Bilangan Biner ke Desimal
  |Perhitungan: |
  |:-----------:|
  |1 × 2^7 = 128|
  |0 × 2^6 = 0|
  |1 × 2^5 = 32|
  |0 × 2^4 = 0|
  |1 × 2^3 = 8|
  |0 × 2^2 = 0|
  |1 × 2^1 = 2|
  |0 × 2^0 = 0|
  |Total = 170|
  ```
  Hasil: 170
  ```

## 4. Konversi Bilangan Biner ke Oktal
  |Konversi: |
  |:-----:|
  |101 = 5|
  |011 = 3|  
  |111 = 7|  
  |001 = 1|
  ```
  Hasil: 5371
  ```

## 5. Konversi Bilangan Oktal ke Biner
  |Konversi:|
  |:-----:|
  |2 = 010|
  |1 = 001|  
  |7 = 111|  
  |0 = 000|  
  ```
  Hasil: 2170 = 010001111000
  ```

## 6. Konversi Bilangan Desimal ke Heksadesimal
  |Langkah-langkah:         |
  |:-----------------------:|
  | 1780 ÷ 16 = 111 sisa 4  |
  | 111 ÷ 16 = 6 sisa 15 (F)| 
  | ÷ 16 = 0 sisa 6  |
  ```
  Hasil: 178010 = 06F4 (a)
  ```

## 7. Konversi Bilangan Heksadesimal ke Desimal
  |Langkah-langkah:         |
  |:-----------------------:|
  |A × 16^3 + B × 16^2 + C × 16^1 + D × 16^0 |
  |= 10 × 4096 + 11 × 256 + 12 × 16 + 13 × 1 |
  |= 40960 + 2816 + 192 + 13 |
  |= 43981|
  ```
  Hasil: ABCD16 = 43981 (a)  
  ```

## 8. Konversi Bilangan Pecahan Desimal ke Biner
  |Langkah-langkah:         |
  |:-----------------------:|
  |0,3125 × 2 = 0,625 → 0|
  |0,625 × 2 = 1,25 → 1|
  |0,25 × 2 = 0,5 → 0|
  |0,5 × 2 = 1,0 → 1|
  ```
  Hasil: 0,312510 = 0,0101 (a) 
  ```

## 9. Konversi Bilangan Desimal ke Biner
  |Langkah-langkah:         |
  |:-----------------------:|
  |Bagian bulat: 11 (10) = 1011 (2)|
  |Bagian pecahan: 0,625 (10) = 0,101 (2)|
  ```
  Hasil: 11,625 (10) = 1011,101 (2)
  ```

## 10. Konversi Bilangan Desimal ke Heksadesimal
  |Langkah-langkah:         |
  |:-----------------------:|
  |Bagian bulat: 348 ÷ 16 = 21 sisa 12 (C)|
  |21 ÷ 16 = 1 sisa 5 |
  |1 ÷ 16 = 0 sisa 1|
  |Bagian pecahan: 0,654 × 16 = 10,464 → 10 (A)|
  |0,464 × 16 = 7,424 → 7 |
  |0,424 × 16 = 6,784 → 6 |
  ```
  Hasil: 348,654 (10) = 15C,A76 (16) 
  ```

## 11. Konversi Bilangan ke Desimal
  |Langkah-langkah:         |
  |:-----------------------:|
  |0 × 2^11 + 1 × 2^10 + 0 × 2^9 + 1 × 2^8 + 0 × 2^7 + 0 × 2^6 + 0 × 2^5 + 1 × 2^4 + 1 × 2^3 + 0 × 2^2 + 1 × 2^1 + 0 × 2^0|
  | = 0 + 1024 + 0 + 256 + 0 + 0 + 0 + 16 + 8 + 0 + 2 + 0 |
  |= 163,245|
  ```
  Hasil: 010100011,001111101 (2) = 163,245 (10)  
  ```

## 12. Konversi Bilangan Biner ke BCD
  |Langkah-langkah:         |
  |:-----------------------:|
  |Pisahkan menjadi digit desimal: , |
  |1010 (10) = 10|
  |0110 (6) = 6|
  |0001 (1) = 1|
  |0111 (7) = 7|
  ```
  Hasil: 10100110000111 (2) = 2987 (BCD)
  ```

## 13. Rubahlah bentuk BCD di bawah ini ke dalam bilangan biner
  |Langkah-langkah:         |
  |:-----------------------:|
  | 1 = 0001|
  | 9 = 1001|
  | 8 = 1000|
  | 7 = 0111|
  ```
  Hasil: 1987 = 0001100100000111 (2)
  ```

## 14. Rubahlah bilangan biner di bawah ini ke dalam BCO.
  |Langkah-langkah:         |
  |:-----------------------:|
  |Kelompokkan dari kanan: 1 111 110 100 1|
  |Konversi: |
  |1 = 1|
  |111 = 7|
  |110 = 6 |
  |100 = 4 |
  | 1 = 1|
  ```
  Hasil: 11111101001 (2) = 3751 (BCO) 
  ```

## 15. Rubahlah bilangan biner di bawah ini ke dalam BCH
  |Langkah-langkah:         |
  |:-----------------------:|
  |Kelompokkan dari kanan: 1101 1110 0010 1110|
  |Konversi:|
  |1101 = D|
  |1110 = E|
  |0010 = 2|
  |1110 = E|
  ```
  Hasil: 1101111100101110 (2) = CF2E (BCH)
  ```

## 16. Rubahlah Bentuk BCH di bawah ini ke dalam bilangan heksadesimal
  |Langkah-langkah:  |
  |:----------------:|
  |F = 1111|
  |0 = 0000 |
  |D = 110|
  |E = 1110|
  ```
  Hasil: F0DE = 1111000011011110 (2) 
  ```

## 17. Nyatakan positip atau negatip bilangan biner di bawah ini
  | Biner Expression                            | Perhitungan |         
  |:-------------------------------------------:|:-----------:|
  | (0×2⁷) + (1×2⁶) + (1×2⁵) + (1×2⁴) + (1×2³) + (1×2²) + (1×2¹) + (1×2⁰) | 0 + 64 + 32 + 16 + 8 + 4 + 2 + 1 |
  ```
  Hasil: 01111111 → Positip 127
  ```

## 18. Nyatakan bilangan biner negatip di bawah ini ke dalam bilangan decimal
  | Biner Asli  | Inversi (1's Complement)| Tambah 1 (2's Complement) |
  |:-----------:|:-----------------------:|:-------------------------:|
  | 10001000    | 01110111                | 01110111 + 1 = 01111000  |
  ```
  Hasil: 10001000 → -120
  ```

## 19. Nyatakan ASCII Code di bawah ini dalam bentuk karakter
  | Heksadesimal | Langkah - langkah            | Hasil  |
  |:------------:|:----------------------------:|:------:|
  | 4116   n     | (4 × 16¹) + (1 × 16⁰)        | 65     |
  ```
  Hasil: karakter ASCII = A
  ```

## 20. Nyatakan Karakter di bawah ini dalam ASCII code
  | Karakter | Desimal | Langkah-langkah       | Heksadesimal |
  |:--------:|:-------:|:---------------------:|:------------:|
  | a        | 97      | 97 ÷ 16 = 6 sisa 1    | 61₁₆         |
  ```
  Hasil: Hexadesimal = 61₁₆
  ```

## 21. Dengan Keyboard standard ASCII, pada layar monitor nampak tulisan sebagai berikut:
  PRINT X
  |Karakter |Biner   |
  |:-------:|:------:|
  |P        |101 0000|
  |R        |101 0010|
  |I        |100 1001|
  |N        |100 1110|
  |T        |101 0100|
  |Space    |010 0000|
  |X        |101 1000|
