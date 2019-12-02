# Tugas-5
# Menbuat dictionary daftar kontak
# {key: value}
kontak = {'Mohammad': '081267888', 'Dina': '087677776'}
# menampilkan kontak ari
print("Kontaknya Mohammad adalah: ", kontak['Mohammad'])
# menambah kontak baru
print(kontak)
kontak['Riko'] = '087654544'
print(kontak)
# mengubah kontak dina
print(kontak)
kontak['Dina'] = '088999776'
print(kontak)
# tampilkan semua nama
print(kontak.keys())
# tampilkan semua nomor
print(kontak.values())
# menampilkan daftar kontak
print("==========================")
print("Nama | Nomor Telpon")
print("==========================")
for x in kontak.items():
    print("{0:10s} | {1}".format(x[0][:10], x[1]))
# hapus kontak dina
del kontak['Dina']
print(kontak)

while True:
    print("")
    c = input("A)dd, E)dit, D)elete, S)earch, L)ist, Q)uit: ")
    if c.lower() == 'q':
        break
    elif c.lower() == 'l':
        print("Daftar Kontak")
        print("==========================")
        print("Nama       | Nomor Telpon")
        print("==========================")
        for x in kontak.items():
            print("{0:10s} | {1}".format(x[0][:10], x[1]))
        print("==========================")
    elif c.lower() == 'a':
        print("Tambah Kontak")
        nama = input("Nama: ")
        nomor = input("Nomor: ")
        kontak[nama] = nomor
    elif c.lower() == 'e':
        print("Edit Kontak")
        nama = input("Nama: ")
        if nama in kontak.keys():
            nomor = input("Nomor baru: ")
            kontak[nama] = nomor
        else:
            print("Kontak {0} tidak ada".format(nama))
    elif c.lower() == 'd':
        print("Hapus Kontak")
        nama = input("Nama: ")
        if nama in kontak.keys():
            del kontak[nama]
        else:
            print("Kontak {0} tidak ada".format(nama))
    elif c.lower() == 's':
        print("Search Kontak")
        nama = input("Nama: ")
        if nama in kontak.keys():
            print("Kontaknya {0} adalah {1}"
                .format(nama, kontak[nama]))
        else:
            print("Kontak {0} tidak ada".format(nama))
    else:
        print("Pilih menu yang tersedia")
