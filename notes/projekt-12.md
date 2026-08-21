## Projekt 12 – Monitorowanie procesów i zarządzanie nimi

# Cel

Poznanie sposobów monitorowania uruchomionych procesów oraz nauczenie się ich wyszukiwania i kończenia przy użyciu podstawowych poleceń systemu Linux.

# Notatki

Na początku wyświetliłem wszystkie aktualnie uruchomione procesy:

* ps aux

Dowiedziałem się, że polecenie "ps" służy do wyświetlania procesów, a opcje "aux" pozwalają zobaczyć procesy wszystkich użytkowników wraz z dodatkowymi informacjami.

Następnie uruchomiłem monitor procesów działający na żywo:

* top

Przeanalizowałem wykorzystanie procesora, pamięci RAM, liczbę uruchomionych procesów oraz czas działania systemu. Po zakończeniu zamknąłem program naciskając "q".

Ponownie zainstalowałem program "htop", aby porównać go z poleceniem "top":

* sudo apt install htop
* htop

Zapoznałem się z wyglądem programu oraz sposobem wyświetlania informacji o procesach. Program zamknąłem przy użyciu klawisza "F10".

Następnie wyszukałem proces usługi SSH:

* ps aux | grep ssh

Dowiedziałem się, że znak "|" przekazuje wynik jednego polecenia do następnego, dzięki czemu "grep" może wyszukać interesujący mnie tekst.

Uruchomiłem proces testowy:

* sleep 60

Przełączyłem się do drugiej konsoli systemu i odnalazłem jego numer PID:

* ps aux | grep sleep

Następnie zakończyłem proces przy użyciu jego numeru PID:

* kill PID

Na końcu ponownie wyszukałem proces, aby potwierdzić, że został poprawnie zakończony:

* ps aux | grep sleep

Zapoznałem się również z poleceniem:

* kill -9 PID

Dowiedziałem się, że służy ono do wymuszenia natychmiastowego zakończenia procesu, gdy zwykłe polecenie "kill" nie działa.

# Problemy

Nie napotkałem żadnych problemów w projekcie.

# Rozwiązania

Nie potrzebowałem rozwiązać żadnych problemów w projekcie.

# Wnioski

Dowiedziałem się, czym jest proces oraz numer PID. Nauczyłem się monitorować uruchomione procesy, wyszukiwać je, sprawdzać wykorzystanie zasobów systemu oraz bezpiecznie kończyć działające procesy.

