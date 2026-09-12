# T-REX HOME — Architektura systemu

Polski | [English](architecture.md)

## Przegląd

T-REX HOME jest centralnym koordynatorem lokalnego systemu sterowania roletami. Konfiguracja i logika automatyki znajdują się w HOME, natomiast fasadowe stacje pogodowe pełnią rolę rozproszonych czujników warunków zewnętrznych.

## Warstwy systemu

1. **Rolety** — napędy sterowane radiowo, przypisane do pomieszczeń i opcjonalnie do fasad budynku.
2. **Stacje fasadowe** — bateryjne stacje ESP32-C3 mierzące lokalne warunki.
3. **T-REX HOME** — centralna konfiguracja, harmonogramy, sceny, przypisanie fasad, agregacja pogody i automatyka.
4. **Lokalny interfejs użytkownika** — konfiguracja i sterowanie przez przeglądarkę.
5. **Warstwa integracji zewnętrznych** — Home Assistant i inne obsługiwane integracje.

## Identyfikacja i wykrywanie stacji

Stacje fasadowe używają trwałego numeru seryjnego wyprowadzonego z identyfikatora sprzętowego ESP32-C3. HOME traktuje numer seryjny jako tożsamość urządzenia — adres IP nie jest tożsamością stacji.

Dzięki temu stacja może pozostać przypisana do fasady również po zmianie adresu sieciowego.

## Model fasad

Zarówno rolety, jak i stacje pogodowe mogą być przypisane do ściany/fasady. Tworzy to relację potrzebną do automatyki zależnej od rzeczywistych warunków na danej elewacji.

## Przepływ danych pogodowych

Stacja budzi się, odczytuje czujniki, łączy się ze skonfigurowaną siecią Wi-Fi, wysyła telemetrię do HOME i przez krótki czas nasłuchuje zapytań HOME, po czym wraca do trybu oszczędzania energii. HOME śledzi odebrane stacje oraz aktualność ich danych.

Aktualny protokół stacji jest publicznie udokumentowany w projekcie open-source:

https://github.com/MateuszPtasz/trex-facade-weather-station/blob/main/docs/protocol_PL.md

## Działanie lokalne

T-REX HOME jest projektowany tak, aby podstawowa ścieżka sterowania pozostawała wewnątrz budynku. Połączenie z chmurą nie powinno być wymagane do podstawowego sterowania roletami, harmonogramów ani lokalnej automatyki pogodowej.

## Podsystem RF

T-REX HOME zawiera warstwę radiowego sterowania obsługiwaną instalacją rolet. Dokumentacja publiczna opisuje zachowanie systemu i model instalacji, ale nie publikuje zamkniętego firmware HOME ani szczegółów implementacyjnych protokołu sterowania roletami.

## Dane trwałe i dane runtime

Konfiguracja trwała obejmuje m.in. rolety, grupy, sceny, harmonogramy, sparowane stacje, przypisanie do fasad oraz konfigurację automatyki.

Stan runtime obejmuje m.in. bieżącą telemetrię pogodową, aktualność danych stacji, stan połączenia i zdarzenia automatyki. Dzięki temu konfiguracja przetrwa restart, a dane bieżące są odtwarzane z rzeczywistych urządzeń.

## Bezpieczeństwo i sterowanie ręczne

Ręczne sterowanie GÓRA / DÓŁ / STOP pozostaje podstawową funkcją systemu. Automatyka jest dodatkową warstwą i nie powinna odbierać użytkownikowi możliwości bezpośredniego sterowania roletami.

## Granica kodu źródłowego

To repozytorium dokumentuje publiczną architekturę. Źródła firmware T-REX HOME są utrzymywane prywatnie. T-REX Facade Weather Station jest osobnym projektem open-source.
