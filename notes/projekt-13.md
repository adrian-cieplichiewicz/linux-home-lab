## Projekt 13 – Archiwizacja i kompresja plików

# Cel

Poznanie sposobów tworzenia archiwów oraz kompresowania i rozpakowywania plików przy użyciu poleceń "tar" i "gzip".

# Notatki

Na początku utworzyłem katalog roboczy oraz kilka plików tekstowych, które posłużyły do nauki archiwizacji:

* cd /home/vboxuser
* mkdir projekt13
* cd projekt13
* echo "Pierwszy plik." > plik1.txt
* echo "Drugi plik." > plik2.txt
* echo "Trzeci plik." > plik3.txt

Sprawdziłem zawartość katalogu:

* ls -l

Następnie utworzyłem archiwum zawierające wszystkie pliki tekstowe:

* tar -cvf archiwum.tar *.txt

Dowiedziałem się, że opcja "c" tworzy archiwum, "v" wyświetla wykonywane operacje, a "f" pozwala podać nazwę pliku archiwum.

Sprawdziłem, czy archiwum zostało poprawnie utworzone:

* ls -lh

Nauczyłem się również wyświetlać zawartość archiwum bez jego rozpakowywania:

* tar -tf archiwum.tar

Następnie skompresowałem archiwum:

* gzip archiwum.tar

Po kompresji ponownie sprawdziłem zawartość katalogu i zauważyłem, że archiwum otrzymało rozszerzenie ".tar.gz":

* ls -lh

Rozpakowałem archiwum, tworząc wcześniej katalog docelowy:

* gunzip archiwum.tar.gz
* mkdir odzyskane
* tar -xvf archiwum.tar -C odzyskane

Na końcu sprawdziłem, czy wszystkie pliki zostały poprawnie odzyskane:

* ls odzyskane

Porównałem również rozmiary plików oraz archiwum przed i po kompresji, aby zobaczyć wpływ kompresji na zajmowane miejsce.

# Problemy

Nie napotkałem żadnych problemów w projekcie.

# Rozwiązania

Nie potrzebowałem rozwiązać żadnych problemów w projekcie.

# Wnioski

Dowiedziałem się, czym różni się archiwizacja od kompresji. Nauczyłem się tworzyć archiwa, kompresować je, sprawdzać ich zawartość bez rozpakowywania oraz odzyskiwać zapisane w nich pliki.
