# Portofoliu PCLP

## Pagina de Titlu

**Titlu:** Portofoliu PCLP  
**Nume:** Rechimciuc Dionisie  
**Facultate, grupă:** IESC, 4LF842  
**Data predării:** *13.01.25*

---

## Cuprins

1. Problema 1 - *sum00*  
2. Problema 2 - *minim3*  
3. Problema 3 - *Suma Cifrelor*  
4. Problema 4 - *Divizorii Oglinditului*
5. Problema 5 - *Fibonacci*
6. Problema 6 - *Ordonare*
7. Problema 7 - *inserare*
8. Problema 8 - *Diagonale1*
9. Problema 9 - *NrMaxim*
10. Problema 10 - *Cautare Binara*
11. Problema 11 - *DublareVocale*
12. Problema 12 - *Poza*
13. Problema 13 - *CifMinParRec*
14. Problema 14 - *Permutari*
15. Problema 15 - *QuickSort*
16. Problema 16 - *Lee2*
17. Problema 17 - *Dijkstra*
18. Problema 18 - *BiFrunze*
19. Problema 19 - *AfisCircuite*
20. Problema 20 - *Catalog_ChatGPT*

---

## Introducere

Scopul acestui portofoliu este de a demonstra competențele dobândite în cadrul disciplinei Programarea Calculatoarelor și Limbaje de Programare (PCLP). Acesta conține 20 de probleme rezolvate în limbajul C++, organizate în funcție de dificultate și complexitate.

---

## Probleme Rezolvate

### Problema 1 - *sum00*

#### Enunț
Se dau `2` numere naturale. Calculaţi suma celor `2` numere date.

#### Date de intrare și ieșire
- **Intrare:** *Programul citește de la tastatură `2` numere naturale.*
- **Ieșire:** *Programul va afișa pe ecran suma celor două numere.*

#### Restricţii şi precizări
 - cele două numere vor fi mai mici decât `1.000.000.000`

#### Rezolvare și explicații

Această problemă este foarte simplă și are ca scop familiarizarea cu citirea și afișarea datelor în C++. Programul citește două numere de la tastatură, calculează suma lor și o afișează. Deoarece datele de intrare sunt într-un interval mare (până la un miliard), variabilele utilizate sunt de tipul `int`, care poate stoca valori până la aproximativ `2.1 miliarde`, suficient pentru această problemă.

#### Codul sursă
```cpp
#include <iostream>
using namespace std;
int main()
{
    int a, b;
    cin >> a >> b;
    cout << a + b;
}
```

#### Exemple de rulare
| Intrare | Ieșire |
| ------- | ------ |
| 3 7     | 10     |
| 100 200 | 300    |

#### Complexitate
- **Timp:** O(1) deoarece operația de adunare și afișarea au un timp constant, independent de valoarea numerelor.

![image-20250112222928463](C:\Users\rekim\AppData\Roaming\Typora\typora-user-images\image-20250112222928463.png)

---

### Problema 2 - *minim3*

#### Enunț

Se dau `3` numere întregi. Calculaţi minimul celor `3` numere date.

#### Date de intrare și ieșire

- **Intrare:** *Programul citeşte de la tastatură `3` numere întregi separate prin spaţii.*
- **Ieșire:** *Programul va afişa pe ecran cel mai mic dintre numerele citite.*

#### Restricţii şi precizări

 - valoare absolută a numerelor citite va fi mai mică decât `1.000.000.000`

#### Rezolvare și explicații

Această problemă se concentrează pe utilizarea structurilor de control pentru a determina minimul a trei numere întregi. Citim trei numere de la tastatură și comparăm valorile folosind operatori condiționali. Deși metoda poate fi extinsă și la mai multe numere, aici soluția este adaptată pentru exact trei valori. Variabilele de tip `int` sunt suficiente pentru a stoca valorile, deoarece sunt în limitele precizate.

#### Codul sursă
```cpp
#include <iostream>
using namespace std;
int main()
{
    int a, b, c;
    cin >> a >> b >> c;
    int minim = a;
    if (b < minim) minim = b;
    if (c < minim) minim = c;
    cout << minim;
}
```

#### Exemple de rulare
| Intrare    | Ieșire |
| ---------- | ------ |
| 3 7 2      | 2      |
| -5 0 -10   | -10    |
| 100 200 50 | 50     |

#### Complexitate
- **Timp:** O(1) deoarece numărul de comparații este constant (2 comparații).

![image-20250112223033695](C:\Users\rekim\AppData\Roaming\Typora\typora-user-images\image-20250112223033695.png)

---

### Problema 3 - *Suma Cifrelor*

#### Enunț

Se da un numar natural. Calculaţi suma cifrelor numărului dat.

#### Date de intrare și ieșire
- **Intrare:** *Programul va citi de la tastatură un număr natural.*
- **Ieșire:** *Programul va afişa pe ecran suma cifrelor numărului citit.*

#### Restricții și precizări
- numărul citit va fi mai mic decât `2.000.000.000`

#### Rezolvare și explicații

Problema necesită calcularea sumei cifrelor unui număr natural. Se poate rezolva prin extragerea fiecărei cifre utilizând operația de împărțire la 10 și calcularea restului. Procedura este repetată până când numărul devine zero. Această abordare este eficientă datorită numărului limitat de cifre (maxim 10 pentru un număr de 2 miliarde).

#### Codul sursă
```cpp
#include <iostream>
using namespace std;
int main()
{
    int n, suma = 0;
    cin >> n;
    while (n > 0) {
        suma += n % 10; // Adăugăm ultima cifră la sumă
        n /= 10;        // Eliminăm ultima cifră
    }
    cout << suma;
}
```

#### Exemple de rulare
| Intrare   | Ieșire |
| --------- | ------ |
| 123       | 6      |
| 1001      | 2      |
| 987654321 | 45     |

#### Complexitate
- **Timp:** O(log₁₀(n)) deoarece numărul de iterații depinde de numărul de cifre ale lui `n` (aproximativ logaritmic în bază 10).

![image-20250112223153186](C:\Users\rekim\AppData\Roaming\Typora\typora-user-images\image-20250112223153186.png)

---

### Problema 4 - *Divizorii Oglinditului*

#### Enunț

Se citește un număr natural `n`. Să se determine numărul de divizori ai oglinditului lui `n`.

#### Date de intrare și ieșire

- **Intrare:** *Programul citește de la tastatură numărul `n`.*
- **Ieșire:** *Programul afișează pe ecran numărul `D`, reprezentând rezultatul cerut.*

#### Restricții și precizări

- `1 ≤ n ≤ 1.000.000.000`

#### Rezolvare și explicații

Problema necesită calcularea numărului de divizori ai oglinditului unui număr natural. Se descompune în două părți: 
1. Calculul oglinditului unui număr prin inversarea cifrelor. Aceasta se face iterativ, folosind operația de modulo pentru a extrage ultima cifră și o adăugare progresivă pentru a construi noul număr.
2. Calculul numărului de divizori al unui număr dat. Divizorii sunt calculați iterând până la rădăcina pătrată a numărului, pentru a minimiza numărul de operații. Dacă un divizor este găsit, este adăugat împreună cu perechea sa (dacă nu sunt egale).

#### Codul sursă
```cpp
#include <iostream>
using namespace std;

// Funcție pentru a determina oglinditul unui număr
int oglindit(int n)
{
    int ogl = 0;
    while (n > 0) 
    {
        ogl = ogl * 10 + n % 10;
        n /= 10;
    }
    return ogl;
}

// Funcție pentru a calcula numărul de divizori al unui număr
int numar_divizori(int n)
{
    int count = 0;
    for (int i = 1; i * i <= n; i++) 
    {
        if (n % i == 0)
        {
            count += (i * i == n) ? 1 : 2; // Adăugăm ambii divizori, dar evităm duplicatele pentru pătratul perfect
        }
    }
    return count;
}

int main()
{
    int n;
    cin >> n;

    int ogl = oglindit(n); // Calculăm oglinditul lui n
    int divizori = numar_divizori(ogl); // Calculăm numărul de divizori al oglinditului

    cout << divizori << endl;

    return 0;
}
```

#### Exemple de rulare
| Intrare | Ieșire |
| ------- | ------ |
| 12      | 4      |
| 21      | 4      |
| 100     | 1      |
| 101     | 2      |

#### Complexitate
- **Timp:** O(d + log₁₀(n)), unde `d` este numărul de divizori ai oglinditului și `log₁₀(n)` este timpul pentru calculul oglinditului.

![image-20250112223305281](C:\Users\rekim\AppData\Roaming\Typora\typora-user-images\image-20250112223305281.png)

---

### Problema 5 - *Fibonacci*

#### Enunț

Se consideră şirul Fibonacci, definit astfel:  $f_1=1$ ,  $f_2=1$ ,  $f_n=f_{n-1}+f_{n-2}$ , dacă `n>2`. Se dă un număr natural `n`. Să se afişeze în ordine crescătoare, primii `n` termeni ai şirului lui Fibonacci.

#### Date de intrare și ieșire

- **Intrare:** *Programul citește de la tastatură numărul `n`.*
- **Ieșire:** *Programul afișează pe ecran primii `n` termeni ai şirului lui Fibonacci, în ordine crescătoare, separați printr-un spaţiu.*

#### Restricții și precizări

- `1 ≤ n ≤ 40`

#### Rezolvare și explicații

Problema necesită generarea primilor `n` termeni ai șirului Fibonacci. Deoarece valoarea lui `n` este limitată la 40, metoda iterativă este eficientă și permite calculul rapid al termenilor fără a consuma resurse suplimentare. 

Șirul este generat pornind de la primii doi termeni, 1 și 1, iar fiecare termen următor este suma celor două anterioare. Folosim variabile de tip `long long` pentru a preveni depășirea limitei de stocare a valorilor numerice, deoarece termenii Fibonacci cresc exponențial.

#### Codul sursă
```cpp
#include <iostream>
using namespace std;

// Funcție pentru a genera șirul Fibonacci
void fibonacci(int n)
{
    long long f1 = 1, f2 = 1;

    if (n >= 1) cout << f1;
    if (n >= 2) cout << " " << f2;

    for (int i = 3; i <= n; ++i)
    {
        long long f_next = f1 + f2;
        cout << " " << f_next;
        f1 = f2;
        f2 = f_next;
    }
    cout << endl;
}

int main()
{
    int n;
    cin >> n;

    fibonacci(n);

    return 0;
}
```

#### Exemple de rulare
| Intrare | Ieșire                  |
| ------- | ----------------------- |
| 5       | 1 1 2 3 5               |
| 10      | 1 1 2 3 5 8 13 21 34 55 |
| 1       | 1                       |

#### Complexitate
- **Timp:** O(n), deoarece se generează termenii în mod iterativ, fiecare termen fiind calculat o singură dată.

![image-20250112223502183](C:\Users\rekim\AppData\Roaming\Typora\typora-user-images\image-20250112223502183.png)

---

### Problema 6 - *Ordonare*

#### Enunț

Se dă un vector cu `n` elemente numere naturale. Să se ordoneze crescător elementele vectorului.

#### Date de intrare și ieșire

- **Intrare:** *Programul citește de la tastatură numărul `n`, apoi `n` numere întregi, reprezentând elementele vectorului.*
- **Ieșire:** *Programul va afișa pe ecran cele `n` elemente ale vectorului, ordonate conform cerinței, separate printr-un spațiu.*

#### Restricții și precizări

- `1 ≤ n ≤ 1000`
- elementele vectorului vor fi mai mici decât `1.000.000.000`

#### Rezolvare și explicații

Bubble Sort este un algoritm simplu de sortare care compară perechi adiacente de elemente dintr-un vector și le interschimbă dacă sunt în ordine greșită. Acest proces se repetă până când vectorul este complet ordonat.

Deși algoritmul are o complexitate de timp mai mare decât alte metode (O(n^2)), este ușor de implementat și potrivit pentru seturi de date mici. În această implementare, vectorul este procesat iterativ, iar după fiecare pas, cel mai mare element "se ridică" la poziția finală.

#### Codul sursă

```cpp
#include <iostream>
using namespace std;

// Funcție pentru a ordona un vector folosind Bubble Sort
void bubbleSort(int arr[], int n) 
{
    for (int i = 0; i < n - 1; i++) 
    {
        for (int j = 0; j < n - i - 1; j++) 
        {
            if (arr[j] > arr[j + 1]) 
            {
                // Schimbăm valorile
                int temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
            }
        }
    }
}

int main() 
{
    int n;
    cin >> n;

    int arr[n];
    for (int i = 0; i < n; i++) 
    {
        cin >> arr[i];
    }

    bubbleSort(arr, n);

    for (int i = 0; i < n; i++) 
    {
        cout << arr[i] << " ";
    }
    cout << endl;

    return 0;
}
```

#### Exemple de rulare
| Intrare     | Ieșire    |
| ----------- | --------- |
| 5 5 3 1 2 4 | 1 2 3 4 5 |
| 4 10 5 3 0  | 0 3 5 10  |
| 5 9 8 7 6 5 | 5 6 7 8 9 |

#### Complexitate
- **Timp:** O(n^2), deoarece fiecare pereche de elemente este comparată în iterații succesive.

![image-20250112223601085](C:\Users\rekim\AppData\Roaming\Typora\typora-user-images\image-20250112223601085.png)

---

### Problema 7 - *inserare*

#### Enunț

Se dă un șir cu `n` elemente întregi,  valoare întreagă `X` și un număr `p`. Să se insereze pe poziția `p` în șir valoarea `X`.

#### Date de intrare și ieșire

- **Intrare:** *Programul va citi de la tastatură trei valori `n`, `X`, `p`, cu semnificația precizată, apoi `n` numere întregi reprezentând elementele șirului.*
- **Ieșire:** *Programul va afișa pe ecran `n+1` valori întregi, separate printr-un spațiu, reprezentând elementele șirului după inserare.*

#### Restricții și precizări

- `1 ≤ p ≤ n ≤ 25`
- valoarea `X` și elementele șirului vor fi cuprinse între `-1.000.000` și `1.000.000`
- elementele șirului vor avea indici între `1` și `n`.

#### Rezolvare și explicații

Pentru a insera un element în șir pe o poziție dată `p`, este necesar să deplasăm toate elementele de la poziția `p` inclusiv, cu o poziție spre dreapta. După crearea spațiului liber, valoarea `X` este introdusă pe poziția `p`. Această metodă utilizează un algoritm simplu și funcționează eficient pentru dimensiuni mici ale șirului, conform restricțiilor date.

#### Codul sursă

```cpp
#include <iostream>
using namespace std;

int main() 
{
    int n, X, p;
    cin >> n >> X >> p;

    int arr[27]; // Avem nevoie de un spațiu suplimentar pentru noul element și încă unul pentru că începem de la i = 1

    for (int i = 1; i <= n; i++) 
    {
        cin >> arr[i];
    }

    // Deplasăm elementele pentru a face loc lui X
    for (int i = n; i >= p; i--) 
    {
        arr[i + 1] = arr[i];
    }

    // Inserăm valoarea X pe poziția p
    arr[p] = X;
    
    // Incrementăm dimensiunea șirului
    ++n;

    // Afișăm șirul modificat
    for (int i = 1; i <= n; i++) 
    {
        cout << arr[i] << " ";
    }
    cout << endl;

    return 0;
}
```

#### Exemple de rulare
| Intrare            | Ieșire         |
| ------------------ | -------------- |
| 5 10 3 1 2 3 4 5   | 1 2 10 3 4 5   |
| 3 -5 2 100 200 300 | 100 -5 200 300 |
| 3 7 1 -1 -2 -3     | 7 -1 -2 -3     |

#### Complexitate
- **Timp:** O(n), deoarece toate elementele de la poziția `p` încolo trebuie mutate o poziție spre dreapta.

![image-20250112223654055](C:\Users\rekim\AppData\Roaming\Typora\typora-user-images\image-20250112223654055.png)

---

### Problema 8 - *Diagonale1*

#### Enunț

Se dă o matrice cu `n` linii şi `n` coloane şi elemente numere naturale. Să se determine suma elementelor de pe cele două diagonale vecine cu diagonala principală.

#### Date de intrare și ieșire

- **Intrare:** *Programul citește de la tastatură numărul `n`, iar apoi `n*n` numere naturale, separate prin spaţii, reprezentând elementele matricei, linie cu linie.*
- **Ieșire:** *Programul afișează pe ecran numărul `S`, cu semnificaţia precizată.*

#### Restricții și precizări

- `1 ≤ n ≤ 100`
- elementele matricei vor fi mai mici decât `1.000.000`

#### Rezolvare și explicații

Problema presupune calcularea sumei elementelor de pe diagonalele imediat vecine cu diagonala principală. Pentru aceasta, parcurgem matricea și:
- Adăugăm elementele de pe diagonala de deasupra diagonalei principale (elementele `matrix[i-1][i]` pentru fiecare `i` valid).
- Adăugăm elementele de pe diagonala de sub diagonala principală (elementele `matrix[i+1][i]` pentru fiecare `i` valid).

Acest algoritm are o complexitate liniară față de dimensiunea matricei, ceea ce îl face eficient pentru intervalul dat.

#### Codul sursă

```cpp
#include <iostream>
using namespace std;

int main() 
{
    int n;
    cin >> n;

    int matrix[100][100];

    // Citirea matricei
    for (int i = 0; i < n; i++) 
    {
        for (int j = 0; j < n; j++) 
        {
            cin >> matrix[i][j];
        }
    }

    int suma = 0;

    // Calculăm suma elementelor de pe diagonalele vecine cu diagonala principală
    for (int i = 0; i < n; i++) 
    {
        if (i > 0) 
        { // Diagonala de deasupra diagonalei principale
            suma += matrix[i - 1][i];
        }
        if (i < n - 1) 
        { // Diagonala de sub diagonala principală
            suma += matrix[i + 1][i];
        }
    }

    cout << suma << endl;

    return 0;
}
```

#### Exemple de rulare
| Intrare                                  | Ieșire |
| ---------------------------------------- | ------ |
| 3 1 2 3 4 5 6 7 8 9                      | 20     |
| 4 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 | 51     |

#### Complexitate
- **Timp:** O(n), deoarece fiecare element relevant al matricei este procesat o singură dată.

![image-20250112223748932](C:\Users\rekim\AppData\Roaming\Typora\typora-user-images\image-20250112223748932.png)

---

### Problema 9 - *NrMaxim*

#### Enunț

Să se scrie o funcție care are ca parametru un număr natural `n` și returnează cel mai mare număr care poate fi obținut mutând, pe rând, prima cifră a numărului `n` și a celor obținute pe parcurs, pe ultima poziție. Nu se vor folosi șiruri de caractere și tablouri auxiliare.

#### Restricții și precizări

- numele funcției va fi `nrmaxim`
- funcția va avea un parametru reprezentând numărul dat, care va fi mai mic decât `1.000.000.000`

#### Rezolvare și explicații

Pentru a rezolva problema, vom genera toate permutările numărului `n` prin mutarea primei cifre la final, una câte una. În fiecare pas, verificăm dacă numărul obținut este mai mare decât valoarea maximă stocată până atunci.

Pașii algoritmului:
1. Calculăm numărul de cifre ale numărului `n` și puterea corespunzătoare a lui 10.
2. Generăm fiecare permutare prin mutarea primei cifre la final și actualizăm maximul găsit.
3. Returnăm valoarea maximă obținută.

Această soluție este eficientă deoarece utilizează doar aritmetică numerică și un număr fix de operații pentru fiecare cifră a numărului.

#### Codul sursă

```cpp
int nrmaxim(int n) 
{
    int maxVal = n;
    int numDigits = 0, powerOfTen = 1, temp = n;

    // Calculăm numărul de cifre și puterea lui 10 corespunzătoare
    while (temp > 0) 
    {
        numDigits++;
        powerOfTen *= 10;
        temp /= 10;
    }
    powerOfTen /= 10; // Ajustăm pentru ultima putere validă

    // Generăm toate permutările prin mutarea primei cifre la final
    for (int i = 0; i < numDigits - 1; ++i) 
    {
        int firstDigit = n / powerOfTen; // Extragem prima cifră
        n = (n % powerOfTen) * 10 + firstDigit; // Mutăm prima cifră la final
        if (n > maxVal) 
        {
            maxVal = n; // Actualizăm valoarea maximă
        }
    }

    return maxVal;
}
```

- #### Exemple de rulare
  | Intrare | Ieșire |
  | ------- | ------ |
  | 197     | 971    |
  | 1234    | 4123   |
  | 120     | 201    |

  #### Complexitate
  - **Timp:** O(d), unde `d` este numărul de cifre ale numărului `n`, deoarece efectuăm `d-1` permutări și verificări.

  ![image-20250112223925135](C:\Users\rekim\AppData\Roaming\Typora\typora-user-images\image-20250112223925135.png)

---

### Problema 10 - *Cautare Binara*

#### Enunț

Se dă un vector `x` cu `n` elemente numere naturale, ordonate crescător, și un vector `y` cu `m` elemente, de asemenea numere naturale. Verificați pentru fiecare element al vectorului `y` dacă apare în `x`.

#### Date de intrare și ieșire

- **Intrare:** *Programul citește de la tastatură numărul `n`, iar apoi cele `n` elemente ale vectorului `x`. Apoi și citește `m` și cele `m` elemente ale lui `y`.*
- **Ieșire:** *Programul va afișa pe ecran `m` valori `0` sau `1`, separate prin exact un spațiu. A `j`-a valoare afișată este `1`, dacă al `j`-lea element al șirului `y` apare în `x`, respectiv  `0` în caz contrar. *

#### Restricții și precizări

- `1 ≤ n ≤ 25.000`
- `1 ≤ m ≤ 200.000`
- elementele celor `2` vectori vor fi mai mici decât `1.000.000.000`

#### Rezolvare și explicații

Căutarea binară este o tehnică eficientă pentru a verifica existența unui element într-un vector sortat. Algoritmul împarte vectorul în jumătate la fiecare pas și decide dacă să continue căutarea în jumătatea inferioară sau superioară, bazându-se pe comparații directe.

Pentru fiecare element din vectorul `y`, utilizăm căutarea binară pentru a verifica prezența sa în vectorul `x`. Deoarece vectorul `x` este sortat, căutarea binară este ideală pentru a rezolva problema în mod eficient.

#### Codul sursă

```cpp
#include <iostream>
using namespace std;

// Funcție pentru a verifica dacă un element este prezent folosind căutarea binară
bool binarySearch(int x[], int n, int target) 
{
    int left = 0, right = n - 1;
    while (left <= right) 
    {
        int mid = left + (right - left) / 2;
        if (x[mid] == target) 
        {
            return true;
        } else if (x[mid] < target) 
        {
            left = mid + 1;
        } else {
            right = mid - 1;
        }
    }
    return false;
}

int main() {
    int n, m;
    cin >> n;
    int x[25000];
    for (int i = 0; i < n; i++) 
    {
        cin >> x[i];
    }

    cin >> m;
    int y[200000];
    for (int i = 0; i < m; i++) 
    {
        cin >> y[i];
    }

    // Verificăm pentru fiecare element din y dacă apare în x
    for (int i = 0; i < m; i++) 
    {
        cout << (binarySearch(x, n, y[i]) ? 1 : 0) << " ";
    }
    cout << endl;

    return 0;
}
```

- #### Exemple de rulare
  | Intrare               | Ieșire  |
  | --------------------- | ------- |
  | 5 1 3 5 7 9 4 2 5 8 9 | 0 1 0 1 |
  | 3 10 20 30 2 15 25    | 0 0     |
  | 6 1 2 3 4 5 6 3 1 4 7 | 1 1 0   |

  #### Complexitate
  - **Timp:** O(m * log(n)), deoarece pentru fiecare element al vectorului `y`, executăm o căutare binară în vectorul `x`.

  ![image-20250112224039415](C:\Users\rekim\AppData\Roaming\Typora\typora-user-images\image-20250112224039415.png)

---

### Problema 11 - *DublareVocale*

#### Enunț

Se dă un şir format din cel mult `100` de caractere – litere mici ale alfabetului englez şi spaţii. Să se modifice acest şir prin dublarea fiecărei vocale.

#### Date de intrare și ieșire

- **Intrare:** *Programul citește de la tastatură șirul dat.*
- **Ieșire:** *Programul va afișa pe ecran şirul obţinut în urma efectuării operaţiilor cerute. *

#### Rezolvare și explicații

Pentru a rezolva problema, parcurgem șirul caracter cu caracter și verificăm dacă acesta este o vocală folosind o funcție dedicată. Dacă este o vocală, o adăugăm de două ori la șirul rezultat. Altfel, adăugăm caracterul o singură dată. Această metodă este eficientă deoarece lucrăm direct pe caractere, fără a utiliza structuri complexe.

#### Codul sursă

```cpp
#include <iostream>
using namespace std;

// Funcție pentru a verifica dacă un caracter este vocală
bool esteVocala(char c) 
{
    return c == 'a' || c == 'e' || c == 'i' || c == 'o' || c == 'u';
}

// Funcție pentru a dubla vocalele dintr-un șir
void dublareVocale(const char* sir, char* rezultat) 
{
    int j = 0;
    for (int i = 0; sir[i] != '\0'; i++) 
    {
        rezultat[j++] = sir[i];
        if (esteVocala(sir[i])) 
        {
            rezultat[j++] = sir[i]; // Dublăm vocala
        }
    }
    rezultat[j] = '\0'; // Adăugăm terminatorul de șir
}

int main() 
{
    char sir[101];
    char rezultat[201]; // Spațiu suficient pentru a dubla toate caracterele

    cin.getline(sir, 101);
    dublareVocale(sir, rezultat);

    cout << rezultat << endl;

    return 0;
}
```

- #### Exemple de rulare
  | Intrare      | Ieșire             |
  | ------------ | ------------------ |
  | ana are mere | aanaa aaree meeree |
  | umbrela      | uumbreelaa         |
  | hello world  | heelloo woorld     |

  #### Complexitate
  - **Timp:** O(n), unde `n` este lungimea șirului de intrare, deoarece fiecare caracter este procesat o singură dată.

  ![image-20250112224127750](C:\Users\rekim\AppData\Roaming\Typora\typora-user-images\image-20250112224127750.png)

---

### Problema 12 - *Poza*

#### Enunț

Fie o poză dată sub forma unei matrice cu `n` linii și `m` coloane, în care elementele sunt `0` sau `1`: un element `0` reprezintă fundalul imaginii, iar un element `1` reprezintă obiect din prim plan. Este necesară tăierea unei bucăți din imagine astfel încât:

- laturile bucății tăiate sunt paralele cu laturile pozei inițiale și cât mai mici;
- toate obiectele din prim-plan în poza inițială apar în poza tăiată;

Determinați dimensiunile pozei tăiate, precum și conținutul ei.

#### Date de intrare și ieșire

- **Intrare:** *Programul citește de la tastatură numerele `n m`, iar apoi `n` șiruri cu câte `m` valori `0` sau `1`, reprezentând poza inițială.*
- **Ieșire:** *Programul va afișa pe ecran numerele `p q`, separate printr-un spațiu, reprezentând dimensiunile pozei tăiate, apoi `p` linii cu câte `q` valori separate prin exact un spațiu, reprezentând poza tăiată.*

#### Restricții și precizări

- `1 ≤ n,m ≤ 100`
- în poză va exista cel puțin un element de prim-plan

#### Rezolvare și explicații

Pentru a rezolva problema, determinăm mai întâi limitele obiectului din prim-plan în matrice:
1. Găsim primul și ultimul rând care conține elemente `1` (limitele verticale: `top` și `bottom`).
2. Găsim prima și ultima coloană care conține elemente `1` (limitele orizontale: `left` și `right`).

Apoi, afișăm submatricea delimitată de aceste limite, calculând dimensiunile sale `p` (numărul de linii) și `q` (numărul de coloane). Acest algoritm parcurge întreaga matrice o singură dată pentru a identifica limitele.

#### Codul sursă

```cpp
#include <iostream>
using namespace std;

int main() 
{
    int n, m;
    cin >> n >> m;

    int matrice[100][100];

    // Citirea matricei
    for (int i = 0; i < n; i++) 
    {
        for (int j = 0; j < m; j++) 
        {
            cin >> matrice[i][j];
        }
    }

    // Găsirea limitelor obiectului din prim-plan
    int top = n, bottom = -1, left = m, right = -1;

    for (int i = 0; i < n; i++) 
    {
        for (int j = 0; j < m; j++) 
        {
            if (matrice[i][j] == 1) 
            {
                if (i < top) top = i;
                if (i > bottom) bottom = i;
                if (j < left) left = j;
                if (j > right) right = j;
            }
        }
    }

    // Dimensiunile pozei tăiate
    int p = bottom - top + 1;
    int q = right - left + 1;

    cout << p << " " << q << endl;

    // Afișarea pozei tăiate
    for (int i = top; i <= bottom; i++) 
    {
        for (int j = left; j <= right; j++) 
        {
            cout << matrice[i][j] << " ";
        }
        cout << endl;
    }

    return 0;
}
```

- #### Exemple de rulare
  | Intrare                                                      | Ieșire                               |
  | ------------------------------------------------------------ | ------------------------------------ |
  | 5 5  <br />0 0 0 0 0<br />0 1 1 1 0<br />0 1 1 1 0<br />0 1 1 1 0<br />0 0 0 0 0 | 3 3<br />1 1 1<br />1 1 1<br />1 1 1 |
  | 3 4<br />0 0 0 0<br />0 1 0 1<br />0 1 1 1                   | 2 3 <br />1 0 1<br />1 1 1           |

  #### Complexitate
  - **Timp:** O(n × m), deoarece parcurgem matricea o singură dată pentru a găsi limitele.

  ![image-20250112224226064](C:\Users\rekim\AppData\Roaming\Typora\typora-user-images\image-20250112224226064.png)

---

### Problema 13 - *CifMinParRec*

#### Enunț

Să se scrie o **funcție C++ recursivă** care să returneze cea mai mică cifră pară a unui număr natural transmis ca parametru. 

#### Restricții și precizări

- numele funcției va fi `cifminpar`
- funcția va avea un parametru reprezentând numărul dat
- numărul pentru care se calculează cifra minimă pară va fi mai mic decât `2.000.000.000`
- **dacă numărul nu conţine nici o cifră pară**, se va returna valoarea `-1`

#### Rezolvare și explicații

Pentru a rezolva problema recursiv:
1. Descompunem numărul în cifre folosind operația modulo 10 și verificăm dacă cifra curentă este pară și mai mică decât cifra minimă găsită până în acel moment.
2. Continuăm apelul recursiv pe numărul fără ultima cifră (folosind împărțirea la 10).
3. Dacă numărul ajunge la 0 și nu am găsit nicio cifră pară, returnăm `-1`.
4. Dacă există cel puțin o cifră pară, returnăm valoarea minimă găsită.

#### Codul sursă

```cpp
int cifminpar(int n, int minPar = 10) 
{
    if (n == 0) 
    {
        return (minPar == 10) ? -1 : minPar; // Dacă nu există cifră pară, returnăm -1
    }

    int cifra = n % 10;
    if (cifra % 2 == 0 && cifra < minPar) 
    {
        minPar = cifra; // Actualizăm cea mai mică cifră pară găsită
    }

    return cifminpar(n / 10, minPar); // Apel recursiv pe numărul fără ultima cifră
}
```

#### Exemple de rulare
| Intrare  | Ieșire |
| -------- | ------ |
| 73519    | -1     |
| 24681357 | 2      |
| 97020    | 0      |

#### Complexitate
- **Timp:** O(d), unde `d` este numărul de cifre ale numărului. Fiecare cifră este procesată o singură dată.
- **Spațiu:** O(d), datorită apelurilor recursive care sunt stocate pe stivă.

![image-20250112233415869](C:\Users\rekim\AppData\Roaming\Typora\typora-user-images\image-20250112233415869.png)

---

### Problema 14 - *Permutari*

#### Enunț

Se citeşte un număr natural nenul `n`. Să se afişeze, în ordine lexicografică, permutările mulţimii `{1,2,..,n}`.

#### Date de intrare și ieșire

- **Intrare:** *Fişierul de intrare `permutari.in` conţine pe prima linie numărul `n`.*
- **Ieșire:** *Fişierul de ieşire `permutari.out` va conţine pe fiecare linie elementele unei permutări, separate prin câte un spaţiu.*

#### Restricții și precizări

- `0 < n < 9`

#### Rezolvare și explicații

Pentru a genera toate permutările în ordine lexicografică folosim o metodă iterativă bazată pe funcția `nextPermutation`. Algoritmul urmărește următoarele etape:
1. Caută cel mai din dreapta element care este mai mic decât următorul (pivot).
2. Găsește cel mai mic element din dreapta pivotului care este mai mare decât acesta și le înlocuiește.
3. Inversează secvența de elemente de după pivot pentru a obține următoarea permutare lexicografică.
4. Procesul continuă până când nu mai există permutări.

#### Codul sursă

```cpp
#include <iostream>
#include <fstream>
using namespace std;

// Funcție pentru a genera următoarea permutare lexicografică
bool nextPermutation(int arr[], int n) 
{
    int i = n - 2;
    while (i >= 0 && arr[i] >= arr[i + 1]) 
    {
        i--;
    }

    if (i < 0) 
    {
        return false; // Nu mai există permutări
    }

    int j = n - 1;
    while (arr[j] <= arr[i]) 
    {
        j--;
    }

    swap(arr[i], arr[j]);

    // Inversăm partea de la i+1 până la sfârșit
    int left = i + 1, right = n - 1;
    while (left < right) 
    {
        swap(arr[left], arr[right]);
        left++;
        right--;
    }

    return true;
}

int main() 
{
    ifstream fin("permutari.in");
    ofstream fout("permutari.out");

    int n;
    fin >> n;

    int arr[8];
    for (int i = 0; i < n; ++i) 
    {
        arr[i] = i + 1;
    }

    do {
        for (int i = 0; i < n; ++i) 
        {
            fout << arr[i] << " ";
        }
        fout << endl;
    } while (nextPermutation(arr, n));

    fin.close();
    fout.close();

    return 0;
}
```

#### Exemple de rulare
| Intrare | Ieșire                                                       |
| ------- | ------------------------------------------------------------ |
| 3       | 1 2 3<br />1 3 2<br />2 1 3<br />2 3 1<br />3 1 2<br />3 2 1 |

#### Complexitate
- **Timp:** O(n! × n), unde `n!` reprezintă numărul total de permutări și fiecare permutare necesită O(n) pași pentru a fi generată sau afișată.
- **Spațiu:** O(n), utilizat pentru stocarea vectorului curent și a câtorva variabile auxiliare.

![image-20250112233453555](C:\Users\rekim\AppData\Roaming\Typora\typora-user-images\image-20250112233453555.png)

---

### Problema 15 - *QuickSort*

#### Enunț

Se dă un șir cu `n` elemente, numere întregi. Folosind metoda QuickSort (Sortare Rapidă), ordonați crescător elementele acestui șir.

#### Date de intrare și ieșire

- **Intrare:** *Programul citește de la tastatură numărul `n`, iar apoi cele `n` elemente ale șirului.*
- **Ieșire:** *Programul va afișa pe ecran elementele șirului sortat, separate prin exact un spațiu.*

#### Restricții și precizări

- `1 ≤ n ≤ 100.000`
- elementele șirului vor fi cuprinse între `-1.000.000.000` și `1.000.000.000`

#### Rezolvare și explicații

QuickSort este un algoritm eficient de sortare care utilizează metoda divide et impera:
1. Alege un element pivot din șir (în implementarea de mai jos, ultimul element).
2. Rearanjează șirul astfel încât toate elementele mai mici sau egale decât pivotul să fie în stânga, iar cele mai mari în dreapta (operațiunea de **partiționare**).
3. Aplică recursiv sortarea pe subșirurile din stânga și din dreapta pivotului.

#### Codul sursă

```cpp
#include <iostream>
using namespace std;

// Funcție pentru a realiza partiționarea șirului
int partition(int arr[], int low, int high) 
{
    int pivot = arr[high]; // Alegem pivotul ca fiind ultimul element
    int i = low - 1; // Indicele elementului mai mic

    for (int j = low; j < high; j++) 
    {
        if (arr[j] <= pivot) 
        {
            i++;
            swap(arr[i], arr[j]);
        }
    }

    swap(arr[i + 1], arr[high]); // Mutăm pivotul la poziția corectă
    return i + 1;
}

// Funcție recursivă pentru QuickSort
void quickSort(int arr[], int low, int high) 
{
    if (low < high) 
    {
        int pi = partition(arr, low, high);

        // Sortăm subșirurile din stânga și dreapta pivotului
        quickSort(arr, low, pi - 1);
        quickSort(arr, pi + 1, high);
    }
}

int main() 
{
    int n;
    cin >> n;

    int* arr = new int[n]; // Alocare dinamică pentru a gestiona n mare
    for (int i = 0; i < n; i++) 
    {
        cin >> arr[i];
    }

    quickSort(arr, 0, n - 1);

    for (int i = 0; i < n; i++) 
    {
        cout << arr[i] << " ";
    }
    cout << endl;

    delete[] arr; // Eliberăm memoria alocată dinamic
    return 0;
}
```

#### Exemple de rulare
| Intrare     | Ieșire       |
| ----------- | ------------ |
| 5 3 1 4 1 5 | 1 1 3 4 5    |
| 4 10 -5 0 3 | -5 0 3 10    |
| 6 5 9 1 3 8 | -1 1 3 5 8 9 |

#### Complexitate
- **Timp:** 
  - **Caz mediu:** O(n log n), deoarece fiecare partiționare împarte șirul în mod echilibrat.
  - **Caz nefavorabil:** O(n²), când pivotul ales este mereu cel mai mare sau cel mai mic element.
- **Spațiu:** O(log n) în medie pentru stiva de apeluri recursive.

![image-20250112233549475](C:\Users\rekim\AppData\Roaming\Typora\typora-user-images\image-20250112233549475.png)

---

### Problema 16 - *Lee2*

#### Enunț

Bil Gheiț, patronul Companiei Macrosoft, vă pune la dispoziție o matrice cu `n` linii, numerotate de la `1` la `n` și `n` coloane, numerotate de la `1` la `n`, care memorează numere naturale. Un drum în matrice care pornește de la poziția `(1,1)` și se termină la poziția `(n,n)` este constituit din componente adiacente două câte două pe linii și  coloane. Costul drumului este egal cu suma costurilor componentelor prin care trece drumul. Determinați costul minim al unui drum care pornește de la poziția `(1,1)` și se termină la poziția `(n,n)` și domnul Bil Gheiț vă va angaja imediat la compania sa pe post de fochist.

#### Date de intrare și ieșire

- **Intrare:** *Pentru toate testele, matricea se va genera aleator. Se citesc de la tastatură mai întâi numerele naturale `n`, `X`, `Y`, `Z`, `T`, iar apoi exact `n` numere naturale reprezentând prima linie din matrice. Restul elementelor se vor genera după formula: `a[i][j] = 1 + (a[i-1][j-1] * X + a[i-1][j] * Y + a[i-1][j+1] * Z) % T`, `i=2..n`, `j=1..n`. Se observă că unele elemente din formulă pot fi `0`, de exemplu, atunci când se calculează valoarea lui `a[2,1]` care depinde de `a[1, 0]`.*
- **Ieșire:** *Programul va afișa la ecran, ca să vadă și Bil, suma minimă a unui drum de la `(1,1)` la `(n,n)`.*

#### Restricții și precizări

- `1 ≤ n ≤ 1500`
- `1 ≤ X, Y, Z, T ≤ 500`
- `1 ≤ a[i,j] ≤ 500`, pentru orice `i=1..n`, `j=1..n`

#### Rezolvare și explicații

Pentru a rezolva problema, folosim algoritmul Lee (BFS pe matrice), care este eficient pentru a găsi costul minim al unui drum în grafuri neponderate sau cu costuri uniforme. În cazul nostru, adaptăm algoritmul pentru a calcula costurile drumurilor. Pașii sunt următorii:
1. Se citește și se generează matricea conform formulei din enunț.
2. Se inițializează o matrice a costurilor minime și o coadă pentru BFS.
3. Se parcurg vecinii fiecărei celule folosind BFS, actualizând costul minim pentru fiecare poziție vecină.
4. La final, costul minim al drumului se află în poziția `(n, n)` a matricei costurilor.

#### Codul sursă

```cpp
#include <iostream>
#include <vector>
#include <queue>
#include <climits>
using namespace std;

const int dx[] = {-1, 1, 0, 0}; // direcții pentru linie (sus, jos)
const int dy[] = {0, 0, -1, 1}; // direcții pentru coloană (stânga, dreapta)

void generateMatrix(vector<vector<int>>& a, int n, int X, int Y, int Z, int T) 
{
    for (int i = 1; i < n; ++i) 
    {
        for (int j = 0; j < n; ++j) 
        {
            int left = (j > 0) ? a[i - 1][j - 1] : 0;
            int mid = a[i - 1][j];
            int right = (j < n - 1) ? a[i - 1][j + 1] : 0;
            a[i][j] = 1 + (left * X + mid * Y + right * Z) % T;
        }
    }
}

int findMinPathCost(const vector<vector<int>>& a, int n) 
{
    vector<vector<int>> cost(n, vector<int>(n, INT_MAX)); // Matricea costurilor minime
    queue<pair<int, int>> q; // Coada pentru BFS

    cost[0][0] = a[0][0]; // Inițializăm costul de start
    q.push({0, 0});

    while (!q.empty()) 
    {
        int x = q.front().first;
        int y = q.front().second;
        q.pop();

        for (int dir = 0; dir < 4; ++dir) 
        {
            int nx = x + dx[dir];
            int ny = y + dy[dir];

            if (nx >= 0 && nx < n && ny >= 0 && ny < n) 
            {
                int newCost = cost[x][y] + a[nx][ny];
                if (newCost < cost[nx][ny]) 
                {
                    cost[nx][ny] = newCost;
                    q.push({nx, ny});
                }
            }
        }
    }

    return cost[n - 1][n - 1]; // Costul minim până la (n, n)
}

int main() 
{
    int n, X, Y, Z, T;
    cin >> n >> X >> Y >> Z >> T;

    vector<vector<int>> a(n, vector<int>(n));

    // Citim prima linie
    for (int j = 0; j < n; ++j) 
    {
        cin >> a[0][j];
    }

    // Generăm restul matricei
    generateMatrix(a, n, X, Y, Z, T);

    // Calculăm costul minim al drumului
    cout << findMinPathCost(a, n) << endl;

    return 0;
}
```

#### Exemple de rulare
| Intrare           | Ieșire |
| ----------------- | ------ |
| 3 2 2 2 10 1 2 3  | 16     |
| 4 1 1 1 5 4 5 6 7 | 21     |

#### Complexitate
- **Timp:** O(n²), deoarece fiecare celulă este procesată o singură dată în BFS.
- **Spațiu:** O(n²), necesar pentru matricea costurilor și matricea de intrare.

![image-20250112233624821](C:\Users\rekim\AppData\Roaming\Typora\typora-user-images\image-20250112233624821.png)

---

### Problema 17 - *Dijkstra*

#### Enunț

Se dă un graf orientat ponderat cu `n` noduri – în care fiecare arc are asociat un cost, număr natural strict pozitiv, și un nod `p`. Să se determine, folosind algoritmul lui Dijkstra, costul minim al drumului de la `p` la fiecare nod al grafului. 

#### Date de intrare și ieșire

- **Intrare:** *Fișierul de intrare `dijkstra.in` conține pe prima linie numerele `n p`, iar următoarele linii câte un triplet `i j c`, cu semnificația: există arcul `(i j)` și are costul `c`.*
- **Ieșire:** *Fișierul de ieșire `dijkstra.out` va conține pe prima linie `n` numere, separate prin exact un spațiu, al `i`-lea număr reprezentând costul drumului minim de la `p` la `i`. Dacă nu există drum de la `p` la un anumit vârf, costul afișat va fi `-1`.*

#### Restricții și precizări

- `1 ≤ n ≤ 100`
- costul unui arc va fi mai mic decât `1000`
- costul unui drum este egal cu suma costurilor arcelor care îl compun

#### Rezolvare și explicații

Algoritmul lui Dijkstra este folosit pentru a calcula drumurile minime de la un nod sursă la toate celelalte noduri dintr-un graf orientat ponderat cu costuri pozitive. Funcționarea algoritmului se bazează pe o coadă de priorități care menține nodurile de procesat în ordinea distanței minime cunoscute până la acel moment. 

1. Inițializăm toate distanțele cu infinit (`INF`), cu excepția nodului sursă, care are distanța `0`.
2. Folosim o coadă de priorități pentru a extrage nodul cu distanța minimă curentă.
3. Actualizăm distanțele pentru toți vecinii nodului curent dacă găsim un drum mai scurt către aceștia.
4. Repetăm procesul până când coada devine goală.

#### Codul sursă

```cpp
#include <iostream>
#include <fstream>
#include <vector>
#include <queue>
#include <climits>
using namespace std;

const int INF = INT_MAX;

void dijkstra(int n, int p, const vector<vector<pair<int, int>>>& graph, vector<int>& dist) 
{
    // Coada de priorități pentru BFS, elementele sunt perechi (cost, nod)
    priority_queue<pair<int, int>, vector<pair<int, int>>, greater<pair<int, int>>> pq;

    // Inițializăm distanțele
    dist.assign(n + 1, INF);
    dist[p] = 0;

    // Adăugăm nodul sursă în coadă
    pq.push({0, p});

    while (!pq.empty()) 
    {
        int d = pq.top().first; // Costul minim până acum
        int u = pq.top().second; // Nodul curent
        pq.pop();

        // Ignorăm distanțele deja actualizate
        if (d > dist[u]) continue;

        // Parcurgem toți vecinii nodului curent
        for (auto& edge : graph[u]) 
        {
            int v = edge.first; // Vecinul
            int cost = edge.second; // Costul arcului

            // Actualizăm distanța dacă găsim un drum mai scurt
            if (dist[u] + cost < dist[v]) 
            {
                dist[v] = dist[u] + cost;
                pq.push({dist[v], v}); // Adăugăm vecinul în coadă
            }
        }
    }
}

int main() 
{
    ifstream fin("dijkstra.in");
    ofstream fout("dijkstra.out");

    int n, p;
    fin >> n >> p;

    // Reprezentarea grafului ca listă de adiacență
    vector<vector<pair<int, int>>> graph(n + 1);

    int i, j, c;
    while (fin >> i >> j >> c) 
    {
        graph[i].emplace_back(j, c);
    }

    vector<int> dist;
    dijkstra(n, p, graph, dist);

    // Scriem rezultatele
    for (int k = 1; k <= n; ++k) 
    {
        fout << (dist[k] == INF ? -1 : dist[k]) << " ";
    }
    fout << endl;

    fin.close();
    fout.close();

    return 0;
}
```

#### Exemple de rulare
| Intrare                                                      | Ieșire     |
| ------------------------------------------------------------ | ---------- |
| 5 4 <br />1 3 1 <br />2 1 2 <br />4 2 1 <br />4 3 8 <br />5 3 5 <br />5 4 2 | 3 1 4 0 -1 |

#### Complexitate
- **Timp:** O((n + m) log n), unde `n` este numărul de noduri și `m` este numărul de arce, deoarece fiecare nod și fiecare arc este procesat o singură dată.
- **Spațiu:** O(n + m), pentru stocarea grafului și a cozii de priorități.

![image-20250112233658858](C:\Users\rekim\AppData\Roaming\Typora\typora-user-images\image-20250112233658858.png)

---

### Problema 18 - *BiFrunze*

#### Enunț

Considerăm un arbore binar cu `n` noduri în care fiecare nod este numerotat de la `1` la `n` și conține o valoare număr natural. Să se afișeze frunzele acestui arbore.

#### Date de intrare și ieșire

- **Intrare:** *Fișierul de intrare `bifrunze.in` conține pe prima linie numărul `n`. Fiecare dintre următoarele `n` linii contine câte `3` numere `X st dr`; linia `i + 1` din fișier conține informatiile despre nodul numerotat cu `i`: `X` reprezintă valoare din nod, `st` reprezintă numărul de ordine al descendentului stâng sau `0` dacă nodul `i` nu are descendent stâng, iar `dr` reprezintă numărul de ordine al descendentului drept sau `0` dacă nodul `i` nu are descendent drept.*
- **Ieșire:** *Fișierul de ieșire `bifrunze.out` va conține pe prima linie  numerele de ordine ale nodurilor din arbore care sunt frunze, în ordine  crescătoare, separate prin exact un spațiu.*

#### Restricții și precizări

- `1 ≤ n ≤ 1000`
- valorile din nodurile arborelui vor fi mai mici sau egale cu `1.000.000`

#### Rezolvare și explicații

Frunzele unui arbore sunt nodurile care nu au niciun copil (descendent stâng sau drept). Pentru a identifica frunzele:
1. Presupunem inițial că toate nodurile sunt frunze.
2. După citirea informațiilor despre descendenți, marcăm nodurile care au copii ca fiind non-frunze.
3. Afișăm nodurile care rămân marcate ca frunze.

Această metodă este eficientă deoarece parcurgem informațiile despre noduri o singură dată.

#### Codul sursă

```cpp
#include <iostream>
#include <fstream>
#include <vector>
#include <algorithm>
using namespace std;

struct Nod {
    int valoare;
    int stanga;
    int dreapta;
};

int main() 
{
    ifstream fin("bifrunze.in");
    ofstream fout("bifrunze.out");

    int n;
    fin >> n;

    vector<Nod> arbore(n + 1); // Vector pentru a memora arborele
    vector<bool> esteFrunza(n + 1, true); // Presupunem inițial că toate nodurile sunt frunze

    // Citim datele despre arbore
    for (int i = 1; i <= n; ++i) 
    {
        int valoare, stanga, dreapta;
        fin >> valoare >> stanga >> dreapta;

        arbore[i] = {valoare, stanga, dreapta};

        // Dacă un nod are copii, el nu este frunză
        if (stanga != 0 || dreapta != 0) 
        {
            esteFrunza[i] = false;
        }
    }

    // Identificăm nodurile care sunt frunze
    vector<int> frunze;
    for (int i = 1; i <= n; ++i) 
    {
        if (esteFrunza[i]) 
        {
            frunze.push_back(i);
        }
    }

    // Sortăm frunzele în ordine crescătoare
    sort(frunze.begin(), frunze.end());

    // Afișăm rezultatele
    for (int frunza : frunze) 
    {
        fout << frunza << " ";
    }
    fout << endl;

    fin.close();
    fout.close();

    return 0;
}
```

#### Exemple de rulare

| Intrare                                                      | Ieșire |
| ------------------------------------------------------------ | ------ |
| 6 <br />2 3 5 <br />6 0 6 <br />1 0 0 <br />7 1 2 <br />4 0 0 <br />10 0 0 | 3 5 6  |

#### Complexitate
- **Timp:** O(n), deoarece procesăm fiecare nod o singură dată.
- **Spațiu:** O(n), pentru stocarea informațiilor despre arbore și vectorul de frunze.

![image-20250112233733990](C:\Users\rekim\AppData\Roaming\Typora\typora-user-images\image-20250112233733990.png)

---

### Problema 19 - *AfisCircuite*

#### Enunț

Se dă lista arcelor unui graf orientat. Să se afișeze, în ordine lexicografică, toate circuitele de lungime trei.

#### Date de intrare și ieșire

- **Intrare:** *Programul citește de la tastatură numărul `n` de noduri și numărul `m` de arce, iar apoi lista arcelor, formată din `m` perechi de forma `i j`, cu semnificația că există arc orientat de la nodul `i` la nodul `j`.*
- **Ieșire:** *Programul va afișa pe ecran circuitele cerute, câte un circuit pe o  linie a ecranului, nodurile unui circuit fiind separate prin exact un  spațiu.*

#### Restricții și precizări

- `1 ≤ n ≤ 100`

#### Rezolvare și explicații

Pentru a găsi toate circuitele de lungime exact 3 dintr-un graf orientat:
1. Reprezentăm graful folosind o matrice de adiacență.
2. Parcurgem toate perechile de noduri `(u, v)` astfel încât există arc `u -> v`.
3. Pentru fiecare astfel de pereche, verificăm dacă există o succesiune de arce `u -> v -> w -> u` care formează un circuit de lungime trei.
4. Stocăm circuitele găsite și le sortăm în ordine lexicografică înainte de afișare.

#### Codul sursă

```cpp
#include <iostream>
#include <vector>
#include <algorithm>
using namespace std;

int main() 
{
    int n, m;
    cin >> n >> m;

    vector<vector<bool>> adj(n + 1, vector<bool>(n + 1, false)); // Matrice de adiacență

    // Citim arcele și construim matricea de adiacență
    for (int i = 0; i < m; ++i) 
    {
        int u, v;
        cin >> u >> v;
        adj[u][v] = true;
    }

    // Găsim circuitele de lungime exact 3
    vector<vector<int>> circuite;

    for (int u = 1; u <= n; ++u) 
    {
        for (int v = 1; v <= n; ++v) 
        {
            if (adj[u][v]) { // Există arc u -> v
                for (int w = 1; w <= n; ++w) 
                {
                    if (adj[v][w] && adj[w][u]) 
                    { // Există arc v -> w și w -> u
                        circuite.push_back({u, v, w});
                    }
                }
            }
        }
    }

    // Sortăm circuitele în ordine lexicografică
    sort(circuite.begin(), circuite.end());

    // Afișăm circuitele
    for (const auto& circuit : circuite) 
    {
        cout << circuit[0] << " " << circuit[1] << " " << circuit[2] << endl;
    }

    return 0;
}
```

- #### Exemple de rulare
  | Intrare                                             | Ieșire                                                  |
  | --------------------------------------------------- | ------------------------------------------------------- |
  | 4 6<br/>1 2<br/>2 3<br/>3 1<br/>1 3<br/>3 4<br/>4 1 | 1 2 3<br/>1 3 4<br/>2 3 1<br/>3 1 2<br/>3 4 1<br/>4 1 3 |

  #### Complexitate
  - **Timp:** O(n^3), deoarece pentru fiecare pereche de noduri `(u, v)`, verificăm toate posibilele noduri intermediare `w`.
  - **Spațiu:** O(n^2), pentru stocarea matricei de adiacență.

  ![image-20250112233811896](C:\Users\rekim\AppData\Roaming\Typora\typora-user-images\image-20250112233811896.png)

---

### Problema 20 - *Catalog_ChatGPT*

#### Enunț

Se dorește implementarea unui program care să gestioneze un catalog școlar. Catalogul trebuie să permită adăugarea elevilor, înregistrarea notelor pentru fiecare elev, calcularea mediei acestora și afișarea detaliilor elevilor cu media peste un prag dat.

#### Date de intrare și ieșire

- **Intrare:** *Programul citește de la tastatură numărul `n` de elevi , fiecare dintre următoarele `n` linii conține un șir de caractere (numele elevului), numărul `m` de note și `m` numere întregi care reprezintă notele acelui elev.*
  *Ultima linie de intrare conține pragul minim pentru afișarea elevilor cu media peste acest prag.*
- **Ieșire:** *Lista elevilor care au media notelor mai mare decât pragul specificat, împreună cu media fiecăruia.*

#### Restricții și precizări

- Numele elevilor nu depășesc 100 de caractere.
- `0 < n < 51`
- `0 < m < 21`
- Notele sunt întregi, între 1 și 10.

#### Rezolvare și explicații

Programul folosește o clasă `Elev` pentru a gestiona datele fiecărui elev. Aceasta include:
1. Metode pentru a adăuga note.
2. Calcularea mediei notelor.
3. Afișarea detaliilor elevilor care îndeplinesc criteriul de medie mai mare decât pragul specificat.

#### Codul sursă

```cpp
#include <iostream>
#include <vector>
#include <string>
#include <iomanip>
using namespace std;

// Clasa pentru a reprezenta un elev
class Elev {
private:
    string nume;
    vector<int> note;
    double media;

public:
    // Constructor
    Elev(string nume) : nume(nume), media(0.0) {}

    // Adăugare note
    void adaugaNota(int nota) {
        note.push_back(nota);
    }

    // Calcularea mediei
    void calculeazaMedia() {
        if (note.empty()) {
            media = 0.0;
            return;
        }
        int suma = 0;
        for (int nota : note) 
        {
            suma += nota;
        }
        media = static_cast<double>(suma) / note.size();
    }

    // Obținerea numelui elevului
    string getNume() const {
        return nume;
    }

    // Obținerea mediei elevului
    double getMedia() const {
        return media;
    }
};

int main() {
    int n;
    cout << "Introduceți numărul de elevi: ";
    cin >> n;

    vector<Elev> catalog;

    // Citirea datelor despre elevi
    for (int i = 0; i < n; i++) {
        string nume;
        cout << "Introduceți numele elevului " << i + 1 << ": ";
        cin.ignore();
        getline(cin, nume);

        Elev elev(nume);

        int m;
        cout << "Introduceți numărul de note pentru " << nume << ": ";
        cin >> m;

        cout << "Introduceți notele: ";
        for (int j = 0; j < m; j++) {
            int nota;
            cin >> nota;
            elev.adaugaNota(nota);
        }

        elev.calculeazaMedia();
        catalog.push_back(elev);
    }

    double prag;
    cout << "Introduceți pragul minim pentru afișare: ";
    cin >> prag;

    cout << "\nElevii cu media mai mare decât " << prag << " sunt:\n";
    for (const Elev& elev : catalog) {
        if (elev.getMedia() > prag) {
            cout << "- " << elev.getNume() << " cu media " << fixed << setprecision(2) << elev.getMedia() << "\n";
        }
    }

    return 0;
}
```

#### Exemple de rulare

| Intrare                                                      | Ieșire                                                       |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| 3<br/>Ion Popescu <br />3 <br />8 9 7<br/>Maria Ionescu <br />3 <br />10 10 9<br/>Dionisie Rechimciuc<br />3<br />3 1 7<br />7.5 | Elevii cu media mai mare decât 7.5 sunt:<br/>- Ion Popescu cu media 8.00<br />- Ana Ionescu cu media 9.67 |

#### Complexitate
- **Timp:** O(n × m), unde `n` este numărul de elevi, iar `m` este numărul mediu de note per elev.
- **Spațiu:** O(n × m), pentru stocarea notelor fiecărui elev.

---

## Anexe

### Bibliografie
- *https://www.pbinfo.ro*
