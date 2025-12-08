class ProdukKosmetik:
    def __init__(self, nama, harga):
        self.nama = nama
        self.harga = harga
from kelas import ProdukKosmetik

# Membuat objek
lipstik = ProdukKosmetik("Lipstik Matte", 50000)

print("Nama Produk :", lipstik.nama)
print("Harga       : Rp", lipstik.harga)
class ProdukKosmetik:
    def __init__(self, nama, harga):
        self.nama = nama
        self.__harga = harga  # enkapsulasi (private)

    # Getter
    def get_harga(self):
        return self.__harga

    # Setter
    def set_harga(self, harga_baru):
        if harga_baru > 0:
            self.__harga = harga_baru

# Uji enkapsulasi
serum = ProdukKosmetik("Serum Acne", 75000)

print("Nama:", serum.nama)
print("Harga (via getter):", serum.get_harga())
class ProdukKosmetik:
    def __init__(self, nama, harga):
        self.nama = nama
        self.harga = harga

    def info(self):
        return f"{self.nama} - Rp {self.harga}"

# Class turunan
class Skincare(ProdukKosmetik):
    def __init__(self, nama, harga, jenis_kulit):
        super().__init__(nama, harga)
        self.jenis_kulit = jenis_kulit

serum = Skincare("Serum Brightening", 90000, "Normal")

print(serum.info())
print("Jenis kulit:", serum.jenis_kulit)
class ProdukKosmetik:
    def info(self):
        return "Ini produk kosmetik umum."

class Makeup(ProdukKosmetik):
    def info(self):
        return "Makeup dipakai untuk mempercantik wajah."

class Skincare(ProdukKosmetik):
    def info(self):
        return "Skincare dipakai untuk merawat kulit."

# Polimorfisme: method sama, hasil berbeda
produk_list = [
    ProdukKosmetik(),
    Makeup(),
    Skincare()
]

for p in produk_list:
    print(p.info())
