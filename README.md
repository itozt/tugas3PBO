# Tugas 3 PBO - Mesin Tiket
Program ini memberikan gambaran dasar tentang bagaimana mengelola transaksi tiket menggunakan Java, dan dapat dikembangkan lebih lanjut sesuai kebutuhan spesifik.

Source Code :
```
public class MesinTiket {
    // Atribut untuk harga tiket, saldo pengguna, dan total yang dibayar
    private double harga;
    private double saldo;
    private double total;

    // Constructor untuk inisialisasi mesin tiket
    public MesinTiket(double harga, double saldo){
        this.harga = harga;
        this.saldo = saldo;
        this.total = 0.0;}

    public double getHarga(){   // Method untuk mendapatkan harga tiket
        return harga;}

    public double getSaldo(){   // Method untuk mendapatkan saldo pengguna
        return saldo;}

    public double getTotal(){   // Method untuk mendapatkan total yang dibayar
        return total;}

    public void bayarTiket(){   // Method untuk membayar tiket
        if (saldo >= harga){
            saldo -= harga;
            total += harga;
            System.out.println("Pembayaran berhasil. Saldo tersisa: " + saldo);
        } else {
            System.out.println("Saldo tidak mencukupi, perlu saldo sebanyak: " + (harga - saldo));
        }
    }

    public void tambahSaldo(double jumlah){ // Method untuk menambahkan saldo
        saldo += jumlah;
        System.out.println("Saldo berhasil ditambahkan. Saldo saat ini: " + saldo);
    }

    // Method utama untuk menjalankan program
    public static void main(String[] args){
        // Membuat objek MesinTiket dengan harga tiket 50 dan saldo awal 100
        MesinTiket mesin = new MesinTiket(50, 100);

        // Menampilkan harga tiket, saldo awal, dan total yang dibayar
        System.out.println("Harga tiket: " + mesin.getHarga());
        System.out.println("Saldo awal: " + mesin.getSaldo());
        System.out.println("Total yang dibayar: " + mesin.getTotal());

        // Mencoba membayar tiket
        mesin.bayarTiket();

        // Menampilkan saldo setelah pembayaran
        System.out.println("Saldo setelah pembayaran: " + mesin.getSaldo());
        System.out.println("Total yang dibayar setelah pembayaran: " + mesin.getTotal());

        mesin.tambahSaldo(30);   // Mencoba menambahkan saldo
        mesin.bayarTiket();      // Mencoba membayar tiket lagi setelah menambahkan saldo

        // Menampilkan saldo akhir dan total yang dibayar
        System.out.println("Saldo akhir: " + mesin.getSaldo());
        System.out.println("Total yang dibayar akhir: " + mesin.getTotal());
    }
}
```
##### Penjelasan Kode :
###### 1. Deklarasi Kelas dan Atribut :
MesinTiket adalah kelas utama yang memiliki tiga atribut: harga (harga tiket), saldo (saldo pengguna), dan total (total yang dibayar).
###### 2. Constructor :
Constructor `MesinTiket(double harga, double saldo)` digunakan untuk menginisialisasi harga tiket dan saldo pengguna. Total pembayaran diatur ke 0.0 pada awalnya.
###### 3. Method Getter :
`getHarga()`, `getSaldo()`, dan `getTotal()` digunakan untuk mengambil nilai dari atribut-atribut harga, saldo, dan total.
###### 4. Method bayarTiket() :
Method ini memeriksa apakah saldo cukup untuk membayar tiket. Jika saldo mencukupi, saldo akan dikurangi sesuai harga tiket dan total akan bertambah. Jika tidak mencukupi, program akan menampilkan pesan yang menunjukkan kekurangan saldo.
###### 5. Method tambahSaldo(double jumlah) :
Method ini digunakan untuk menambahkan saldo pengguna dengan jumlah yang ditentukan. Setelah menambahkan saldo, saldo saat ini ditampilkan.
###### 6. Method main(String[] args) :
Method utama ini membuat objek MesinTiket, menampilkan informasi awal, mencoba melakukan pembayaran, menambah saldo, dan mencoba melakukan pembayaran lagi. Ini juga menampilkan saldo dan total yang dibayar setelah setiap tindakan.
