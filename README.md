## Bash -- zadania
[Czarkowska, Monika](https://github.com/monika001/zadania-z-basha/),[1](https://github.com/monika001/Programowanie-w-C)
Treści dostępne sa na [stronie](http://wbzyl.inf.ug.edu.pl/sp/labs01).

## Bash -- zadania
### Laboratorium 1

1\. Używając linii poleceń stwórz strukturę katalogów:
```sh
mkdir ~/temp/{dom,nauka/{c,logo,pascal},praca/{dokumenty,zlecenia/{niezrealizowane,zrealizowane}}} -p

```
2\. Przejdź do katalogu dom i utwórz katalog wazne-sprawy.
```sh
mkdir ~/temp/dom/wazne-sprawy
```

3\. Wejdź do katalogu wazne-sprawy i utwórz tam pusty plik rachunki.txt.
```sh
touch ~/temp/dom/wazne-sprawy/rachunki.txt
```

4\. Będąc w katalogu wazne-sprawy skopiuj plik rachunki.txt do katalogu zrealizowane.
```sh
cp rachunki.txt ~/temp/praca/zlecenia/zrealizowane
```

5\.Przejdź do katalogu zrealizowane i zmień nazwę pliku rachunki.txt na wykonano.txt.
```sh
cd praca/zlecenia/zrealizowane/
mv rachunki.txt wykonano.txt
```

6\. Utwórz plik wykonano.txt wielkości 11 bajtów, następnie podziel go pliki wielkości 5 bajtów. W ten sposób otrzymasz 3 pliki.
```sh
touch wykonano.txt
atom wykonano. txt
split -b 5 wykonano.txt
```

7\. Będąc w katalogu logo skopiuj powyżej otrzymane 3 pliki do katalogu dokumenty.
```sh
cd ~/temp/nauka/logo
cp ~/temp/praca/zlecenia/zrealizowane/{xaa,xab,xac} ~/temp/praca/dokumenty/
```

8\. Będąc w katalogu dokumenty połącz skopiowane 3 pliki w plik odtworzono.txt, tak aby otrzymać plik o zawartości identycznej z wykonano.txt. Następnie plik odtworzono.txt skopiuj do katalogu wazne-sprawy.
```sh
cat xaa xab xac > odtworzono.txt
cp odtworzono.txt ~/temp/dom/wazne-sprawy/
```

9\. Będąc w katalogu wazne-sprawy sprawdź, czy są jakieś różnice w zawartości plików wykonano.txt i odtworzono.txt.
Odp: Nie ma. 
 
10\. Wyświetl kalendarz na październik 2009 r.
```sh
cal oct 2009
```

Wyświetl kalendarz na wrzesień, październik i listopad 2009 r. z miesiącami obok siebie (cal):
```sh
cal -3 oct 2009

   Wrzesień 2009        Październik 2009       Listopad 2009      
ni po wt śr cz pi so  ni po wt śr cz pi so  ni po wt śr cz pi so  
       1  2  3  4  5               1  2  3   1  2  3  4  5  6  7  
 6  7  8  9 10 11 12   4  5  6  7  8  9 10   8  9 10 11 12 13 14  
13 14 15 16 17 18 19  11 12 13 14 15 16 17  15 16 17 18 19 20 21  
20 21 22 23 24 25 26  18 19 20 21 22 23 24  22 23 24 25 26 27 28  
27 28 29 30           25 26 27 28 29 30 31  29 30 
```

Wyświetl kalendarz na październik, listopad i grudzień 2009 r. w taki sposób:
```sh
cal -3 nov 2009
                            2009
    Październik             Listopad              Grudzień        
ni po wt śr cz pi so  ni po wt śr cz pi so  ni po wt śr cz pi so  
             1  2  3   1  2  3  4  5  6  7         1  2  3  4  5  
 4  5  6  7  8  9 10   8  9 10 11 12 13 14   6  7  8  9 10 11 12  
11 12 13 14 15 16 17  15 16 17 18 19 20 21  13 14 15 16 17 18 19  
18 19 20 21 22 23 24  22 23 24 25 26 27 28  20 21 22 23 24 25 26  
25 26 27 28 29 30 31  29 30                 27 28 29 30 31   
```
I jeszcze raz na wrzesień i październik oraz na październik i listopad 2009 r z miesiącami obok siebie:
```sh
cal -A 1 sep 2009

   Wrzesień 2009        Październik 2009    
ni po wt śr cz pi so  ni po wt śr cz pi so  
       1  2  3  4  5               1  2  3  
 6  7  8  9 10 11 12   4  5  6  7  8  9 10  
13 14 15 16 17 18 19  11 12 13 14 15 16 17  
20 21 22 23 24 25 26  18 19 20 21 22 23 24  
27 28 29 30           25 26 27 28 29 30 31  

cal -A 1 oct 2009

  Październik 2009       Listopad 2009      
ni po wt śr cz pi so  ni po wt śr cz pi so  
             1  2  3   1  2  3  4  5  6  7  
 4  5  6  7  8  9 10   8  9 10 11 12 13 14  
11 12 13 14 15 16 17  15 16 17 18 19 20 21  
18 19 20 21 22 23 24  22 23 24 25 26 27 28  
25 26 27 28 29 30 31  29 30 
```

11\.Jaki był dzień tygodnia 25 maja 1975 r.?

```sh
cal -H 1975-05-25
Sobota
```
### Laboratorium 2

1\. Wyświetl na ekran 2 pierwsze wiersze pliku program.c. (head)
```sh
cd ~/temp/nauka/c
atom program.c
head program.c
```
2\. Wyświetl na ekran 4 ostatnie wiersze pliku program.c. (head, tail)
```sh
tail -n 4 program.c
```

3\. W pliku program.c znajdź wszystkie wiersze z wystąpieniem słowa „main”. (grep)
```sh
grep 'main' program.c
```
4\. Plikowi program.c nadaj następujące uprawnienia: właściciel – czytanie, pisanie, grupa – czytanie, pozostali użytkownicy: brak uprawnień. (chmod)
```sh
chmod u=rw,g=r,o=--- program.c
```
5\. Będąc w katalogu temp przenieś katalog wazne-sprawy do katalogu praca.
```sh
cd temp
mv dom/wazne-sprawy praca
```
6\. Zarchiwizuj cały katalog temp. (zip i tar)
```sh
tar -czf archiwum1.tar.gz temp
tar -czf archiwum1.tar.gz temp
```
7\. Usuń katalog temp.
```sh
rm -r temp
```

8\. Odtwórz z archiwum katalog temp. (unzip i tar)
```sh
tar -xzf archiwum1.tar.gz
unzip archiwum2.zip
```
###Laboratorium 3

1\. Wyświetl plik /etc/passwd z podziałem na strony przyjmując, że strona na 5 linii tekstu. (raczej more niż less)
```sh
 more -5 /etc/passwd
 ```
2\. Korzystając z polecenia cat utwórz plik tekst3.txt, który będzie składał się z zawartości pliku tekst1.txt, ciągu znaków podanego ze standardowego wejścia (klawiatury) i pliku tekst2.txt.
```sh
touch tekst1.txt
touch tekst2.txt
cat tekst1.txt tekst2.txt > tekst3.txt
```

4\. Wyświetl linie o numerach 3, 4 i 5 z pliku /etc/passwd.
```sh
sed -n '3,5p' /etc/passwd
```

5\. Wyświetl linie o numerach 7, 6 i 5 od końca pliku /etc/passwd.
```sh
tail -n 7 /etc/passwd | head -n 1
tail -n 6 /etc/passwd | head -n 1
tail -n 5 /etc/passwd | head -n 1
```

6\. Wyświetl zawartość pliku /etc/passwd w jednej linii.
```sh
cat /etc/passwd | tr '\n' ' '
```
7\. Za pomocą filtru tr wykonaj modyfikację pliku plik.txt, polegającą na wypisaniu każdego słowa w osobnej linii.
```sh
cat /etc/passwd | tr ' ' '\n'
```
8\. Zlicz wszystkie pliki znajdujące się w katalogu /var i jego podkatalogach.
```sh
ls -1 /var | wc -l
```
9\. Napisać polecenie zliczające ilość znaków z pierwszych trzech linii pliku /etc/passwd.
```sh
cat /etc/passwd |head -n 3 |wc -c
```
###Laboratorium 4


1\. Wyświetl listę plików z aktualnego katalogu, zamieniając wszystkie małe litery na duże.
```sh
ls | tr [:lower:] [:upper:]
```
2\. Wyświetl listę praw dostępu do plików w aktualnym katalogu, ich rozmiar i nazwę.
```sh
ls -l | awk '{print $1,$5,$9}'
```
3\. Wyświetl listę plików w aktualnym katalogu, posortowaną według rozmiaru pliku.
```sh
ls -l | sort -k5,5
```

