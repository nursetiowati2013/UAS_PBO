# UAS_PBO
Class Diagram :
```mermaid
classDiagram
    Nasabah <-- Perusahaan
    Nasabah <-- Individu
    Nasabah "1" o--> "1..*" Rekening
    class Nasabah{
      -String nama
      -String alamat
      -String idNasabah

      -ArrayList<Rekening> rekening
      +Nasabah(nama,alamat,idNasabah, rekening)
      +tambahRekening(Rekening rek)
      +print() : void
      <<abstract>>
    }
 
    class Rekening{
      -int noRekening
      -double saldo
      +Rekening(noRekening, saldo)
      +tambahSaldo(double jumlah) : void
      +tarikTunai(double jumlah) :void
    }

    class Perusahaan{
      -String nib
      
      +Perusahaan(nib, nama, alamat, idNasabah)
      +print()
    }

    class Individu{
        -Long nik
        -Long npwp

        +Individu(nik, npwp, nama, alamat, idNasabah, Rekening)
        +print()
    }
```
ER Diagram :
 ```mermaid  
  erDiagram
          Nasabah ||--|| Perusahaan : is
          Nasabah ||--|| Individu : is
          Nasabah ||--|{ Rekening : have
          
          REKENING{
                int noRekening
                double saldo
                int id_nasabah
            }

            Nasbaah {
                int idNasabah
                string nama
                string alamat
            }
            
            INDIVIDU{
                int id_nasabah
                long nik
                long npwp
            }
            PERUSAHAAN{
                int id_nasabah
                string nib
            }
```
