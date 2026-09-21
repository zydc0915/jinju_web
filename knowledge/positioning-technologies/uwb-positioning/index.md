Canonical page: [UWB Positioning Technology: TDoA, ToF / TWR & PDoA](https://www.rpilink.com/knowledge/positioning-technologies/uwb-positioning/)

Website: Jinju Intelligence (Beijing) Technology Co., Ltd.

Language: English

Published: 2026-09-21

Last substantive update: 2026-09-21

Format: Markdown alternative generated from the public HTML main content.

---

POSITIONING TECHNOLOGIES / GUIDE 02

# UWB Positioning Technology.

TDoA, ToF / TWR and PDoA / AoA explained: learn how ultra-wideband measures time, distance and direction, then connect those measurements to an industrial indoor positioning system.

By Jinju Intelligence 21 September 2026 4 original diagrams · Architecture and deployment guide

START WITH THE MEASUREMENT

## From radio observations to useful location.

UWB is a radio technology used in real-time locating systems for personnel, tools and mobile assets. Selecting a system means choosing the measurements, compatible hardware and deployment geometry together. Use this guide to prepare an engineering discussion, compare options and define a representative site trial.

[Compare the methods](https://www.rpilink.com/knowledge/positioning-technologies/uwb-positioning/#comparison)

01 / ARRIVAL-TIME DIFFERENCES

## UWB TDoA positioning: one transmission, multiple anchors

Time Difference of Arrival (TDoA) compares when the same radio packet reaches different receivers. In an uplink TDoA system, a moving tag broadcasts a UWB frame. Fixed anchors timestamp its arrival and forward those observations to a location engine. After clock synchronization or offset correction, the engine converts arrival-time differences into distance differences and estimates the tag position using surveyed anchor coordinates.

A distance difference constrains the target to a hyperbola in a two-dimensional model, rather than giving a direct range to one anchor. Multiple independent observations and suitable geometry are needed to resolve a position. A shared network connection alone does not establish the timing accuracy required by the ranging system.

For a warehouse with many asset tags, assess uplink TDoA when reducing repeated tag-to-anchor exchanges is useful. Plan the transmission schedule, overlapping reception areas and backhaul together. Downlink TDoA reverses the signal direction: reference anchors transmit with known timing, and a compatible mobile receiver uses those observations. The two architectures require different device roles and software.

![A moving UWB tag sends one packet to three synchronized anchors; arrival timestamps reach an engine that estimates position from time differences.](https://www.rpilink.com/knowledge/uwb-tdoa.svg)

Uplink TDoA signal flow. Three receivers illustrate the measurement path, not a universal minimum anchor count or a complete site layout. CONCEPT DIAGRAM · NOT TO SCALE · SWIPE TO EXPLORE

Ask how anchor clocks are aligned, how synchronization loss is detected and what location quality is reported when too few anchors hear a tag.

[Explore the UWB TDoA solution](https://www.rpilink.com/solutions/uwb-tdoa/)

Technical references: [Qorvo — UWB and Bluetooth Channel Sounding](https://www.qorvo.com/design-hub/blog/the-future-of-positioning-exploring-uwb-and-bluetooth-channel-sounding) [Research — Design and Implementation of a UWB TDoA RTLS](https://arxiv.org/abs/2112.04839)

02 / PROPAGATION TIME

## UWB ToF and TWR: measuring the distance between devices

Time of Flight (ToF) is the travel time of a radio signal. Ideally, distance equals propagation time multiplied by the speed of light. Two-Way Ranging (TWR) is a message-exchange method used to estimate that travel time without requiring the two devices to share an absolute clock. ToF describes the physical quantity; TWR describes how it is measured.

The radio records transmit and receive timestamps. Its calculation accounts for the responder turnaround interval and timing errors; simply dividing the elapsed application time by two is incorrect. Double-sided TWR uses measurements from both sides, commonly a poll, response and final exchange, to reduce sensitivity to clock-rate differences. Antenna-delay calibration remains part of accurate ranging.

Start with a pairwise ranging trial when the immediate requirement is a distance threshold or local interaction. For coordinates, add independent ranges to known anchors or other position constraints. When comparing a small pilot with a full deployment, budget airtime for every exchange, retry and requested update. Record the actual measurement age at the application, rather than treating the radio update interval as end-to-end latency.

![A UWB tag and anchor exchange poll, response and final messages over time, then use hardware timestamps and delay corrections to estimate range.](https://www.rpilink.com/knowledge/uwb-tof.svg)

Illustrative double-sided two-way ranging sequence. Message spacing is not proportional to propagation time; implementation details depend on the protocol. CONCEPT DIAGRAM · NOT TO SCALE · SWIPE TO EXPLORE

Specify whether the output is pairwise distance or a map coordinate, then verify the ranging protocol, calibration procedure and total airtime budget.

[Explore UWB tags and beacon architectures](https://www.rpilink.com/solutions/uwb-beacon/)

Technical references: [Decawave / Qorvo — APS013: Two-Way Ranging](https://forum.qorvo.com/uploads/short-url/x34DrF7EW5fQP9wY3aNESqPKz8z.pdf) [FiRa Consortium — UWB Technical FAQ](https://www.firaconsortium.org/resource-hub/technical-faq)

03 / PHASE TO DIRECTION

## UWB PDoA and AoA: adding direction to ranging

Phase Difference of Arrival (PDoA) measures the relative phase of an incoming signal at different antenna elements. With a suitable receiver, known array geometry and calibration, these measurements can be converted into an Angle of Arrival (AoA). PDoA is a measurement used for direction finding; AoA is the estimated direction.

An angle alone does not identify a unique point in space. A system may combine an angle with a TWR distance, intersect directions from multiple locators, or use a known movement plane. Full three-dimensional positioning needs enough independent information about elevation as well as horizontal position. The antenna arrangement and the estimator determine which angles are observable.

For an entrance or workstation, evaluate range-and-angle measurements over the intended field of view. Include different tag orientations and nearby metal surfaces in the trial. Phase ambiguity, receiver calibration and multipath can affect the result. Confirm PDoA support in the radio, antenna system and firmware: a product name containing “dual channel” or “UWB AoA” is not enough to establish its internal implementation.

![Two receiving antenna elements observe different phases from a UWB tag; a calibrated angle estimate combines with range and geometry to constrain position.](https://www.rpilink.com/knowledge/uwb-pdoa.svg)

PDoA-to-AoA concept with range fusion. The drawing represents a measurement plane; it does not imply that one antenna pair produces complete 3D coordinates. CONCEPT DIAGRAM · NOT TO SCALE · SWIPE TO EXPLORE

Request the supported angle axes, usable field of view, calibration method and compatible tag protocol before choosing a locator.

[Explore the UWB PDoA solution](https://www.rpilink.com/solutions/uwb-pdoa/)

Technical references: [Research — Angle of Arrival and Distance Estimation on a UWB Node](https://arxiv.org/abs/2312.13672)

04 / THE SITE IS PART OF THE SYSTEM

## UWB RTLS deployment: geometry, NLOS and useful position data

A real-time locating system (RTLS) includes tags, anchors, a position estimator and the application consuming its output. Ultra-wideband signals support fine timing measurements, but a blocked direct path can still distort range observations. Non-line-of-sight (NLOS) conditions and reflections from equipment must be considered when placing anchors in a factory or warehouse.

Spread observations around the working area instead of concentrating all anchors along one edge. Evaluate height diversity when vertical position matters, and test rack aisles, corners and coverage boundaries. A layout that works in an empty building should be checked again with stock, vehicles and people present. The number of anchors depends on the measurement method, dimensions, visibility and desired redundancy.

For personnel tracking, test badge and helmet mounting in the orientations used during work. For asset tracking, repeat the route with the tag installed on its actual container or tool. Agree on measurable acceptance criteria: position error at surveyed points, valid-fix availability, stale-data handling and latency during motion. A map should distinguish a fresh valid fix from a predicted or last-seen location.

![A warehouse plan shows anchors around a rack, a clear radio path and a blocked path with a longer reflection, illustrating the need for site validation.](https://www.rpilink.com/knowledge/uwb-deployment.svg)

Conceptual top view of a rack aisle. Reflected paths and visibility change with the environment; anchor placement should be validated with representative operating conditions. CONCEPT DIAGRAM · NOT TO SCALE · SWIPE TO EXPLORE

Use the site trial to choose the architecture and acceptance limits. A chipset capability, a laboratory result and a finished system specification are different evidence.

[Review hardware and English specifications](https://www.rpilink.com/products/)

Technical references: [FiRa Consortium — UWB Technical FAQ](https://www.firaconsortium.org/resource-hub/technical-faq) [Research — UWB TDoA Anchor Placement in Cluttered Environments](https://arxiv.org/abs/2204.04508)

AT A GLANCE

## Compare UWB TDoA, TWR and PDoA

Use this table to identify what a proposed system measures. The rows are not interchangeable performance grades; some systems combine several measurements.

| Method | Measurement | Signal flow | What to verify |
| --- | --- | --- | --- |
| Uplink TDoA | Arrival-time differences | Tag → synchronized anchors | Clock alignment, geometry, airtime and reception overlap |
| ToF via TWR | Pairwise distance | Tag ↔ anchor exchanges | Timing corrections, antenna delays and exchange capacity |
| PDoA → AoA | Direction estimate | Tag → calibrated antenna array | Phase-capable hardware, field of view and additional constraints |
| Range + angle fusion | Combined spatial constraints | Compatible ranging and angle measurements | Consistent timestamps, coordinate frames and observable dimensions |

FROM PILOT TO OPERATION

## Plan an industrial UWB positioning project

Define the business event: finding a tool, locating personnel in a zone, following a vehicle route or measuring a distance. Specify which dimensions the application actually needs.

Prepare a site drawing: anchor positions and heights, metal structures, mounting restrictions, power, network access and the routes used in the acceptance test.

Verify compatibility: exact tag and anchor models, channel configuration, firmware, timestamps, ranging mode and the location engine interface.

Measure under load: expected tag count, update policy, packet loss, moving obstacles and representative battery settings. Keep measurement time and application receipt time separately.

Plan maintenance: surveyed coordinates, calibration records, replacement procedures and revalidation after layout changes. Agree who can access personnel tracks and how long records are kept.

For a technology comparison, continue with the [Bluetooth positioning guide](https://www.rpilink.com/knowledge/positioning-technologies/bluetooth-positioning/) . For a product discussion, review the [UWB AoA positioning station](https://www.rpilink.com/products/product-20/) and its English datasheet, then share your floor plan and acceptance criteria through our [contact page](https://www.rpilink.com/contact/) .

COMMON QUESTIONS

## UWB positioning FAQ

### Which UWB positioning method should I choose?

Start with the required output and installation constraints. Compare TDoA for a shared multi-tag infrastructure, TWR for explicit ranging interactions, and PDoA when direction is useful. Treat this as a shortlist for a site trial, not a performance ranking independent of hardware and environment.

### Is a UWB beacon the same as a Bluetooth beacon?

No. “Beacon” describes a device role, while UWB and Bluetooth use different radio technologies and protocols. Identify the signal direction and measurement method before choosing compatible transmitters and receivers. The separate Bluetooth guide explains gateway, beacon, AoA and Channel Sounding architectures.

### Does UWB always deliver centimeter-level indoor positioning?

There is no single accuracy figure for every UWB system. Request the test conditions, error statistic, coverage area, tag mounting and valid-fix rate for the proposed hardware. Evaluate moving targets and obstructed areas separately from static line-of-sight measurements.

### Do all Jinju UWB products support TDoA or PDoA?

These articles explain possible system designs. The current product documents do not establish a universal TDoA or PDoA compatibility list. Confirm the exact model, firmware, antenna configuration and positioning engine before procurement; related product links are starting points for that review.

## Sources and scope

The technical explanation draws on manufacturer documentation, FiRa guidance and the research below. The deployment checklist is our practical evaluation guidance. All diagrams are original conceptual illustrations. This article does not certify product interoperability or extend the capabilities stated in a model-specific datasheet.

1. [Qorvo — UWB and Bluetooth Channel Sounding](https://www.qorvo.com/design-hub/blog/the-future-of-positioning-exploring-uwb-and-bluetooth-channel-sounding)
2. [Decawave / Qorvo — APS013: Two-Way Ranging](https://forum.qorvo.com/uploads/short-url/x34DrF7EW5fQP9wY3aNESqPKz8z.pdf)
3. [FiRa Consortium — UWB Technical FAQ](https://www.firaconsortium.org/resource-hub/technical-faq)
4. [Research — Angle of Arrival and Distance Estimation on a UWB Node](https://arxiv.org/abs/2312.13672)
5. [Research — UWB TDoA Anchor Placement in Cluttered Environments](https://arxiv.org/abs/2204.04508)
6. [Research — Design and Implementation of a UWB TDoA RTLS](https://arxiv.org/abs/2112.04839)

LET’S BUILD YOUR POSITIONING SYSTEM

## Make location data work for your site.

Plan your site survey, hardware selection and platform integration with Jinju.

[zydc0915@gmail.com](mailto:zydc0915@gmail.com) [Discuss your requirements](https://www.rpilink.com/contact/)
