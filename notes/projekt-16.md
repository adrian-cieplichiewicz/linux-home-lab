## Projekt 16 – Dowiązania symboliczne i twarde

# Cel

Poznanie różnic pomiędzy dowiązaniami symbolicznymi i twardymi oraz nauczenie się ich tworzenia i wykorzystywania.

# Notatki

Utworzyłem plik testowy oraz dowiązanie symboliczne do niego:

* echo "Linux jest super." > oryginal.txt
* ln -s oryginal.txt symlink.txt

Sprawdziłem zawartość obu plików oraz potwierdziłem, że symlink wskazuje na plik oryginalny:

* cat oryginal.txt
* cat symlink.txt
* ls -l

Następnie usunąłem oryginalny plik i sprawdziłem działanie symlinka:

* rm oryginal.txt
* cat symlink.txt

Dowiedziałem się, że dowiązanie symboliczne przechowuje ścieżkę do pliku, dlatego po usunięciu oryginału przestaje działać.

Ponownie utworzyłem plik, a następnie stworzyłem dowiązanie twarde:

* echo "Nowy plik." > oryginal.txt
* ln oryginal.txt hardlink.txt

Porównałem numery inode obu plików:

* ls -li

Na końcu usunąłem plik oryginalny i sprawdziłem, że hard link nadal działa:

* rm oryginal.txt
* cat hardlink.txt

# Problemy

Nie napotkałem żadnych problemów w projekcie.

# Rozwiązania

Nie potrzebowałem rozwiązać żadnych problemów w projekcie.

# Wnioski

Dowiedziałem się, czym różni się dowiązanie symboliczne od twardego. Zrozumiałem, że symlink wskazuje na ścieżkę do pliku, natomiast hard link odwołuje się bezpośrednio do danych zapisanych na dysku.
