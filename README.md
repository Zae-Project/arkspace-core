# ArkSpace Core: Infrastructure Research for Orbital Neural Computing

**Preliminary Research and Specification Repository**

---

## Overview

This repository contains research, specifications, and architectural documentation for a proposed satellite constellation designed to host neuromorphic computing payloads in Low Earth Orbit (LEO). The system combines established satellite technology with emerging neuromorphic processors to explore distributed neural computation in space.

**Project Status**: Conceptual research phase (TRL 2). No hardware exists. This repository documents theoretical architecture and identifies technology gaps.

**Critical Note**: The concept of "consciousness substrate transfer" represents a highly speculative application of this infrastructure. The feasibility of such transfer is unproven and remains a subject of philosophical and scientific debate.

---

## Core Architecture Concept

The proposed Exocortex Constellation consists of satellite nodes equipped with neuromorphic processors (Spiking Neural Networks) connected via high-bandwidth optical inter-satellite links. This differs from traditional communication satellites by placing computational processing in orbit rather than merely relaying data.

```
                              ┌─────────────┐
                              │  Satellite  │
                        ┌────►│   Node A    │◄────┐
                        │     │   (SNN)     │     │
                        │     └─────────────┘     │
                   OISL │                         │ OISL
                60 Gbps │                         │ 60 Gbps
                 <20ms  │                         │  <20ms
                        │                         │
              ┌─────────▼─────┐           ┌──────▼────────┐
              │   Satellite   │◄─────────►│   Satellite   │
              │    Node B     │   OISL    │    Node C     │
              │    (SNN)      │           │    (SNN)      │
              └───────────────┘           └───────────────┘
                      │
                      │ Ground Link
                      ▼
              ┌───────────────┐
              │  Ground Node  │◄───── Interface (proposed)
              │  (Edge)       │
              └───────────────┘
```

---

## Key Technologies

### 1. Optical Inter-Satellite Links (OISL)

High-bandwidth free-space optical communication between satellites.

| Specification | Value | Technology Status |
|---------------|-------|-------------------|
| Bandwidth | 60-200 Gbps | Demonstrated by Starlink Gen2 (claims 100+ Gbps) |
| Latency | <20ms RTT | Physics-limited (speed of light) |
| Range | Up to 5,400 km | Demonstrated in commercial LEO constellations |
| Wavelength | 1,550 nm | Telecom standard, mature optical components |

**Current Technology**: Laser communication terminals exist commercially (TESAT, Mynaric). Demonstrated data rates vary from 1.8 Gbps (EDRS, operational) to 100+ Gbps (Starlink Gen2, claimed but not independently verified).

**Technology Gap**: Adaptation of OISL protocols for neural spike train data is novel and unproven.

---

### 2. Neuromorphic Processors (SPECULATIVE)

Spiking Neural Network processors proposed for orbital deployment.

| Specification | Proposed Value | Current Technology |
|---------------|----------------|-------------------|
| Processor | Neuromorphic (Loihi-class) | Intel Loihi 2: 1M neurons/chip; Hala Point packs 1,152 chips. SpiNNaker2: 152k neurons/chip, deployed at Sandia (2025). Terrestrial only |
| Neuron Count | 100M per node | ~100× a single Loihi 2 chip; reachable only by multi-chip systems on the ground |
| Power | 50-200W per payload | Loihi 2: ~1W (terrestrial, unverified for space) |
| Radiation Hardening | Required for LEO | Rad-tolerant neuromorphic IP is emerging (BrainChip Akida in Frontgrade Gaisler space-grade parts); IBM NorthPole has heavy-ion test data. No flight-qualified part at 100M-neuron scale |

**Technology Status**: Terrestrial neuromorphic processors run at laboratory and multi-chip scale (Intel Loihi 2 / Hala Point, SpiNNaker2, IBM NorthPole). Radiation-tolerant neuromorphic IP has reached space-grade silicon at small scale (BrainChip Akida via Frontgrade Gaisler). Space deployment at the proposed neuron count still requires thermal management and power scaling that have not been demonstrated.

**Technology Gap**: 
- No radiation-hardened neuromorphic processor at the required scale. Rad-tolerant IP (BrainChip Akida / Frontgrade Gaisler) and rad-tested research parts (IBM NorthPole) exist at far smaller scale
- Power consumption at proposed neuron counts is unknown
- Long-term reliability in space environment is uncharacterized

---

### 3. Neural Data Transmission (HIGHLY SPECULATIVE)

The proposed system would transmit neural data between a hypothetical brain-computer interface and orbital processors.

**Assumptions**:
- High-bandwidth BCI capable of 2-20 Gbps data rates (does not currently exist)
- Neural signals can be encoded as spike trains for transmission
- Round-trip latency <50 ms preserves neural function

**Scientific Basis**: Libet (1983) measured ~350 ms between neural activity and conscious awareness. The assumption that external processing within this window would be imperceptible is extrapolation beyond Libet's experimental conditions.

**Current BCI Technology**: State-of-the-art brain-computer interfaces achieve data rates of ~100-1,000 bits per second (Neuralink claims, unverified). The proposed 2-20 Gbps represents a 10,000,000× increase.

---

## System Architecture

### Satellite Node Components

```
┌─────────────────────────────────────────────────────────────────┐
│                      SATELLITE NODE                              │
├─────────────────────────────────────────────────────────────────┤
│                                                                  │
│   ┌─────────────────────────────────────────────────────────┐   │
│   │                    PAYLOAD BAY                           │   │
│   │  ┌─────────────┐  ┌─────────────┐  ┌─────────────────┐  │   │
│   │  │ Neuromorphic│  │   Memory    │  │  Neural State   │  │   │
│   │  │  Processor  │  │   (HBM)     │  │    Storage      │  │   │
│   │  │   (SNN)     │  │             │  │                 │  │   │
│   │  └─────────────┘  └─────────────┘  └─────────────────┘  │   │
│   └─────────────────────────────────────────────────────────┘   │
│                                                                  │
│   ┌─────────────────────────────────────────────────────────┐   │
│   │                 COMMUNICATION BAY                        │   │
│   │  ┌─────────────┐  ┌─────────────┐  ┌─────────────────┐  │   │
│   │  │    OISL     │  │  Ground RF  │  │   Encryption    │  │   │
│   │  │  Terminal   │  │   Link      │  │    Module       │  │   │
│   │  └─────────────┘  └─────────────┘  └─────────────────┘  │   │
│   └─────────────────────────────────────────────────────────┘   │
│                                                                  │
│   ┌─────────────────────────────────────────────────────────┐   │
│   │                    BUS SYSTEMS                           │   │
│   │  ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌───────────────┐  │   │
│   │  │  Power  │ │  ADCS   │ │ Thermal │ │   Command &   │  │   │
│   │  │ (Solar) │ │         │ │ Control │ │    Data       │  │   │
│   │  └─────────┘ └─────────┘ └─────────┘ └───────────────┘  │   │
│   └─────────────────────────────────────────────────────────┘   │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

**Technology Status by Subsystem**:

| Subsystem | TRL | Notes |
|-----------|-----|-------|
| Satellite Bus | 7-9 | Flight-proven for CubeSats (OreSat, Planet Labs) |
| Ka-band Ground Link | 8-9 | Operational on commercial satellites |
| OISL Terminal | 6-7 | Demonstrated (Starlink, EDRS), not yet widespread |
| Neuromorphic Processor | 3-4 | Lab demonstration only, not space-qualified |
| Neural Protocol | 2 | Conceptual design, no implementation |
| **Full System** | **2** | Conceptual integration only |

---

### Constellation Topology

**Minimum Viable Constellation**: 3 nodes
- Provides continuous coverage with node redundancy
- Triangular formation for inter-node communication
- One ground-visible node at all times from equatorial regions

**Expanded Constellation**: 12+ nodes
- Global 24/7 coverage
- Reduced inter-node hop distance
- Higher redundancy

---

## Role in the Zae Project

This repository is the **Infrastructure** pillar of the [Zae Project](https://github.com/Zae-Project) 4-pillar stack. It defines the orbital host for the synthetic hemisphere: LEO satellites, OISL, SNN payload, ground segment.

| Pillar | Repo | Role |
|---|---|---|
| 🛰️ **Infrastructure** | **arkspace-core** (this repo) | **LEO satellite constellation. OISL. Neuromorphic payload specifications. Latency envelope (<50 ms RTT). Power envelope (50-200W).** |
| 🧠 Interface | [brain-emulation](https://github.com/Zae-Project/brain-emulation) | Atlas-based Brian2 SNN simulation and 3D visualizer. Biological-fidelity reference. |
| ⚡ Engine | [neutral-consciousness-engine](https://github.com/Zae-Project/neutral-consciousness-engine) | Nengo + ROS 2 SNN runtime. Must fit within this repo's latency and power envelope. |
| 🌡️ Substrate | [thermodynamic-core](https://github.com/Zae-Project/thermodynamic-core) | Physical computing paradigm (p-bits, Langevin). Phase 3 target: radiation-hardened stochastic silicon for the payload. |
| 📚 Docs | [zae-docs](https://github.com/Zae-Project/zae-docs) | Authoritative unified architecture and bibliography. |

Per-pillar contract docs:
- Substrate ↔ Infrastructure. [`thermodynamic-core/docs/integration/with-arkspace.md`](https://github.com/Zae-Project/thermodynamic-core/blob/main/docs/integration/with-arkspace.md)
- Engine ↔ Infrastructure. [`docs/integration/consciousness-interface.md`](./docs/integration/consciousness-interface.md)
- Interface ↔ Infrastructure. [`docs/integration/mindtransfer-interface.md`](./docs/integration/mindtransfer-interface.md)

---

## Repository Structure

```
arkspace-core/
├── README.md                           # This file
├── CONTRIBUTING.md                     # Research contribution guidelines
├── docs/
│   ├── architecture/
│   │   ├── exocortex-constellation.md  # Constellation design specification
│   │   ├── satellite-node.md           # Individual node specifications
│   │   └── ground-segment.md           # Ground infrastructure design
│   ├── protocols/
│   │   ├── oisl-neural-protocol.md     # Protocol for neural data over OISL
│   │   └── latency-budget.md           # System latency analysis
│   ├── hardware/
│   │   └── snn-payload.md              # Neuromorphic processor specifications
│   └── integration/
│       ├── mindtransfer-interface.md   # (Planned) BCI integration spec
│       └── consciousness-interface.md  # (Planned) SNN software interface
├── specs/                              # (Planned) YAML specifications
├── reference/                          # (Planned) Research papers and references
└── roadmap/                            # (Planned) Development milestones
```

---

## Getting Started

### For Researchers and Contributors

This is a documentation and research repository. There is no executable code.

1. **Review the architecture documentation**:
   - Start with [exocortex-constellation.md](./docs/architecture/exocortex-constellation.md)
   - Review [latency-budget.md](./docs/protocols/latency-budget.md) for timing analysis
   - Examine [satellite-node.md](./docs/architecture/satellite-node.md) for hardware specs

2. **Understand the technology gaps**:
   - Each document identifies TRL levels and unresolved challenges
   - Speculative components are clearly labeled

3. **Contribute**:
   - See [CONTRIBUTING.md](./CONTRIBUTING.md) for research guidelines
   - Focus on fact-checking, citation improvements, and technical analysis

---

## Research Roadmap

### Phase 1: Foundation (Q1 2026) - Completed January 14, 2026
- [x] Initial architecture documentation
- [x] Preliminary specifications for key subsystems
- [x] Complete OISL protocol specifications (`docs/protocols/oisl-neural-protocol.md`, v0.1)
- [x] Regulatory requirements research (FCC Part 25, ITU, ITAR; under `docs/regulatory/`)
- [x] Cost modeling (per `roadmap/milestones.md` Milestone 1.1)

### Phase 2: Analysis (Q2-Q3 2026)
- [ ] Link budget verification
- [ ] Orbital mechanics simulation
- [ ] Thermal modeling for neuromorphic payload
- [ ] Radiation environment analysis
- [ ] Failure modes and effects analysis (FMEA)

### Phase 3: Technology Assessment (Q4 2026)
- [ ] Survey of available neuromorphic processors
- [ ] Radiation hardening requirements
- [ ] Vendor consultation for OISL terminals
- [ ] Ground station site selection analysis

**Note**: This roadmap addresses documentation and analysis only. Hardware development is not planned pending technology maturation.

---

## Related Projects

See the "Role in the Zae Project" section above for the full 4-pillar table. Canonical remotes under [Zae-Project](https://github.com/Zae-Project):

| Repo | Role | Status |
|---------|------|--------|
| [brain-emulation](https://github.com/Zae-Project/brain-emulation) | Atlas-based Brian2 SNN + 3D visualizer | v1.0 feature-complete |
| [neutral-consciousness-engine](https://github.com/Zae-Project/neutral-consciousness-engine) | Nengo + ROS 2 SNN runtime, Neural Firewall | Research & prototyping |
| [thermodynamic-core](https://github.com/Zae-Project/thermodynamic-core) | p-bits, Langevin substrate (Phase 2 sims landed Apr 2026) | TRL 2-3 |
| [zae-docs](https://github.com/Zae-Project/zae-docs) | Unified architecture + bibliography | Public |

---

## Technology Readiness Assessment

### Established Technology (TRL 7-9)
- CubeSat platforms
- Solar power systems for satellites
- Ka-band ground stations
- Star trackers and ADCS systems

### Emerging Technology (TRL 4-6)
- High-bandwidth OISL (operational in SDA Tranche programs; TESAT SCOT80 to 100 Gbps, SDA OCT Standard 3.1)
- Neuromorphic processors (terrestrial multi-chip: Hala Point, SpiNNaker2, NorthPole)
- Rad-tolerant neuromorphic IP at small scale (BrainChip Akida via Frontgrade Gaisler)

### Conceptual Technology (TRL 1-3)
- Radiation-hardened neuromorphic processors at 100M-neuron scale
- High-bandwidth brain-computer interfaces
- Neural data transmission protocols
- Consciousness substrate transfer (TRL 1, speculative)

---

## Research Resources

For the research materials supporting this project, see the **[Zae Project Bibliography](https://github.com/Zae-Project/zae-docs/blob/main/reference/bibliography.md)** - a centralized repository containing:

- **100+ Key Researchers** - Leading scientists in neuromorphic computing, satellite systems, and consciousness studies
- **50+ Foundational Papers** - Seminal publications with full citations
- **35+ Essential Books** - Organized by topic with reading recommendations
- **Research Institutions & Labs** - Major centers advancing relevant technologies
- **Industry Leaders** - Companies working on neuromorphic hardware and satellite systems

**Relevant Sections for ArkSpace:**
- Neuromorphic Computing (Mead, Boahen, Eliasmith, Furber)
- Satellite Communications (SpaceX, FCC/ITU standards)
- Computational Neuroscience (Sejnowski, Gerstner, Izhikevich)

Also see the **[Researchers Directory](https://github.com/Zae-Project/zae-docs/blob/main/reference/researchers-directory.md)** for detailed profiles and contact information.

### Key References for This Repository

#### Satellite Technology
- Space Mission Analysis and Design (SMAD), 3rd Edition
- OreSat: Open source CubeSat platform
- Starlink FCC filings (OISL specifications)

#### Neuromorphic Computing
- Davies, M., et al. (2021). Advancing Neuromorphic Computing with Loihi 2. Intel Labs.
- Furber, S. B., et al. (2014). The SpiNNaker Project. Proceedings of the IEEE.

#### Neuroscience
- Libet, B., et al. (1983). Time of conscious intention to act in relation to onset of cerebral activity. Brain, 106(3), 623-642.

#### Optical Communication
- TESAT Laser Communication Terminal specifications
- Hemmati, H. (2006). Deep Space Optical Communications. Wiley.

---

## Disclaimer

This repository documents a conceptual system. The feasibility of implementing such a system, particularly for applications involving biological neural interfaces or consciousness, is unproven. Technology gaps are substantial and clearly identified throughout the documentation.

The project makes no claims about the philosophical or scientific validity of consciousness transfer, substrate independence of mind, or related concepts. These remain subjects of ongoing debate in philosophy of mind and neuroscience.

---

## Contact

For technical questions or collaboration inquiries:
- Open an issue in this repository for documentation questions
- Email: info@arkspace.me (if available)

---

## License

See LICENSE file for terms.

---

*This is a research project documenting a proposed system. All specifications are preliminary and subject to revision as technology develops and analysis continues.*
