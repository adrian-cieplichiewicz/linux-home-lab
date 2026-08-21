## Projekt 18 – Podstawy skryptów Bash

# Cel

Nauczenie się tworzenia prostych skryptów Bash, uruchamiania ich oraz wykonywania w nich kilku poleceń po kolei.

# Notatki

Na początku utworzyłem katalog projektu i przeszedłem do niego:

* cd /home/vboxuser/projekty
* mkdir projekt18
* cd projekt18

Następnie utworzyłem plik skryptu:

* nano skrypt.sh

Na początku skryptu dodałem:

#!/bin/bash

Dowiedziałem się, że jest to informacja dla systemu, że skrypt powinien zostać wykonany przy użyciu Bash.

W skrypcie wykorzystałem polecenia "echo", "whoami", "pwd" oraz "df -h", dodając własne komunikaty opisujące wyświetlane informacje.

Sprawdziłem uprawnienia skryptu:

* ls -l skrypt.sh

Następnie nadałem mu prawo wykonywania:

* chmod +x skrypt.sh

Ponownie sprawdziłem uprawnienia:

* ls -l skrypt.sh

Po dodaniu prawa wykonywania uruchomiłem skrypt:

* ./skrypt.sh

Skrypt wyświetlił informacje o aktualnie zalogowanym użytkowniku, aktualnym katalogu oraz ilości dostępnego miejsca na dysku.

Sprawdziłem również możliwość uruchomienia skryptu bez nadawania mu prawa wykonywania poprzez bezpośrednie przekazanie go do Bash:

* bash skrypt.sh

# Problemy

Początkowo skrypt nie uruchamiał się przez "./skrypt.sh", ponieważ nie posiadał prawa wykonywania.

# Rozwiązania

Sprawdziłem uprawnienia pliku za pomocą "ls -l" i nadałem skryptowi prawo wykonywania poleceniem "chmod +x skrypt.sh".

# Wnioski

Dowiedziałem się, jak stworzyć prosty skrypt Bash i uruchamiać w nim kilka poleceń po kolei. Zrozumiałem również znaczenie "#!/bin/bash" oraz dowiedziałem się, że skrypt musi mieć prawo wykonywania, aby można było uruchomić go bezpośrednio przez "./skrypt.sh".