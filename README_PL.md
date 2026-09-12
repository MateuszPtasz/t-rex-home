# T-REX HOME

**Lokalny sterownik rolet, fasadowych stacji pogodowych i integracji Smart Home.**

Polski | [English](README.md)

> To repozytorium zawiera wyłącznie **publiczną dokumentację**. Firmware sterownika T-REX HOME jest oprogramowaniem zamkniętym i **nie jest publikowany w tym repozytorium**.

## Czym jest T-REX HOME?

T-REX HOME jest centralnym sterownikiem systemu T-REX Smart Home. Projekt powstaje według prostej zasady: podstawowe funkcje domu powinny działać lokalnie, bez uzależnienia od chmury i stałego dostępu do Internetu.

Sterownik łączy w jednym systemie:

- sterowanie roletami,
- pomieszczenia, grupy i sceny,
- harmonogramy,
- przypisanie rolet do fasad,
- lokalne fasadowe stacje pogodowe,
- automatykę zależną od warunków pogodowych,
- lokalny panel WWW,
- lokalny ekran statusu,
- rozwijaną integrację z Home Assistant.

Obecny system rozwijany jest przede wszystkim dla instalacji rolet kompatybilnych z YOODA oraz stacji pogodowych T-REX.

## Idea systemu

```text
Fasadowe stacje pogodowe T-REX
             |
             | Wi-Fi / sieć lokalna
             v
         T-REX HOME
          /   |   \
         /    |    \
      rolety  WWW   Home Assistant
        RF    UI    integracja
```

T-REX HOME jest koordynatorem całego systemu. Stacje fasadowe dostarczają lokalne pomiary, a HOME przypisuje je do rzeczywistych ścian/fasad budynku i może wykorzystywać te informacje w automatyce.

## Dlaczego pogoda dla konkretnej fasady?

Jedna stacja pogodowa nie zawsze opisuje warunki występujące na każdej ścianie budynku. Nasłonecznienie, opad i temperatura mogą wyglądać zupełnie inaczej na różnych elewacjach.

Dlatego T-REX wykorzystuje **kontekst fasady**. Stację pogodową można przypisać do konkretnej ściany, a rolety również mogą należeć do tej fasady. Dzięki temu automatyka może reagować na lokalne warunki zamiast opierać się wyłącznie na zegarze lub ogólnej prognozie internetowej.

## Local-first — najpierw działanie lokalne

Założeniem projektu jest lokalne działanie podstawowych funkcji:

- ręcznego sterowania roletami,
- grup i scen,
- harmonogramów,
- lokalnych danych pogodowych,
- lokalnej automatyki,
- konfiguracji przez panel WWW.

Usługi internetowe mogą rozszerzać system, ale nie powinny być podstawą działania rolet.

## T-REX Facade Weather Station

Fasadowa stacja pogodowa jest osobnym, **otwartym projektem open-source** T-REX opartym na ESP32-C3. Mierzy lokalne warunki na elewacji i komunikuje się z T-REX HOME w sieci lokalnej.

Repozytorium open-source stacji:

https://github.com/MateuszPtasz/trex-facade-weather-station

Projekt stacji zawiera firmware, dokumentację połączeń oraz publiczny protokół telemetrii i wykrywania `trex-wall/1`.

## Hardware

T-REX HOME jest sterownikiem embedded. Platforma prototypowa wykorzystuje sterownik klasy ESP oraz interfejsy potrzebne w instalacji T-REX, w tym układ radiowy do sterowania roletami i lokalny ekran statusu.

Publiczna dokumentacja sprzętu i montażu będzie rozszerzana wraz z finalizacją obudowy i docelowej konfiguracji sprzętowej.

Zobacz [opis hardware](docs/hardware_PL.md).

## Home Assistant

T-REX HOME ma pełnić rolę mostu pomiędzy instalacją T-REX a Home Assistant. Założeniem architektury jest, aby bateryjne stacje fasadowe komunikowały się z HOME, a nie utrzymywały każda osobnego połączenia MQTT.

Integracja jest aktywnie rozwijana. Publiczna dokumentacja będzie opisywała wyłącznie funkcje potwierdzone w aktualnej wersji sterownika.

Zobacz [integrację Home Assistant](docs/home-assistant_PL.md).

## Dostępność firmware

Kod źródłowy T-REX HOME **nie jest open-source**.

To publiczne repozytorium jest celowo oddzielone od prywatnego repozytorium firmware. Zawiera dokumentację, informacje instalacyjne i integracyjne, diagramy oraz publiczne materiały techniczne — bez źródeł sterownika HOME.

Do korzystania z systemu użytkownik nie potrzebuje kodu źródłowego HOME. Docelowym modelem jest **zaprogramowany sterownik/moduł T-REX HOME** dostarczany z odpowiednim firmware.

Otwarta stacja fasadowa pozostaje niezależnie udokumentowana i możliwa do samodzielnego zbudowania.

## Dokumentacja

- [Architektura systemu](docs/architecture_PL.md)
- [Hardware](docs/hardware_PL.md)
- [Instalacja i uruchomienie](docs/setup_PL.md)
- [Integracja Home Assistant](docs/home-assistant_PL.md)
- [Stacje fasadowe](docs/facade-stations_PL.md)

Dokumentacja angielska zaczyna się w [README.md](README.md).

## Status projektu

T-REX HOME jest aktywnie rozwijany. Repozytorium opisuje publiczny interfejs i potwierdzone funkcje. Zdjęcia, obudowa, zrzuty ekranu i kolejne materiały instalacyjne będą dodawane wraz z finalizacją fizycznego systemu.

## Strona projektu

https://t-rexlab.pl

---

**T-REX HOME** — najpierw sterowanie lokalne, potem integracje zewnętrzne.
