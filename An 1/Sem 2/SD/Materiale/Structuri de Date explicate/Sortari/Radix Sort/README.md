# Radix Sort

Tags: Sorts
Observații: Aproape suficient pt examen (lipsesc Avantaje/Dezavantaje) + alte explicații de detaliu
Scris?: Yes

## Ce este Radix Sort? 🧐

- Este un algoritm de sortare linear care sortează elementele procesându-le cifră cu cifră / caracter cu caracter.
- Este un algoritm folosit în special pentru ordonarea șirurilor de caractere.
- Asemănător cu bucket sort - este o generalizare pentru numere mari.

---

## Ideea de bază? 🫎

Radix Sort distribuie elemetele în bucket-uri după fiecare cifră a acestora.

Sortând elementele după fiecare cifră, de la coadă la cap (cifra unităților → …), Radix Sort ajunge la forma finală - sortată.

---

## Algoritm 🐴

### *Pasul 1:*

- Găsim cel mai mare număr din vectorul de input și aflăm câte cifre are.

De exemplu, dacă cel mai mare număr are 3 cifre, atunci vom parcurge vectorul de 3 ori, pentru a procesa numerele pentru fiecare cifră.

### *Pasul 2:*

- Parcurgem vectorul și sortăm numerele începând cu cifra unităților și terminând cu prima cifră *(de la stânga la dreapta. De exemplu, pentru 802, prma cifră ar fi 8).*

Pentru a sorta numerele folosim un algoritm de sortare **stabil**, de exemplu **Counting Sort**.

---

## Complexități ⏱️

Complexitatea algoritmului este **O(N log max)**. *(„discuție mai lungă” - Dumitran în curs 🤷‍♂️)*

**Spațiu: O(N + Baza).**

---

## Avantaje ✅

---

## Dezavantaje ❌

---

## Bibliografie

- https://www.geeksforgeeks.org/radix-sort/
- Structuri de Date - Curs 2 *(Prof. Marius Dumitran)*
