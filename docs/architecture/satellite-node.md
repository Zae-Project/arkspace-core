# Satellite Node Specification

**Version**: 0.1.0  
**Status**: Preliminary Research  
**Last Updated**: January 2026

---

## Overview

This document specifies the individual satellite node design for the proposed Exocortex Constellation. The design draws from established CubeSat and small satellite platforms while incorporating neuromorphic computing payloads.

**Technology Readiness**: This specification combines existing satellite bus technology (TRL 7-9) with emerging neuromorphic processors (TRL 4-6). Full system integration remains theoretical (TRL 2-3).

---

## Node Classification

### Form Factor

| Parameter | Value | Basis |
|-----------|-------|-------|
| Platform Class | 12U+ CubeSat or Microsat | Based on OreSat, Planet Labs platforms |
| Mass Budget | 15-25 kg | Typical for 12U CubeSat |
| Volume | 20×20×30 cm (12U) or custom | Standard CubeSat or custom bus |
| Deployment | P-POD compatible or dedicated | Launch flexibility |

**Note**: Form factor selection depends on payload power requirements and thermal constraints.

---

## Subsystems

### 1. Attitude Determination and Control System (ADCS)

| Component | Specification | Technology Status |
|-----------|---------------|-------------------|
| Star Tracker | ±10 arcsec accuracy | Commercial off-the-shelf (COTS) |
| Reaction Wheels | 3-axis, 1 mNm·s | COTS, flight-proven |
| Magnetorquers | 3-axis, 0.2 Am² | COTS |
| Control Loop | 10 Hz | Standard satellite systems |

**Purpose**: Maintain OISL pointing requirements (±0.1 arcsec) for optical links.

**Current Technology**: Mature. Blue Canyon Technologies, NanoAvionics provide flight-proven ADCS for CubeSats.

---

### 2. Communication Subsystem

#### Ground Link

| Parameter | Specification | Technology Status |
|-----------|---------------|-------------------|
| Frequency | Ka-band (26.5-40 GHz) | Mature (commercial satcom) |
| Data Rate | 100 Mbps to 1 Gbps | Demonstrated by Planet, Starlink |
| Antenna | Phased array or parabolic | COTS available |
| Link Margin | 6 dB minimum | Standard practice |

#### Inter-Satellite Link (OISL)

| Parameter | Specification | Technology Status |
|-----------|---------------|-------------------|
| Technology | Free-space optical (laser) | Demonstrated by Starlink, EDRS |
| Wavelength | 1550 nm (C-band) | Telecom standard |
| Data Rate | 60-200 Gbps target | Starlink Gen2: 100+ Gbps demonstrated |
| Range | Up to 5,400 km | Demonstrated in LEO meshes |
| Terminals per Node | 2 | Allows mesh connectivity |

**Current Technology**: Laser communication terminals exist commercially (TESAT, Mynaric). Demonstrated bandwidths: 1.8 Gbps (EDRS), 100+ Gbps (Starlink Gen2 claims).

**Gap**: Neural data protocol optimization for spike trains is novel and unproven.

---

### 3. Power System

| Component | Specification | Technology Status |
|-----------|---------------|-------------------|
| Solar Array | 400W beginning-of-life | COTS deployable panels |
| Battery | 100 Wh Li-ion | Flight-proven |
| Bus Voltage | 28V regulated | Standard |
| MPPT Efficiency | >95% | Commercial |

**Power Budget**:
- Neuromorphic payload: 50-100W (variable)
- OISL terminals: 30W × 2 = 60W
- Bus systems: 30W
- **Total**: 140-190W average

**Challenge**: Neuromorphic processor power consumption in space environment is uncharacterized.

---

### 4. Thermal Control

| Parameter | Specification | Notes |
|-----------|---------------|-------|
| Payload TDP | 100W maximum | Heat load from neuromorphic chip |
| Cooling Method | Passive radiator + heat pipes | Active cooling adds complexity |
| Radiator Area | 0.1-0.2 m² | Sized for 100W dissipation |
| Operating Range | -20°C to +60°C | Electronics thermal limits |

**Current Technology**: Heat pipes and radiators are well-established. Challenge is localized high heat flux from neuromorphic processor.

---

## Neuromorphic Payload (SPECULATIVE)

### Processor Architecture

The payload design assumes a Loihi-class neuromorphic processor. Current status:

**Established Facts**:
- Intel Loihi 2 (terrestrial): 1M neurons, 128M programmable connections, ~1W typical power (2021)
- Event-driven computing reduces idle power consumption
- Spiking Neural Network (SNN) execution demonstrated

**Speculative Elements**:
- Scaling to 100M neurons per node (100× current Loihi 2)
- Radiation hardening for space environment
- Power scaling at high neuron counts
- Real-time biological-timescale execution for consciousness substrate

**Technology Gap**: No radiation-hardened neuromorphic processors exist. Proposed system requires significant R&D.

---

## Radiation Environment

### LEO at 550 km

| Source | Annual Dose | Mitigation |
|--------|-------------|------------|
| Trapped protons | ~10 krad | Shielding (2-5mm Al) |
| Galactic Cosmic Rays | ~5 krad | TMR, EDAC |
| Solar Particle Events | Variable (0-50 krad) | Detect and safe mode |

**Required Hardness**:
- Total Ionizing Dose (TID): 50 krad minimum
- Single Event Upset (SEU): Error correction (ECC, TMR)
- Single Event Latchup (SEL): Latchup-immune design

**Current Technology**: Radiation-hardened FPGAs and processors exist (e.g., Xilinx Virtex-5QV, BAE RAD750). Neuromorphic chips require custom hardening.

---

## Development Status Assessment

| Subsystem | TRL | Comments |
|-----------|-----|----------|
| Satellite Bus | 7-9 | Flight-proven for CubeSats |
| Ka-band Ground Link | 8-9 | Operational on commercial satellites |
| OISL Terminal | 6-7 | Demonstrated, not yet widespread |
| Neuromorphic Processor | 3-4 | Lab demonstration, not space-qualified |
| Neural Protocol | 2 | Conceptual design only |
| Full System | 2 | Conceptual integration |

**TRL Definitions** (NASA scale):
- TRL 2: Technology concept formulated
- TRL 3: Experimental proof of concept
- TRL 4: Technology validated in lab
- TRL 6: Technology demonstrated in relevant environment
- TRL 7: System prototype demonstrated in operational environment
- TRL 9: Actual system proven through successful mission operations

---

## Mass Budget Estimate

| Subsystem | Mass (kg) | Confidence |
|-----------|-----------|------------|
| Structure | 3.0 | High |
| ADCS | 1.5 | High |
| Power (panels, battery) | 4.0 | High |
| Thermal | 1.0 | Medium |
| Ground Comm | 1.5 | High |
| OISL Terminals (2x) | 3.0 | Medium |
| Neuromorphic Payload | 0.5 | Low (SWAG) |
| Harness, Misc | 1.5 | Medium |
| **Total** | **16.0 kg** | **Medium** |
| Margin (30%) | 4.8 kg | Standard practice |
| **With Margin** | **20.8 kg** | |

**Note**: Neuromorphic payload mass is a rough estimate pending actual hardware design.

---

## Cost Estimate (Order of Magnitude)

| Item | Cost (USD) | Confidence |
|------|------------|------------|
| Satellite Bus | $500K - $1M | Based on Planet Labs, OreSat |
| Neuromorphic Payload | $200K - $2M | Highly uncertain |
| OISL Terminals | $1M - $3M | Based on TESAT, Mynaric quotes |
| Integration & Test | $500K | Standard |
| Launch (rideshare) | $300K - $500K | Per SpaceX rideshare pricing |
| **Total per Node** | **$2.5M - $7M** | Very rough estimate |

**Note**: Costs highly dependent on production volume, neuromorphic chip availability, and launch opportunities.

---

## References

1. OreSat Open Source CubeSat Project
2. Intel Loihi 2: A New Generation of Neuromorphic Computing (2021)
3. Starlink Gen2 FCC Filings (OISL specifications)
4. TESAT Laser Communication Terminal specifications
5. NASA Radiation Effects on Electronics database

---

*This is a preliminary research document. Specifications subject to significant revision as technology matures.*
