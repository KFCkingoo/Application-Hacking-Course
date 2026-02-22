## h5 It's Alive!
Harjoitukset on tehty keväällä Teron ja Larin 2026 Sovellusten hakkerointi ja haavoittuvuudet - ICI012AS3A-3003 kurssia varten.

### Ympäristö
VirtualBox - Debian 13 Trixie VM

AMD Ryzen 7

---
### main.cpp
Käännettiin ohjelma ajettavaan muotoon `g++ main.cpp -g -Wall -Werror -o main`.

Ohjelma tulosti aina 0. Kun syötti kirjaimen niin tulostu 1.

Ajettiin ohjelma GNU debuggerilla `gdp ./main`.

Laitettiin komento `lay next`, painamalla Enteriä tuo esille main.cpp lähdekoodin ja assembly koodin. Lisättiin breakpoint `break 11`:

<img width="600" height="400" alt="kuva" src="https://github.com/user-attachments/assets/06f4aace-7f4c-4da9-a906-0013a5d21991" />

Ajettiin ohjelma niin voitiin debuggaa se `r`.
Katsottiin muuttujia `watch n` ja `watch result`. Ajettiin jatkuvasti `s` ja tarkistettiin muutokset.

Syötetty arvo vähennettiin ennen kertolaskua, lopuksi ohjelma myös kertoi itsensä arvolla 0 ja -1. Lopputuloksena saatiin aina 0.

Tunnilla että myös Larin moodle materiaalissa on kerrottu, että virhe on `while(n--)` silmukassa.

Ratkaisuna olisi ohjelman laskea heti annetulla arvolla ja varmistaen, että ohjelma ei tee laskua arvolla 0.

<img width="200" height="200" alt="kuva" src="https://github.com/user-attachments/assets/9e9a287d-bfed-4a1c-b6c0-b16eccc1013a" />

>_Muutettiin `n--` silmukka `n > 1` ja lisättiin laskun jälkeen `n--`. Koodissa hyödynnetty tekoälyä._

---
### Lab0
Ohjelma tulosti
```
Element 0: 1
Element 1: 2
Element 2: 3
Element 3: 4
Element 4: 5
Element 5: 0
```

<img width="666" height="247" alt="kuva" src="https://github.com/user-attachments/assets/a41a625f-af7a-4b8b-a93e-8cae8b648ad1" />

>_Lähdekoodin kommentissa luki `<=` puskuriylivuodon ja väärän kokon._

Kun i = 5, se totesi olevan yhtä suuri kuin size joten se teki yhden rivilistauksen lisää. Numerolistalla ei ollut numero 5 jälkeen mitään ja tulostui 0.

Kokeiltiin muuttaa `i < size`, tulostui:
```
Element 0: 1
Element 1: 2
Element 2: 3
Element 3: 4
Element 4: 5
```

Lisättiin printf riville `i + 1` niin Elementin arvo ja listan arvo olisivat samat:
```
Element 1: 1
Element 2: 2
Element 3: 3
Element 4: 4
Element 5: 5
```



