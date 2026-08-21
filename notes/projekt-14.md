## Projekt 14 – Przekierowania i potoki w systemie Linux

# Cel

Poznanie sposobu przekazywania danych pomiędzy poleceniami oraz zapisywania ich do plików przy użyciu operatorów przekierowań i potoków.

# Notatki

Na początku utworzyłem katalog roboczy projektu:

* cd /home/vboxuser/projekty
* mkdir projekt14
* cd projekt14

Następnie nauczyłem się przekierowywać wynik działania polecenia do pliku:

* date > data.txt

Sprawdziłem zawartość pliku:

* cat data.txt

Dowiedziałem się, że operator ">" zapisuje wynik do pliku oraz nadpisuje jego poprzednią zawartość, jeżeli plik już istnieje.

Następnie dopisałem nazwę aktualnie zalogowanego użytkownika do tego samego pliku:

* whoami >> data.txt

Ponownie sprawdziłem jego zawartość:

* cat data.txt

Dowiedziałem się, że operator ">>" dopisuje nowe dane na końcu pliku, nie usuwając wcześniejszej zawartości.

Aby zobaczyć różnicę pomiędzy tymi operatorami, nadpisałem plik nazwą serwera:

* hostname > data.txt

Sprawdziłem zawartość pliku i potwierdziłem, że wcześniejsze dane zostały zastąpione:

* cat data.txt

Następnie poznałem operator "|" (pipe), który przekazuje wynik jednego polecenia do następnego.

Wyszukałem proces usługi SSH:

* ps aux | grep ssh

Następnie wyświetliłem zawartość katalogu i wyszukałem tylko pliki tekstowe:

* ls -l | grep ".txt"

Na końcu zapisałem zawartość katalogu domowego do pliku, a następnie wyszukałem w nim katalogi projektów:

* ls -l /home/vboxuser > pliki.txt
* grep "projekt" pliki.txt

# Problemy

Nie napotkałem żadnych problemów w projekcie.

# Rozwiązania

Nie potrzebowałem rozwiązać żadnych problemów w projekcie.

# Wnioski

Dowiedziałem się, czym różnią się operatory ">" oraz ">>" i kiedy należy ich używać. Nauczyłem się również korzystać z operatora "|" (pipe), który pozwala przekazywać wynik jednego polecenia do kolejnego, dzięki czemu można łączyć proste polecenia w bardziej przydatne rozwiązania.
