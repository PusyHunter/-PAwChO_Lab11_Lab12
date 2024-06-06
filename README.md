#Lab 11

docker compose byl zainstalowany domyslne w Docker Desktop
![image](https://github.com/PusyHunter/-PAwChO_Lab11_Lab12/assets/98088572/6e4f0779-4002-40be-b637-b3df07e54ed5)

dalej utworzylem folder projektu i umiescilem tam wszystkie potrzebne pliki, ktore znajduja sie na repo na github
(dodatkowo umiescilem wersje zadania nie rozbudowanego o wymagania z lab 12 w postaci arhiwu .zip)

uruchamiam za pomoca polecenia(uruchomienie w trybie -detach):

docker-compose up -d

sprawdzic dzialanie uslug mozna za pomoca polecenia:

docker-compose ps
![image](https://github.com/PusyHunter/-PAwChO_Lab11_Lab12/assets/98088572/c40ea469-fce6-4e4d-82ca-153673521ef0)

czy naprzyklad wyswietlic  logi:

docker-compose logs
![image](https://github.com/PusyHunter/-PAwChO_Lab11_Lab12/assets/98088572/759d8832-78e8-422d-a99a-9cd9d458fcc1)

dzialanie aplikacji tak samo  potwierdzamy   saprawdzajac strony localhost'a na portach 4001 oraz 6001:
wyswietlenie strony na porcie 4001 oznacza, że Nginx i PHP-FPM dzialaja poprawnie
![image](https://github.com/PusyHunter/-PAwChO_Lab11_Lab12/assets/98088572/0bfbd605-ce4a-4400-9024-dbad84d82033)
wyswietlenie strony na porcie 6001 oznacza, że phpMyAdmin dziala poprawnie.
Wyswietlana strona logowania na phpMyAdmin
![image](https://github.com/PusyHunter/-PAwChO_Lab11_Lab12/assets/98088572/082cf239-9c85-4b80-8293-f221c0a62319)
zalogowac sie mozna jako user testowy czy root. Dane do zalogowania, jak i sekrety beda podane w pliku tekstowym na moodle
Po zalogowaniu:
![image](https://github.com/PusyHunter/-PAwChO_Lab11_Lab12/assets/98088572/b834505c-4177-4d22-8e11-43ec0727d15e)

Dodatkowo polączylem sie z serwerem MySQL z poziomu kontenera za pomocą narzędzia mysql, aby sprawdzic dzialanie oraz zalozyc przykladowa baze:
polecenie:

docker exec -it zad_l11_l12-mysql-1 mysql -u root -p

![MySQL](https://github.com/PusyHunter/-PAwChO_Lab11_Lab12/assets/98088572/aebfc091-d6c8-4284-b64a-e2e3e305ae00)
![database](https://github.com/PusyHunter/-PAwChO_Lab11_Lab12/assets/98088572/70728608-55bf-434f-922c-1f206b458a37)

teraz po zalogowaniu sie do phpMyAdmin mozna zobaczyc utworzona baze:

![image](https://github.com/PusyHunter/-PAwChO_Lab11_Lab12/assets/98088572/6fafa45b-a3f3-4d70-844b-dfeee40eb49c)
![image](https://github.com/PusyHunter/-PAwChO_Lab11_Lab12/assets/98088572/65db3ff5-04e6-4771-a4e8-b7ac1a64af85)

oto wyglad katalogu roboczego:

![image](https://github.com/PusyHunter/-PAwChO_Lab11_Lab12/assets/98088572/54a9ec9b-d4a2-44dd-99e9-a470b9406ead)

#Lab12
Zadanie z lab 11 bylo zmodyfikowano:

plik docker-compose byl podzielony na pliki bazowy oraz plik override(nowa struktura umieszczona jest na repo)

oraz dodane pliki mysql_root_password.txt i mysql_password.txt, aby wykorzystac ich jako sekrety. Tych plikow
nie bedzie na repo na github, ich trzeba bedzie utworzyc w folderze roboczym, gdzie znajduja sie pliki compose
zawartosc tych plikow, przypominam, bedzie znajdowala sie w pliku tekstowym z zadaniem na moodle

oto struktura foldera roboczego:

![image](https://github.com/PusyHunter/-PAwChO_Lab11_Lab12/assets/98088572/ba3873f9-cf19-4d69-9179-90c6fbd4dd1d)

zatrzymanie uslug realizuje sie za pomoca polecenia:

docker-compose down
