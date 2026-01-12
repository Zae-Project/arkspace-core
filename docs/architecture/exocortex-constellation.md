# Exocortex Constellation Architecture

**Version**: 1.0.0  
**Status**: Specification  
**Last Updated**: January 2026

---

## Overview

The **Exocortex Constellation** is a network of Low Earth Orbit (LEO) satellites designed to serve as distributed neural substrate. Unlike traditional communication satellites, these nodes contain neuromorphic processors that can execute Spiking Neural Networks (SNNs), effectively becoming external brain tissue in orbit.

---

## Design Principles

### 1. Latency-First Architecture

Every design decision prioritizes minimizing round-trip time (RTT) to stay within the Libet buffer (~350ms).

### 2. Redundancy & Fault Tolerance

Neural substrate must be highly reliable. Triple modular redundancy where possible.

### 3. Scalability

Architecture must support expansion from 3 nodes to 100+ nodes without redesign.

### 4. Security by Design

Zero-trust architecture with encryption at every layer.

---

## Constellation Topology

### Minimum Viable Constellation (MVC)

**3 Satellite Nodes** in a Walker Delta pattern:

```
                    N
                    │
         Node A ────┼──── Node B
              \     │     /
               \    │    /
                \   │   /
                 \  │  /
                  \ │ /
                   \│/
                 Node C
                    │
                    S

Orbital Parameters:
- Altitude: 550 km (LEO)
- Inclination: 53°
- Spacing: 120° apart
- Period: ~96 minutes
```

### Benefits of MVC Configuration

| Aspect | Benefit |
|--------|---------|
| **Coverage** | Always 1 node visible from equatorial ground stations |
| **Redundancy** | 2-node failure tolerance for critical operations |
| **Latency** | Maximum 1 hop between any two nodes |
| **Cost** | Minimal viable investment |

### Target Constellation (12+ Nodes)

**Phase 2 Expansion**:
- 4 orbital planes
- 3 satellites per plane
- Global continuous coverage
- <15ms inter-node latency

---

## Orbital Parameters

### Primary Orbit Selection: LEO 550km

| Parameter | Value | Rationale |
|-----------|-------|-----------|
| **Altitude** | 550 km | Balance: low latency vs drag |
| **Inclination** | 53° | Global coverage, avoid polar |
| **Eccentricity** | ~0 (circular) | Consistent latency |
| **RAAN Spacing** | 120° (MVC) | Even coverage |

### Latency Analysis

**Speed of Light Propagation**:
- LEO to Ground (550km): ~1.8ms one-way
- Inter-satellite (max 2,000km): ~6.7ms one-way
- Total single-hop RTT: ~17ms

**With Processing**:
- SNN processing: ~5ms
- Encryption/decryption: ~1ms
- Total system RTT: **<30ms** (target)

---

## Node Architecture

### Satellite Node Block Diagram

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                           SATELLITE NODE v1.0                                │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                              │
│  ┌───────────────────────────────────────────────────────────────────────┐  │
│  │                         PAYLOAD SEGMENT                                │  │
│  │                                                                        │  │
│  │   ┌──────────────────┐   ┌──────────────────┐   ┌─────────────────┐   │  │
│  │   │   NEUROMORPHIC   │   │   HIGH-BANDWIDTH │   │  NEURAL STATE   │   │  │
│  │   │    PROCESSOR     │   │     MEMORY       │   │    STORAGE      │   │  │
│  │   │                  │   │                  │   │                 │   │  │
│  │   │  • Loihi-class   │   │  • HBM2e 32GB    │   │  • NVMe 1TB     │   │  │
│  │   │  • 1M+ neurons   │   │  • 1 TB/s BW     │   │  • Encrypted    │   │  │
│  │   │  • 1B+ synapses  │   │  • ECC protected │   │  • Redundant    │   │  │
│  │   │  • 50-100W       │   │                  │   │                 │   │  │
│  │   └──────────────────┘   └──────────────────┘   └─────────────────┘   │  │
│  │              │                    │                      │             │  │
│  │              └────────────────────┼──────────────────────┘             │  │
│  │                                   │                                    │  │
│  │                         ┌─────────▼─────────┐                          │  │
│  │                         │  PAYLOAD COMPUTER │                          │  │
│  │                         │   (Rad-hardened)  │                          │  │
│  │                         └─────────┬─────────┘                          │  │
│  │                                   │                                    │  │
│  └───────────────────────────────────┼────────────────────────────────────┘  │
│                                      │                                       │
│  ┌───────────────────────────────────┼────────────────────────────────────┐  │
│  │                    COMMUNICATION SEGMENT                               │  │
│  │                                   │                                    │  │
│  │   ┌──────────────────┐   ┌───────▼────────┐   ┌──────────────────┐    │  │
│  │   │   OISL TERMINAL  │   │  COMM ROUTER   │   │   GROUND LINK    │    │  │
│  │   │                  │   │                │   │                  │    │  │
│  │   │  • 60+ Gbps      │◄─►│  • Routing     │◄─►│  • Ka-band RF    │    │  │
│  │   │  • 1550nm laser  │   │  • Encryption  │   │  • 1 Gbps        │    │  │
│  │   │  • Full duplex   │   │  • QoS         │   │  • Steerable     │    │  │
│  │   │  • 2x terminals  │   │                │   │                  │    │  │
│  │   └──────────────────┘   └────────────────┘   └──────────────────┘    │  │
│  │                                                                        │  │
│  └────────────────────────────────────────────────────────────────────────┘  │
│                                                                              │
│  ┌────────────────────────────────────────────────────────────────────────┐  │
│  │                         BUS SEGMENT                                    │  │
│  │                                                                        │  │
│  │   ┌─────────┐  ┌─────────┐  ┌─────────┐  ┌─────────┐  ┌─────────┐    │  │
│  │   │  POWER  │  │  ADCS   │  │ THERMAL │  │  C&DH   │  │STRUCTURE│    │  │
│  │   │         │  │         │  │         │  │         │  │         │    │  │
│  │   │ • Solar │  │ • Star  │  │ • Active│  │ • OBC   │  │ • 12U+  │    │  │
│  │   │   400W  │  │   track │  │   cool  │  │ • Store │  │ • Deploy│    │  │
│  │   │ • Batt  │  │ • React │  │ • Heat  │  │ • TM/TC │  │ • Mount │    │  │
│  │   │   100Wh │  │   wheels│  │   pipes │  │         │  │         │    │  │
│  │   └─────────┘  └─────────┘  └─────────┘  └─────────┘  └─────────┘    │  │
│  │                                                                        │  │
│  └────────────────────────────────────────────────────────────────────────┘  │
│                                                                              │
└──────────────────────────────────────────────────────────────────────────────┘
```

---

## Subsystem Specifications

### 1. Neuromorphic Payload

| Component | Specification | Notes |
|-----------|---------------|-------|
| Processor | Intel Loihi 2 class | Or custom rad-hard equivalent |
| Neuron Count | 1,000,000+ | Per node |
| Synapse Count | 1,000,000,000+ | 1000:1 fan-out |
| Power | 50-100W | Event-driven efficiency |
| Latency | <5ms | For standard inference |
| Radiation | SEU tolerant | TMR on critical paths |

### 2. OISL Terminal

| Component | Specification | Notes |
|-----------|---------------|-------|
| Data Rate | 60-200 Gbps | Full duplex |
| Wavelength | 1550 nm | C-band telecom |
| Range | 5,400 km | Max inter-satellite |
| Acquisition | <10 seconds | Pointing, acquisition, tracking |
| Terminals | 2 per satellite | Mesh connectivity |
| Pointing | ±0.1 arcsec | Fine pointing assembly |

### 3. Power System

| Component | Specification | Notes |
|-----------|---------------|-------|
| Solar Panels | 400W BOL | Body-mounted + deployable |
| Battery | 100 Wh Li-ion | Eclipse operations |
| Bus Voltage | 28V regulated | Standard spacecraft bus |
| Payload Power | 200W average | SNN + comms |

### 4. Ground Link

| Component | Specification | Notes |
|-----------|---------------|-------|
| Frequency | Ka-band (26.5-40 GHz) | High bandwidth |
| Data Rate | 1 Gbps | Downlink/uplink |
| Antenna | Steerable phased array | Ground tracking |
| Coverage | Ground stations every 120° | For continuous contact |

---

## Data Flow Architecture

### Normal Operations

```
┌─────────────────────────────────────────────────────────────────────────┐
│                        NEURAL DATA FLOW                                  │
├─────────────────────────────────────────────────────────────────────────┤
│                                                                          │
│   GROUND                    SPACE                      GROUND            │
│   (User)                 (Constellation)               (Return)          │
│                                                                          │
│   ┌─────────┐            ┌─────────────┐              ┌─────────┐       │
│   │ Neural  │ ──────────►│  Primary    │─────────────►│ Neural  │       │
│   │ Input   │  Uplink    │   Node      │   OISL       │ Output  │       │
│   │ (BCI)   │  1 Gbps    │   (SNN)     │   60 Gbps    │ (Stim)  │       │
│   └─────────┘            └──────┬──────┘              └─────────┘       │
│        │                        │                          ▲             │
│        │                        │ State Sync               │             │
│        │                        ▼                          │             │
│        │                 ┌─────────────┐                   │             │
│        │                 │  Backup     │                   │             │
│        │                 │   Node      │                   │             │
│        │                 │  (Mirror)   │                   │             │
│        │                 └─────────────┘                   │             │
│        │                                                   │             │
│        └───────────────────────────────────────────────────┘             │
│                         (Redundant Path)                                 │
│                                                                          │
└─────────────────────────────────────────────────────────────────────────┘
```

### Consciousness Transfer Between Nodes

For "light-speed travel" between orbital locations:

```
1. FREEZE: Snapshot neural state on Source Node
2. TRANSMIT: Send state via OISL to Destination Node (speed of light)
3. VERIFY: Confirm state integrity at Destination
4. ACTIVATE: Resume processing on Destination Node
5. RETIRE: Safely power down Source Node instance

Total Transfer Time: <100ms for intra-constellation
```

---

## Fault Tolerance

### Redundancy Levels

| Level | Mechanism | Coverage |
|-------|-----------|----------|
| **Node** | Hot standby satellite | Full node failure |
| **Processor** | TMR on neuromorphic | SEU/SEL events |
| **Memory** | ECC + RAID-like | Bit flips |
| **Communication** | Dual OISL + RF backup | Link failure |
| **Power** | Battery + safe mode | Eclipse/anomaly |

### Failure Modes and Responses

| Failure | Detection | Response | Recovery |
|---------|-----------|----------|----------|
| Single Node Loss | Heartbeat timeout | Route around | State transfer to backup |
| OISL Link Loss | BER threshold | Switch to RF | Re-acquire OISL |
| Processor SEU | TMR voting | Scrub memory | Continue operation |
| Power Anomaly | Current monitor | Safe mode | Battery operation |
| Ground Link Loss | Timeout | Store & forward | Next ground pass |

---

## Scalability Path

### Phase 1: Minimum Viable Constellation (3 nodes)
- Proof of concept
- Limited geographic coverage
- Single user capacity

### Phase 2: Regional Constellation (12 nodes)
- 4 orbital planes
- Continuous coverage over populated regions
- Multi-user support

### Phase 3: Global Constellation (36+ nodes)
- Full global coverage
- High capacity
- Inter-planetary link ready

### Phase 4: Solar System Network (100+ nodes)
- Earth-Moon links
- Earth-Mars links
- Consciousness travel at light speed

---

## Regulatory Considerations

### Spectrum Allocation
- Ka-band: Coordination with ITU
- OISL: Unregulated (space-to-space optical)
- UWB ground segment: FCC Part 15

### Orbital Debris
- Compliance with FCC 25-year deorbit rule
- Conjunction assessment with Space Force
- Collision avoidance maneuvers

### Export Control
- ITAR/EAR assessment for neuromorphic hardware
- Encryption export controls

---

## Development Roadmap

### Q1 2026: Architecture Finalization
- [ ] Complete this specification
- [ ] Vendor assessment for components
- [ ] Regulatory pre-filing

### Q2 2026: Simulation & Modeling
- [ ] Orbital dynamics simulation
- [ ] Link budget analysis
- [ ] Thermal modeling

### Q3 2026: Prototype Design
- [ ] Payload breadboard
- [ ] OISL terminal selection
- [ ] Ground segment design

### Q4 2026: Development Start
- [ ] CDR (Critical Design Review)
- [ ] Long-lead procurement
- [ ] Software development

---

## References

1. Starlink Gen2 OISL specifications (public filings)
2. Intel Loihi 2 datasheet
3. OreSat CubeSat platform documentation
4. ESA OISL technology studies
5. NASA LEO communications architecture

---

*Document maintained by ArkSpace.me team*
