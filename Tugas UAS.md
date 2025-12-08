<!DOCTYPE html>
<html>
<head>
  <title>Contoh Kelas</title>
  <meta charset="UTF-8">
</head>
<body>
<h2>Contoh Kelas ProdukKosmetik</h2>
<pre id="out"></pre>

<script>
class ProdukKosmetik {
  constructor(nama, harga) {
    this.nama = nama;
    this.harga = harga;
  }
}

const out = document.getElementById("out");
out.textContent = "Kelas ProdukKosmetik berhasil dibuat!";
</script>
</body>
</html>
 

<!DOCTYPE html>
<html>
<head>
  <title>Contoh Objek</title>
  <meta charset="UTF-8">
</head>
<body>
<h2>Contoh Objek</h2>
<pre id="out"></pre>

<script>
class ProdukKosmetik {
  constructor(nama, harga) {
    this.nama = nama;
    this.harga = harga;
  }
}

// membuat objek
const lipstik = new ProdukKosmetik("Lipstik Matte", 50000);

document.getElementById("out").textContent =
  Objek dibuat:\nNama: ${lipstik.nama}\nHarga: Rp ${lipstik.harga};
</script>
</body>
</html>


<!DOCTYPE html>
<html>
<head>
  <title>Contoh Enkapsulasi</title>
  <meta charset="UTF-8">
</head>
<body>
<h2>Contoh Enkapsulasi</h2>
<pre id="out"></pre>

<script>
class ProdukKosmetik {
  #harga; // private

  constructor(nama, harga) {
    this.nama = nama;
    this.#harga = harga;
  }

  getHarga() {
    return this.#harga;
  }

  setHarga(h) {
    if (h > 0) this.#harga = h;
  }
}

const serum = new ProdukKosmetik("Serum Acne", 80000);

document.getElementById("out").textContent =
  Nama: ${serum.nama}\nHarga (via getter): Rp ${serum.getHarga()};
</script>
</body>
</html>


 <!DOCTYPE html>
<html>
<head>
  <title>Contoh Inheritance</title>
  <meta charset="UTF-8">
</head>
<body>
<h2>Contoh Inheritance</h2>
<pre id="out"></pre>

<script>
class ProdukKosmetik {
  constructor(nama, harga) {
    this.nama = nama;
    this.harga = harga;
  }

  info() {
    return ${this.nama} - Rp ${this.harga};
  }
}

// Child class
class Skincare extends ProdukKosmetik {
  constructor(nama, harga, jenisKulit) {
    super(nama, harga);
    this.jenisKulit = jenisKulit;
  }
}

const toner = new Skincare("Toner Glow", 45000, "Berminyak");

document.getElementById("out").textContent =
  toner.info() + \nJenis Kulit: ${toner.jenisKulit};
</script>
</body>
</html>


<!DOCTYPE html>
<html>
<head>
  <title>Contoh Polimorfisme</title>
  <meta charset="UTF-8">
</head>
<body>
<h2>Contoh Polimorfisme</h2>
<pre id="out"></pre>

<script>
class ProdukKosmetik {
  info() {
    return "Ini produk kosmetik umum.";
  }
}

class Makeup extends ProdukKosmetik {
  info() {
    return "Makeup: Produk untuk mempercantik wajah.";
  }
}

class Skincare extends ProdukKosmetik {
  info() {
    return "Skincare: Produk untuk merawat kulit.";
  }
}

// Polimorfisme: memanggil method yang sama → output berbeda
const list = [
  new ProdukKosmetik(),
  new Makeup(),
  new Skincare()
];

let text = "";
list.forEach((p, i) => {
  text += ${i+1}. ${p.info()}\n;
});

document.getElementById("out").textContent = text;
</script>
</body>
</html>
