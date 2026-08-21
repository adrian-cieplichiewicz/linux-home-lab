## Projekt 17 – Zarządzanie użytkownikami, grupami i uprawnieniami

# Cel

Poznanie zaawansowanego zarządzania użytkownikami w Linuxie poprzez tworzenie grup, dodawanie użytkowników do grup oraz kontrolowanie dostępu do plików.

# Notatki

Na początku sprawdziłem dostępne grupy użytkowników w systemie:

* cat /etc/group

Dowiedziałem się, że Linux przechowuje informacje o grupach użytkowników w pliku "/etc/group". Każdy użytkownik posiada również własną grupę o takiej samej nazwie, co pozwala na łatwiejsze zarządzanie dostępem do jego plików.

Następnie utworzyłem własną grupę:

* sudo groupadd administratorzy

Sprawdziłem, czy grupa została poprawnie utworzona:

* grep administratorzy /etc/group

Dodałem użytkownika do utworzonej grupy:

* sudo usermod -aG administratorzy adam

Dowiedziałem się, że opcja "-aG" oznacza dodanie użytkownika do dodatkowej grupy bez usuwania jego wcześniejszych grup.

Sprawdziłem przynależność użytkownika do grup:

* groups adam

Następnie stworzyłem katalog projektu oraz plik testowy:

* mkdir projekt17
* echo "Dostęp grupowy" > plik.txt

Sprawdziłem obecne uprawnienia pliku:

* ls -l

Zmieniłem grupę przypisaną do pliku:

* sudo chgrp administratorzy plik.txt

Ponownie sprawdziłem uprawnienia:

* ls -l

Nadałem właścicielowi oraz grupie pełne uprawnienia, blokując dostęp innym użytkownikom:

* chmod 770 plik.txt

Poznałem różnicę między "chmod 700" oraz "chmod 770":

* chmod 700 pozwala na pełny dostęp tylko właścicielowi pliku.
* chmod 770 pozwala na pełny dostęp właścicielowi oraz użytkownikom należącym do przypisanej grupy.

Na końcu sprawdziłem działanie uprawnień dla użytkownika należącego do grupy.

Dodatkowo sprawdziłem znaczenie pliku "/etc/shadow":

* sudo cat /etc/shadow

Dowiedziałem się, że przechowuje on zabezpieczone informacje dotyczące haseł użytkowników (hashe haseł), a dostęp do niego posiada tylko administrator systemu.

# Problemy

Nie napotkałem większych problemów podczas wykonywania projektu.

# Rozwiązania

Nie potrzebowałem wykonywać dodatkowych działań naprawczych.

# Wnioski

Projekt pozwolił mi lepiej zrozumieć sposób zarządzania dostępem w Linuxie. Nauczyłem się tworzyć grupy, dodawać użytkowników do grup oraz kontrolować dostęp do plików poprzez uprawnienia. Zrozumiałem również znaczenie pliku "/etc/shadow" oraz różnicę między prywatnymi uprawnieniami użytkownika a dostępem grupowym.
