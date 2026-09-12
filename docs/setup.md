# T-REX HOME — Setup

[Polski](setup_PL.md) | English

## Documentation status

This is the public setup framework for T-REX HOME. Exact commissioning steps will be expanded alongside the finalized controller hardware and released firmware.

## Intended installation flow

1. Install and power the T-REX HOME controller.
2. Connect to the local T-REX setup interface.
3. Configure the home Wi-Fi connection where required.
4. Add roller shutters and assign human-readable names/rooms.
5. Create groups and scenes as required.
6. Assign shutters to building facades where facade automation will be used.
7. Discover/pair T-REX Facade Weather Stations.
8. Assign each station to its physical facade.
9. Configure schedules and supported automation rules.
10. Configure Home Assistant integration when available in the installed firmware.

## Facade stations

The facade station has its own local setup interface and open-source documentation. See:

https://github.com/MateuszPtasz/trex-facade-weather-station

Station identity is based on its persistent serial number, not on its current IP address.

## Important installation principle

Before enabling weather automation, verify:

- shutter direction and manual UP / DOWN / STOP behavior,
- correct room and facade assignment,
- correct physical placement of each weather station,
- current station telemetry,
- rain sensor behavior.

Automation should be enabled only after the manual control path and sensor assignments are confirmed.

## Firmware

T-REX HOME is supplied as a programmed controller/module. HOME source firmware is not distributed through this public repository.

## More detailed instructions

Screenshots and exact UI steps will be added after the current web interface and physical HOME enclosure are finalized for public documentation.
