## Projekt 19 – Argumenty skryptów Bash

# Cel

Poznanie sposobu przekazywania danych do skryptu Bash podczas jego uruchamiania oraz wykorzystywania ich wewnątrz skryptu.

# Notatki

Na początku utworzyłem katalog projektu:

* cd /home/vboxuser/projekty
* mkdir projekt19
* cd projekt19

Następnie utworzyłem skrypt:

* nano argumenty.sh

Dodałem do niego obsługę argumentów. Dowiedziałem się, że "$1", "$2" itd. oznaczają kolejne argumenty podane podczas uruchamiania skryptu.

Nadałem skryptowi prawo wykonywania:

* chmod +x argumenty.sh

Uruchomiłem skrypt bez argumentów oraz z podanymi argumentami:

* ./argumenty.sh
* ./argumenty.sh Linux Ubuntu

Następnie poznałem kolejne specjalne zmienne Bash:

* "$#" oznacza liczbę podanych argumentów.
* "$@" oznacza wszystkie podane argumenty.

Sprawdziłem ich działanie:

* ./argumenty.sh Linux Ubuntu Server

Następnie wykorzystałem argument jako ścieżkę do pliku:

* ./argumenty.sh /etc/hostname

Sprawdziłem również działanie skryptu dla nieistniejącego pliku:

* ./argumenty.sh /nieistniejacy-plik

Na końcu dodałem warunek sprawdzający, czy użytkownik podał argument. Dzięki temu skrypt może zachować się inaczej, gdy nie otrzyma wymaganych danych.

Podczas samodzielnego pisania warunku zapomniałem początkowo o "then", "fi" oraz średniku ";". Po poprawieniu składni skrypt działał prawidłowo.

# Problemy

* Podczas samodzielnego pisania warunku zapomniałem o "then", "fi" oraz średniku ";".

# Rozwiązania

* Poprawiłem składnię warunku, dodając brakujące elementy, a następnie ponownie uruchomiłem skrypt.

# Wnioski

Nauczyłem się przekazywać argumenty do skryptów Bash i wykorzystywać je wewnątrz skryptu. Poznałem znaczenie "$1", "$2", "$#", "$@" oraz zacząłem wykorzystywać warunki "if" w Bashu.