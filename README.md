# SDA_PROJEKT2
## Zadanie 1 - Łamanie haseł (met. brute-force)

### 1/3 Dla podanych niżej hashy określ typ wykorzystanego algorytmu hashującego, a następnie złam hasło metodą brute-force.
    Każde hasło składa się z maksymalnie 5 znaków (tylko cyfry).
    1. 81dc9bdb52d04dc20036dbd8313ed055
    2. d8826bbd80b4233b7522d1c538aeaf66c64e259a
    3. b021d0862bc76b0995927902ec697d97b5080341a53cd90b780f50fd5886f4160bbb9d4a573b76c23004c9b3a44ac95cfde45399e3357d1f651b556dfbd0d58f
    4. 31bca02094eb78126a517b206a88c73cfa9ec6f704c7030d18212cace820f025f00bf0ea68dbf3f3a5436ca63b53bf7bf80ad8d5de7d8359d0b7fed9dbc3ab99

 ### 2/3 Dla podanych niżej hashy określ typ wykorzystanego algorytmu hashującego, a następnie złam hasło metodą brute-force.
     Każde hasło składa się z maksymalnie 5 znaków (małe i wielkie litery).
    1. 9e66d646cfb6c84d06a42ee1975ffaae90352bd016da18f51721e2042d9067dcb120accc574105b43139b6c9c887dda8202eff20cc4b98bad7b3be1e471b3aa5
    2. 8a04bd2d079ee38f1af784317c4e2442625518780ccff3213feb2e207d2be42ca0760fd8476184a004b71bcb5841db5cd0a546b9b8870f1cafee57991077c4a9

### 3/3 Dla podanego niżej hasha określ typ wykorzystanego algorytmu hashującego, a następnie złam hasło metodą brute-force.

     44d9886c0a57ddbfdb31aa936bd498bf2ab70f741ee47047851e768db953fc4e43f92be953e205a3d1b3ab752ed90379444b651b582b0bc209a739a624e109da

![:(](/screenshots/1_3.png)
Określenie typu hash'y za pomocą aplikacji "hash-identifier" (prawa strona zdjęcia).

Następnie łamanie hasha za pomoca aplikacji "hashcat" (lewa strona zdjęcia).


## Zadanie 2 - Łamanie haseł (met. słownikowa)

### 1/2 Dla podanych niżej hashy określ typ wykorzystanego algorytmu hashującego, a następnie złam hasło metodą słownikową.
    Hasła pochodzą ze słownika rockyou.
    1. 9fd8301ac24fb88e65d9d7cd1dd1b1ec
    2. 7f9a6871b86f40c330132c4fc42cda59
    3. 6104df369888589d6dbea304b59a32d4
    4. 276f8db0b86edaa7fc805516c852c889
    5. 04dac8afe0ca501587bad66f6b5ce5ad

### 2/2 Dla podanych niżej hashy określ typ wykorzystanego algorytmu hashującego, a następnie złam hasło metodą słownikową.
    Hasła pochodzą ze słownika rockyou.
    1. 7ab6888935567386376037e042524d27fc8a24ef87b1944449f6a0179991dbdbc481e98db4e70f6df0e04d1a69d8e7101d881379cf1966c992100389da7f3e9a
    2. 470c62e301c771f12d91a242efbd41c5e467cba7419c664f784dbc8a20820abaf6ed43e09b0cda994824f14425db3e6d525a7aafa5d093a6a5f6bf7e3ec25dfa

Podobnie jak w zadaniu 1 określam typy hash'ów aplikacją "hash-identifier" a następnie zapisuję je do pliku i zamałem hash'e za pomocą aplikacji "hashcat".
![:(](/screenshots/1_2_3.png)
![:(](/screenshots/2_1_2.png)
![:(](/screenshots/2_1_3.png)

## Zadanie 3 - Analiza ruchu HTTP

    1. Rozpocznij monitorowanie ruchu sieciowego (narzędziem Wireshark).
    2. W przeglądarce nawiąż połączenie z http://testphp.vulnweb.com/login.php
    3. Wykonaj próbę logowania (dowolne dane).
    4. Odszukaj w zapisanym ruchu swoje dane logowania.
    Dla porównania powtórz ćwiczenie z logowaniem np. do Facebooka (również dowolne, nieprawdziwe dane logowania).

Do monitorowania ruchu sieci wykorzystałem aplikację "Wireshark". Po wpisaniu przykładowego loginu i hasła zakończyłem w Wireshark i zacząłem filtrować zapisane dane.

*Na stronach wykorzystujących "https://" Wireshark nie pokaże loginu ani hasła. Login/e-mail można znaleźć w narzędziach programistycznych przeglądarki, widoczne hasło w tych narzędziach zależy od wykorzystania odpowiednich skryptów przez programistów owej strony.
![:(](/screenshots/3_1.png)
*
![:(](/screenshots/narzedzia_programistyczne_przegladarki.png)

### Zadanie 4 - Analiza ruchu SSH

    1. Rozpocznij monitorowanie ruchu sieciowego (narzędziem Wireshark).
    2. Nawiąż połączenie pomiędzy Kalim a SDA po SSH.
    3. Stwórz pliki sekret1.txt i sekret2.txt z tajnymi hasłami.
    4. Edytuj konfigurację vsFTPd, żeby umożliwić wgrywanie plików po FTP.
    5. Zakończ połączenie po SSH.
    6. Spróbuj poszukać w zapisanym ruchu sieciowym zawartość plików sekret1.txt i sekret2.txt
    Dane logowania do SDA: uranus/butterfly, root/666
    

Za pomocą aplikacji "namap" sprawdziłem urządzenia w sieci.
Następnie włączyłem skanowanie sieci za pomocą aplikacji Wireshark.
Za pomoca polecenia ssh ``` "ssh user@<ip maszyny do której chcesz się zalogować>"```.
Przelogowując się na użytkownika: root (okazało się, że użytwownik: uranus nie ma uprawnień do edycji pliku "vsftpd.conf") w celu konfiguracji vsFTPd. Wróciłem do użytkownika: uranus i stworzyłem pliki txt. Sprawdziłem jaki ruch wychwycił Wireshark.

![:(](/screenshots/4_1.png)
![:(](/screenshots/4_3_1.png)
![:(](/screenshots/4_4_1.png)
![:(](/screenshots/4_5.png)
![:(](/screenshots/4_6.png)

### Zadanie 5 - Analiza ruchu FTP

    1. Rozpocznij monitorowanie ruchu sieciowego (narzędziem Wireshark).
    2. Nawiąż połączenie pomiędzy Kalim a SDA po FTP.
    3. Prześlij z Kaliego do SDA zwykły plik tekstowy (z własną zawartością).
    4. Ściągnij z SDA do Kaliego pliki sekret1.txt i sekret2.txt
    5. Zakończ połączenie.
    6. Odszukaj w zapisanym ruchu sieciowym zawartość przesłanego i ściągniętych plików.
    Dane logowania do SDA: uranus/butterfly, root/666

Za pomocą aplikacji "namap" sprawdziłem urządzenia w sieci.
Następnie włączyłem skanowanie sieci za pomocą aplikacji Wireshark.
Za pomoca polecenia ssh ```"ftp user@<ip maszyny do której chcesz się zalogować>"```
Utworzyłem plik do_wyslania.txt na maszynie atakującej a na stępnie na maszynie atakowanej za pomocą komendy ```put <ścieżka do pliku>``` umieściłem plik, pobrałem pliki sekret1.txt i sekret2.txt z maszyny atakowanej komendą ```get <scieżka do pliku>```.
W Wireshark znalazłem zawartość wysylanego i pobieranych plików.

![:(](/screenshots/5_1.png)
![:(](/screenshots/5_2.png)
![:(](/screenshots/5_4.png)
![:(](/screenshots/5_4.png)
![:(](/screenshots/5_5.png)
![:(](/screenshots/5_6.png)
![:(](/screenshots/5_7.png)

### Zadanie 6 - Eternal Blue

    1. Przygotuj maszynę wirtualną z podatnością MS17-010 (np. Windows 7) i umieść ją w tej samej sieci co Kali Linux.
    Atakujący:
    2. Wykryj i potwierdź podatność (np. nmapem).
    3. Wykorzystaj podatność korzystając z frameworka Metasploit (nie jest wymagana eskalacja uprawnień).

Podobnie jak wcześniej za pomocą aplikacji "nmap" sprawdziłem ip maszyny która chcę atakować. Na kalim linux za pomocą komendy ```msfconsole``` a następnie wyszukuję modół/podatność "Eternal Blue" ustawiam wszystkie wymagane informacje, po nawiązaniu połaczenia z maszyna windows przechodzę na pulpit i tworzę folder.

![:(](/screenshots/6_0.png)
![:(](/screenshots/6_1.png)
![:(](/screenshots/6_2.png)
![:(](/screenshots/6_3.png)
