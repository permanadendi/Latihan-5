# Latihan-5

## Latihan
![1](ss/1.png)
Dari modul praktikum 3, tambahkan constructor pada masing-masing class dan tambahkan overload dan override constructor tersebut.

Pegawai
``` JavaSricpt
public class Pegawai {
    private String nama;
    private double gajiPokok;

    public Pegawai (String nama, double gajipokok) {
        this.nama = nama;
        this.gajiPokok = gajipokok;
    }

    // Setter dan getter untuk nama
    public void setNama(String nama) {
        this.nama = nama;
    }
    public String getNama() {
        return nama;
    }

    // Setter dan getter untuk gaji pokok
    public void setGajiPokok(double gajiPokok) {
        this.gajiPokok = gajiPokok;
    }
    public double getGajiPokok() {
        return gajiPokok;
    }

    // Metode untuk mencetak informasi pegawai
    public void cetakInfo() {
        System.out.println("Nama: " + nama);
        System.out.println("Gaji Pokok: " + gajiPokok);
    }

}
```

Manager
``` Javasripct
public class Manager extends Pegawai {
    private double tunjangan;

    public Manager(String nama, double gajipokok, double tunjangan) {
        super(nama, gajipokok);
        this.tunjangan = tunjangan;
    }

    // Setter dan getter untuk tunjangan
    public void setTunjangan(double tunjangan) {
        this.tunjangan = tunjangan;
    }
    public double getTunjangan() {
        return tunjangan;
    }

    // Metode untuk mencetak informasi manager
    @Override
    public void cetakInfo() {
        super.cetakInfo();
        System.out.println("Tunjangan: " + tunjangan);
    }

}
```

Programmer
``` Javascript
public class Programmer extends Pegawai {
    private double bonus;

    public Programmer(String nama, double gajipokok, double bonus) {
        super(nama, gajipokok);
        this.bonus = bonus;
    }

    // Setter dan getter untuk bonus
    public void setBonus(double bonus) {
        this.bonus = bonus;
    }
    public double getBonus() {
        return bonus;
    }

    // Metode untuk mencetak informasi programmer
    @Override
    public void cetakInfo() {
        super.cetakInfo();
        System.out.println("Bonus: " + bonus);
    }

    // Metode tambahan untuk mencetak bonus
    public void cetakBonus() {
        System.out.println("Bonus: " + bonus);
    }

}
```

#### Tampilan Output
![2](ss/2.png)

## Studi Kasus: Sistem Pembelian Online dengan Keranjang Belanja
**Deskripsi:**
Buatlah sistem pembelian online sederhana dengan keranjang belanja (shopping cart) yang dapat menampung beberapa jenis produk, seperti **Elektronik**, **Pakaian**, dan **Makanan**.
### Detail Soal:
1. **Class Produk**:
   - Buat class `Produk` sebagai class induk dengan property `namaProduk`, `harga`, dan `jumlahStok`.
   - Tambahkan constructor untuk inisialisasi property tersebut.
   - Tambahkan method `displayInfo()` untuk menampilkan informasi produk.
2. **Subclass Elektronik, Pakaian, dan Makanan**:
   - Buat subclass `Elektronik` dengan tambahan property `garansi` (misalnya, 1 tahun atau 2 tahun).
   - Buat subclass `Pakaian` dengan tambahan property `ukuran` dan `warna`.
   - Buat subclass `Makanan` dengan property tambahan `tanggalKadaluwarsa`.
   - Override method `displayInfo()` pada setiap subclass untuk menampilkan informasi spesifik.
3. **Class KeranjangBelanja**:
   - Buat class `KeranjangBelanja` yang berisi daftar produk yang dibeli.
   - Tambahkan method `tambahProduk(Produk p, int jumlah)`, untuk menambahkan produk ke dalam keranjang, dan periksa apakah stok produk mencukupi.
   - Tambahkan method `hitungTotalBelanja()` untuk menghitung total harga seluruh produk di keranjang.
   - Tambahkan method `displayKeranjang()` untuk menampilkan isi keranjang belanja.
4. **Main Class**:
   - Buat beberapa objek dari jenis produk yang berbeda, tambahkan beberapa produk ke `KeranjangBelanja`.
   - Tampilkan total belanja dan isi keranjang menggunakan method `displayKeranjang()`.
**Contoh Output**: Saat `displayKeranjang()` dipanggil, sistem harus menampilkan daftar produk di dalam keranjang dengan harga masing-masing produk, serta total harga seluruh produk di keranjang.
![3](ss/3.png)

Produk
``` Javascript
// Kelas Produk
class Produk {
    protected String namaProduk;
    protected double harga;
    protected int jumlahStok;

    public Produk(String namaProduk, double harga, int jumlahStok) {
        this.namaProduk = namaProduk;
        this.harga = harga;
        this.jumlahStok = jumlahStok;
    }

    public void displayInfo() {
        System.out.println("Nama Produk: " + namaProduk);
        System.out.println("Harga: " + harga);
        System.out.println("Stok: " + jumlahStok);
    }
}
```

Elektronik
``` Javascript
// Subclass Elektronik
class Elektronik extends Produk {
    private int garansi;

    public Elektronik(String namaProduk, double harga, int jumlahStok, int garansi) {
        super(namaProduk, harga, jumlahStok);
        this.garansi = garansi;
    }

    @Override
    public void displayInfo() {
        super.displayInfo();
        System.out.println("Garansi: " + garansi + " tahun");
    }
}
```

Pakaian
``` Javascript
// Subclass Pakaian
class Pakaian extends Produk {
    private String ukuran;
    private String warna;

    public Pakaian(String namaProduk, double harga, int jumlahStok, String ukuran, String warna) {
        super(namaProduk, harga, jumlahStok);
        this.ukuran = ukuran;
        this.warna = warna;
    }

    @Override
    public void displayInfo() {
        super.displayInfo();
        System.out.println("Ukuran: " + ukuran);
        System.out.println("Warna: " + warna);
    }
}
```

Makanan
``` Javascript
// Subclass Makanan
class Makanan extends Produk {
    private String tanggalKadaluarsa;

    public Makanan(String namaProduk, double harga, int jumlahStok, String tanggalKadaluarsa) {
        super(namaProduk, harga, jumlahStok);
        this.tanggalKadaluarsa = tanggalKadaluarsa;
    }

    @Override
    public void displayInfo() {
        super.displayInfo();
        System.out.println("Tanggal Kadaluarsa: " + tanggalKadaluarsa);
    }
}
```

KeranjangBelanja
``` Javascript
// Kelas KeranjangBelanja
import java.util.ArrayList;

class KeranjangBelanja {
    private ArrayList<Produk> daftarProduk = new ArrayList<>();

    public void tambahProduk(Produk p, int jumlah) {
        if (p.jumlahStok >= jumlah) {
            daftarProduk.add(p);
            p.jumlahStok -= jumlah;
            System.out.println(jumlah + " " + p.namaProduk + " berhasil ditambahkan ke keranjang.");
        } else {
            System.out.println("Stok " + p.namaProduk + " tidak mencukupi.");
        }
    }

    public double hitungTotalBelanja() {
        double total = 0;
        for (Produk p : daftarProduk) {
            total += p.harga;
        }
        return total;
    }

    public void displayKeranjang() {
        System.out.println("Isi Keranjang Belanja:");
        for (Produk p : daftarProduk) {
            p.displayInfo();
            System.out.println("---------------------");
        }
        System.out.println("Total Harga: " + hitungTotalBelanja());
    }
}
```

Main
``` Javascript
// Kelas Main untuk pengujian
public class Main {
    public static void main(String[] args) {
        // Membuat beberapa objek produk
        Elektronik laptop = new Elektronik("Laptop", 1500000, 10, 2);
        Pakaian baju = new Pakaian("Baju", 200000, 20, "L", "Merah");
        Makanan roti = new Makanan("Roti", 15000, 50, "2024-12-01");

        // Membuat keranjang belanja
        KeranjangBelanja keranjang = new KeranjangBelanja();

        // Menambahkan produk ke keranjang belanja
        keranjang.tambahProduk(laptop, 1);
        keranjang.tambahProduk(baju, 2);
        keranjang.tambahProduk(roti, 3);

        // Menampilkan isi keranjang belanja
        keranjang.displayKeranjang();
    }
}
```

#### Tampilan Output
![4](ss/4.png)
