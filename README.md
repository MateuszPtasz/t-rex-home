# T-REX HOME

**Local-first controller for roller shutters, facade weather stations and smart-home integration.**

[Polski](README_PL.md) | English

> This repository contains **public documentation only**. The T-REX HOME controller firmware is proprietary and is **not published in this repository**.

## What is T-REX HOME?

T-REX HOME is the central controller of the T-REX Smart Home system. It is designed around a simple principle: important home functions should continue to work locally, without depending on a cloud service or a permanent Internet connection.

The controller brings together:

- roller-shutter control,
- rooms, groups and scenes,
- schedules,
- facade assignment,
- local facade weather stations,
- weather-based automation,
- local web configuration,
- status display,
- planned / evolving Home Assistant integration.

The current system is being developed primarily around YOODA-compatible roller-shutter installations and T-REX facade weather stations.

## System concept

```text
T-REX Facade Weather Stations
          |
          | Wi-Fi / local network
          v
      T-REX HOME
       /   |   \
      /    |    \
 shutters  web   Home Assistant
   RF      UI    integration
```

T-REX HOME is the system coordinator. Facade stations provide local environmental measurements, while HOME associates them with actual building facades and can use those measurements in automation decisions.

## Why facade-aware weather?

A single weather station does not always describe what is happening on every wall of a building. Sunlight, rain exposure and temperature can differ significantly between facades.

T-REX is therefore designed around **facade context**. A weather station can be assigned to a wall/facade, and shutters can also be assigned to that facade. This allows automation to work from local conditions rather than only from a clock or a generic Internet weather forecast.

## Local-first operation

The design goal is that core functions remain available locally:

- manual shutter control,
- groups and scenes,
- schedules,
- local weather data,
- local automation,
- configuration through the local web interface.

Internet services may extend the system, but they are not intended to be the foundation of basic shutter operation.

## T-REX Facade Weather Station

The facade weather station is a separate **open-source** T-REX project based on ESP32-C3. It measures local facade conditions and communicates with T-REX HOME over the local network.

Open-source station repository:

https://github.com/MateuszPtasz/trex-facade-weather-station

The station project includes firmware, wiring documentation and the public `trex-wall/1` telemetry/discovery protocol.

## Hardware

T-REX HOME is an embedded controller. The prototype platform includes an ESP-class controller and interfaces required by the T-REX installation, including the roller-shutter radio subsystem and local status display.

Public hardware and installation documentation will be expanded as the enclosure and production-oriented hardware configuration are finalized.

See [Hardware overview](docs/hardware.md).

## Home Assistant

T-REX HOME is intended to act as the bridge between the T-REX installation and Home Assistant. The integration model keeps the facade stations behind HOME rather than requiring each battery station to maintain its own MQTT connection.

The integration is under active development. The public documentation will describe only functionality verified in the current released controller software.

See [Home Assistant integration](docs/home-assistant.md).

## Firmware availability

The T-REX HOME source code is **not open-source**.

This public repository is intentionally separated from the private firmware repository. It contains documentation, installation information, integration information, diagrams and public-facing technical material only.

A user does not need access to the HOME source code to use the system. The intended distribution model is a **pre-programmed T-REX HOME controller/module** supplied with the required firmware.

The open-source facade station remains independently documented and buildable.

## Documentation

- [System architecture](docs/architecture.md)
- [Hardware overview](docs/hardware.md)
- [Setup and installation](docs/setup.md)
- [Home Assistant integration](docs/home-assistant.md)
- [Facade weather stations](docs/facade-stations.md)

Polish documentation starts at [README_PL.md](README_PL.md).

## Project status

T-REX HOME is an actively developed project. This repository documents the public interface and verified functionality; screenshots, enclosure photos and additional installation material will be added as the physical system is finalized.

## Project website

https://t-rexlab.pl

---

**T-REX HOME** — local control first, external integrations second.
