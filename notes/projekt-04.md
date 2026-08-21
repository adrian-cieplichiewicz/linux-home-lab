## Projekt 04 - Podstawowa konfiguracja firewalla

# Cel

Poznanie podstaw ochrony serwera Linux poprzez konfigurację firewalla. Nauczę się sprawdzać aktualny stan zapory sieciowej, dodawać reguły oraz kontrolować dostęp do usług.

# Notatki

Zacząłem od sprawdzenia statusu usługi firewalla (ufw):

* sudo ufw status

Przed włączeniem ufw dodałem regułę aby pozwalało na SSH:

* sudo ufw allow ssh

Aktywowałem ufw i sprawdziłem jego reguły:

* sudo ufw enable
* sudo ufw status verbose

Dodałem testową regułę, sprawdziłem czy się dodała oraz usunąłem ją wraz z jej wersją v6:

* sudo ufw allow 80/tcp
* sudo ufw status
* sudo ufw status numbered
* sudo ufw delete 2
* sudo ufw delete 3

# Problemy

* Nie wiedziałem początkowo, dlaczego po dodaniu reguły SSH pojawiają się również wpisy dla IPv6.
* Nie byłem pewien, czy usunięcie reguły dla portu 80 wymaga usunięcia tylko jednej pozycji, czy również jej wersji IPv6.

# Rozwiązania

* Dowiedziałem się że firewall obsługuje zarówno IPv4 jak i IPv6, dlatego przy dodawaniu reguł pojawiają się dwie pozycje.
* Sprawdziłem listę reguł za pomocą "sudo ufw status numbered" i usunąłem odpowiednie reguły odpowiednimi numerami reguł.

# Wnioski

Nauczyłem się czym jest ufw i co oznacza skrót (uncomplicated firewall). Zrozumiałem że firewall kontroluje dostęp do usług poprzez użycie reguł oraz portów. Zrozumiałem jak edytować jego reguły i aktywować lub dezaktywować go.
