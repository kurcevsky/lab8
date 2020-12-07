<h2 align="center"><center>Sprawozdanie</center>
<br>Programowanie równoległe i rozproszone</h2>.

```md
mpicc main.c -o main
mpirun -np 4 main
```
<b>Reguły gry:</b>
Gra toczy się na nieskończonej planszy (tutaj na skonczonej, w celu ukazania efektow), podzielonej na kwadratowe komórki. Każda komórka ma ośmiu „sąsiadów” (tzw. sąsiedztwo Moore’a), czyli komórki przylegające do niej bokami i rogami. Każda komórka może znajdować się w jednym z dwóch stanów: może być albo „żywa” (włączona), albo „martwa” (wyłączona). Stany komórek zmieniają się w pewnych jednostkach czasu. Stan wszystkich komórek w pewnej jednostce czasu jest używany do obliczenia stanu wszystkich komórek w następnej jednostce. Po obliczeniu wszystkie komórki zmieniają swój stan dokładnie w tym samym momencie. Stan komórki zależy tylko od liczby jej żywych sąsiadów. W grze w życie nie ma graczy w dosłownym tego słowa znaczeniu. Udział człowieka sprowadza się jedynie do ustalenia stanu początkowego komórek.

<b>Reguły gry według Conwaya:</b>
Martwa komórka, która ma dokładnie 3 żywych sąsiadów, staje się żywa w następnej jednostce czasu (rodzi się)
Żywa komórka z 2 albo 3 żywymi sąsiadami pozostaje nadal żywa; przy innej liczbie sąsiadów umiera (z „samotności” albo „zatłoczenia”).

<br>
Ów program jest implementacją Gry w życie w wersji Conwaya, który wykorzystuje przesyłanie komunikatów pomiędzy procesami równolegle (send i receive MPI). Obsługiwalna liczba procesów powinna być wielokrotnością liczby 2 (2^N, również dla N=0).
