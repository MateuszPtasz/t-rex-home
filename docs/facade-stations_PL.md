# Fasadowe stacje pogodowe

Polski | [English](facade-stations.md)

T-REX HOME może korzystać z wielu stacji T-REX Facade Weather Station rozmieszczonych na różnych elewacjach budynku.

## Otwarta stacja pogodowa

Stacja jest celowo oddzielona od zamkniętego firmware T-REX HOME i została opublikowana jako projekt open-source:

https://github.com/MateuszPtasz/trex-facade-weather-station

Aktualny hardware prototypu obejmuje:

- ESP32-C3 Super Mini,
- BME280,
- VEML7700,
- RainPoint jako czujnik deszczu ze stykiem bezpotencjałowym,
- pomiar napięcia akumulatora.

W prototypie obudowa RainPoint jest jednocześnie fizyczną obudową kompletnej stacji fasadowej.

## Przypisanie do fasady

Każda stacja posiada trwały numer seryjny. HOME może przypisać ten numer do konkretnej ściany/fasady. Przypisanie jest elementem konfiguracji i nie zależy od zachowania tego samego adresu IP przez stację.

## Pomiary

Publiczny protokół stacji udostępnia obecnie pola dla temperatury, wilgotności, ciśnienia, natężenia światła, stanu deszczu, informacji o akumulatorze, RSSI oraz danych identyfikacyjnych/statusowych urządzenia.

## Brak lub nieaktualne dane stacji

Sparowana stacja powinna pozostać logicznie przypisana również wtedy, gdy jest chwilowo niedostępna. HOME rozdziela bieżącą telemetrię runtime od trwałej konfiguracji, dlatego chwilowa utrata łączności nie usuwa konfiguracji instalacji.

## Model sieciowy

Stacje komunikują się lokalnie przez Wi-Fi. Zależnie od konfiguracji instalacji stacja może łączyć się z techniczną siecią T-REX HOME albo z inną skonfigurowaną siecią Wi-Fi. ESP32 pracuje jako klient jednej sieci nadrzędnej Wi-Fi w danym momencie.

## Protokół

Stacja wykorzystuje UDP na porcie `4210` i publiczny identyfikator protokołu `trex-wall/1`.

Dokumentacja protokołu:

https://github.com/MateuszPtasz/trex-facade-weather-station/blob/main/docs/protocol_PL.md

## Zbuduj samodzielnie

W przeciwieństwie do firmware T-REX HOME firmware stacji fasadowej jest publiczny. Repozytorium stacji zawiera kod źródłowy oraz dokumentację połączeń, dzięki czemu stację można odtworzyć lub rozwijać niezależnie.
