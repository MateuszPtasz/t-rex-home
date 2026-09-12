# Facade Weather Stations

[Polski](facade-stations_PL.md) | English

T-REX HOME can use multiple T-REX Facade Weather Stations as distributed sensors around a building.

## Open-source station

The station is intentionally separated from the closed T-REX HOME firmware and is published as an open-source project:

https://github.com/MateuszPtasz/trex-facade-weather-station

Current prototype hardware includes:

- ESP32-C3 Super Mini,
- BME280,
- VEML7700,
- RainPoint dry-contact rain sensor,
- battery-voltage measurement.

The prototype reuses the RainPoint enclosure as the physical housing for the complete facade station.

## Assignment to a facade

Each station has a persistent serial number. HOME can pair that serial with a wall/facade. The assignment is configuration data and is not dependent on the station keeping the same IP address.

## Measurements

The public station protocol currently provides fields for temperature, humidity, pressure, illuminance, rain state, battery information, RSSI and device identification/status data.

## Missing or stale stations

A paired station should remain logically assigned when temporarily unavailable. HOME distinguishes current runtime telemetry from persistent pairing/configuration so a temporary loss of communication does not erase the installation setup.

## Network model

Stations communicate locally over Wi-Fi. Depending on installation configuration, a station can connect to the T-REX HOME technical network or another configured Wi-Fi network. An ESP32 station operates as a station on one upstream Wi-Fi network at a time.

## Protocol

The station uses UDP port `4210` and the public protocol marker `trex-wall/1`.

Protocol documentation:

https://github.com/MateuszPtasz/trex-facade-weather-station/blob/main/docs/protocol.md

## Build your own

Unlike T-REX HOME firmware, the facade-station firmware is public. The station repository contains the source firmware and wiring documentation, allowing the station to be reproduced or adapted independently.
