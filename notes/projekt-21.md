## Projekt 21 - Git od podstaw

# Cel

Poznanie podstaw działania systemu kontroli wersji Git oraz nauczenie się tworzenia lokalnego repozytorium, śledzenia zmian w plikach i zapisywania kolejnych wersji projektu poprzez commity.

# Notatki

Na początku sprawdziłem czy Git jest zainstalowany:

* git --version

Następnie utworzyłem katalog projektu i wszedłem do niego:

* cd /home/vboxuser/projekty
* mkdir projekt21
* cd projekt21
* pwd

Utworzyłem swoje pierwsze lokalne repozytorium Git poprzez:

* git init

Sprawdziłem zawartość katalogu razem z ukrytymi plikami:

* ls -la

Dowiedziałem się, że Git tworzy ukryty katalog ".git", w którym przechowuje informacje o repozytorium oraz jego historii.

Sprawdziłem aktualny stan repozytorium:

* git status

Następnie utworzyłem plik README.md:

* nano README.md

Po zapisaniu pliku ponownie użyłem:

* git status

Git pokazał, że README.md jest plikiem nieśledzonym.

Dodałem plik do staging area poprzez:

* git add README.md

Następnie ponownie sprawdziłem:

* git status

Dowiedziałem się, że "git add" przygotowuje wybrane zmiany do zapisania w następnym commicie, ale sam jeszcze nie zapisuje ich w historii.

Skonfigurowałem nazwę użytkownika i adres e-mail używany przez Git:

* git config --global user.name "Moja nazwa"
* git config --global user.email "mój@email"

Sprawdziłem ustawienia poprzez:

* git config --list

Następnie utworzyłem swój pierwszy commit:

* git commit -m "Dodano README"

Sprawdziłem historię commitów poprzez:

* git log

Edytowałem ponownie plik README.md:

* nano README.md

Po zmianie zawartości sprawdziłem stan repozytorium:

* git status

Następnie sprawdziłem dokładne różnice między poprzednią a obecną wersją pliku:

* git diff

Dowiedziałem się, że "git diff" pokazuje zmiany wykonane w plikach przed zapisaniem ich w kolejnym commicie.

Dodałem zmiany do staging area i utworzyłem kolejny commit:

* git add README.md
* git status
* git commit -m "Rozszerzono opis projektu"

Sprawdziłem krótszą wersję historii commitów:

* git log --oneline

Historia była jeszcze krótka, ponieważ dopiero zacząłem używać repozytorium Git.

Utworzyłem również drugi plik:

* nano test.txt

Następnie użyłem:

* git status
* git add .

Dowiedziałem się, że "git add ." dodaje zmiany z bieżącego katalogu do staging area.

Utworzyłem kolejny commit:

* git commit -m "Dodano plik testowy"

Podczas robienia screenów wykonywałem małe zmiany w plikach, np. usuwałem kropkę na końcu zdania, żeby Git ponownie wykrył zmianę i żebym mógł pokazać odpowiedni wynik na screenie.

# Problemy

Nie napotkałem żadnych problemów w projekcie.

# Rozwiązania

Nie potrzebowałem rozwiązać żadnych problemów w projekcie.

# Wnioski

Dowiedziałem się czym jest Git oraz jak tworzyć lokalne repozytorium i zapisywać kolejne wersje projektu.

Nauczyłem się używać podstawowych komend takich jak "git init", "git status", "git add", "git commit", "git diff" oraz "git log".

Zrozumiałem również podstawowy sposób pracy z Gitem:

zmiana pliku -> git status -> git diff -> git add -> git commit -> git log