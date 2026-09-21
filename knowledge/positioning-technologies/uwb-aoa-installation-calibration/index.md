Canonical page: [UWB AoA Station Installation & Calibration Guide](https://www.rpilink.com/knowledge/positioning-technologies/uwb-aoa-installation-calibration/)

Website: Jinju Intelligence (Beijing) Technology Co., Ltd.

Language: English

Published: 2026-09-21

Last substantive update: 2026-09-21

Format: Markdown alternative generated from the public HTML main content.

---

POSITIONING TECHNOLOGIES / INSTALLATION & CALIBRATION

# How to Install and Calibrate a UWB AoA Positioning Station

A practical commissioning sequence for mounting, surveying and validating an angle-based UWB system, with a clear boundary between site calibration and device-specific radio calibration.

By Jinju Intelligence 21 September 2026 2 original diagrams · Practical engineering guide

THE PRACTICAL ANSWER

## What to decide first

Record the station position and orientation in the site coordinate system, install it with a clear view of the working area, confirm compatible tags and networking, then validate against independent surveyed checkpoints. Use the manufacturer procedure for array or RF calibration; a site guide cannot supply universal calibration values.

01 / PRACTICAL GUIDE

## Survey the working area and define the coordinate frame

Choose a site origin, the direction of the horizontal axes and a consistent unit such as meters before mounting hardware. Record the intended tag plane or height range, nearby metal structures, expected movement and possible mounting surfaces. Store a diagram showing how the site axes correspond to the drawing used by the application.

Plan enough visible observations for the dimensions the application needs. A one-dimensional corridor, a floor-plane position and full three-dimensional tracking are different requirements. Do not turn a single-station 1D or 2D product statement into a general 3D positioning promise.

![A mounted UWB AoA station is surveyed relative to site X and Y axes, installation height and test points distributed around the working area.](https://www.rpilink.com/knowledge/installation-geometry.svg)

Conceptual installation geometry. The drawing does not specify a universal mounting height, tilt or coverage boundary. ORIGINAL CONCEPT DIAGRAM · NOT TO SCALE · SWIPE TO EXPLORE

02 / PRACTICAL GUIDE

## Mount the station and verify power, network and tag compatibility

Choose a stable bracket and follow the device instructions for orientation, fasteners, cable entry and environmental sealing. Keep the antenna view clear of nearby structural metal where the installation permits. Photograph the final orientation and label the station so that the physical unit can be matched to its configuration record.

The PY-U360 A/B/C brochure supports ceiling or side-bracket mounting and lists PoE 48V, 3W, LAN backhaul and DHCP or static addressing. Its functional table gives 0.5–1m positioning accuracy in unobstructed conditions and an open-area radius of 20m. These are model-document planning references, not an acceptance result for a furnished site. The brochure does not provide a universal installation height or a complete calibration command sequence.

Confirm the ordered variant, compatible tag protocol and engine version before commissioning. Verify that observations reach the intended server and that timestamps, device IDs and position units are interpreted correctly. Configure network access according to the deployed product documentation; avoid copying port or protocol settings from a different station model.

03 / PRACTICAL GUIDE

## Separate site geometry, angle calibration and range calibration

Site geometry calibration records where the station is installed and how its local axes map to the floor plan. Verify axis direction, yaw, tilt and height rather than adjusting coordinates until one test point looks right. A consistent offset or a rotated track is a reason to check the coordinate transform first.

Angle calibration concerns the antenna array and receiver response. Range calibration concerns timing effects such as antenna delays when a ranging method is used. These procedures are hardware-specific. Qorvo calibration notes explain this for particular devices; they are not a set of settings to apply to every finished station. Keep factory parameters unless the manufacturer provides an approved procedure for the exact model and firmware.

![The commissioning sequence records the mount, configures the coordinate transform, checks manufacturer calibration and validates with independent points before handover.](https://www.rpilink.com/knowledge/installation-validation.svg)

Commissioning order: establish geometry, follow the applicable device procedure, then test on points not used for adjustment. ORIGINAL CONCEPT DIAGRAM · NOT TO SCALE · SWIPE TO EXPLORE

Keep calibration points and validation points separate. A fitted point proves less than a repeatable result elsewhere in the working area.

04 / PRACTICAL GUIDE

## Validate static points, moving routes and maintenance changes

Distribute checkpoints across the center, edges and difficult parts of the intended coverage. At each point, record the true coordinates, observed coordinates, tag mounting, orientation, valid-fix rate and measurement age. Repeat with the tag moving across a boundary and with representative obstructions present.

Save the station coordinates, orientation, firmware, tag configuration and test report as the commissioning baseline. Recheck after a bracket moves, a station is replaced or the layout changes. If the site cannot meet the agreed criteria, investigate visibility and geometry before attempting to hide errors with stronger display smoothing.

DECISION WORKSHEET

## UWB AoA commissioning records and checks

| Record | Check | Evidence to retain |
| --- | --- | --- |
| Mount and survey | Position, height, orientation and stable fixture | Coordinates, photographs and installation drawing |
| Radio and firmware | Exact variant and compatible tag mode | Model IDs, versions and manufacturer procedure |
| Coordinate transform | Axes, origin, units and tag-height assumptions | Configuration export and known-point results |
| Acceptance | Independent points and moving routes | Error, availability, timestamps and exceptions |

NEXT STEPS

## Your project checklist

- Confirm the installation instructions for the shipped model.
- Label and survey each installed station.
- Check independent points across the useful field of view.
- Document changes that require recommissioning.

COMMON QUESTIONS

## Frequently asked questions

### What is the best mounting height?

There is no single height for every station and site. Use the manufacturer field-of-view requirements, target height range, obstruction map and a trial. The available PY-U360 brochure does not establish a universal height.

### Can calibration remove all errors caused by metal racks?

No. Calibration does not restore a blocked direct path. Reassess visibility, placement, tag mounting and the measurements available to the estimator.

### Does a UWB AoA product automatically support PDoA or TDoA?

No. Verify the actual radio implementation and supported firmware. A capability label does not establish compatibility with a different measurement architecture.

## References and further reading

Technical background is linked below. The selection questions, diagrams and project checklists are Jinju Intelligence editorial guidance. Product figures are tied to the linked model specifications; validate the ordered configuration and site conditions before using them as acceptance limits.

- [Qorvo / Decawave — APS012 production tests and antenna-delay calibration](https://forum.qorvo.com/uploads/short-url/lCKsd97GZVsd8WG4o61gAAEy7R6.pdf)
- [Research — AoA and distance estimation on a UWB sensor node](https://arxiv.org/abs/2312.13672)

[PY-U360 station and English datasheet](https://www.rpilink.com/products/product-20/) [UWB positioning fundamentals](https://www.rpilink.com/knowledge/positioning-technologies/uwb-positioning/) [Plan the project budget](https://www.rpilink.com/knowledge/positioning-technologies/indoor-positioning-project-cost/)

LET’S BUILD YOUR POSITIONING SYSTEM

## Make location data work for your site.

Plan your site survey, hardware selection and platform integration with Jinju.

[zydc0915@gmail.com](mailto:zydc0915@gmail.com) [Discuss your requirements](https://www.rpilink.com/contact/)
