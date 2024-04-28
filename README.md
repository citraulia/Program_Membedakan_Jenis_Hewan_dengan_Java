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
