# Home Assistant Integration

[Polski](home-assistant_PL.md) | English

## Status

Home Assistant integration is part of the T-REX HOME development roadmap and architecture. This page intentionally distinguishes the **integration model** from features that have not yet been publicly released and verified.

## Integration model

T-REX HOME is intended to be the single bridge between the T-REX installation and Home Assistant.

Facade weather stations communicate with HOME. HOME then exposes the relevant system entities to Home Assistant. This avoids requiring every battery-powered facade station to maintain an independent MQTT/Home Assistant connection.

## Planned entity model

The architecture is intended to expose, where supported by the released firmware:

- roller shutters,
- facade weather measurements,
- rain state,
- station battery/status information,
- selected system status information.

Exact entity names, discovery topics and supported controls will be documented only after they are verified in the released HOME firmware.

## Manual control versus T-REX automation

Home Assistant is intended to provide an additional control/integration layer. T-REX HOME remains responsible for its local configuration and T-REX automation logic.

The design goal is to allow Home Assistant users to add and manually control shutters without making the local T-REX system dependent on Home Assistant availability.

## MQTT

The planned architecture uses HOME as the MQTT-facing device rather than publishing each facade station directly. MQTT broker configuration and Home Assistant Discovery details will be added here when the implementation is finalized and physically verified.

## Current limitation

Do not treat this document as a claim that every item above is available in the current public/released build. The integration is evolving. This page will be updated with exact setup steps once the HOME integration reaches the verified release state.
