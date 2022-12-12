# Praktikum8

Repository ini digunakan untuk memenuhi Tugas Bahasa Pemrograman Pertemuan-12

Nama    : Mohamad Irvan Zidni

NIM     : 312210308

Kelas   : TI.22.A.3

## Flowchart
Buatlah alur flowchart terlebih dahulu untuk mempermudah dalam membuat program

![Img](Foto/Flowchart%20Tugas%201.png)

## Code
### Penjelasan setiap program

1. Membuat class_Mahasiswa terlebih dahulu
        
        class Mahasiswa:
            nama = ""
            nim = ""
            uts = ""
            uas = ""
            tugas = ""
            akhir = ""

2. Membuat list data_Mhs kosong terlebih dahulu untuk menampung data dalam class_Mahasiswa
        
        dataMhs = []

3. Menu program menambahkan data (Nama, NIM, Nilai)

        def add():
            Mhs = Mahasiswa()
            print("TAMBAH DATA")

            Mhs.nama = input("Nama        : ")
            Mhs.nim  = input("NIM         : ")
            Mhs.tugas = int(input("Nilai Tugas : "))
            Mhs.uts = int(input("Nilai UTS   : "))
            Mhs.uas = int(input("Nilai UAS   : "))
            Mhs.akhir = (Mhs.tugas * 30/100) + (Mhs.uts * 35/100) + (Mhs.uas * 35/100)

            dataMhs.append(Mhs)
    
4. Menu program melihat data yang sudah dimasukkan kedalam list

        def show():
            print("\n")
            print("      DAFTAR NILAI MAHASISWA")
            if len(dataMhs) <= 0:
                print("=================================")
                print("         TIDAK ADA DATA")
                print("\n")
                print("=================================")
            else:
                for Mhs in dataMhs:
                    print("=================================")
                    print("Nama        : {} ".format(Mhs.nama))
                    print("NIM         : {} ".format(Mhs.nim))
                    print("Nilai Tugas : {} ".format(Mhs.tugas))
                    print("Nilai UTS   : {} ".format(Mhs.uts))
                    print("Nilai UAS   : {} ".format(Mhs.uas))
                    print("Nilai Akhir : {:.1f} ".format(Mhs.akhir))
                    print("=================================")

5. Menu program menghapus data dalam list

        def delete():
            print("HAPUS DATA")
            nama = Mahasiswa()
            nama = input("Nama : ")
            for data in dataMhs:
                if nama == data.nama:
                    dataMhs.remove(data)

                    print("Berhasil Dihapus")
            
                else:
                    print("DATA TIDAK DITEMUKAN")

6. Menu program memperbarui data dalam list

        def update():
            print("UBAH DATA")
            nama = Mahasiswa()
            nama = input("Nama : ")
            print("\n")

            for data in dataMhs:
                if nama == data.nama:
                    data.tugas = int(input("Nilai Tugas : "))
                    data.uts = int(input("Nilai UTS   : "))
                    data.uas = int(input("Nilai UAS   : "))
                    data.akhir = (data.tugas * 30/100) + (data.uts * 35/100) + (data.uas * 35/100)

                    print("DATA BERHASIL DIUBAH")

                else:
                    print("DATA TIDAK DITEMUKAN")
7. Menu program menu utama dengan menggunakan perulangan while

        while True:
            print("\n")
            print("==========================")
            print("    Program Input Nilai   ")
            print("==========================")

            print("[1] LIHAT DATA (L)")
            print("[2] TAMBAH DATA (T)")
            print("[3] UBAH DATA (U)")
            print("[4] HAPUS DATA (H)")
            print("[5] KELUAR (K)")

            menu = input("PILIH MENU :")

            if menu == 'L':
                show()

            elif menu == 'T':
                add()
            
            elif menu == 'U':
                update()
            
            elif menu == 'H':
                delete()
            
            elif menu == 'K':
                print("\n")
                print("thank you for using the code :) ")

                exit()