## h7 Uhagre2 !
Harjoitukset on tehty keväällä Teron ja Larin 2026 Sovellusten hakkerointi ja haavoittuvuudet - ICI012AS3A-3003 kurssia varten.

### Ympäristö
VirtualBox - Debian 13 Trixie VM

AMD Ryzen 7

---

### x) Lue ja tiivistä

#### € Schneier 2015: Applied Cryptography, 20ed: Chapter 1: Foundations:
##### 1.1 Terminology ("Historical Terms" to the end)
- Termistöä ja yleistä tietoa salauksesta, algoritmeistä ja avaimista.
- Cryptanalyysissä eri hyökkäyksiä.

##### 1.4 Simple XOR
- Käytetty salaus, heikko
- Vertailee bitit toisiinsa, kun ovat samoja niin tulostaa 0, muuten 1.

##### 1.7 Large Numbers
- Taulukko suuresta määristä, voidaan verrata esimerkkeinä kirjassa käytettyihin kryptografiaan.

#### Karvinen 2024: Python Basics for Hackers
- Python perusteet

---
### Solve CryptoPals Set 1 challenges.
### a) 1. Convert hex to base64.
String `49276d206b696c6c696e6720796f757220627261696e206c696b65206120706f69736f6e6f7573206d757368726f6f6d`.

Haluttu tulos `SSdtIGtpbGxpbmcgeW91ciBicmFpbiBsaWtlIGEgcG9pc29ub3VzIG11c2hyb29t`.

```
from base64 import b64encode, b64decode

hex = " 49276d206b696c6c696e6720796f757220627261696e206c696b65206120706f69736f6e6f7573206d757368726f6f6d"
b64 = b64encode(bytes.fromhex(hex)).decode()
print(b64)
```

`bytes.fromhex()` kääntää hex-stringin tavuiksi.

Sitten `b64encode` kääntää tavut base64 muotoon.

`decode()` kääntää base64 muodon stringiksi. 




---
### b) 2. Fixed XOR.
Tehtävässä pitää hex dekoodata stringit ja verrata toisiinsa käyttämällä XOR.

Yritettiin aluksi käyttäen edellisen tehtävän mallia, mutta aina päädyttiin virheisiin liittyen str tai tavu tyyppiseen muotoihin mitä ei kyetty verrata käyttäen XOR-vertailua.
Pyydettiin Copilotilta neuvoa.

```
hex_a = "1c0111001f010100061a024b53535009181c"
hex_b = "686974207468652062756c6c277320657965"

a = bytes.fromhex(hex_a)
b = bytes.fromhex(hex_b)

xor = bytes(x ^ y for x, y in zip (a, b))
print(xor)
```
XOR tulosti väärän muodon.
```
b"the kid don't play"
```
Tulostus korjattiin viimeisellä print-komennossa `print(xor.hex())`.


### c) 3. Single-byte XOR cipher.
### d) 4. Detect single-character XOR.




---
### Lähteet
Karvinen 2024: Python Basics for Hackers

Schneier 2015: Applied Cryptography, 20ed: Chapter 1: Foundations

Abbas 2022. How to Convert Hex to Base64 in Python. https://www.delftstack.com/howto/python/convert-hex-to-base64-python/

Tehtävässä hyödynnetty Copilot ChatGPT5.1 https://copilot.microsoft.com/.
