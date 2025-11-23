# Aqara Bridge for Home Assistant

Built on the Aqara Open Platform to control devices and receive updates through cloud APIs.

[![version](https://img.shields.io/github/manifest-json/v/bernard3378/AqaraBridge?filename=custom_components%2Faqara_bridge%2Fmanifest.json)](https://github.com/bernard3378/AqaraBridge/releases/latest) [![stars](https://img.shields.io/github/stars/bernard3378/AqaraBridge)](https://github.com/bernard3378/AqaraBridge/stargazers) [![issues](https://img.shields.io/github/issues/bernard3378/AqaraBridge)](https://github.com/bernard3378/AqaraBridge/issues) [![hacs](https://img.shields.io/badge/HACS-Default-orange.svg)](https://hacs.xyz)

## Add to HACS with One Click
[![Open your Home Assistant instance and open a repository inside the Home Assistant Community Store.](https://my.home-assistant.io/badges/hacs_repository.svg)](https://my.home-assistant.io/redirect/hacs_repository/?owner=bernard3378&repository=AqaraBridge&category=integration)

## Developer Account Required
Apply for an Aqara IoT developer account: [Aqara IoT Cloud](https://developer.aqara.com/register).

- Tip: If installation says this integration does not support UI configuration, the RocketMQ library is likely missing. The current build bundles x86 and arm64 only.
- [V2.1.1] adds more architecture support. If the issue persists, copy the log and open an issue.
- Configuration is supported through HACS. Custom repository URL: `bernard3378/AqaraBridge`.

Key reminders:
1. You must request your own Aqara developer account.
2. Step 1: [Register](https://developer.aqara.com/register). After approval, choose personal verification and provide your name and ID number for developer verification.
3. Step 2: After approval you will have a DEMO app. Go to Project Management -> Details -> Message Push -> Edit -> choose China Service, MQ Message Push, keep the single default message key, select All subscriptions -> Save.
4. Step 3: Go back to Overview. Expand AppId & Key, find China Service, note the `appId`, `appKey` (click the eye), and `keyId`, then fill these three values into the integration.
5. Message inspection: set the integration log level to `info` if you want to confirm incoming messages.

## Release Notes
Current version: V2.1.2 (regular update, most stable).

V2.1.4
- Added support for W400 FCU controller `lumi.airrtc.acn003`.

V2.1.3
- Added support for W400 VRF controller `lumi.airrtc.acn002`.

V2.1.2
- Improved onboarding prompts.
- Improved device initialization flow.
- Improved FP2 human presence scene sensor state handling.
- Improved FP1/FP1E presence sensor movement events.
- Added devices:
  - Gateways:
    - `lumi.gateway.acn008` - Gateway M1S (2nd gen)
    - `lumi.gateway.acn012` - Gateway M3
  - Cameras:
    - `lumi.camera.gwpagl01` - Smart Camera G3 (gateway edition) with gesture events
  - Switches/Outlets:
    - `lumi.switch.acn048` - Kanon Smart Wall Switch Z1 (single button)
    - `lumi.switch.acn049` - Kanon Smart Wall Switch Z1 (double button)
    - `lumi.switch.acn054` - Kanon Smart Wall Switch Z1 (triple button)
    - `lumi.switch.acn055` - Kanon Smart Wall Switch Z1 (quad button)
    - `lumi.switch.acn056` - Kanon Smart Wall Switch Z1 Pro (single button)
    - `lumi.switch.acn057` - Kanon Smart Wall Switch Z1 Pro (double button)
    - `lumi.switch.acn058` - Kanon Smart Wall Switch Z1 Pro (triple button)
    - `lumi.switch.acn059` - Kanon Smart Wall Switch Z1 Pro (quad button)
    - `lumi.switch.acn040` - Smart Wall Switch E1 (neutral, triple button)
    - `lumi.switch.acn041` - Smart Wall Switch J1 (single live wire, single button)
    - `lumi.switch.acn042` - Smart Wall Switch J1 (single live wire, double button)
    - `lumi.switch.acn043` - Smart Wall Switch J1 (single live wire, triple button)
    - `lumi.switch.acn044` - Smart Wall Switch J1 (neutral, single button)
    - `lumi.switch.acn045` - Smart Wall Switch J1 (neutral, double button)
    - `lumi.switch.acn046` - Smart Wall Switch J1 (neutral, triple button)
    - `lumi.switch.acn062` - Smart Wall Switch Q1 (single button)
    - `lumi.switch.acn063` - Smart Wall Switch Q1 (double button)
    - `lumi.switch.acn065` - Smart Wall Switch Q1 (quad button)
    - `lumi.switch.acn047` - Dual-channel control module T2
    - `lumi.sensor_switch.v1` - Wireless switch
    - `lumi.sensor_switch.v2` - Wireless switch
    - `lumi.sensor_switch.aq2` - Wireless switch
  - Lighting (thanks to PR by XaoflySho):
    - `lumi.dimmer.acn003` - Smart LED strip driver T1
    - `lumi.dimmer.acn004` - Smart LED strip driver T1 (120W)
    - `lumi.dimmer.acn005` - Smart LED strip driver T1 (240W)
  - HVAC/Thermostats:
    - `aqara.airrtc.acn02` - Temperature controller companion T1 (indoor unit)
    - `lumi.airrtc.pcacn2` - Smart thermostat S3
    - `lumi.airrtc.pcacn2_thermostat` - Smart thermostat S3
    - `lumi.airrtc.agl001` - Smart valve thermostat E1
  - Curtains:
    - `lumi.curtain.vagl02` - Smart tubular motor T1
    - `lumi.curtain.acn002` - Smart roller shade companion E1

V2.1.1
- Fixed curtain position sync delays.
- Updated functions deprecated by Home Assistant.
- Improved RocketMQ support for arm64.
- Prevented creation of unmanaged entities during initialization.
- Improved cold-start wizard.
- Reduced warnings for partially supported devices.
- Changed button entities to event class.
- Added devices:
  - Clothes dryer:
    - `lumi.airer.acn001` - Smart clothes dryer H1
    - `lumi.airer.acn02` - Aqara Smart Clothes Dryer Lite

V2.1.0 (fixed many errors and added many devices)
- Rewrote the air-conditioner controller class.
- Fixed RocketMQ blocking HA startup.
- Fixed calls to deprecated or soon-to-be-deprecated HA constants.
- Fixed color mapping for light devices.
- Fixed button device UI buttons.
- Fixed wireless scene switch (6-button) model ID.
- Optimized entity loading.
- Optimized multi-channel device initialization.
- Optimized automatic device and entity naming rules.
- Added devices:
  - Gateways:
    - `lumi.controller.a4acn1` - Jiyue Smart Panel S1
  - Switches/Outlets:
    - `lumi.switch.n3acn3` - Smart Wall Switch D1 (neutral, triple button)
    - `lumi.switch.l3acn3` - Smart Wall Switch D1 (single live wire, triple button)
    - `lumi.ctrl_86plug.aq1` - Wall outlet (Zigbee)
    - `lumi.relay.c2acn01` - Dual-channel controller
  - Lighting:
    - `lumi.light.cbacn1` - Aqara constant-current driver T1-1
    - `lumi.light.cwopcn01` - MX960 ceiling light (tunable white)
    - `lumi.light.acn007` - Track grille light H1 (6-head)
    - `lumi.light.acn008` - Track grille light H1 (12-head)
    - `lumi.light.acn009` - Track flood light H1 (30 cm)
    - `lumi.light.acn010` - Track flood light H1 (60 cm)
    - `lumi.light.acn011` - Track pendant light H1
    - `lumi.light.acn012` - Track folding grille light H1 (6-head)
    - `lumi.light.acn013` - Track polarized light H1 (22 cm)
    - `lumi.light.cwjwcn02` - Downlight (tunable white)
    - `lumi.light.acn004` - Aqara dual-color driver T1 Pro
    - `lumi.light.acn006` - Track light H1 Pro
    - `lumi.light.acn023` - Spotlight T2 (15°)
    - `lumi.light.acn024` - Spotlight T2 (24°)
    - `lumi.light.acn025` - Spotlight T2 (36°)
    - `lumi.light.acn026` - Downlight T2 (60°)
    - `lumi.light.acn128` - Down/spot light T3
    - `lumi.light.acn014` - LED bulb T1 (tunable white)
    - `lumi.light.acn003` - Aqara ceiling light L1-350
    - `lumi.light.acn015` - Aqara Guangyi Clear Sky light H1
    - `lumi.light.acn032` - Colorful ceiling light T1 (40W)
    - `lumi.light.acn132` - Flow light strip T1
  - Curtains:
    - `lumi.curtain.v1` - Smart curtain motor (Zigbee open/close version)
    - `umi.curtain.acn007` - Aqara smart curtain motor T1
    - `lumi.curtain.hagl07` - Smart curtain motor C2
    - `lumi.curtain.hagl08` - Aqara smart curtain motor A1
    - `lumi.curtain.hagl04` - Smart curtain motor B1
    - `lumi.curtain.acn015` - Aqara smart curtain motor T2
    - `lumi.curtain.aq2` - Smart tubular motor
    - `lumi.curtain.hagl04` - Smart curtain motor B1
    - `lumi.curtain.acn04` - Aqara smart curtain motor C3
    - `lumi.curtain.acn003` - Smart curtain companion E1
  - Air conditioning / floor heating:
    - `lumi.aircondition.acn05` - Air conditioner companion P3
    - `lumi.airrtc.vrfegl01` - VRF air conditioner controller
    - `lumi.acpartner.aq1` - Air conditioner companion
    - `lumi.acpartner.v3` - Air conditioner companion (upgraded)
    - `lumi.ctrl_hvac.es1` - HVAC thermostat
    - `lumi.airrtc.tcpco2ecn01` - Thermostat (CO2)
    - `lumi.acpartner.es1` - Air conditioner companion
    - `lumi.airrtc.tcpecn01` - Thermostat
    - `lumi.airrtc.tcpecn02` - Thermostat S2
  - Sensors:
    - `lumi.motion.ac02` - Motion sensor P1
    - `umi.motion.agl02` - Motion sensor T1
    - `lumi.motion.acn001` - Motion sensor E1
    - `lumi.motion.agl001` - FP2 human presence scene sensor
    - `lumi.sensor_occupy.agl1` - FP1E AI presence sensor
    - `lumi.sensor_natgas.v1` - Natural gas alarm
    - `lumi.sensor_gas.acn02` - Aqara natural gas alarm
    - `lumi.airmonitor.acn01` - TVOC air quality companion
    - `lumi.sen_ill.agl01` - Illuminance sensor T1

V2.0.3
- Fixed developer configuration so you can use your own developer credentials.

V2.0.2
- Fixed save errors and added startup dependency (start after HomeKit is up).
- Fixed flow option errors so tokens can be refreshed by phone number and improved error messages.
- hass icons are approved; component and manufacturer icons now display correctly.
- Fixed other common issues.

V2.0.1
- Merged everything into master; the old configuration method required the `dev` branch, which is no longer maintained.
- Updated the flow: multiple gateways are merged into an account; developer auth info is separated so you can configure your own developer AK, etc.
- Fixed most device state retrieval issues and history state updates.
- Thanks to [Silver Wolf](https://bbs.hassbian.com/?62352) for added device configs: support for Wireless Knob H1, H1 12-head magnetic grille light, and upgraded wireless button. Wall switches are split into two parts; neutral models add power monitoring, and LED driver modules add power monitoring.

V1.0.1
- Fixed most device issues and added wireless buttons. Buttons now use event subscriptions instead of polling for faster refresh.
- Added room location retrieval.
- Added button name retrieval for button-type switches.
- Added RocketMQ dynamic library for arm64 (only x86 and arm64 handled for now).
- Added history data retrieval to refresh `trigger_time` or `last_update_time`.
- Added `button` entity type by separating wireless switches from sensors.
- Configured most common gateways, wireless switches, single-live/neutral switches, temperature/humidity sensors, smart outlets, motion sensors, etc.
- Added more error prompts so configuration errors are less likely.

V1.0.0

I only support most devices I own and similar components. If you find unsupported devices and can code Python, please update: [custom_components/aqara_bridge/core/aiot_mapping.py](https://github.com/meishild/AqaraBridge/blob/master/custom_components/aqara_bridge/core/aiot_mapping.py)
