Canonical page: [Personnel Tracking Badge Selection: Protocols, Battery & IP](https://www.rpilink.com/knowledge/positioning-technologies/personnel-tracking-badge-selection/)

Website: Jinju Intelligence (Beijing) Technology Co., Ltd.

Language: English

Published: 2026-09-21

Last substantive update: 2026-09-21

Format: Markdown alternative generated from the public HTML main content.

---

POSITIONING TECHNOLOGIES / PERSONNEL DEVICES

# Personnel Tracking Badges: Protocols, Battery Life and Protection

Turn a list of radio features into a wearable device specification that fits the working shift, the installed infrastructure and the actual environment.

By Jinju Intelligence 21 September 2026 2 original diagrams · Practical engineering guide

THE PRACTICAL ANSWER

## What to decide first

Choose the location output first, verify the exact badge-to-gateway protocol, then test battery endurance using the intended reporting and alert policy. Match environmental evidence to real exposure. A radio acronym, battery capacity or IP rating alone is not a complete personnel-tracking specification.

01 / PRACTICAL GUIDE

## Separate positioning from the communication link

A badge may advertise over BLE, send an AoA-compatible signal, participate in UWB ranging, obtain an outdoor satellite position or forward data over another radio. These roles can coexist, but listing several radios does not prove that all modes are included in every model. Ask which device measures position, which device calculates it and how the result reaches the application.

LoRa is a radio technology; LoRaWAN defines a network protocol. A LoRa-labelled or proprietary LORALAN product should not be assumed to join a LoRaWAN network. Match the exact protocol, region configuration, gateway, payload decoder and management software. For AoA and UWB, confirm the receiver and firmware compatibility as well as the badge model.

![A personnel badge connects through a positioning layer and a separate communication layer to a personnel platform; compatibility must be checked at each interface.](https://www.rpilink.com/knowledge/badge-protocols.svg)

Separate device roles before selecting protocols. A badge need not contain every illustrated technology. ORIGINAL CONCEPT DIAGRAM · NOT TO SCALE · SWIPE TO EXPLORE

02 / PRACTICAL GUIDE

## Specify endurance as a working profile

Battery capacity is stored charge, not a guaranteed number of working days. Average current depends on time spent transmitting, receiving, sensing and sleeping, plus features such as audio, vibration or an outdoor positioning receiver. Reporting intervals and retries are part of the test configuration, so two endurance claims are comparable only when their operating profiles are comparable.

As a first-order estimate, operating hours equal usable capacity in mAh divided by measured average current in mA. For illustration only, a usable 1,000mAh capacity and a measured 5mA average give 200 hours before additional reserve is applied. This is arithmetic, not a prediction for any catalog badge. Check temperature, aging, discharge limits and the energy required for alerts before setting a charging policy.

Define an active shift, idle period, expected alert usage and an end-of-shift reserve. Run the actual firmware through that profile and record the observed low-battery behavior. Include charging docks, spare badges and time for issuance in the plan. Increasing a reporting interval may help endurance but must still meet the required location freshness.

![A badge operating profile separates active movement, idle periods, alert events and charging, linking measured current and usable capacity to a shift endurance test.](https://www.rpilink.com/knowledge/badge-shift.svg)

Build the endurance test from the actual shift. Segment widths are illustrative and do not represent measured power consumption. ORIGINAL CONCEPT DIAGRAM · NOT TO SCALE · SWIPE TO EXPLORE

03 / PRACTICAL GUIDE

## Match protection evidence to the working environment

Ingress protection describes resistance to specified dust and water test conditions. It does not by itself establish resistance to drops, solvents, corrosion or every cleaning method. Ask for the claimed test rating, enclosure conditions and maintenance instructions, including how charging contacts and seals should be treated.

For hazardous locations, the applicable explosion-protection evidence must be checked for the exact shipped device and intended environment. An IP67 marking is not an explosion-protection certificate. Separately verify operating temperature, cleaning practice, attachment method, wearing comfort and whether a lanyard or clip is appropriate to the job.

04 / PRACTICAL GUIDE

## Turn the shortlisted model into a pilot specification

The IR-T10 A/B/C/D product page lists BLE5.0 / LORALAN base protocols, IP67, magnetic charging and a configuration-dependent 1,000–1,400mAh battery. UWB, AoA, BeiDou and access functions require model-specific confirmation. The published capacity should not be converted into an advertised runtime without the intended operating profile.

During a pilot, test the badge worn on a lanyard or waist as intended, including body turns and clothing. Verify reassignment, lost-device handling, low-battery reporting and alert delivery. Agree who may see personnel location and how long tracks are retained. Handover should include a compatible gateway list and a repeatable device-issuance procedure.

DECISION WORKSHEET

## Personnel badge selection evidence

| Selection area | Question | Evidence |
| --- | --- | --- |
| Protocol | Does this exact badge work with the installed receivers? | Model, firmware, protocol and payload compatibility test |
| Endurance | Will it complete the shift with reserve? | Measured operating profile, temperature and battery condition |
| Protection | Which actual exposures are covered? | IP test evidence, temperature limits and applicable certificates |
| Daily use | Can staff reliably wear, charge and return it? | Wear trial, dock plan, spare pool and issuance workflow |

NEXT STEPS

## Your project checklist

- Write the required location freshness and alert behavior.
- Request the exact radio and protocol combination on the order.
- Measure endurance using the real shift profile.
- Confirm environmental evidence and a practical charging workflow.

COMMON QUESTIONS

## Frequently asked questions

### Can a LoRa badge use any LoRaWAN gateway?

No. Matching radio terminology or frequency is insufficient. Confirm LoRaWAN support or the required proprietary protocol, network configuration and application payload.

### Does a larger battery always give a longer useful service interval?

Only under comparable conditions. Radio usage, receive windows, sensors, alerts and charging practices can outweigh a capacity difference. Compare complete operating profiles.

### Is IP67 enough for an industrial personnel badge?

It may address the specified ingress requirement, but selection also depends on temperature, impact, cleaning, wearing method and any applicable hazardous-location requirements.

## References and further reading

Technical background is linked below. The selection questions, diagrams and project checklists are Jinju Intelligence editorial guidance. Product figures are tied to the linked model specifications; validate the ordered configuration and site conditions before using them as acceptance limits.

- [LoRa Alliance — What is LoRaWAN?](https://lora-alliance.org/resource_hub/what-is-lorawan/)
- [Bluetooth SIG — Bluetooth LE Primer](https://www.bluetooth.com/bluetooth-le-primer/)
- [Zebra — What is an IP rating?](https://www.zebra.com/us/en/resource-library/faq/what-is-ip-rating.html)

[IR-T10 personnel badge and English datasheet](https://www.rpilink.com/products/product-18/) [Indoor and outdoor integration](https://www.rpilink.com/solutions/hybrid/) [Include badge operation in your project budget](https://www.rpilink.com/knowledge/positioning-technologies/indoor-positioning-project-cost/)

LET’S BUILD YOUR POSITIONING SYSTEM

## Make location data work for your site.

Plan your site survey, hardware selection and platform integration with Jinju.

[zydc0915@gmail.com](mailto:zydc0915@gmail.com) [Discuss your requirements](https://www.rpilink.com/contact/)
