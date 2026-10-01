# <h1 align="center">Laporan Praktikum - Latihan Modul 2 Praktikum Struktur Data – S1IF-13-01</h1>
<p align="center">Arvin Ihsan Fatih - 109082500050</p>

## Dasar Teori
Array adalah struktur data yang digunakan untuk menyimpan sekumpulan data dalam satu tempat. Data dalam array disimpan dalam posisi-posisi yang disebut indeks. Indeks array selalu dimulai dari angka nol[1]. 

Pointer adalah sebuah variabel yang berisikan alamat memori (bukan nilai) atau dengan kata lain dapat dikatakan bahwa pointer adalah suatu variabel penunjuk ke lamat memori tertentu[2].

### A. Fungsi Struktur Data Array<br/>
Array memiliki beberapa fungsi utama, di antaranya:
#### 1. Penyimpanan Data: Array digunakan untuk mengumpulkan data dalam satu tempat sehingga lebih mudah dikelola.
#### 2. Akses Data: Kita dapat mengakses data dalam array dengan menggunakan indeksnya. Misalnya, jika kita ingin mengambil data ke-3 dalam array, kita menggunakan indeks 2.
#### 3. Pengulangan Data: Array memungkinkan kita untuk melakukan operasi atau pemrosesan pada setiap elemen data dalam array dengan lebih efisien[1].

### B. Keuntungan menggunakan pointer<br/>
#### 1. Untuk menciptakan data struktur yang kompleks.
#### 2. Memungkinkan suatu fungsi untuk menghasilkan lebih dari satu nilai.
#### 3. Memiliki kemampuan untuk mengirimkan alamat suatu fungsi ke fungsi yang lain[2].

## Guided 

### 1. Array 1

```C++
#include <iostream>
using namespace std;

int main() {
    int nilai[5];

    nilai[0] = 80;
    nilai[1] = 85;
    nilai[2] = 90;
    nilai[3] = 75;
    nilai[4] = 95;

    for (int i = 0; i < 5; i++) {
        cout << "index ke-" << i << " = " << nilai[i] << endl;
    }

    return 0;
}
```
Program ini menampilkan penggunaan array satu dimensi dengan ukuran 5 elemen bertipe integer. Nilai dimasukkan satu per satu ke setiap indeks array (dari indeks 0 sampai 4). Selanjutnya, perulangan for digunakan untuk mencetak seluruh isi elemen array beserta indeksnya ke layar secara berurutan.

### 2. Array 2

```C++
#include <iostream>
using namespace std;

int main() {
    int nilai[3][3] = {
        {80, 85, 90},
        {75, 80, 85},
        {90, 95, 100}
    };

    cout << nilai[0][0] << endl; // 80
    cout << nilai[1][1] << endl; // 80
    cout << nilai[2][2] << " " ; // 100

    return 0;
}
```
Program ini membuat array dua dimensi berukuran 3x3 (3 baris dan 3 kolom). Program mengakses elemen menggunakan dua indeks, yaitu nilai [baris] [kolom]. Perintah cout mencetak nilai diagonal utama dari matriks tersebut, yaitu baris 0 kolom 0 (80), baris 1 kolom 1 (80), dan baris 2 kolom 2 (100).

### 3. Array 3

```C++
#include <iostream>
using namespace std;

int main() {
    int data[2][3][3] = {
        {
            {1, 2, 3},
            {4, 5, 6},
            {7, 8, 9}
        },
        {
            {10, 11, 12},
            {13, 14, 15},
            {16, 17, 18}
        }
    };

    cout << data[0][1][1] << " "; // 5

    return 0;
}
```
Program ini memperlihatkan contoh array tiga dimensi data [2] [3] [3] yang memuat 2 kelompok tabel berukuran 3x3. Untuk mengambil nilainya, digunakan tiga indeks [kelompok] [baris] [kolom]. Pada program ini, data[0] [1] [1] mengambil nilai pada kelompok pertama (indeks 0), baris kedua (indeks 1), dan kolom kedua (indeks 1), yang menghasilkan angka 5.

### 4. Array 4

```C++
#include <iostream>
using namespace std;

int main() {
    int data[2][2][2][2] = {
        {
            {
                {1, 2},
                {3, 4}
            },
            {
                {5, 6},
                {7, 8}
            }
        },
        {
            {
                {9, 10},
                {11, 12}
            },
            {
                {13, 14},
                {15, 16}
            }
        }
    };

    cout << data[0][0][0][0] << endl; // 1
    cout << data[1][1][1][1] << endl; // 16

    return 0;
}
```
Program ini menjalankan array empat dimensi data [2 ][2] [2] [2]. Program ini menyimpan sekumpulan nilai terstruktur dalam 4 tingkatan dimensi. Dalam program ini, data [0] [0] [0] [0] mencetak elemen paling pertama (1), sedangkan dat [1] [1] [1] [1] mencetak elemen paling terakhir (16).

### 5. Pointer 1

```C++
#include <iostream>
using namespace std;

int main() {
    char a;
    int j;
    char arr[6];

    arr[3] = 'b';
    a = 'u';
    j = 10;

    cout << a << endl;   // u
    cout << &a << endl;  // alamat memory atau address

    cout << j << endl;   // 10
    cout << &j << endl;  // alamat memory atau address

    cout << arr[3] << endl;    // value
    cout << &(arr[4]) << endl; // alamat memory atau address

    return 0;
}
```
Program ini bertujuan untuk mengenalkan cara melihat alamat memori suatu variabel menggunakan operator &. Ketika dipanggil langsung (a, j, arr[3]), program menampilkan nilai data yang tersimpan. Namun ketika ditambahkan simbol & di depannya (&a, &j, &(arr[4])), program menampilkan alamat lokasi memori tempat data tersebut disimpan.

### 6. Pointer 2

```C++
#include <iostream>
using namespace std;

int main() {
    int x, y;
    int *px;

    x = 87;
    px = &x;
    y = *px;

    cout << "Alamat x= " << &x << endl;
    cout << "Isi px= " << px << endl;
    cout << "Isi X= " << x << endl;
    cout << "Nilai yang ditunjuk px= " << *px << endl;
    cout << "Nilai y= " << y << endl;

    return 0;
}
```
Program ini mempelajari pembuatan variabel pointer px menggunakan tanda *. Pointer px diisi dengan alamat dari variabel x (px = &x). Operator *px digunakan untuk mengambil nilai yang tersimpan di alamat yang ditunjuk oleh px. Hasilnya, nilai y menjadi sama dengan nilai x (87), serta &x dan px memiliki alamat memori yang sama.

### 7. Pointer 3

```C++
#include <iostream>
#define MAX 5
using namespace std;

int main() {
    int i, j;
    float nilai_total, rata_rata;
    float nilai[MAX];

    static int nilai_tahun[MAX][MAX] = {
        {0, 2, 2, 0, 0},
        {0, 1, 1, 1, 0},
        {0, 3, 3, 3, 0},
        {4, 4, 0, 0, 4},
        {5, 0, 0, 0, 5}
    };

    // inisialisasi array satu dimensi
    for (i = 0; i < MAX; i++) {
        cout << "masukkan nilai ke-" << i + 1 << endl;
        cin >> nilai[i];
    }

    cout << "\ndata nilai siswa :\n";

    // menampilkan array satu dimensi
    for (i = 0; i < MAX; i++) {
        cout << "nilai k-" << i + 1 << "=" << nilai[i] << endl;
    }

    cout << "\nnilai tahunan :\n";

    // menampilkan array dua dimensi
    for (i = 0; i < MAX; i++) {
        for (j = 0; j < MAX; j++) {
            cout << nilai_tahun[i][j];
        }
        cout << "\n";
    }

    return 0;
}
```
Program ini menggabungkan pemrosesan array 1 dimensi dan 2 dimensi dalam satu program. Program meminta input nilai ke array 1 dimensi nilai[MAX] menggunakan perulangan for lalu menampilkannya kembali. Selanjutnya, program menampilkan tabel matriks 5x5 dari array 2 dimensi nilai_tahun menggunakan perulangan bersarang (nested loop).

### 8. Pointer 4

```C++
#include <iostream>
using namespace std;

int main() {
    char nama[] = "strukdat";

    cout << nama << endl;
    cout << nama[3] << endl;

    return 0;
}
```
Program ini menunjukkan bahwa variabel array string pada dasarnya bekerja mirip seperti pointer. Deklarasi char nama[] = "strukdat" menyimpan kumpulan karakter secara berurutan. Jika dipanggil nama, seluruh string akan dicetak (strukdat). Jika dipanggil dengan indeks nama[3], program hanya mencetak karakter keempat yaitu huruf 'k'.

## Unguided 

### 1. Buatlah program yang dapat melakukan operasi penjumlahan, pengurangan, dan perkalian matriks 3x3.

```C++
#include <iostream>
using namespace std;

int main() {
    int A[3][3] = {
        {1, 2, 3},
        {4, 5, 6},
        {7, 8, 9}
    };

    int B[3][3] = {
        {9, 8, 7},
        {6, 5, 4},
        {3, 2, 1}
    };

    int hasilPenjumlahan[3][3];
    int hasilPengurangan[3][3];
    int hasilPerkalian[3][3];

    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            hasilPenjumlahan[i][j] = A[i][j] + B[i][j];
        }
    }

    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            hasilPengurangan[i][j] = A[i][j] - B[i][j];
        }
    }

    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            hasilPerkalian[i][j] = 0;
            for (int k = 0; k < 3; k++) {
                hasilPerkalian[i][j] += A[i][k] * B[k][j];
            }
        }
    }

    cout << "Penjumlahan :" << endl;
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            cout << hasilPenjumlahan[i][j] << "\t";
        }
        cout << endl;
    }

    cout << "\nPengurangan :" << endl;
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            cout << hasilPengurangan[i][j] << "\t";
        }
        cout << endl;
    }

    cout << "\nPerkalian :" << endl;
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            cout << hasilPerkalian[i][j] << "\t";
        }
        cout << endl;
    }

    return 0;
}
```
### Output Unguided 1 :
Penjumlahan :
10      10      10
10      10      10
10      10      10

Pengurangan :
-8      -6      -4
-2      0       2
4       6       8

Perkalian :
30      24      18
84      69      54
138     114     90

##### Output 1
![Screenshot Output Unguided 1_1](https://github.com/arvinihsnn/Praktikum-Struktur-Data-2/blob/main/Praktikum-Modul-2/Output-Unguided/Output-Unguided-1.png)

Program ini melakukan operasi aritmatika pada dua matriks 3x3 (A dan B). Penjumlahan dan pengurangan dilakukan dengan menjumlahkan atau mengurangkan elemen pada posisi baris dan kolom yang sejajar menggunakan perulangan bersarang. Untuk perkalian matriks, digunakan tiga tingkatan perulangan for untuk mengalikan elemen baris matriks pertama dengan elemen kolom matriks kedua.

### 2. Berdasarkan guided pointer dan reference sebelumnya, buatlah keduanya dapat menukar nilai dari 3 variabel.

```C++
#include <iostream>
using namespace std;

void tukarPointer(int *a, int *b, int *c) {
    int temp = *a;
    *a = *b;
    *b = *c;
    *c = temp;
}

void tukarReference(int &a, int &b, int &c) {
    int temp = a;
    a = b;
    b = c;
    c = temp;
}

int main() {
    int x = 10, y = 20, z = 30;

    cout << "Nilai Awal" << endl;
    cout << "x = " << x << ", y = " << y << ", z = " << z << endl;

    tukarPointer(&x, &y, &z);
    cout << "\nTukar dengan Pointer" << endl;
    cout << "x = " << x << ", y = " << y << ", z = " << z << endl;

    tukarReference(x, y, z);
    cout << "\nTukar dengan Reference" << endl;
    cout << "x = " << x << ", y = " << y << ", z = " << z << endl;

    return 0;
}
```
### Output Unguided 2 :
Nilai Awal
x = 10, y = 20, z = 30

Tukar dengan Pointer
x = 20, y = 30, z = 10

Tukar dengan Reference
x = 30, y = 10, z = 20

##### Output 1
![Screenshot Output Unguided 2_1](https://github.com/arvinihsnn/Praktikum-Struktur-Data-2/blob/main/Praktikum-Modul-2/Output-Unguided/Output-Unguided-2.png)

Program ini menukar nilai tiga variabel (x, y, dan z) menggunakan dua cara, yaitu pointer dan reference. Fungsi tukarPointer menggunakan *, sedangkan fungsi tukarReference menggunakan tanda &. Sebuah variabel sementara (temp) digunakan untuk menyimpan nilai pertama agar nilainya tidak hilang saat proses pergeseran tukar nilai terjadi.

### 3. Diketahui sebuah array 1 dimensi sebagai berikut : arrA = {11, 8, 5, 7, 12, 26, 3, 54, 33, 55}. Buatlah program yang dapat mencari nilai minimum, maksimum, dan rata – rata dari array tersebut! Gunakan function cariMinimum() untuk mencari nilai minimum dan function cariMaksimum() untuk mencari nilai maksimum, serta gunakan prosedur hitungRataRata() untuk menghitung nilai rata – rata! Buat program menggunakan menu switch-case seperti berikut ini :
--- Menu Program Array ---
1. Tampilkan isi array
2. cari nilai maksimum
3. cari nilai minimum
4. Hitung nilai rata - rata

```C++
#include <iostream>
using namespace std;

int arrA[10] = {11, 8, 5, 7, 12, 26, 3, 54, 33, 55};
int n = 10;

void tampilkanArray() {
    cout << "Isi Array: ";
    for (int i = 0; i < n; i++) {
        cout << arrA[i] << " ";
    }
    cout << endl;
}

int cariMaksimum() {
    int max = arrA[0];
    for (int i = 1; i < n; i++) {
        if (arrA[i] > max) {
            max = arrA[i];
        }
    }
    return max;
}

int cariMinimum() {
    int min = arrA[0];
    for (int i = 1; i < n; i++) {
        if (arrA[i] < min) {
            min = arrA[i];
        }
    }
    return min;
}

void hitungRataRata() {
    float total = 0;
    for (int i = 0; i < n; i++) {
        total += arrA[i];
    }
    float rataRata = total / n;
    cout << "Nilai Rata-rata = " << rataRata << endl;
}

int main() {
    int pilihan;

    cout << "--- Menu Program Array ---" << endl;
    cout << "1. Tampilkan isi array" << endl;
    cout << "2. cari nilai maksimum" << endl;
    cout << "3. cari nilai minimum" << endl;
    cout << "4. Hitung nilai rata - rata" << endl;
    cin >> pilihan;

    switch (pilihan) {
        case 1:
            tampilkanArray();
            break;
        case 2:
            cout << "Nilai Maksimum = " << cariMaksimum() << endl;
            break;
        case 3:
            cout << "Nilai Minimum = " << cariMinimum() << endl;
            break;
        case 4:
            hitungRataRata();
            break;
        default:
            cout << "Menu tidak ada" << endl;
    }

    return 0;
}
```
### Output Unguided 3 :
--- Menu Program Array ---
1. Tampilkan isi array
2. cari nilai maksimum
3. cari nilai minimum
4. Hitung nilai rata - rata
1
Isi Array: 11 8 5 7 12 26 3 54 33 55

--- Menu Program Array ---
1. Tampilkan isi array
2. cari nilai maksimum
3. cari nilai minimum
4. Hitung nilai rata - rata
2
Nilai Maksimum = 55

--- Menu Program Array ---
1. Tampilkan isi array
2. cari nilai maksimum
3. cari nilai minimum
4. Hitung nilai rata - rata
3
Nilai Minimum = 3

--- Menu Program Array ---
1. Tampilkan isi array
2. cari nilai maksimum
3. cari nilai minimum
4. Hitung nilai rata - rata
4
Nilai Rata-rata = 21.4

##### Output 1
![Screenshot Output Unguided 3_1](https://github.com/arvinihsnn/Praktikum-Struktur-Data-2/blob/main/Praktikum-Modul-2/Output-Unguided/Output-Unguided-3.png)

Program ini mengolah data array 1 dimensi arrA menggunakan struktur menu switch-case dengan memilih nomor menu dari 1 hingga 4. Fungsi cariMaksimum() dan cariMinimum() membandingkan tiap elemen di dalam array untuk menemukan angka terbesar dan terkecil. Prosedur hitungRataRata() menghitung total penjumlahan seluruh elemen lalu membaginya dengan jumlah total data (10). Fungsi tampilkanArray() digunakan untuk mencetak seluruh isi elemen array ke layar.

## Kesimpulan
Pada praktikum modul 2 ini memberikan saya pemahaman mendasar mengenai konsep serta penerapan Array dan Pointer dalam bahasa C++. Array memudahkan penyimpanan sekumpulan data dengan tipe yang sama, baik dalam bentuk satu dimensi maupun multidimensi seperti contohnya matriks. Sementara itu, pointer memungkinkan pengaksesan dan pemrosesan lokasi alamat memori secara langsung menggunakan operator `&` dan `*`. Kombinasi keduanya sangat berguna untuk efisiensi pengolahan data serta pembuatan fungsi atau prosedur dalam pemrograman.

## Referensi
<br>[1] Annisa. (2023). Struktur Data Array: Pengertian, Fungsi, dan Contoh Program. Medan: FAKULTAS ILMU KOMPUTER DAN TEKNOLOGI INFORMASI UNIVERSTAS MUHAMMADIYAH SUMATERA UTARA MEDAN. Diakses pada 1 Oktober 2026 Melalui https://fikti.umsu.ac.id/struktur-data-array-pengertian-fungsi-dan-contoh-program/.
<br>[2] JURUSAN TEKNIK ELEKTRO FAKULTAS TEKNIK, UNIVERSITAS NEGERI MALANG. (2016). Modul Praktikum C++ Dasar Pemrograman Komputer. Malang: FAKULTAS TEKNIK UNIVERSITAS NEGERI MALANG. Diakses pada 1 Oktober 2026 melalui https://tei.um.ac.id/wp-content/uploads/2016/04/Dasar-Pemrograman-Modul-7-Pointer.pdf.