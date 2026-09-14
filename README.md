Ispravci imena ulica službenog DGU repozitorija adresa. Imamo dvije datoteke, `curated_streets.csv` i `curated_streets_per_naselje.csv`. 

## curated_streets.csv

Ovo je datoteka koja na imena ulica stavlja ispravke. Jedno ime ulice potencijalno ima nekoliko ulica u nekoliko gradova koje se isto zovu. Zato je ovo manje precizno ispravljanje, a u drugoj datoteci imamo preciznije ispravljanje.

## Kolone

* rgz_name - službeno ime ulice u DGU
* name - ispravljeno ime ulice
* name:rs - srpsko ispravljeno ime ulice, ako je naselje dvojezično
* name:it - talijansko ispravljeno ime ulice, ako je naselje dvojezično
* name:hu - mađarsko ispravljeno ime ulice, ako je naselje dvojezično
* loc_name - lokalno ime ulice
* name:etymology:wikidata - wikidata item po kojem je ulica nazvana
* comment - komentar

## name
Kod ispravljanja imena koristila su se slijedeća pravila:

1. dodavanje riječi "ulica" ako je izostavljeno, što znači:
  * ako imamo ime u genitivu, recimo `Vesne Parun`, onda dodajemo `Ulica Vesne Parun`
  * ako imamo pridjev tipa `Vinkovačka`, onda dodajemo `Vinkovačka ulica`
2. brisanje crtice kod nadimaka, ako imamo `Ulica Marije Jurić - Zagorke` onda brišemo crticu i imamo `Ulica Marije Jurić Zagorke`
3. dodavanje crtica ako je nešto spojeno prezime, recimo `Ulica Ivane Brlić Mažuranić` pretvaramo u `Ulica Ivane Brlić-Mažuranić`
4. dodajemo točku na redne brojeve, recimo `Ulica kralja Petra Krešimira IV` pretvaramo u `Ulica kralja Petra Krešimira IV.`
5. popravljanje redoslijeda riječi, recimo `Ulica Trajektna` prepravljamo u `Trajektna ulica`

## name:etymology:wikidata
Dodajemo wikidata item od nečega što je direktan povod za ime ulice. Ako se ulica zove `Ulica kraljice Jelene` onda dodajemo `Q1283638`. Ali ako se ulica zove `Ulica staro selo` onda nećemo dodati wikidata item za "starost" ili "selo" nego bi trebali naći po kojem je to starom selu nazvana ulica, i onda dodati wikidata item od tog starog sela. Često nećemo imati wikidata item za to, pa treba ostaviti prazno.

## loc_name
Ponekad ime ulice u DGU bazi ima alternativan naziv u zagradama, recimo `Trg hrvatskih branitelja (Bećarski križ)` tu `Bećarski križ` stavljamo u loc_name

## comment
Dobro je kod nekih slučajeva staviti komentar kako slijedeći korisnik ne bi morao ponovo tražiti zašto je nešto postavljeno kako je.

## curated_streets_per_naselje.csv

Ovo je datoteka koja direktno na id ulice koji imamo u DGU bazi dodajemo njene ispravke.
