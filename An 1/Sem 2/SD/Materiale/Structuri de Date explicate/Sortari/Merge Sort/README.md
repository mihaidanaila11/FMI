# Merge Sort

Tags: Sorts
Observații: Bun pt examen, merită imbunatatit
Scris?: Yes

## Ce este Merge Sort? 🧐

Este un algoritm de sortare bazat pe algoritmul ***Divide et Impera***. Acesta împarte vectorul in sub-vectori, îi sortează, apoi îi unește, astfel obținându-se vectorul sortat.

Este un algoritm cunoscut pentru eficiență și stabilitate

---

## Ideea de bază? 🫎

- **Divide:** se împarte vectorul în jumătate și se sortează independent fiecare parte
- **Impera:** se sortează recursiv cei doi subvectori
- **Merge:** Se unesc toate partițiile în ordinea sortată.

---

## Algoritm 🐴

- La fiecare pas împărțim vectorul  în două jumătăți. Facem același lucru pentru partițiile obținute până când nu mai poate fi divizat *(i.e. partiția are un singur element).*
- Interclasăm pe rând partițiile *(„de la stânga la dreapta”)* până când ajungem la vectorul sortat

---

## Complexități ⏱️

**Worst-case: $O(N logN)$** *(Când vectorul este sortat descrescător).*

**Average-case: $O(N logN)$** *(Când vectorul e neordonat).*

**Best-case: $O(N logN)$** *(Când vectorul e deja sortat / aproape sortat).*

**Spațiu: $O(N)$** folosit pentru merging**.**

---

## Avantaje ✅

- Este un algoritm de sortare stabil
- Are o complexitate în cel mai rău caz de $O(N logN)$ ceea ce înseamnă că e eficient chiar și pentru seturi mari de date
- Ușor de implementat - pașii sunt clari.
- Poate fi folosit pentru a număra inversiunile
- Poate fi folosit pentru a găsi mediana unui vector

---

## Dezavantaje ❌

- Are nevoie de memorie adițională pentru a stoca vectorii merge-uiți
- Nu e in-place - are nevoie de memorie adițională pentru a stoca datele sortate *(Poate fi o problemă acolo unde avem memorie limitată)*.

---

## Bibliografie

- https://www.geeksforgeeks.org/merge-sort/
- Structuri de Date - Curs 2 *(Prof. Marius Dumitran)*
