## Projekt 02 – Użytkownicy i uprawnienia

# Cel

Zrozumienie, jak wygląda zarządzanie użytkownikami oraz podstawowym systemem uprawnień w Linux.

# Notatki

Sprawdziłem informacje o aktualnie zalogowanym użytkowniku przy użyciu poleceń:

* whoami
* id
* groups

Następnie utworzyłem nowego użytkownika za pomocą:

* sudo adduser adam

Sprawdziłem, czy użytkownik został poprawnie utworzony:

* grep adam /etc/passwd
* ls /home

Przełączyłem się na nowo utworzone konto:

* su - adam

oraz zweryfikowałem nazwę użytkownika i katalog domowy:

* whoami
* pwd

Po powrocie na konto `vboxuser` utworzyłem katalog `tajne` oraz plik tekstowy:

* mkdir tajne
* echo "To jest tajny plik." > tajne/notatka.txt

Sprawdziłem aktualne uprawnienia:

* ls -l
* ls -ld tajne

Następnie zmieniłem uprawnienia katalogu:

* chmod 700 tajne

Na koniec zalogowałem się ponownie jako użytkownik `adam` i sprawdziłem, czy ma dostęp do katalogu `tajne`.

# Problemy

* Początkowo nie rozumiałem znaczenia uprawnień `rwx`.
* Nie byłem pewien, dlaczego użytkownik `adam` nie może otworzyć katalogu `tajne`.

# Rozwiązania

* Zapoznałem się z działaniem uprawnień dla właściciela, grupy oraz pozostałych użytkowników.
* Zrozumiałem, że `chmod 700` przyznaje pełny dostęp wyłącznie właścicielowi katalogu, a pozostali użytkownicy nie mają żadnych uprawnień.

# Wnioski

Projekt pozwolił mi zrozumieć sposób działania użytkowników oraz uprawnień w systemie Linux. Nauczyłem się tworzyć nowe konta, przełączać między użytkownikami oraz kontrolować dostęp do katalogów za pomocą polecenia `chmod`. Zdobyta wiedza będzie potrzebna podczas konfiguracji usług oraz zabezpieczania serwera w kolejnych projektach.

