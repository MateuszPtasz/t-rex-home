# T-REX HOME — Instalacja i uruchomienie

Polski | [English](setup.md)

## Status dokumentacji

To publiczny szkielet instrukcji uruchomienia T-REX HOME. Dokładne kroki będą rozszerzane wraz z finalizacją sprzętu sterownika i wydaniem odpowiedniego firmware.

## Docelowa kolejność uruchomienia

1. Zamontuj i zasil sterownik T-REX HOME.
2. Połącz się z lokalnym interfejsem konfiguracji T-REX.
3. Skonfiguruj połączenie z domową siecią Wi-Fi, jeśli jest wymagane.
4. Dodaj rolety i nadaj im czytelne nazwy/pomieszczenia.
5. Utwórz potrzebne grupy i sceny.
6. Przypisz rolety do fasad budynku, jeśli ma być używana automatyka fasadowa.
7. Wykryj/sparuj T-REX Facade Weather Stations.
8. Przypisz każdą stację do jej fizycznej fasady.
9. Skonfiguruj harmonogramy i obsługiwane reguły automatyki.
10. Skonfiguruj integrację Home Assistant, gdy jest dostępna w zainstalowanym firmware.

## Stacje fasadowe

Stacja fasadowa posiada własny lokalny interfejs konfiguracji i otwartą dokumentację:

https://github.com/MateuszPtasz/trex-facade-weather-station

Tożsamość stacji opiera się na jej trwałym numerze seryjnym, a nie na aktualnym adresie IP.

## Ważna zasada instalacyjna

Przed włączeniem automatyki pogodowej należy sprawdzić:

- kierunki rolet i ręczne działanie GÓRA / DÓŁ / STOP,
- prawidłowe przypisanie pomieszczeń i fasad,
- rzeczywiste miejsce montażu każdej stacji pogodowej,
- aktualną telemetrię stacji,
- działanie czujnika deszczu.

Automatykę należy uruchamiać dopiero po potwierdzeniu ręcznego sterowania i poprawności przypisań czujników.

## Firmware

T-REX HOME jest dostarczany jako zaprogramowany sterownik/moduł. Kod źródłowy firmware HOME nie jest dystrybuowany przez to publiczne repozytorium.

## Dalsza dokumentacja

Zrzuty ekranu i dokładne kroki w interfejsie dodamy po finalizacji aktualnego panelu WWW i fizycznej obudowy HOME przeznaczonej do publicznej prezentacji.
