# prawo-jazdy

Skrypt do importowania bazy pytań egzaminacyjnych na prawo jazdy publikowanych przez Ministerstwo Infrastruktury do programu [Anki](https://apps.ankiweb.net/).

## Pliki wejściowe

Źródłem danych są pliki ze strony Ministerstwa Infrastruktury: https://www.gov.pl/web/infrastruktura/prawo-jazdy

- [Baza pytań na prawo jazdy](https://www.gov.pl/attachment/a9abfbe4-51a8-4976-8a98-3e1d5df98c57)
- [Multimedia cz. 1](https://www.gov.pl/pliki/rozne/KLIPY-PYTANIA%202021_01%20cz.%201.zip)
- [Multimedia cz. 2](https://www.gov.pl/pliki/rozne/KLIPY-PYTANIA%202021_01%20cz.%202.zip)
- [Multimedia cz. 3](https://www.gov.pl/pliki/rozne/KLIPY-PYTANIA%202021_01%20cz.%203.zip)

## Release

Przygotowany plik do zaimportowania do Anki z pytaniami dla kategorii A
z października 2018 roku jest dostępny na stronie z releasami:

[Kategoria A, październik 2018](https://github.com/dpurge/prawo-jazdy/releases/tag/v2018.10)

## Przygotowanie plików do importu

- Należy ściągnąć wszystkie potrzebne pliki ze strony Ministerstwa Infrastruktury
- Zip-y z multimediami należy wypakować do jednego katalogu (bez podkatalogów)
- Zainstalować pythona 3 oraz dwie biblioteki: argparse i pyexcel_xlsx
- Ściągnąć plik `prawko2anki.py`

Skrypt uruchamiamy tak: `python prawko2anki.py -i pytania_plik_październik_2018.xlsx -m media -o out -c A`

Pomoc wyświetlana przez skrypt:

```
> python prawko2anki.py -h
usage: prawko2anki.py [-h] -i INPUT -m MEDIA -o OUTPUT -c CATEGORY

optional arguments:
  -h, --help            show this help message and exit
  -i INPUT, --input INPUT
                        Input XLSX file name
  -m MEDIA, --media MEDIA
                        Media directory
  -o OUTPUT, --output OUTPUT
                        Output directory
  -c CATEGORY, --category CATEGORY
                        License category
```

W katalogu wyjściowym powstanie plik `prawo-jazdy-pytania.txt`
oraz podkatalog `media` z filmikami i obrazkami do pytań.

## Import do Anki

[Anki ](https://apps.ankiweb.net/) należy przygotować.

W menu `Tools, Note types` tworzymy kopię typu `Basic`
i edytujemy pola (`Tools, Note types, Fields...`) do takiej postaci:

![fields](https://github.com/dpurge/prawo-jazdy/raw/master/img/anki-fields.png "Screenshot z listą pól w nowym typie notki")

Następnie w menu `Tools, Note types, Cards...` dla nowo utworzonego
typu formatujemy karty przez wklejenie w odpowiednie pola 
zawartości plików `anki-styling.txt`, `anki-front-template.txt`
i `anki-back-template.txt`.

![cards](https://github.com/dpurge/prawo-jazdy/raw/master/img/anki-cards.png "Screenshot z edytorem stylów")

Pytania wyglądają mniej więcej tak:

![question](https://github.com/dpurge/prawo-jazdy/raw/master/img/anki-question.png "Screenshot z pytaniem")

Filmiki są odtwarzane w MPlayerze dostarczanym z Anki. Filmik można
odtworzyć ponownie nasiskając klawisz `R` (od: replay).

Odpowiedzi wyglądają tak:

![answer](https://github.com/dpurge/prawo-jazdy/raw/master/img/anki-answer.png "Screenshot z odpowiedzią")

## Inne uwagi

Wrzucam to na GitHub-a, bo może się to komuś przyda.

Z wyłączeniem celów komercyjnych, możesz tego skryptu używać i go dowolnie modyfikować oraz publikować zmodyfikowane kopie skryptu.

Pull requesty przyjmę z wdzięcznością.

Jeśli masz kłopoty z odpaleniem skryptu, poproś o pomoc kogoś ze znajomych - dla mnie to jednorazowy skrypcik, nie planuję go ulepszać. Nie starałem się też uczynić go pięknym ani obsłużyć wszelkich możliwych błędów - mi są potrzebne tylko pytania na kategorię A.

