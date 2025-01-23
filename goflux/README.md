## Specyfikacja języka programowania Flux

**(21 stycznia 2025)**

Ten dokument służy jako nieformalna specyfikacja i propozycja nowego języka programowania.

## Przegląd

Flux to nowy język programowania zaprojektowany jako alternatywa dla Go, połączona z możliwościami skryptowymi Bash. Jego głównym celem jest umożliwienie efektywnego tworzenia skompilowanych programów, takich jak serwery. Język został opracowany z myślą o szybkości i wydajności, zapewniając, że kompilator i środowisko wykonawcze działają z optymalną efektywnością.

## Opis programu

Program Flux składa się z jednej lub więcej paczek. Wśród nich domyślna paczka o nazwie `main` pełni rolę punktu wejścia programu. Jeśli paczka `main` zawiera funkcję `.init()`, zostanie ona zawsze wykonana przed funkcją `.main()`.

Każda jednostka kompilacji w Flux składa się z:

1. **Deklaracji paczki**.
2. Opcjonalnych **instrukcji importu**.
   - Liczba zaimportowanych paczek nie wpływa na priorytet ich wykonania.

Programy Flux obejmują różne elementy, takie jak paczki (zależne lub niezależne), typy, funkcje i inne. Poszczególne paczki można definiować w oddzielnych plikach, eksportować do ponownego wykorzystania i jawnie importować do innych jednostek kompilacji.

Zasady zakresu (ang. scoping) w Flux są zasadniczo podobne do tych w Go.

## Kluczowe cechy

- **Wydajność i efektywność**: Zaprojektowany do tworzenia szybkich, skompilowanych aplikacji, takich jak serwery.
- **Struktura paczek**: Promuje modularność dzięki dobrze zdefiniowanym paczkom.
- **Jawne importy**: Paczki muszą być jawnie importowane do każdej jednostki kompilacji, w której są używane.

Flux łączy solidność Go z elastycznością Bash, oferując programistom potężne, a jednocześnie lekkie narzędzie do budowy wydajnego oprogramowania.

## Wyjaśnienie symboli w Flux

W Flux różne symbole i operatory pełnią specyficzne role w programowaniu. Pozwalają one programistom wykonywać obliczenia arytmetyczne, przypisywać wartości, porównywać dane, manipulować logiką i wiele więcej. Ten przewodnik przedstawia zwięzły przegląd roli i zastosowania każdego operatora w Flux, podkreślając ich znaczenie w upraszczaniu i ulepszaniu procesu kodowania.

### Operatory arytmetyczne

- `+` - Dodawanie.
- `-` - Odejmowanie.
- `*` - Mnożenie.
- `/` - Dzielenie.
- `%` - Modulo (reszta z dzielenia).
- `**` - Potęgowanie.

### Operatory przypisania

- `=` - Przypisanie wartości.
- `+=` - Dodanie i przypisanie.
- `-=` - Odjęcie i przypisanie.
- `*=` - Mnożenie i przypisanie.
- `/=` - Dzielenie i przypisanie.
- `%=` - Modulo i przypisanie.

### Operatory porównania

- `==` - Luźna równość (tylko wartość).
- `===` - Ścisła równość (wartość i typ).
- `!=` - Luźna nierówność (tylko wartość).
- `!==` - Ścisła nierówność (wartość i typ).
- `>` - Większe niż.
- `<` - Mniejsze niż.
- `>=` - Większe lub równe.
- `<=` - Mniejsze lub równe.

### Operatory logiczne

- `&&` - Logiczne AND.
- `||` - Logiczne OR.
- `!` - Logiczne NOT.
- `??` - Koalescencja nullish (wartość domyślna, gdy `null` lub `undefined`).

### Operatory bitowe

- `&` - Bitowe AND.
- `|` - Bitowe OR.
- `^` - Bitowe XOR.
- `~` - Bitowe NOT.
- `<<` - Bitowe przesunięcie w lewo.
- `>>` - Bitowe przesunięcie w prawo.

### Inne operatory

- `()` - Grupowanie lub wywołanie funkcji.
- `[]` - Tworzenie tablicy lub dostęp do elementów.
- `{}` - Tworzenie obiektu lub blok kodu.
- `typeof` - Sprawdzenie typu wartości.
- `instanceof` - Sprawdzenie, czy obiekt jest instancją klasy.
- `in` - Sprawdzenie, czy właściwość istnieje w obiekcie.
- `...` - Operator spread lub rest.
- `:` - Używany w obiektach lub wyrażeniach warunkowych (`? :`).

Dzięki zrozumieniu i wykorzystaniu tych symboli programiści mogą pisać efektywny, czysty i solidny kod. Każdy operator stanowi element budulcowy funkcjonalności, umożliwiając rozwiązywanie złożonych problemów i tworzenie innowacyjnych rozwiązań w Flux. Opanowanie ich użycia to kluczowy krok w kierunku biegłości w tym wszechstronnym języku.

## Typy zmiennych i danych w Flux

Flux oferuje kilka sposobów zmiennych, takich jak `var`, `let`, `const`.
Zmienne w Flux można deklarować za pomocą następujących słów kluczowych:

- `var` - Starszy sposób deklarowania zmiennych. Ma zasięg globalny lub funkcyjny (nie blokowy).
- `let` - Używany do zmiennych z zasięgiem blokowym.
- `const` - Służy do deklarowania stałych.
- `int` - Służy do przechowywania liczb całkowitych.
- `varchar` - Służy do przechowywania krótkich ciągów znaków (tekstowych).
- `text` - Służy do przechowywania dłuższych ciągów znaków.
- `boolean` - Służy do przechowywania wartości logicznych (true/false).
- `json` - Umożliwia przechowywanie danych w formacie JSON (JavaScript Object Notation).
- `set` - Zbiór unikalnych wartości. Przydatny do przechowywania danych bez duplikatów.
- `float` - Służy do przechowywania liczb zmiennoprzecinkowych.
- `map` - Służy do przechowywania par klucz-wartość.
- `chan` - Kanały służą do komunikacji między goroutines (funkcje współbieżne).
- `struct` - Struktury umożliwiają definiowanie własnych typów danych, zawierających różne pola.

## Wartości do wyświetlania i interakcji w Flux

Flux oferuje zestaw funkcji do wyświetlania danych oraz interakcji w trakcie działania programu. Funkcje te pozwalają na debugowanie, obsługę błędów oraz komunikację z użytkownikiem.

### Główne funkcje

- `print()` - Wyświetla dane w standardowym wyjściu (konsoli). Używane do wyświetlania tekstu, zmiennych lub wyników obliczeń.
- `println()` - Działa jak `print()`, ale dodaje znak nowej linii po wyświetleniu.
- `printf()` - Wyświetla sformatowane dane w konsoli. Pozwala na dynamiczne tworzenie tekstów z wykorzystaniem symboli formatowania, takich jak `%d`, `%s`, itp.
- `panic()` - Wywołuje błąd i natychmiast zatrzymuje działanie programu. Używane do obsługi krytycznych błędów.
- `recover()` - Funkcja używana w mechanizmach odzyskiwania po błędzie wywołanym przez `panic`. Pozwala na kontynuowanie działania programu.
- `scan()` - Pobiera dane wejściowe od użytkownika z konsoli. Może być używane do wczytywania prostych wartości.
- `scanf()` - Pobiera dane wejściowe od użytkownika w określonym formacie. Wykorzystywane do bardziej precyzyjnego wczytywania danych.

Funkcje te umożliwiają interakcję z użytkownikiem oraz zarządzanie wyjściem i wejściem w trakcie działania programów napisanych w Flux. Dzięki ich znajomości możesz efektywnie debugować aplikacje i tworzyć dynamiczne programy, które reagują na dane od użytkownika.

## Komendy konsoli w Flux

Flux udostępnia zestaw komend do zarządzania projektami, kompilacji, uruchamiania programów oraz innych operacji związanych z rozwojem aplikacji.

### Podstawowe komendy

- `flux version` - Wyświetla aktualną wersję Flux zainstalowaną na systemie.
- `flux run` - Kompiluje i uruchamia wskazany plik źródłowy Flux.
- `flux build` - Kompiluje projekt Flux i generuje plik wykonywalny.
- `flux init` - Tworzy nowy projekt Flux z domyślną strukturą plików.
- `flux get` - Pobiera zależności wymagane przez projekt Flux.
- `flux test` - Uruchamia testy jednostkowe w projekcie Flux.
- `flux debug` - Uruchamia aplikację w trybie debugowania.
- `flux doc` - Wyświetla dokumentację dla modułu lub pakietu.
- `flux clean` - Usuwa pliki tymczasowe i binarne wygenerowane przez Flux.

Te komendy konsoli umożliwiają skuteczne zarządzanie projektami i środowiskiem programistycznym Flux. Dzięki nim można łatwo kompilować, testować i uruchamiać aplikacje, a także zarządzać zależnościami i dokumentacją.
