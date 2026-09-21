Canonical page: [Bluetooth Positioning: Gateways, Beacons, AoA & ToF](https://www.rpilink.com/knowledge/positioning-technologies/bluetooth-positioning/)

Website: Jinju Intelligence (Beijing) Technology Co., Ltd.

Language: English

Published: 2026-09-21

Last substantive update: 2026-09-21

Format: Markdown alternative generated from the public HTML main content.

---

POSITIONING TECHNOLOGIES / GUIDE 01

# Introduction to Bluetooth Positioning.

Base stations, beacons, AoA and ToF: understand what each approach measures, how devices are deployed and which questions to ask before building an indoor positioning system.

By Jinju Intelligence 21 September 2026 4 illustrated methods · Practical selection guide

THE KEY DISTINCTION

## Deployment roles are not measurement methods.

A base station or beacon describes what a device does in the system. RSSI, angle of arrival and radio ranging describe the observations used to estimate location. A useful design specifies both. Bluetooth positioning can support personnel and asset tracking, but radio reception alone does not produce reliable coordinates.

[Jump to the comparison](https://www.rpilink.com/knowledge/positioning-technologies/bluetooth-positioning/#comparison)

01 / FIXED RECEIVERS

## Bluetooth base station positioning: tags move, gateways listen

In a gateway-based deployment, Bluetooth tags travel with people or assets while receiving stations stay at surveyed locations. A tag broadcasts its identifier and supported telemetry; gateways forward observations such as received signal strength (RSSI) to a server. The software can associate a tag with a room or zone, or estimate position using a calibrated model.

“Bluetooth base station” does not identify a single positioning algorithm. A basic receiver may support RSSI collection, while an AoA locator needs different radio and antenna capabilities. Putting several ordinary gateways in a room does not automatically create an AoA system.

For personnel badges, start by defining whether the application needs presence in a zone or a continuous coordinate track. Test gateways near doors, shelving and occupied work areas. Set broadcast and reporting intervals together so that battery life, network traffic and location freshness match the task.

![Mobile BLE tags broadcast to two fixed receiving gateways; their observations are sent over the network to a location engine and zone map](https://www.rpilink.com/knowledge/bluetooth-gateways.svg)

Figure 1. Fixed gateways collect moving-tag broadcasts. The engine interprets observations using known station locations and the selected location method. CONCEPT DIAGRAM · NOT TO SCALE · SWIPE TO EXPLORE

Best starting question: do you need zone presence, or a coordinate with a defined error bound?

[Bluetooth ceiling gateway](https://www.rpilink.com/products/product-13/) [Personnel tracking badges](https://www.rpilink.com/products/product-18/)

Technical references: [Bluetooth SIG — Location Services](https://www.bluetooth.com/learn-about-bluetooth/solutions/location-services/) [Bluetooth SIG — The Bluetooth LE Primer](https://www.bluetooth.com/bluetooth-le-primer/)

02 / FIXED TRANSMITTERS

## Bluetooth beacon positioning: reference signals at known locations

In a fixed-beacon layout, transmitters are attached to known places. A phone or scanning terminal detects their identifiers and signal levels, then a device application or server estimates the receiver location. This reverses the common asset-tracking layout: the reference transmitter stays still and the receiver moves.

Beacon formats such as iBeacon identify a broadcast; they do not independently calculate coordinates. Proximity thresholds, zone rules or a site fingerprint can turn observations into location estimates. RSSI is affected by body absorption, walls, antenna orientation and reflections, so signal strength is not an exact distance ruler.

For a visitor-navigation or mobile-terminal project, validate scanning support and application behavior on the actual devices. For asset inventory, it may be simpler to attach broadcasting tags to assets and let fixed gateways listen. Both use BLE broadcasts, but the receiver, power and software responsibilities differ.

![Three fixed Bluetooth beacons broadcast toward a moving scanning terminal, which matches received identifiers and signal levels to a reference map](https://www.rpilink.com/knowledge/bluetooth-beacons.svg)

Figure 2. Fixed reference beacons are scanned by a moving receiver. A mapped ID establishes a reference point; it does not establish precise range. CONCEPT DIAGRAM · NOT TO SCALE · SWIPE TO EXPLORE

Choose who carries the receiver before selecting beacon hardware or developing a mobile application.

[Bluetooth beacon variants](https://www.rpilink.com/products/product-03/) [BLE beacon deployment solution](https://www.rpilink.com/solutions/ble-beacon/)

Technical references: [Bluetooth SIG — Location Services](https://www.bluetooth.com/learn-about-bluetooth/solutions/location-services/) [Bluetooth SIG — The Bluetooth LE Primer](https://www.bluetooth.com/bluetooth-le-primer/)

03 / DIRECTION FINDING

## Bluetooth AoA positioning: measure direction with an antenna array

Angle of arrival (AoA) estimates the direction from which a radio signal reaches a receiver. A compatible transmitting tag and a receiving antenna array provide the measurements used by the direction-finding algorithm. Phase observations across array elements, combined with array geometry, allow the receiver to estimate an arrival angle.

An angle is not yet a complete position. A positioning engine must combine observations with known locator coordinates, orientation and suitable geometric constraints. Depending on the design, this can involve multiple locators or a known target plane. Mounting height and target height matter when translating an angle into a floor position.

For tool and medical-equipment tracking, check tag compatibility, calibration and coverage with people and metal objects present. The JJ-IS40BXPA specification lists less than 0.5 m in unobstructed conditions; this is a model-specific nominal figure, not a guarantee for all Bluetooth AoA installations.

![A tag transmits to a ceiling antenna array; phase observations produce an arrival angle that a location engine combines with installation geometry](https://www.rpilink.com/knowledge/bluetooth-aoa.svg)

Figure 3. AoA adds direction information. Locator pose and additional geometric constraints are needed to convert the angle into a usable position. CONCEPT DIAGRAM · NOT TO SCALE · SWIPE TO EXPLORE

Confirm direction-finding signal support on both ends. A Bluetooth version number alone is not a compatibility list.

[Indoor AoA gateway and English datasheet](https://www.rpilink.com/products/product-12/) [Bluetooth AoA system planning](https://www.rpilink.com/solutions/ble-aoa/)

Technical references: [Bluetooth SIG — A Technical Look at Direction Finding](https://www.bluetooth.com/blog/a-technical-look-at-direction-finding/)

04 / DISTANCE MEASUREMENT

## Bluetooth ToF positioning: understand RTT and Channel Sounding

Time of flight (ToF) relates signal travel time to distance. For Bluetooth product selection, the standardized feature to examine is Channel Sounding, introduced in Bluetooth Core 6.0. It includes phase-based ranging (PBR) and round-trip timing (RTT). Calling the whole feature “Bluetooth ToF” leaves out the phase-based measurement path.

RTT measures a two-way exchange; the responder turnaround and implementation timing must be accounted for before interpreting propagation time. PBR uses phase observations at multiple frequencies to estimate distance. The available measurements, algorithms and calibration determine the result. Ordinary beacon packet timestamps or RSSI readings are not substitutes for Channel Sounding radio support.

A distance between two devices is not a 2D or 3D coordinate. Positioning needs known references and enough independent geometric constraints. Pairwise ranging may suit a defined proximity task, while a multi-device tracking design must also evaluate measurement scheduling, battery use and system capacity.

The Jinju specifications currently supplied on this site do not confirm Channel Sounding support. Treat this section as a technology guide and verify radio, firmware and host software support on both devices before selecting hardware.

![Initiator and reflector exchange ranging signals over time; the diagram separates round-trip timing from multi-frequency phase-based ranging and notes that distance is not a full coordinate](https://www.rpilink.com/knowledge/bluetooth-tof.svg)

Figure 4. Conceptual two-way ranging sequence. Channel Sounding supports RTT and PBR; actual measurement processing follows the radio implementation and specification. CONCEPT DIAGRAM · NOT TO SCALE · SWIPE TO EXPLORE

Request an explicit Channel Sounding capability statement and a representative ranging demonstration.

[Discuss ranging and hardware requirements](https://www.rpilink.com/contact/)

Technical references: [Bluetooth SIG — Core 6.0 Feature Overview](https://www.bluetooth.com/core-specification-6-feature-overview/) [Bluetooth SIG — Channel Sounding](https://www.bluetooth.com/learn-about-bluetooth/feature-enhancements/channel-sounding/)

AT A GLANCE

## Compare architectures and measurements

The first two rows describe where devices are deployed. The last two describe what the radio measures. These choices can overlap in a system design.

| Approach | Observation | Location output | What to verify |
| --- | --- | --- | --- |
| Fixed gateways + moving tags | Broadcast ID and typically RSSI | Zone association or a calibrated estimate | Gateway placement, radio coverage and reporting intervals |
| Fixed beacons + moving receiver | Known beacon IDs and typically RSSI | Receiver proximity, zones or a fingerprint estimate | Reference map, scanning behavior and application support |
| Bluetooth AoA | Direction from antenna-array measurements | Angles; position after geometric processing | Compatible signals, array calibration and locator pose |
| Channel Sounding / Bluetooth ToF | PBR and/or RTT ranging measurements | Pairwise distance; position needs further constraints | Supported radios, firmware, ranging algorithm and scheduling |

FROM CONCEPT TO SITE

## A practical deployment checklist

Define the output: room presence, a zone event, a distance threshold or coordinates. Specify acceptable delay and error before discussing the radio.

Record the site: floor plan, mounting height, power, network, metal racks, moving vehicles and expected tag orientation.

Verify the complete chain: tag signal, receiver mode, firmware, location engine and the interface used by your business application.

Run a representative trial: compare measured locations against surveyed points and test transitions, missed observations and battery policy.

Plan operation: device identity, calibration records, access controls for personnel data, maintenance responsibilities and revalidation after layout changes.

For an RSSI starting point, compare the [Bluetooth beacon solution](https://www.rpilink.com/solutions/ble-beacon/) . For array-based measurements, review the [AoA solution](https://www.rpilink.com/solutions/ble-aoa/) and its product specifications. Use the [technology comparison](https://www.rpilink.com/solutions/) when deciding between Bluetooth and UWB.

COMMON QUESTIONS

## Bluetooth positioning FAQ

### Are Bluetooth base stations and beacons competing algorithms?

No. They describe deployment roles. A beacon transmits, while a receiving gateway collects observations. A beacon can also move with an asset. State which devices are fixed, which move and where the location is calculated before comparing solutions.

### Does one Bluetooth gateway give an exact location?

A basic RSSI gateway can indicate reception or proximity. Precise coordinates require a suitable measurement method, calibrated geometry and a positioning engine. Coverage range should never be read as positioning accuracy.

### Can existing BLE tags be upgraded to AoA or ToF?

Do not assume a firmware upgrade is sufficient. AoA requires direction-finding support and a suitable receiving array. Channel Sounding needs compatible radio and firmware support on both ranging devices. Check the complete device combination.

### How should positioning accuracy be tested?

Use surveyed reference points and representative movement, occupancy and obstructions. Agree on horizontal or 3D error, the percentile to report, update interval, missed fixes and test duration. Keep nominal datasheet figures separate from results measured on your site.

## Sources and scope

This guide explains technology principles using Bluetooth SIG documentation and the product specifications linked above. It is not a statement that every listed product implements every method. Diagrams are original conceptual illustrations; coverage, precision and device capacity require model-specific verification.

1. [Bluetooth SIG — Location Services](https://www.bluetooth.com/learn-about-bluetooth/solutions/location-services/)
2. [Bluetooth SIG — The Bluetooth LE Primer](https://www.bluetooth.com/bluetooth-le-primer/)
3. [Bluetooth SIG — A Technical Look at Direction Finding](https://www.bluetooth.com/blog/a-technical-look-at-direction-finding/)
4. [Bluetooth SIG — Core 6.0 Feature Overview](https://www.bluetooth.com/core-specification-6-feature-overview/)
5. [Bluetooth SIG — Channel Sounding](https://www.bluetooth.com/learn-about-bluetooth/feature-enhancements/channel-sounding/)

LET’S BUILD YOUR POSITIONING SYSTEM

## Make location data work for your site.

Plan your site survey, hardware selection and platform integration with Jinju.

[zydc0915@gmail.com](mailto:zydc0915@gmail.com) [Discuss your requirements](https://www.rpilink.com/contact/)
