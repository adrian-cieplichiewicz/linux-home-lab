## Projekt 08 – Automatyzacja zadań przy użyciu Cron

# Cel

Poznanie usługi "cron" oraz nauczenie się tworzenia zadań wykonywanych automatycznie o określonym czasie.

# Notatki

(Komendy w tym projekcie które wpisywałem w crontab zaczynają się tabem zamiast gwiazdki (*) aby dało się je odczytać poprawnie)

Na początku sprawdziłem, czy usługa "cron" działa poprawnie:

* sudo systemctl status cron

Następnie otworzyłem harmonogram zadań użytkownika:

* crontab -e

Zapoznałem się ze składnią wpisów w pliku "crontab" oraz dowiedziałem się, że każde zadanie składa się z pięciu pól określających czas wykonania oraz polecenia, które ma zostać uruchomione.

Dodałem zadanie wykonywane co minutę, które miało utworzyć plik tekstowy:

	* * * * * echo "Cron działa: $(date)" >> /home/vboxuser/cron-test.txt

Sprawdziłem, czy zadanie zostało poprawnie zapisane:

* crontab -l

Po odczekaniu około minuty sprawdziłem, czy plik został utworzony:

* cat /home/vboxuser/cron-test.txt

Plik nie działał, więc upewniłem się że został utworzony sprawdzając katalog w ścieżce /home/vboxuser poprzez:

* ls -l

Okazało się że plik nie został utworzony, zauważyłem że polecenie z $(date) nie może zostać zrealizowane i tymczasowo uprościłem komendę:

	* * * * * echo "Test" >> /home/vboxuser/cron-test.txt

Po potwierdzeniu poprawnego zapisu zadania i odczekaniu minuty, odczytałem plik który się utworzył:

* cat /home/vboxuser/cron-test.txt

Potwierdziłem, że usługa "cron" działa poprawnie i wykonuje zapisane zadania.

Spróbowałem ponownie użyć daty w poleceniu jednak w inny sposób aby spróbować je naprawić:

* crontab -e
	* * * * * /usr/bin/date >> /home/vboxuser/cron-test.txt

Udało mi się naprawić wcześniejszy błąd i polecenie zaczęło wysyłać datę do pliku co minutę.

Na końcu usunąłem zadanie z harmonogramu i sprawdziłem, czy zostało poprawnie usunięte:

* crontab -e
* crontab -l

# Problemy

* Początkowo próbowałem użyć polecenia z "$(date)", jednak zadanie nie tworzyło pliku.

# Rozwiązania

* Sprawdziłem, że usługa "cron" działa poprawnie, a następnie uprościłem polecenie do zwykłego "echo". Po zmianie zadanie wykonywało się prawidłowo i plik został utworzony. Później poprawiłem swój błąd i zmieniłem komendę przez co cron zaczął poprawnie wysyłać datę do pliku.

# Wnioski

Projekt pozwolił mi zrozumieć, czym jest usługa "cron" oraz jak tworzyć zadania wykonywane automatycznie o określonym czasie. Nauczyłem się edytować harmonogram użytkownika oraz sprawdzać zapisane zadania. 
