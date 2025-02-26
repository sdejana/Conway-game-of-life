# Conway’s Game of Life

Ovaj repozitorijum sadrži implementaciju **Conway’s Game of Life** – simulacije ćelijskog automata koji je osmislio Džon Konvej. Projekat prikazuje kako jednostavna pravila mogu generisati kompleksne obrasce kroz simulaciju evolucije mreže ćelija. Repozitorijum je nastao na osnovu zadataka na kursu Programiranje u realnom vremenu, koji se izvodi na Elektrotehničkom fakultetu u Banjoj Luci na smjeru Računarsko inženjerstvo.

U sklopu repozitorijuma obrađene su sljedeće teme:
## 1. Implementacija Conway - game of life na različite načine (IOCTL drajver, konzolna aplikacija)
## 2. Raspoređivanje procesa (zadataka)

## Karakteristike Conway - game-of-life 
- **Prilagodljiv početni raspored**: Korisnik može definisati početnu konfiguraciju mreže ili postaviti nasumičan raspored živih i mrtvih ćelija.
- **Vizuelizacija na terminalu**: Stanje mreže se prikazuje u konzoli, koristeći jednostavne simbole (`[#]` za žive ćelije i `[ ]` za mrtve ćelije).
- **Korisnički unos**: 
  - Učitavanje vremena pauze između generacija ćelija.
  - Ručno definisanje početnih stanja.
- **Jednostavan algoritam**: Efikasna logika za simulaciju promjena stanja mreže u svakom koraku.

## Kako funkcioniše
- **Pravila simulacije**:
  1. Živa ćelija preživljava ako ima **2 ili 3 susjeda**.
  2. Mrtva ćelija postaje živa ako ima **tačno 3 susjeda**.
  3. Sve ostale ćelije umiru ili ostaju mrtve.
  4. Susjedi se računaju prema Murovom pravilu susjeda
     
  ![Murovi susjedi](https://upload.wikimedia.org/wikipedia/commons/thumb/2/23/CA-Moore-Neighborhood.svg/300px-CA-Moore-Neighborhood.svg.png?20130202163711)
- **Simulacija**: Svaka iteracija mijenja stanje mreže prema ovim pravilima.

## Tehnologije i alati
- **C**: Implementacija simulacije i logike pravila.
- **Komandna linija**: Za unos početnih konfiguracija.
- **Konzola**: Za prikaz rezultata simulacije.

## Pokretanje aplikacije
1. Klonirajte repozitorijum: git clone https://github.com/sdejana/Conway-game-of-life.git
2. Na odgovarajućoj platformi (Raspbian OS, Raspberry 3 B+, sa preemptive verzijom Linux OS-a) učitajte drajvere: sudo insmod naziv_drajvera.ko
3. Provjerite minor i major broj učitanog drajvera (dmesg npr)
4. Napravite čvor u /dev particiji: sudo mknod /dev/naziv_čvora c minor major
5. Pokrenite main.c, odnosno testnu aplikaciju

## IOCTL drajver
## Osnovne funkcionalnosti IOCTL drajvera
### Učitavanje i registracija drajvera

Drajver se učitava u kernel pomoću: sudo insmod naziv_drajvera.ko.
Nakon učitavanja, potrebno je kreirati odgovarajući /dev čvor za interakciju s drajverom, kao što je opisano gore.

### IOCTL komande
IOCTL sistemski poziv omogućava slanje specijalnih komandi ka drajveru radi kontrole simulacije. Ključne funkcije uključuju:

-> Podešavanje početne konfiguracije – Korisnik može definisati inicijalno stanje mreže.

-> Postavljanje vremenskog intervala – Kontrola brzine generacija.

-> Pokretanje i zaustavljanje simulacije – Omogućava ručno pokretanje i pauziranje igre.

-> Čitanje trenutnog stanja mreže – Dohvata se trenutno stanje simulacije.

Korisnička aplikacija nakon kreiranja čvora može koristiti open(), read(), write() i ioctl() sistemske pozive za interakciju s drajverom.
