## Projekt 10 – Monitorowanie dysków i miejsca na systemie Linux

# Cel

Poznanie sposobów sprawdzania wykorzystania przestrzeni dyskowej w Ubuntu Server oraz nauczenie się analizowania dysków, partycji i rozmiaru plików.

# Notatki

Sprawdziłem pierwszy raz miejsce na dysku używając:

* df -h

Dodałem "-h" żeby mieć czytelny format zamiast samych bajtów.

Następnie sprawdziłem dostępne dyski i partycje systemowe:

* lsblk

Dowiedziałem się też jak sprawdzać poszczególne rozmiary katalogów i sprawdziłem rozmiar katalogów domowych:

* du -sh /home/vboxuser
* du -sh /home/*

Aby sprawdzić, czy zmiana wykorzystania miejsca na dysku będzie widoczna, utworzyłem plik testowy w ścieżce /home/vboxuser oraz sprawdziłem czy jego rozmiar się zgadza:

* fallocate -l 100M testowy-plik
* ls -lh testowy-plik

Ponownie sprawdziłem miejsce na dysku aby zobaczyć czy plik wprowadził w nim zmiany:

* df -h

Zauważyłem zmianę wykorzystania miejsca na dysku i usunąłem testowy plik:

* rm testowy-plik
* df -h

# Problemy

Nie napotkałem żadnych problemów w projekcie.

# Rozwiązania

Nie potrzebowałem rozwiązać żadnych problemów w projekcie.

# Wnioski

Dowiedziałem się, jak monitorować wykorzystanie miejsca na dysku oraz sprawdzać rozmiary plików i katalogów. Zrozumiałem, do czego służą polecenia "df", "du" oraz "lsblk" i kiedy warto z nich korzystać.
