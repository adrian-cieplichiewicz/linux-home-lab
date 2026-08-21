## Projekt 23 - Logowanie SSH kluczem i zabezpieczenie serwera

# Cel

Nauczenie się logowania do serwera poprzez klucz SSH oraz poznanie podstaw bezpieczniejszej konfiguracji usługi SSH.

# Notatki

Na początku przełączyłem się na użytkownika adam:

* su - adam
* whoami

Następnie sprawdziłem zwykłe logowanie SSH na konto vboxuser:

* ssh vboxuser@localhost

Po upewnieniu się, że połączenie działa, wygenerowałem parę kluczy SSH dla użytkownika adam:

* ssh-keygen -t ed25519

Klucze zostały zapisane w katalogu ".ssh" użytkownika adam.

Sprawdziłem utworzone pliki poprzez:

* ls -la ~/.ssh

Dowiedziałem się, że:

* id_ed25519 jest kluczem prywatnym
* id_ed25519.pub jest kluczem publicznym

Następnie skopiowałem klucz publiczny użytkownika adam na konto vboxuser poprzez:

* ssh-copy-id vboxuser@localhost

Dowiedziałem się, że klucz publiczny trafia do pliku "authorized_keys" na koncie użytkownika, do którego chcemy uzyskać dostęp.

Przetestowałem logowanie poprzez klucz:

* ssh vboxuser@localhost
* whoami

Logowanie zadziałało bez wpisywania hasła użytkownika vboxuser.

Następnie sprawdziłem plik zawierający dozwolone klucze publiczne:

* cat ~/.ssh/authorized_keys

Sprawdziłem uprawnienia katalogu ".ssh" i pliku "authorized_keys":

* ls -ld ~/.ssh
* ls -l ~/.ssh/authorized_keys

Ustawiłem odpowiednie uprawnienia:

* chmod 700 ~/.ssh
* chmod 600 ~/.ssh/authorized_keys

Następnie sprawdziłem aktywną konfigurację serwera SSH:

* sudo sshd -T | grep -E 'permitrootlogin|passwordauthentication|pubkeyauthentication|maxauthtries'

Otworzyłem główny plik konfiguracji SSH:

* sudo nano /etc/ssh/sshd_config

Przed wprowadzeniem zmian utworzyłem kopię zapasową pliku:

* sudo cp /etc/ssh/sshd_config /etc/ssh/sshd_config.backup

W konfiguracji SSH ustawiłem:

* PermitRootLogin no
* MaxAuthTries 3

Dowiedziałem się, że "PermitRootLogin no" blokuje bezpośrednie logowanie na konto root przez SSH.

"MaxAuthTries 3" ogranicza liczbę prób uwierzytelnienia w jednym połączeniu.

Przed zastosowaniem zmian sprawdziłem poprawność konfiguracji poprzez:

* sudo sshd -t

Komenda nie zwróciła żadnych błędów.

Następnie przeładowałem konfigurację SSH:

* sudo systemctl reload ssh

Sprawdziłem stan usługi:

* sudo systemctl status ssh

Po zmianach ponownie przetestowałem logowanie kluczem:

* ssh vboxuser@localhost
* whoami

Logowanie nadal działało poprawnie.

Na końcu sprawdziłem logi usługi SSH:

* sudo journalctl -u ssh -n 20

# Problemy

Nie napotkałem żadnych problemów w projekcie.

# Rozwiązania

Nie potrzebowałem rozwiązać żadnych problemów w projekcie.

# Wnioski

Dowiedziałem się jak działa logowanie poprzez klucz SSH i jaka jest różnica między kluczem prywatnym a publicznym.

Nauczyłem się używać "ssh-keygen", "ssh-copy-id" oraz pliku "authorized_keys".

Dowiedziałem się również jak sprawdzać i bezpiecznie zmieniać konfigurację serwera SSH poprzez "sshd_config".

Nauczyłem się sprawdzać poprawność konfiguracji przed jej zastosowaniem poprzez "sshd -t".

Zrozumiałem również dlaczego warto blokować bezpośrednie logowanie na konto root oraz ograniczać liczbę prób uwierzytelnienia.