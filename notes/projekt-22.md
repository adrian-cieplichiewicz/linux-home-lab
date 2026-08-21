## Projekt 22 - Pierwsze repozytorium na GitHubie

# Cel

Połączenie lokalnego repozytorium Git z GitHubem oraz nauczenie się wysyłania zmian do zdalnego repozytorium.

# Notatki

Na początku utworzyłem publiczne repozytorium na GitHubie o nazwie:

* linux-home-lab

Następnie przeszedłem do lokalnego repozytorium Git:

* cd /home/vboxuser/projekty/projekt21

Sprawdziłem aktualny stan repozytorium:

* git status

Sprawdziłem nazwę aktualnej gałęzi:

* git branch

Następnie dodałem zdalne repozytorium GitHub jako "origin":

* git remote add origin https://github.com/LOGIN/linux-home-lab.git

Sprawdziłem poprawność połączenia poprzez:

* git remote -v

Dowiedziałem się, że "origin" jest standardową nazwą głównego zdalnego repozytorium.

Przy pierwszej próbie wysłania zmian użyłem:

* git push -u origin main

GitHub poprosił mnie o nazwę użytkownika i hasło.

Dowiedziałem się, że zwykłe hasło do konta GitHub nie działa przy operacjach Git przez HTTPS i zamiast niego potrzebny jest token lub inna metoda uwierzytelnienia.

Po poprawnym uwierzytelnieniu push został odrzucony komunikatem "fetch first", ponieważ zdalne repozytorium zawierało już zmiany, których nie miałem lokalnie.

Próbując połączyć lokalną i zdalną historię, napotkałem konflikt w pliku.

Sprawdziłem stan repozytorium poprzez:

* git status

Otworzyłem plik z konfliktem, usunąłem znaczniki konfliktu i pozostawiłem odpowiednią treść.

Następnie oznaczyłem konflikt jako rozwiązany poprzez:

* git add README.md

Dokończyłem merge i ponownie wykonałem:

* git push -u origin main

Tym razem zmiany zostały poprawnie wysłane na GitHuba.

Następnie skonfigurowałem logowanie do GitHuba poprzez klucz SSH, aby nie wpisywać tokenu przy każdym pushu.

Wygenerowałem klucz SSH:

* ssh-keygen -t ed25519 -C "mój_email"

Klucz został zapisany w domyślnej lokalizacji:

* /home/vboxuser/.ssh/id_ed25519
* /home/vboxuser/.ssh/id_ed25519.pub

Dowiedziałem się, że:

* id_ed25519 jest kluczem prywatnym i nie powinien być nikomu udostępniany
* id_ed25519.pub jest kluczem publicznym i można dodać go do GitHuba

Wyświetliłem klucz publiczny poprzez:

* cat ~/.ssh/id_ed25519.pub

Dodałem klucz publiczny na GitHubie w ustawieniach SSH.

Następnie przetestowałem połączenie:

* ssh -T git@github.com

GitHub poprawnie rozpoznał mój klucz i uwierzytelnienie zadziałało.

Zmieniłem adres zdalnego repozytorium z HTTPS na SSH poprzez:

* git remote set-url origin git@github.com:LOGIN/linux-home-lab.git

Sprawdziłem nowy adres poprzez:

* git remote -v

Przy pierwszym pushu przez SSH Git poinformował mnie, że lokalna gałąź "main" nie ma ustawionego upstream.

Ustawiłem go poprzez:

* git push --set-upstream origin main

Po tym zwykła komenda:

* git push

działała już poprawnie bez pytania o nazwę użytkownika i token.

# Problemy

* Przy pierwszym pushu GitHub nie akceptował zwykłego hasła do konta.
* Push został odrzucony komunikatem "fetch first", ponieważ zdalne repozytorium posiadało własne zmiany.
* Podczas łączenia lokalnej i zdalnej historii pojawił się konflikt w pliku.
* Po przejściu na SSH lokalna gałąź "main" nie miała ustawionego upstream.

# Rozwiązania

* Dowiedziałem się, że do operacji Git przez HTTPS potrzebny jest token zamiast zwykłego hasła.
* Połączyłem lokalną i zdalną historię repozytorium oraz ręcznie rozwiązałem konflikt w pliku.
* Skonfigurowałem klucz SSH typu ed25519 i dodałem klucz publiczny do GitHuba.
* Zmieniłem zdalny adres repozytorium z HTTPS na SSH.
* Ustawiłem upstream dla gałęzi "main" poprzez:
git push --set-upstream origin main

# Wnioski

Dowiedziałem się czym różni się Git od GitHuba oraz jak połączyć lokalne repozytorium ze zdalnym repozytorium na GitHubie.

Nauczyłem się używać komend "git remote", "git push" oraz rozwiązywać podstawowy konflikt podczas łączenia dwóch historii Git.

Dowiedziałem się również jak działa uwierzytelnienie poprzez klucze SSH i dlaczego klucz prywatny musi pozostać tajny, a publiczny może zostać dodany do GitHuba.

Po skonfigurowaniu SSH mogę wykonywać "git push" bez ciągłego wpisywania tokenu.