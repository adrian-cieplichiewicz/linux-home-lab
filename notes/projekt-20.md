## Projekt 20 - Podstawy Dockera

# Cel

Poznanie podstaw działania Dockera, różnicy między obrazem a kontenerem oraz uruchamiania i zarządzania prostymi kontenerami.

# Notatki

Na początku sprawdziłem czy docker jest zainstalowany:

* docker --version

Po dowiedzeniu się że nie jest, zainstalowałem go i sprawdziłem czy jest aktywny:

* sudo apt install docker.io
* sudo systemctl status docker

Następnie sprawdziłem informacje o dockerze:

* sudo docker info

Uruchomiłem swój pierwszy kontener przez dockera po naprawieniu daty:

* sudo docker run hello-world

Sprawdziłem lokalne obrazy szukając niedawno użytego hello-world:

* sudo docker images

Sprawdziłem kontenery przez:

* sudo docker ps

Jednak hello-world nie był na liście, dowiedziałem się że muszę dodać '-a' aby również wyświetlić zatrzymane i zakończone kontenery:

* sudo docker ps -a

Jako następny kontener, uruchomiłem Nginx

* sudo docker run -d --name moj-kontener nginx

Porównałem wyniki komend z aktywną usługą:

* sudo docker ps
* sudo docker ps -a

Następnie sprawdziłem pierwszy raz logi kontenera:

* sudo docker logs moj-kontener

Po sprawdzeniu logów, zatrzymałem kontener, upewniłem się że został zatrzymany oraz ponownie go uruchomiłem aby nauczyć się restartować kontenery:

* sudo docker stop moj-kontener
* sudo docker ps
* sudo docker ps -a
* sudo docker start moj-kontener
* sudo docker ps

Jako ostatnia część projektu zatrzymałem kontener i nauczyłem się usuwać kontenery poprzez:

* sudo docker stop moj-kontener
* sudo docker rm moj-kontener

Upewniłem się że kontener został usunięty poprzez: 

* sudo docker ps -a

# Problemy

* Nie byłem pewny jak zainstalować dockera.
* Docker nie działał poprzez niepoprawną datę na serwerze Linux.

# Rozwiązania

* Dowiedziałem się że usługę instaluje się używając poprzez wpisanie docker.io (sudo apt install docker.io)
* Zmieniłem datę w serwerze na poprawną poprzez:
sudo date -s '2026-08-15 15:25:00'

# Wnioski

Dowiedziałem się czym jest docker oraz nauczyłem się go używać poprzez podstawowe komendy do włączania kontenerów, zatrzymywania ich, sprawdzania ich logów, sprawdzania aktywnych oraz pobranych kontenerów, itd.