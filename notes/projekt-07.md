## Projekt 07 – Statyczny adres IP w Ubuntu Server (Netplan)

# Cel

Poznanie różnicy pomiędzy automatycznym przydzielaniem adresu IP przez DHCP a ręczną konfiguracją statycznego adresu IP. Zapoznanie się ze sposobem edytowania konfiguracji sieci w Ubuntu Server przy użyciu Netplan.

# Notatki

Na początku sprawdziłem aktualną konfigurację sieci, aby poznać nazwę interfejsu sieciowego, adres IP oraz trasę domyślną:

* ip a
* ip route

Następnie utworzyłem kopię zapasową pliku konfiguracji sieci przed rozpoczęciem zmian:

* sudo cp /etc/netplan/00-installer-config.yaml /etc/netplan/00-installer-config.backup.yaml

Sprawdziłem, czy kopia zapasowa została utworzona:

* ls /etc/netplan

Następnie otworzyłem plik konfiguracji Netplan:

* sudo nano /etc/netplan/00-installer-config.yaml

Zapoznałem się ze strukturą pliku oraz sposobem zapisywania ustawień sieciowych w formacie YAML.

Dowiedziałem się, że w konfiguracji Netplan można ustawić sposób uzyskiwania adresu IP, adresy statyczne, bramę domyślną oraz serwery DNS.

Przetestowałem działanie konfiguracji sieci przy użyciu:

* sudo netplan try

Po sprawdzeniu konfiguracji zastosowałem ustawienia:

* sudo netplan apply

Następnie ponownie sprawdziłem konfigurację sieci:

* ip a
* ip route

Sprawdziłem również połączenie z internetem:

* ping 8.8.8.8

oraz działanie DNS:

* ping google.com

# Problemy

* Początkowo nie wiedziałem dokładnie, jak działa konfiguracja sieci w pliku Netplan oraz za co odpowiadają poszczególne elementy konfiguracji.

# Rozwiązania

* Przeanalizowałem strukturę pliku "00-installer-config.yaml" i zrozumiałem, że Netplan odpowiada za konfigurację ustawień sieciowych systemu.
* Dowiedziałem się, że adres IP identyfikuje urządzenie w sieci, brama domyślna pozwala komunikować się z innymi sieciami, a DNS tłumaczy nazwy domen na adresy IP.

# Wnioski

Projekt pozwolił mi lepiej zrozumieć sposób konfiguracji sieci w Ubuntu Server. Nauczyłem się sprawdzać aktualne ustawienia sieci, pracować z plikami Netplan oraz zrozumiałem podstawowe elementy potrzebne do działania połączenia sieciowego.

