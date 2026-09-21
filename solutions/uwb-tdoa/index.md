Canonical page: [UWB TDoA Positioning & Multi-Tag RTLS](https://www.rpilink.com/solutions/uwb-tdoa/)

Website: Jinju Intelligence (Beijing) Technology Co., Ltd.

Language: English

Format: Markdown alternative generated from the public HTML main content.

---

[Solutions / UWB TDoA Positioning](https://www.rpilink.com/solutions/)

TIME DIFFERENCE OF ARRIVAL

# UWB TDoA Positioning .

One broadcast. Multiple synchronized observations.

Uplink TDoA targets real-time systems with multiple tags. Stations record the arrival of a tag signal and use timing differences to constrain its position. Synchronization, geometry and capacity planning are central to the design.

[Discuss your solution](https://www.rpilink.com/contact/)

SOLUTION PROFILE

Positioning objective

Multi-tag coordinate tracking with system calibration

System components

TDoA-compatible tags + synchronized station network + engine

Large warehouses Production floors Personnel and asset tracks

HOW IT WORKS

## From radio signals to usable location.

The same signal reaches different stations at different times. After synchronization or clock-offset correction, time differences become range differences. Multiple hyperbolic or hyperboloid constraints determine position.

SYSTEM ARCHITECTURE CONCEPT · NOT LIVE DATA

01

### Tag broadcast

Send scheduled UWB frames and control channel utilization.

02

### Multi-station reception

Capture the same frame and record its timestamps.

03

### Time-difference solution

Correct clocks and solve from arrival-time differences.

04

### Track output

Filter invalid observations and publish usable coordinates.

### Fewer tag exchanges

Uplink broadcasts reduce per-station two-way interactions for multi-tag systems.

### Central processing

Manage synchronization, observation quality and tracks through a common engine.

### Extendable coverage

Plan overlapping station coverage and suitable geometric placement.

DEPLOYMENT ESSENTIALS

## Check the deployment requirements.

01 Time synchronization is essential. Confirm its implementation and the timing error budget.

02 Station count depends on 2D/3D requirements, observability and redundancy; one fixed count cannot suit every deployment.

03 The supplied specifications do not provide a TDoA support list. Related UWB products are evaluation candidates only; verify timestamp and firmware capabilities first.

RELATED HARDWARE

## Start with the right hardware

Related products are selection entry points. Confirm models, channels, protocols, firmware and acceptance criteria.

![Indoor UWB Positioning Station](https://www.rpilink.com/products/product-20/product.png)

Positioning Stations

JJ-IS40BUA / JJ-U

### Indoor UWB Positioning Station

Connect floor-level location with 3D space.

UWB / Dual-mode communication

[Open linked page](https://www.rpilink.com/products/product-10/)

![Bluetooth UWB Asset Tag](https://www.rpilink.com/products/product-05/image2.png)

Beacons & Tags

JJ-IP32BU

### Bluetooth UWB Asset Tag

Dual-mode tracking for detailed asset visibility.

BLE + UWB / Three-axis sensor

[Open linked page](https://www.rpilink.com/products/product-05/)

Technical reference: [Qorvo · UWB time-difference positioning ↗](https://www.qorvo.com/resources/d/qorvo-getting-back-to-basics-with-ultra-wideband-uwb-white-paper) . Product capabilities remain subject to their specifications and selection validation.

SELECTION QUESTIONS

## UWB timing architecture selection

### UWB TDoA vs TWR: what changes in deployment?

Uplink TDoA compares the arrival times of one tag transmission at multiple synchronized anchors. Two-way ranging (TWR) exchanges messages to estimate individual ranges. Evaluate synchronization, channel use, battery policy and the hardware firmware available for the intended tag population.

[Compare UWB system architectures](https://www.rpilink.com/solutions/uwb-beacon/)

### Can any UWB station be used for TDoA?

No. The available specifications do not establish a TDoA compatibility list. Verify timestamp access, synchronization, supported channels and engine integration before choosing stations or promising a tag capacity.

[Ask about hardware and firmware compatibility](https://www.rpilink.com/contact/)

LET’S BUILD YOUR POSITIONING SYSTEM

## Make location data work for your site.

Plan your site survey, hardware selection and platform integration with Jinju.

[zydc0915@gmail.com](mailto:zydc0915@gmail.com) [Discuss your requirements](https://www.rpilink.com/contact/)
