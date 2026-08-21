## Projekt 11 – Wyszukiwanie plików i tekstu w systemie Linux

# Cel

Poznanie sposobów wyszukiwania plików oraz odnajdywania tekstu w plikach przy użyciu poleceń "find" i "grep".

# Notatki

Na początku utworzyłem katalog roboczy oraz kilka plików testowych, które posłużyły do nauki wyszukiwania:

* cd /home/vboxuser
* mkdir projekt11
* cd projekt11
* touch notatka.txt
* touch dane.txt
* touch log.txt
* touch raport.md

Następnie dodałem do plików przykładową zawartość:

* echo "Linux jest świetny." > notatka.txt
* echo "Administrator systemu." > dane.txt
* echo "Błąd połączenia SSH." > log.txt
* echo "Projekt numer 11." > raport.md

Nauczyłem się wyszukiwać pliki przy użyciu polecenia "find". Dowiedziałem się, że kropka "." oznacza aktualny katalog, od którego rozpoczyna się wyszukiwanie.

* find . -name "notatka.txt"
* find . -name "*.txt"
* find . -type d
* find . -type f

Następnie poznałem polecenie "grep", które służy do wyszukiwania tekstu wewnątrz plików.

* grep "Linux" notatka.txt
* grep -r "SSH" .

Dowiedziałem się, że opcja "-r" powoduje przeszukiwanie wszystkich podkatalogów, a kropka "." oznacza rozpoczęcie wyszukiwania od aktualnego katalogu.

Sprawdziłem również wyszukiwanie bez rozróżniania wielkości liter:

* grep -i "linux" notatka.txt

Na końcu dodałem kilka dodatkowych wpisów do pliku i nauczyłem się liczyć wystąpienia tekstu oraz wyświetlać numery linii, w których został znaleziony.

* echo "Linux" >> notatka.txt
* echo "Linux" >> notatka.txt
* grep -c "Linux" notatka.txt
* grep -n "Linux" notatka.txt

# Problemy

Nie napotkałem żadnych problemów w projekcie.

# Rozwiązania

Nie potrzebowałem rozwiązać żadnych problemów w projekcie.

# Wnioski

Dowiedziałem się, czym różnią się polecenia "find" i "grep". Nauczyłem się wyszukiwać pliki według nazwy oraz odnajdywać konkretny tekst wewnątrz plików. Zrozumiałem również, że kropka "." oznacza aktualny katalog, od którego rozpoczyna się wyszukiwanie.
