## Projekt 06 – Konfiguracja sieci w Ubuntu Server (Netplan)

# Cel

Poznanie sposobu konfiguracji sieci w Ubuntu Server przy użyciu Netplan oraz zrozumienie podstawowych elementów konfiguracji sieci.

# Notatki

Na początku sprawdziłem, jakie pliki konfiguracyjne sieci znajdują się w katalogu Netplan:

* ls /etc/netplan

Znalazłem plik:

* "00-installer-config.yaml"

Następnie wyświetliłem jego zawartość:

* cat /etc/netplan/00-installer-config.yaml

Dowiedziałem się, że plik ten zawiera konfigurację interfejsu sieciowego oraz ustawienia połączenia z siecią.

Sprawdziłem dostępne interfejsy sieciowe:

* ip link

Następnie wyświetliłem aktualnie przypisany adres IP:

* ip a

Sprawdziłem trasę domyślną systemu:

* ip route

Dowiedziałem się, że trasa domyślna określa, gdzie system wysyła pakiety przeznaczone do innych sieci, np. do Internetu.

Na końcu sprawdziłem konfigurację serwerów DNS:

* resolvectl status

Dowiedziałem się, że serwery DNS odpowiadają za tłumaczenie nazw domen, takich jak "google.com", na adresy IP, z którymi komputer może się połączyć.

Otworzyłem również plik konfiguracyjny w edytorze Nano i zapoznałem się z jego strukturą:

* sudo nano /etc/netplan/00-installer-config.yaml

# Problemy

Nie napotkałem problemów podczas wykonywania projektu.

# Rozwiązania

Projekt przebiegł bez problemów.

# Wnioski

Projekt pozwolił mi lepiej zrozumieć, w jaki sposób Ubuntu Server uzyskuje połączenie z siecią. Dowiedziałem się, gdzie znajduje się konfiguracja sieci, jak sprawdzić interfejsy sieciowe, adres IP, trasę domyślną oraz serwery DNS. Zrozumiałem również, jaką rolę pełni Netplan w konfiguracji sieci.

