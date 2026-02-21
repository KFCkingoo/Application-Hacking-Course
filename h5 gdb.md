## h5 It's Alive!
Harjoitukset on tehty keväällä Teron ja Larin 2026 Sovellusten hakkerointi ja haavoittuvuudet - ICI012AS3A-3003 kurssia varten.

### Ympäristö
VirtualBox - Debian 13 Trixie VM

AMD Ryzen 7

---

### main.cpp)
Käännettiin ohjelma ajettavaan muotoon `g++ main.cpp -g -Wall -Werror -o main`.

Ajettiin ohjelma GNU debuggerilla `gdp ./main`.

Laitettiin komento `lay next`, painamalla Enteriä tuo esille main.cpp lähdekoodin ja assembly koodin. Lisättiin breakpoint `break 11`:

<img width="600" height="400" alt="kuva" src="https://github.com/user-attachments/assets/06f4aace-7f4c-4da9-a906-0013a5d21991" />

Ajettiin ohjelma niin voitiin debuggaa se `run`.
`next` menee lähdekoodissa seuraavaan riviin suorittamatta aliohjelmia.
`step` menee seuraavaan riviin ja aliohjelmiin.


