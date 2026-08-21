## Projekt 03 - Podstawy konfiguracji SSH

# Cel

Nauczenie się zdalnego zarządzania serwerem Linux poprzez SSH oraz poznanie podstawowej konfiguracji usługi SSH.

# Notatki

Zacząłem od sprawdzenia statusu usługi SSH:

* sudo systemctl status ssh

Okazało się, że SSH nie było zainstalowane, dlatego zainstalowałem usługę:

* sudo apt install ssh

Po instalacji ponownie sprawdziłem status usługi:

* sudo systemctl status ssh

Następnie sprawdziłem adres IP serwera przy użyciu:

* ip a

Adres był przydzielony przez VirtualBox w trybie NAT.

Przetestowałem połączenie SSH lokalnie poprzez:

* ssh vboxuser@localhost

Po udanym połączeniu sprawdziłem aktualnego użytkownika:

* whoami

Po sprawdzeniu że usługa działa wyłączyłem połączenie lokalne:

* exit

Następnie nauczyłem się zarządzania usługami systemowymi poprzez:

* sudo systemctl stop ssh
* sudo systemctl start ssh
* sudo systemctl enable ssh

Sprawdziłem również, czy SSH będzie uruchamiało się automatycznie po starcie systemu:

* systemctl is-enabled ssh

# Problemy

Brak zainstalowanej usługi SSH na serwerze linux.

# Rozwiązania

Zainstalowałem daną usługę przy użyciu "sudo apt install ssh".

# Wnioski

Projekt pozwolił mi się nauczyć użytkowania usługą SSH oraz zarządzania usługami w linux. Nauczyłem się instalować brakujące elementy, sprawdzać adres i dane usług oraz kontrolować ich działanie poprzez systemctl.