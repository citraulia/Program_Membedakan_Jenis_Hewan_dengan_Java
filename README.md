# Program Membedakan Jenis Hewan dengan Java
<br> Nama        : CITRA AULIA
<br> NIM         : 1227050030
<br> Mata Kuliah : Praktikum Pemrograman Berorientasi Objek

<br> Di bawah ini adalah contoh program untuk membedakan jenis hewan dengan menggunakan bahasa Java yang didalamnya terdapat konsep PBO yaitu sebagai berikut:
<br> 1. Encapsulation
<br> 2. Inheritance
<br> 3. Polimorphism
<br> 4. Interface atau Abstract

## Source Code
```Java
// Encapsulation (Kelas Hewan)
class Hewan {
    private String nama;
    private int usia;

    public Hewan(String nama, int usia) {
        this.nama = nama;
        this.usia = usia;
    }

    public String getNama() {
        return nama;
    }

    public void setNama(String nama) {
        this.nama = nama;
    }

    public int getUsia() {
        return usia;
    }

    public void setUsia(int usia) {
        this.usia = usia;
    }

    public void bersuara() {
        System.out.println("Suara hewan belum ditentukan");
    }
}

// Inheritance (Kelas Burung dan Anjing)
class Burung extends Hewan {
    public Burung(String nama, int usia) {
        super(nama, usia);
    }

    @Override
    public void bersuara() {
        System.out.println(getNama() + " berkicau");
    }
}

class Anjing extends Hewan {
    public Anjing(String nama, int usia) {
        super(nama, usia);
    }

    @Override
    public void bersuara() {
        System.out.println(getNama() + " menggonggong");
    }
}

// Interface (Kelas Peliharaan)
interface Peliharaan {
    void makan();
    void bermain();
}

// Polimorphism (Implementasi Interface Peliharaan)
class BurungPeliharaan extends Burung implements Peliharaan {
    public BurungPeliharaan(String nama, int usia) {
        super(nama, usia);
    }

    @Override
    public void makan() {
        System.out.println(getNama() + " sedang makan biji-bijian");
    }

    @Override
    public void bermain() {
        System.out.println(getNama() + " sedang bermain di sangkar");
    }
}

class AnjingPeliharaan extends Anjing implements Peliharaan {
    public AnjingPeliharaan(String nama, int usia) {
        super(nama, usia);
    }

    @Override
    public void makan() {
        System.out.println(getNama() + " sedang makan dog food");
    }

    @Override
    public void bermain() {
        System.out.println(getNama() + " sedang bermain di taman");
    }
}

// Penggunaan Kelas dan Interface
public class DemoEncapsulationInheritancePolimorphismInterface {

    public static void main(String[] args) {
        BurungPeliharaan burungPeliharaan = new BurungPeliharaan("Kakatua", 5);
        AnjingPeliharaan anjingPeliharaan = new AnjingPeliharaan("Budi", 3);

        System.out.println("**Burung Peliharaan**");
        burungPeliharaan.bersuara();
        burungPeliharaan.makan();
        burungPeliharaan.bermain();

        System.out.println("\n**Anjing Peliharaan**");
        anjingPeliharaan.bersuara();
        anjingPeliharaan.makan();
        anjingPeliharaan.bermain();
    }
}
```

## Output
![Screenshot (409)](https://github.com/citraulia/Program_Membedakan_Jenis_Hewan_dengan_Java/assets/121267209/11e05f0a-f70d-40a5-b678-9d3015cdd4c6)

## Penjelasan
**Encapsulation (Kelas Hewan):**
<br> 1. Atribut Private: nama dan usia dideklarasikan sebagai private. Artinya, atribut ini hanya dapat diakses dari dalam kelas Hewan sendiri. Hal ini membantu menjaga data tersembunyi dari luar kelas dan meningkatkan keamanan.
<br> 2. Metode Getter dan Setter: Kelas Hewan menyediakan metode getNama(), setNama(), getUsia(), dan setUsia(). Metode-metode ini memungkinkan akses dan modifikasi nilai atribut nama dan usia secara terkontrol.
<br> getNama(): Mengambil nilai atribut nama.
<br> setNama(): Mengubah nilai atribut nama dengan parameter baru.
<br> getUsia(): Mengambil nilai atribut usia.
<br> setUsia(): Mengubah nilai atribut usia dengan parameter baru.
<br> 3. Metode bersuara(): Metode ini didefinisikan sebagai abstract. Artinya, kelas Hewan tidak memberikan implementasi spesifik untuk metode ini. Implementasi yang konkret akan disediakan oleh kelas turunannya (seperti Burung dan Anjing).

<br> **Inheritance (Kelas Burung dan Anjing):**
<br> 1. Pewarisan Atribut dan Metode: Kelas Burung dan Anjing mewarisi atribut nama dan usia serta metode getNama(), setNama(), getUsia(), dan setUsia() dari kelas Hewan. Ini memungkinkan reuse kode dan menghindari duplikasi.
<br> 2. Konstruktor: Kelas Burung dan Anjing memiliki konstruktornya sendiri yang memanggil konstruktor super (super(nama, usia)) untuk menginisialisasi atribut nama dan usia.
<br> 3. Metode bersuara() yang Diubah: Metode bersuara() didefinisikan ulang (override) di kelas Burung dan Anjing. Hal ini memungkinkan implementasi yang berbeda untuk menghasilkan suara yang berbeda sesuai dengan jenis hewannya.
<br> Burung.bersuara(): Mencetak pesan "Kakatua berkicau".
<br> Anjing.bersuara(): Mencetak pesan "Budi menggonggong".

<br> **Interface (Kelas Peliharaan):**
<br> 1. Deklarasi Interface: Interface Peliharaan mendefinisikan dua metode abstrak: makan() dan bermain(). Interface ini tidak memiliki implementasi metode, hanya deklarasi.
<br> 2. Implementasi Interface: Kelas BurungPeliharaan dan AnjingPeliharaan mengimplementasikan interface Peliharaan. Artinya, kelas-kelas ini wajib menyediakan implementasi untuk metode makan() dan bermain().
<br> BurungPeliharaan.makan(): Mencetak pesan "Kakatua sedang makan biji-bijian".
<br> BurungPeliharaan.bermain(): Mencetak pesan "Kakatua sedang bermain di sangkar".
<br> AnjingPeliharaan.makan(): Mencetak pesan "Budi sedang makan dog food".
<br> AnjingPeliharaan.bermain(): Mencetak pesan "Budi sedang bermain di taman".

<br> **Polimorphism:**
<br> 1. Metode bersuara() yang Diubah: Seperti dijelaskan sebelumnya, metode bersuara() diubah di kelas Burung dan Anjing. Hal ini memungkinkan program untuk memilih implementasi yang tepat berdasarkan kelas objek saat runtime.
<br> 2. Panggilan Metode makan() dan bermain(): Di dalam metodemain(), objekburungPeliharaandananjingPeliharaandipanggil untuk menjalankan metodemakan()danbermain(). Karena kedua kelas mengimplementasikan interfacePeliharaan`, program dapat memanggil metode-metode ini tanpa mengetahui kelas spesifiknya.

<br> **Penggunaan Kelas dan Interface:**
<br> 1. Kelas Demo: Kelas ini hanya berisi metode main() yang digunakan untuk membuat objek BurungPeliharaan dan AnjingPeliharaan, kemudian memanggil metode bersuara(), makan(), dan bermain() untuk setiap objek.
<br> 2. Pembuatan Objek: Objek burungPeliharaan dan anjingPeliharaan dibuat dengan menggunakan konstruktor dari kelas BurungPeliharaan dan AnjingPeliharaan
Panggilan Metode: Metode bersuara(),
