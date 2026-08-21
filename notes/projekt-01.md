## Projekt 01 – Konfiguracja podstawowego laboratorium Linux

# Cel

Przygotowanie własnego środowiska do nauki administracji systemami Linux z wykorzystaniem Ubuntu Server uruchomionego w VirtualBox.

# Notatki

Zainstalowałem ubuntu server oraz skonfigurowałem podstawowe dane systemu.
Następnie zaktualizowałem system poprzez:

* sudo apt update
* sudo apt upgrade -y

Po aktualizacji sprawdziłem informacje systemowe używając: 

* hostname
* hostnamectl
* whoami
* ip a
* uname -r

Nauczyłem się od razu podstaw poruszania się po plikach systemowych przez:

* pwd
* ls
* cd

Utworzyłem katalog roboczy "projekty" w katalogu domowym oraz w ścieżce /home/vboxuser/projekty stworzyłem "linux-lab".
Następnie nauczyłem się obsługiwać edytor nano oraz stworzyłem pierwszy plik tekstowy i odczytałem go używając:

* cat

# Problemy

* Nie pamiętałem danych logowania do porzedniej testowej maszyny wirtualnej ubuntu server.

# Rozwiązania

* Usunąłem poprzednią maszynę wirtualną.
* Zainstalowałem nową maszynę ubuntu server.
* Zapisałem dane logowania w bezpiecznym miejscu.

# Wnioski

Projekt pozwolił przygotować własne środowisko do dalszej nauki administracji Linuxem. Poznałem podstawowe komendy terminala oraz sposób organizacji pracy z serwerem. To będzie baza do kolejnych projektów związanych z użytkownikami, SSH, Dockerem i konfiguracją usług.





