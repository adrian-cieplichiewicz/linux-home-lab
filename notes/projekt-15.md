## Projekt 15 – Zmienne środowiskowe w systemie Linux

# Cel

Poznanie zmiennych środowiskowych w systemie Linux oraz nauczenie się ich wyświetlania, tworzenia i wykorzystywania w terminalu.

# Notatki

Na początku wyświetliłem wszystkie zmienne środowiskowe dostępne w systemie:

* printenv

Następnie sprawdziłem wartości kilku najważniejszych zmiennych:

* echo $USER
* echo $HOME
* echo $HOSTNAME

Dowiedziałem się, że zmienne środowiskowe przechowują informacje wykorzystywane przez system i programy, takie jak nazwa użytkownika czy katalog domowy.

Następnie wyświetliłem zawartość zmiennej "PATH":

* echo $PATH

Dowiedziałem się, że zawiera ona listę katalogów, w których system szuka programów wpisywanych w terminalu.

Sprawdziłem, gdzie znajdują się wybrane programy:

* which ls
* which nano
* which grep

Nauczyłem się również tworzyć własne zmienne środowiskowe:

* export IMIE="TwojeImię"

Sprawdziłem wartość utworzonej zmiennej:

* echo $IMIE

Następnie wykorzystałem ją w poleceniu:

* echo "Cześć $IMIE"

Na końcu usunąłem utworzoną zmienną i upewniłem się, że została usunięta:

* unset IMIE
* echo $IMIE

# Problemy

Nie napotkałem żadnych problemów w projekcie.

# Rozwiązania

Nie potrzebowałem rozwiązać żadnych problemów w projekcie.

# Wnioski

Dowiedziałem się, czym są zmienne środowiskowe oraz do czego służą. Zrozumiałem również, jak działa zmienna "PATH", dlaczego można uruchamiać programy bez podawania ich pełnej ścieżki oraz jak tworzyć i usuwać własne zmienne środowiskowe.
