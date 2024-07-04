# Count Sort

Tags: Sorts
Scris?: Yes

## Ce este Counting Sort? 🧐

**Counting Sort** este un algoritm de sortare **prin numărare** care funcționează foarte bine când intervalul de valori din input este limitat. Este un algoritm de sortare pentru **numere întregi mici**

---

## Ideea de bază? 🫎

**Input: Vector de lungime *N* cu valori ≤ *max***

**Output: Un alt vector de lungime *N* cu valori ≤ *max***

```cpp
std::vector<int> countSort(const std::vector<int>& vector){
	std::vector<int> output(vector.size());
	
	//
	// Algoritm...
	//
	
	return output;
}
```

Numărăm aparițiile fiecărei valori și folosim informația asta pentru a așeza valorile într-un nou vector sortat.

---

## Algoritm 🐴

### *Pasul 1:*

- Găsim valoarea maximă din vectorul de input

```cpp
 int M = 0;
 
 for (const auto& number : vector)
	 M = max(M, number);
```

### *Pasul 2:*

- Facem un vector de frecvență de lungime ***max + 1***  cu toate elementele ***0***.

```cpp
vector<int> countArray(M + 1, 0);
```

### *Pasul 3:*

- Parcurgem vectorul de input și actualizăm corespunzător vectorul de frecvență: Pentru fiecare apariție `i` ******actualizăm `countArray[i]++` .
- Pe scurt, numărăm de câte ori apare fiecare valoare și stocăm informația în vectorul de frecvență

```cpp
for (const auto& number : vector)
	countArray[number]++;
```

### *Pasul 4:*

- Facem ***suma acumulată / prefix sum***  în vectorul de frecvență.
    
    ***Ce înseamnă asta?***
    

Parcurgem vectorul de frecvență de la al doilea element și îl actualizăm cu **suma** dintre **elementul curent** și **elementul de pe poziția anterioară.**

```cpp
for (int i = 1; i <= M; i++)
	countArray[i] += countArray[i - 1];
```

### *Pasul 5:*

- Așezăm valorile în ordine într-un nou vector `std::vector<int> output(vector.size());`
    
    ***Cum facem asta?  Păstrăm ordinea pentru valorile egale? (i.e. este algoritmul stabil?)***
    

Pentru a păstra ordinea elementelor vom începe prin a parcurge vectorul de input ***de la coadă spre cap.***

***Ok îl parcurgem și ce facem?***

Să notăm valoarea curentă din vectorul de input cu `X` Atunci `X` ******se va afla în vectorul de output pe poziția `countArray[X] - 1`. De fiecare dată când plasăm un element în vectorul de output vom scădea cu valoarea corelată în vectorul de frecvență, adică `countArray[X]--` .

Facem asta pentru fiecare element din vectorul de input si e **GATA!**

```cpp
for (int i = vector.size() - 1; i >= 0; i--){
	outputArray[countArray[inputArray[i]] - 1] = inputArray[i];
 
	countArray[inputArray[i]]--;
}
```

---

## Complexități ⏱️

Complexitatea algoritmului este **O(N + M)** unde 

- **N - Lungimea vectorului;**
- **M - Lungimea vectorului de frecvență / Valoarea maximă din vector.**

**Worst-case: O(N+M).**

**Average-case: O(N+M).**

**Best-case: O(N+M).**

**Spațiu: O(M).**

---

## Avantaje ✅

- Algoritmul e mai rapid decât toți algoritmii prin comparație dacă numerele sunt la fel de mari ca lungimea vectorului de input - în principiu pentru numere mici.
- Este ușor de implementat.
- Este un algoritm stabil *(dacă e implementat cum trebuie).*

---

## Dezavantaje ❌

- Algoritmul nu funcționeză pentru numere zecimale.
- Nu este eficient dacă intervalul de valori e foarte mare
- Nu este In-place, adică folosește spațiu auxiliar pentru a sorta elementele.

---

## Bibliografie

- [Counting Sort - Data Structures and Algorithms Tutorials - GeeksforGeeks](https://www.geeksforgeeks.org/counting-sort/)
- Structuri de Date - Curs 1 *(Prof. Marius Dumitran)*
