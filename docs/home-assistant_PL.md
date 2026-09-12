# Integracja Home Assistant

Polski | [English](home-assistant.md)

## Status

Integracja z Home Assistant jest częścią architektury i roadmapy T-REX HOME. Ta strona celowo rozdziela **model integracji** od funkcji, które nie zostały jeszcze publicznie wydane i potwierdzone.

## Model integracji

T-REX HOME ma być pojedynczym mostem pomiędzy instalacją T-REX a Home Assistant.

Fasadowe stacje pogodowe komunikują się z HOME. Następnie HOME udostępnia odpowiednie encje systemu do Home Assistant. Dzięki temu każda bateryjna stacja fasadowa nie musi utrzymywać własnego połączenia MQTT/Home Assistant.

## Planowany model encji

Architektura przewiduje udostępnienie — tam, gdzie będzie to obsługiwane przez wydany firmware:

- rolet,
- pomiarów pogodowych dla fasad,
- stanu deszczu,
- informacji o baterii i stanie stacji,
- wybranych informacji o stanie systemu.

Dokładne nazwy encji, tematy Discovery i obsługiwane komendy zostaną opisane dopiero po ich potwierdzeniu w wydanym firmware HOME.

## Sterowanie ręczne a automatyka T-REX

Home Assistant ma być dodatkową warstwą sterowania i integracji. T-REX HOME pozostaje odpowiedzialny za własną konfigurację lokalną i automatykę T-REX.

Założeniem jest możliwość dodania rolet do Home Assistant i ręcznego sterowania nimi bez uzależniania lokalnego systemu T-REX od dostępności Home Assistant.

## MQTT

Planowana architektura wykorzystuje HOME jako urządzenie komunikujące się z MQTT, zamiast publikowania każdej stacji fasadowej bezpośrednio. Konfiguracja brokera MQTT i szczegóły Home Assistant Discovery zostaną dodane po finalizacji i fizycznym potwierdzeniu implementacji.

## Aktualne ograniczenie

Tego dokumentu nie należy traktować jako deklaracji, że wszystkie powyższe elementy są już dostępne w aktualnym wydaniu. Integracja jest rozwijana. Po osiągnięciu zweryfikowanego stanu wydania dodamy tutaj dokładną instrukcję konfiguracji krok po kroku.
