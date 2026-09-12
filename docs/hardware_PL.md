# T-REX HOME — Hardware

Polski | [English](hardware.md)

Ta strona opisuje **publiczną koncepcję sprzętową** T-REX HOME. Nie jest publikacją zamkniętego firmware sterownika.

## Sterownik

T-REX HOME jest zbudowany wokół sterownika embedded klasy ESP z lokalną łącznością Wi-Fi. Prototyp integruje interfejsy potrzebne w aktualnej instalacji T-REX.

## Radio do sterowania roletami

Dedykowany podsystem RF zapewnia komunikację z obsługiwanymi instalacjami rolet. T-REX HOME przedstawia rolety w lokalnej aplikacji jako nazwane urządzenia przypisane do pomieszczeń, grup i fasad.

Szczegóły implementacyjne zamkniętego protokołu sterowania nie są częścią publicznej dokumentacji.

## Ekran statusu

Prototyp sterownika HOME wykorzystuje **4,2-calowy ekran e-paper 400 × 300** jako energooszczędny lokalny panel statusu. Docelowo pokazuje najważniejsze informacje o systemie i pogodzie bez potrzeby sięgania po telefon.

## Zegar czasu rzeczywistego

Prototyp zawiera sprzętowy RTC wykorzystywany do lokalnego czasu i funkcji związanych z harmonogramami.

## Wi-Fi

HOME może pracować z własnym lokalnym/technicznym punktem dostępowym oraz jako klient domowej sieci Wi-Fi. Dokładna procedura instalacji będzie dokumentowana dla wydanej konfiguracji hardware/firmware.

## Stacje fasadowe

Stacje fasadowe są osobnymi urządzeniami ESP32-C3 i posiadają własne repozytorium open-source:

https://github.com/MateuszPtasz/trex-facade-weather-station

## Co będziemy publikować

Wraz z finalizacją fizycznego modułu HOME dokumentacja może obejmować:

- schemat funkcjonalny połączeń,
- listę obsługiwanych modułów,
- wymagania zasilania,
- zdjęcia obudowy,
- opis złączy,
- diagramy instalacyjne,
- instrukcję pierwszego uruchomienia.

## Czego nie publikujemy

Repozytorium nie publikuje:

- kodu źródłowego firmware T-REX HOME,
- prywatnych plików build,
- sekretów ani danych dostępowych,
- własnościowych szczegółów implementacyjnych, które nie są potrzebne do instalacji lub integracji.

Docelową opcją dla użytkownika jest zaprogramowany sterownik/moduł T-REX HOME.
