## Projekt 09 – Logi systemowe i diagnostyka przy użyciu journalctl

# Cel

Poznanie sposobu przechowywania logów w Ubuntu Server oraz nauczenie się sprawdzania informacji o działaniu usług i systemu za pomocą journalctl.

# Notatki

Zacząłem od wyświetlenia pierwszy raz logów serwera poprzez:

* journalctl

Po szybkim przeanalizowaniu kilku zdarzeń zamknąłem podgląd logów naciskając "q" i nauczyłem się sprawdzać logi poszczególnych usług:

* journalctl -u ssh

Później nauczyłem się, jak wyświetlać określoną ilość najnowszych wpisów oraz wszystkie wpisy od ostatniego uruchomienia systemu:

* journalctl -n 10
* journalctl -u ssh -n 10
* journalctl -b

Dowiedziałem się również, że można filtrować logi według poziomu ważności:

* journalctl -p err
* journalctl -p warning
* journalctl -p info

Nauczyłem się dodawać własne wpisy do logów za pomocą polecenia "logger":

* logger "Test"

Dowiedziałem się również, że można monitorować logi systemu na żywo poprzez użycie:

* journalctl -f

Włączyłem komendę na pierwszej konsoli, a następnie przełączyłem się do drugiej, aby wysłać wiadomość używając "logger":

* logger "Test na zywo"

Po szybkim powrocie na pierwszą konsolę zauważyłem, że wpis pojawił się w logach i potwierdziłem poprawne działanie monitorowania zdarzeń na żywo.

# Problemy

* Nie wiedziałem, jak wykonać kolejną komendę podczas działania "journalctl -f", ponieważ terminal był zajęty monitorowaniem logów.

# Rozwiązania

* Użyłem skrótu CTRL + ALT + F2, aby przełączyć się do drugiej konsoli systemu, gdzie wykonałem polecenie "logger". Następnie wróciłem do pierwszej konsoli i sprawdziłem pojawienie się nowego wpisu w logach.

# Wnioski

Projekt pozwolił mi zrozumieć, czym są logi systemowe oraz jak ważnym narzędziem pracy administratora Linux jest "journalctl". Nauczyłem się sprawdzać logi usług, filtrować informacje według poziomu ważności, dodawać własne wpisy oraz monitorować zdarzenia systemowe na żywo.
