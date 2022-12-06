 ## Tugas Praktikum 8 
 
 # Nama : Bayu Pratama
 # Nim : 312210351
 # Kelas : TI.22.A3



### A. Flowchart

![flowchart](https://user-images.githubusercontent.com/115516635/205839633-0e9c1156-1382-48ca-830e-76bdbc056de3.jpeg)



![Gambar 3](img/ss2.png)

### B. Program

```bash
import os

class data_mhsw:
    nama=""
    nim=""
    tugas=""
    uts=""
    uas=""
    
data = []

def no_data():
        print("DAFTAR NILAI MAHASISWA")
        print("----------------------")
        print()
        print(" - TIDAK ADA DATA - ")
        print()
def tambah():
    os.system("cls")
    b = data_mhsw()
    print("TAMBAH DATA")
    print("------------")
    b.nama = (input("Nama Mahasiswa\t: "))
    b.nim = (int(input("NIM Mahasiswa\t: ")))
    b.tugas = (int(input("Nilai Tugas\t: ")))
    b.uts = (int(input("Nilai UTS\t: ")))
    b.uas = (int(input("Nilai UAS\t: ")))
    b.akhir = (b.tugas*30/100) + (b.uts*35/100) + (b.uas*35/100) 
    data.append(b)
    print()
def lihat():
    os.system("cls")
    if len(data) <=0:
        no_data()     
    else:
        for a in data:
            print("DAFTAR NILAI MAHASISWA")
            print("-----------------------")
            print("Nama Mahasiswa\t: "+a.nama)
            print("NIM Mahasiswa\t: "+str(a.nim))
            print("Nilai Tugas\t: "+str(a.tugas))
            print("Nilai UTS\t: "+str(a.uts))
            print("Nilai UAS\t: "+str(a.uas))
            print("Nilai Akhir\t: "+str(a.akhir))
            print()
def hapus():
        os.system("cls")
        if len(data) <=0:
            no_data()
        else:
            nama = data_mhsw()
            print("HAPUS DATA")
            print("----------")
            nama = (input("Nama Mahasiswa\t: "))
            for nama in data:
                data.remove(nama)
            print()
def ubah():
    os.system("cls")
    if len(data) <=0:
        no_data()
    else:
        nama = data_mhsw()
        print("UBAH DATA")
        print("---------")
        nama = (input("Nama Mahasiswa\t: "))
        for nama in data:
            nama.tugas = (int(input("Nilai Tugas\t: ")))
            nama.uts = (int(input("Nilai UTS\t: ")))
            nama.uas = (int(input("Nilai UAS\t: ")))
            akhir = (nama.tugas*30/100) + (nama.uts*35/100) + (nama.uas*35/100)
        print()
Loop = True
while Loop:
    print("Pilih Menu")
    print("----------")
    tanya = input("[(L)ihat, (T)ambah, (U)bah, (H)apus, (K)eluar] : ")
    print()

    if tanya=="l" or tanya=="L":
        lihat()
    
    elif tanya=="t" or tanya=="T":
        tambah()
    
    elif tanya=="u" or tanya=="U":
        ubah()
    
    elif tanya=="h" or tanya=="H":
        hapus()
    
    elif tanya=="k" or tanya=="K":
        print("Program Selesai")
        Loop = False
```

### D. Penjelasan

1. Untuk memanggil fungsi dengan nama "os".

    ```python
    import os
    ```

2. Membuat class `data_mhsw` dengan atributnya, yaitu nama, nim, tugas, uts dan uas.

    ```python
    class data_mhsw:
        nama=""
        nim=""
        tugas=""
        uts=""
        uas=""
    ```

3. Membuat variable `data = []` untuk menampung list dari `data_mhsw`.

    ```python
    data = []
    ```

4. Membuat fungsi tambahan, jika diperlukan fungsi tersebut akan dipanggil oleh program.

    ```python
    def no_data():
        print("DAFTAR NILAI MAHASISWA")
        print("----------------------")
        print()
        print(" - TIDAK ADA DATA - ")
        print()
    ```

5. Menambah data ( **tambah()** )
    * Menginput nim, nama, nilai tugas, nilai uts dan nilai uas.
    * Data yang telah diinput akan ditambahkan ke dalam variable `data`.

        ```python
        def tambah():
            os.system("cls")
            b = data_mhsw()
            print("TAMBAH DATA")
            print("------------")
            b.nama = (input("Nama Mahasiswa\t: "))
            b.nim = (int(input("NIM Mahasiswa\t: ")))
            b.tugas = (int(input("Nilai Tugas\t: ")))
            b.uts = (int(input("Nilai UTS\t: ")))
            b.uas = (int(input("Nilai UAS\t: ")))
            b.akhir = (b.tugas*30/100) + (b.uts*35/100) + (b.uas*35/100) 
            data.append(b)
            print()
        ```

    #### Output tambah()

    ![Gambar 4](img/ss3.jpeg)

6. Menampilkan data ( **lihat()** )
    * Jika belum menginput data, maka akan memanggil fungsi `no_data()`.
    * Jika sebelumnya sudah menginput data, maka data yang sudah diinput akan ditampilkan oleh program.

        ```python
        def lihat():
            os.system("cls")
            if len(data) <=0:
                no_data()     
            else:
                for a in data:
                    print("DAFTAR NILAI MAHASISWA")
                    print("-----------------------")
                    print("Nama Mahasiswa\t: "+a.nama)
                    print("NIM Mahasiswa\t: "+str(a.nim))
                    print("Nilai Tugas\t: "+str(a.tugas))
                    print("Nilai UTS\t: "+str(a.uts))
                    print("Nilai UAS\t: "+str(a.uas))
                    print("Nilai Akhir\t: "+str(a.akhir))
                    print()
        ```

    #### Output lihat()

    ![Gambar 5](img/ss4.jpeg)

7. Mengubah data ( **ubah()** )
    * Menginput nama, kemudian input data yang ingin diubah. 

        ```python
        def ubah():
            os.system("cls")
            if len(data) <=0:
                no_data()
            else:
                nama = data_mhsw()
                print("UBAH DATA")
                print("---------")
                nama = (input("Nama Mahasiswa\t: "))
                for nama in data:
                    nama.tugas = (int(input("Nilai Tugas\t: ")))
                    nama.uts = (int(input("Nilai UTS\t: ")))
                    nama.uas = (int(input("Nilai UAS\t: ")))
                    akhir = (nama.tugas*30/100) + (nama.uts*35/100) + (nama.uas*35/100)
                print()
        ```

    #### Output ubah()

    ![Gambar 6](img/ss5.jpeg)

8. Menghapus data ( **hapus()** )
    * Menginput nama, setelah nama diinput maka data yang lainnya akan ikut terhapus sesuai dengan nama yang diinputkan.

        ```python
        def hapus():
            os.system("cls")
            if len(data) <=0:
                no_data()
            else:
                nama = data_mhsw()
                print("HAPUS DATA")
                print("----------")
                nama = (input("Nama Mahasiswa\t: "))
                for nama in data:
                    data.remove(nama)
                print()
        ```

    #### Output hapus()

    ![Gambar 7](img/ss6.jpeg)

9. Menggunakan perulangan uncountable, yang artinya selama statement bernilai "True" maka program akan terus berjalan. Jika statementnya "False" maka program terhenti.

    ```python
    Loop = True
    while Loop:
        print("Pilih Menu")
        print("----------")
        tanya = input("[(L)ihat, (T)ambah, (U)bah, (H)apus, (K)eluar] : ")
        print()
        if tanya=="l" or tanya=="L":
            lihat()
        
        elif tanya=="t" or tanya=="T":
            tambah()
        
        elif tanya=="u" or tanya=="U":
            ubah()
        
        elif tanya=="h" or tanya=="H":
            hapus()
        
        elif tanya=="k" or tanya=="K":
            print("Program Selesai")
            Loop = False
    ```
  
# SEKIAN
