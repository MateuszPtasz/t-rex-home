# T-REX HOME — Hardware Overview

[Polski](hardware_PL.md) | English

This page describes the **public hardware concept** of T-REX HOME. It is not a publication of the proprietary controller firmware.

## Controller

T-REX HOME is built around an ESP-class embedded controller with local Wi-Fi connectivity. The prototype integrates the interfaces needed for the current T-REX installation.

## Roller-shutter radio

A dedicated RF subsystem provides communication with supported roller-shutter installations. T-REX HOME exposes shutters to the local application as named devices assigned to rooms, groups and facades.

Detailed proprietary protocol implementation is intentionally outside the scope of this public repository.

## Status display

The prototype HOME controller uses a **4.2-inch, 400 × 300 e-paper display** as a low-power local status panel. The dashboard is intended to show essential system and weather information without requiring a phone.

## Real-time clock

The prototype includes a hardware RTC for local timekeeping and schedule-related operation.

## Wi-Fi

HOME can operate with both its local/technical access point and a station connection to the home network. The exact installation procedure will be documented against the released hardware/firmware configuration.

## Facade stations

Facade stations are separate ESP32-C3 devices and are documented in the open-source repository:

https://github.com/MateuszPtasz/trex-facade-weather-station

## What will be published here

As the physical HOME unit is finalized, this documentation may include:

- connection overview,
- supported module list,
- power requirements,
- enclosure photos,
- connector descriptions,
- installation diagrams,
- commissioning instructions.

## What will not be published here

This repository does not publish:

- T-REX HOME firmware source code,
- private build files,
- secrets or credentials,
- proprietary implementation details that are not required for installation or integration.

The intended end-user option is a pre-programmed T-REX HOME controller/module.
