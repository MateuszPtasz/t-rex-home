# T-REX HOME — System Architecture

[Polski](architecture_PL.md) | English

## Overview

T-REX HOME is the central coordinator of a local-first roller-shutter system. Configuration and automation logic live in HOME; facade weather stations act as distributed environmental sensors.

## Logical layers

1. **Roller shutters** — RF-controlled actuators assigned to rooms and optionally to building facades.
2. **Facade stations** — battery-powered ESP32-C3 stations measuring local environmental conditions.
3. **T-REX HOME** — central configuration, schedules, scenes, facade mapping, weather aggregation and automation.
4. **Local user interface** — browser-based configuration and control.
5. **External integration layer** — Home Assistant and other integrations where supported.

## Identity and discovery

Facade stations use a persistent serial derived from the ESP32-C3 hardware identity. HOME uses that serial as the station identity; an IP address is not treated as identity.

A station can therefore be paired with a facade and remain logically assigned even if its network address changes.

## Facade model

Both shutters and weather stations can be associated with a facade/wall. This provides the relationship required for facade-aware automation.

## Weather data flow

A station wakes, reads its sensors, joins the configured Wi-Fi network, sends telemetry to HOME and listens briefly for HOME requests before returning to low-power operation. HOME tracks the received stations and their runtime freshness.

The current station protocol is documented publicly in the open-source station project:

https://github.com/MateuszPtasz/trex-facade-weather-station/blob/main/docs/protocol.md

## Local operation

T-REX HOME is designed so that the essential control path stays inside the building. Cloud connectivity is not intended to be required for basic shutter operation, schedules or local weather automation.

## RF subsystem

T-REX HOME contains the radio control layer used by the supported shutter installation. Public documentation describes the system behavior and installation model, but does not publish proprietary HOME firmware or implementation details of the shutter-control protocol.

## Runtime versus persistent data

Persistent configuration includes items such as shutters, groups, scenes, schedules, paired stations, facade assignments and automation configuration.

Runtime state includes live weather telemetry, station freshness, connection state and automation events. This distinction allows configuration to survive restarts while live data is re-established from actual devices.

## Safety and manual control

Manual UP / DOWN / STOP control remains a primary system function. Automation is an additional layer and should not remove the user's ability to operate shutters directly.

## Source-code boundary

This repository documents the public architecture. T-REX HOME firmware sources are maintained privately. The T-REX Facade Weather Station is a separate open-source project.
