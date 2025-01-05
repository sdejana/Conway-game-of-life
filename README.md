# Conway’s Game of Life

Ovaj repozitorijum sadrži implementaciju **Conway’s Game of Life** – simulacije ćelijskog automata koji je osmislio Džon Konvej. Projekat prikazuje kako jednostavna pravila mogu generisati kompleksne obrasce kroz simulaciju evolucije mreže ćelija. Repozitorijum je nastao na osnovu zadataka na kursu Programiranje u realnom vremenu, koji se izvodi na Elektrotehničkom fakultetu u Banjoj Luci na smjeru Računarsko inženjerstvo.

U sklopu repozitorijuma obrađene su sljedeće teme:
dodati

## Karakteristike Conway - game-of-life Task1
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
1. Klonirajte repozitorijum:  
  
