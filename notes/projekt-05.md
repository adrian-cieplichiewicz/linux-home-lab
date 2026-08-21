## Projekt 05 – Zarządzanie pakietami APT

# Cel

Poznanie systemu zarządzania pakietami APT w Ubuntu (instalowanie, usuwanie, aktualizowanie oraz wyszukiwanie oprogramowania).

# Notatki

Rozpocząłem projekt od sprawdzenia informacji systemowych oraz wersji APT, aby upewnić się, że system działa poprawnie:

* apt --version
* lsb_release -a

Następnie odświeżyłem listę dostępnych pakietów oraz zaktualizowałem zainstalowane programy:

* sudo apt update
* sudo apt upgrade -y

Pierwszy raz spróbowałem wyszukać pakiet, używając:

* apt search htop

Po czym zainstalowałem go i uruchomiłem:

* sudo apt install htop
* htop

Po uruchomieniu programu zapoznałem się z jego działaniem. Dowiedziałem się, że pozwala monitorować procesy oraz zasoby systemu w czasie rzeczywistym. Użyłem klawisza F1, aby wyświetlić pomoc programu, a następnie zamknąłem go przy pomocy F10.

Sprawdziłem, czy pakiet został poprawnie zainstalowany:

* apt list --installed | grep htop

Następnie usunąłem program, upewniłem się, że został odinstalowany, oraz wyczyściłem niepotrzebne pakiety:

* sudo apt remove htop
* htop
* sudo apt autoremove

Poznałem również program dpkg, który odpowiada za instalację pakietów .deb i jest wykorzystywany przez APT:

* dpkg --version
* dpkg

# Problemy

* Początkowo nie rozumiałem, jak wygląda proces instalacji pakietów oraz jaka jest różnica między APT i dpkg.

# Rozwiązania

* Zrozumiałem, że APT jest menedżerem pakietów korzystającym z repozytoriów Ubuntu i odpowiada za pobieranie oraz zarządzanie oprogramowaniem.
* Dowiedziałem się, że właściwą instalację pakietów wykonuje program dpkg, z którego korzysta APT.

# Wnioski

Projekt pozwolił mi zrozumieć sposób instalowania oprogramowania w systemach Linux opartych na Debianie. Poznałem działanie repozytoriów, nauczyłem się wyszukiwać, instalować, aktualizować i usuwać pakiety oraz zrozumiałem rolę APT i dpkg. Zdobyta wiedza będzie niezbędna podczas instalowania kolejnych usług i narzędzi administracyjnych.

