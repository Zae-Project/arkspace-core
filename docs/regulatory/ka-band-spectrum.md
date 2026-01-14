# Ka-Band Spectrum Availability Analysis

**Document Type**: Regulatory Research  
**Focus**: Frequency Allocation and Coordination  
**Last Updated**: January 14, 2026  
**Research Status**: Complete  
**Confidence Level**: High

---

## Executive Summary

### Key Findings

- **Ka-band is heavily allocated** but usable with proper coordination
- **Primary competition**: Starlink, Kuiper, OneWeb (NGSO mega-constellations)
- **Available bandwidth**: 2.5 GHz uplink / 2.5 GHz downlink (full allocation)
- **Realistic usable**: 500 MHz - 1 GHz per direction after coordination

### Spectrum Allocations

**Uplink (Earth-to-Space)**: 27.5 - 30.0 GHz  
**Downlink (Space-to-Earth)**: 17.7 - 20.2 GHz  
**Service**: Fixed-Satellite Service (FSS) - Primary allocation globally

### Competition Analysis

1. **Starlink**: Operational, 4,408+ satellites, same Ka-band frequencies
2. **Amazon Kuiper**: Authorized 3,236 satellites, Ka-band primary
3. **OneWeb**: 648 satellites, Ku-band primary (limited Ka overlap)
4. **Regional systems**: Various smaller constellations

### Coordination Strategy

- **Geographic differentiation**: Focus on specific service areas
- **Frequency segmentation**: Use specific sub-bands (e.g., 28-29 GHz up, 18-19 GHz down)
- **Time-based sharing**: Coordinate with operational schedules
- **Power management**: Conservative EIRP limits to minimize interference

---

## ITU Frequency Allocations

### Uplink Bands (27.5-30.0 GHz)

**Allocation Table** (ITU Radio Regulations Article 5):

| Band (GHz) | Service | Status | Regions | Footnotes |
|------------|---------|--------|---------|-----------|
| 27.5-28.35 | FSS (Earth-to-space) | Primary | 1, 2, 3 | 5.540 |
| 28.35-28.45 | FSS (Earth-to-space) | Primary | 1, 2, 3 | 5.540 |
| 28.45-28.94 | FSS (Earth-to-space) | Primary | 1, 2, 3 | 5.540 |
| 28.94-29.10 | FSS (Earth-to-space) | Primary | 1, 2, 3 | 5.540, 5.541 |
| 29.10-29.25 | FSS (Earth-to-space) | Primary | 1, 2, 3 | 5.540, 5.541 |
| 29.25-29.46 | FSS (Earth-to-space) | Primary | 1, 2, 3 | 5.540 |
| 29.46-30.00 | FSS (Earth-to-space) | Primary | 1, 2, 3 | 5.540 |

**Total Uplink Bandwidth**: 2.5 GHz

**Sharing Requirements**:
- RR 5.540: Coordination with Fixed Service (terrestrial microwave)
- RR 5.541: Specific conditions for protection of GSO networks

### Downlink Bands (17.7-20.2 GHz)

**Allocation Table**:

| Band (GHz) | Service | Status | Regions | Footnotes |
|------------|---------|--------|---------|-----------|
| 17.7-18.1 | FSS (space-to-Earth) | Primary | 1, 2, 3 | 5.484A |
| 18.1-18.4 | FSS (space-to-Earth) | Primary | 1, 2, 3 | 5.484A |
| 18.4-18.6 | FSS (space-to-Earth) | Primary | 1, 2, 3 | 5.484A, 5.516B |
| 18.6-18.8 | FSS (space-to-Earth) | Primary | 1, 2, 3 | 5.484A, 5.516B, 5.519 |
| 18.8-19.3 | FSS (space-to-Earth) | Primary | 1, 2, 3 | 5.484A, 5.516B |
| 19.3-19.7 | FSS (space-to-Earth) | Primary | 1, 2, 3 | 5.484A, 5.520 |
| 19.7-20.2 | FSS (space-to-Earth) | Primary | 1, 2, 3 | 5.484A |

**Total Downlink Bandwidth**: 2.5 GHz

**Sharing Requirements**:
- RR 5.484A: EPFD limits for protection of GSO FSS
- RR 5.516B: Sharing with Broadcasting-Satellite Service (BSS)

---

## Existing NGSO Constellation Analysis

### Major Operators in Ka-Band

#### 1. Starlink (SpaceX)

**ITU Filing**: US-38-KEPLER (and subsequent modifications)

**Frequency Usage**:
- Uplink: 27.5-30.0 GHz (full band)
- Downlink: 17.7-20.2 GHz (full band)
- User terminals: 10.7-12.7 GHz (Ku-band also used)

**Constellation Size**:
- Phase 1: 4,408 satellites (FCC authorized)
- Future phases: Up to 42,000 satellites planned

**Operational Status**: Fully operational (3,000+ satellites on-orbit as of 2026)

**Coordination Impact**: **CRITICAL**
- Direct frequency overlap
- Global coverage area overlap
- Must coordinate before FCC license grant

#### 2. Amazon Kuiper

**ITU Filing**: US-273-KUIPER

**Frequency Usage**:
- Uplink: 27.5-30.0 GHz (full Ka-band)
- Downlink: 17.7-20.2 GHz (full Ka-band)

**Constellation Size**: 3,236 satellites (FCC authorized)

**Operational Status**: Construction phase, launches planned 2026-2029

**Coordination Impact**: **HIGH**
- Same frequencies as ArkSpace target
- Global service area
- Coordination required before FCC grant

#### 3. OneWeb

**ITU Filing**: UK-ND-1

**Frequency Usage**:
- Primary: Ku-band (10.7-12.75 / 14.0-14.5 GHz)
- Secondary: Ka-band planned for future expansion

**Constellation Size**: 648 satellites

**Operational Status**: Operational (600+ satellites)

**Coordination Impact**: **MEDIUM**
- Limited Ka-band usage currently
- Potential future coordination

#### 4. Telesat Lightspeed

**ITU Filing**: C-1-TELESAT

**Frequency Usage**:
- Ka-band: 27.5-30.0 / 17.7-20.2 GHz
- V-band: 37.5-42.5 / 47.2-50.2 GHz (primary)

**Constellation Size**: 298 satellites

**Operational Status**: Development phase

**Coordination Impact**: **MEDIUM**
- V-band primary, Ka-band secondary
- Smaller constellation

---

## Recommended Frequency Plan for ArkSpace

### Conservative Approach

**Target Allocation**:
- **Uplink**: 28.6-29.1 GHz (500 MHz)
- **Downlink**: 18.8-19.3 GHz (500 MHz)

**Rationale**:
1. Center portions of band (less edge effects)
2. Avoid heavily used sub-bands where possible
3. Sufficient for initial 12-satellite constellation

**Data Rate Support**:
- 500 MHz bandwidth supports ~1-5 Gbps per link (depending on modulation)
- Adequate for compressed neural data streams

### Aggressive Approach (If coordination successful)

**Target Allocation**:
- **Uplink**: 28.0-29.0 GHz (1 GHz)
- **Downlink**: 18.0-19.0 GHz (1 GHz)

**Rationale**:
- Larger bandwidth for future growth
- Supports higher data rates (2-10 Gbps)

**Risk**: Requires extensive coordination and may face opposition

---

## Interference Analysis

### NGSO-to-NGSO Interference

**Key Challenge**: Multiple NGSO constellations in same frequency bands

**Mitigation Techniques**:

1. **Geographic Separation**:
   - Focus ArkSpace on specific regions (e.g., North America initially)
   - Reduces simultaneous visibility with competitor satellites

2. **Frequency Coordination Zones**:
   - Bilateral agreements with Starlink/Kuiper
   - Time/frequency sharing arrangements

3. **Adaptive Beam Steering**:
   - Dynamically avoid interference directions
   - Requires sophisticated antenna systems

4. **Power Flux Density Limits**:
   - Conservative EIRP to minimize interference footprint
   - May reduce link capacity but improves coordination

### NGSO-to-GSO Protection

**Requirement**: Must not exceed EPFD limits to protect geostationary satellites

**EPFD Limits** (ITU Radio Regulations Article 22):
- Single-entry EPFD: -165 dB(W/m²/40 kHz) for 17.7-19.7 GHz
- Aggregate EPFD: -160 dB(W/m²/40 kHz)

**Compliance Method**:
- Automated satellite pointing algorithms
- Exclusion zones around GSO arc
- Demonstrated in FCC application

---

## Coordination Timeline

### Phase 1: Frequency Selection (Months 1-2)

**Tasks**:
- Analyze ITU SNS database for existing filings
- Identify least congested sub-bands
- Model interference scenarios

**Deliverable**: Recommended frequency plan

### Phase 2: Pre-Coordination Discussions (Months 3-6)

**Tasks**:
- Informal contact with SpaceX, Amazon
- Present ArkSpace concept and proposed frequencies
- Identify potential objections early

**Deliverable**: Feedback from major operators

### Phase 3: Formal ITU Coordination (Months 6-18)

**Tasks**:
- FCC files coordination requests
- Respond to coordination requests from other administrations
- Negotiate agreements if interference concerns raised

**Deliverable**: Coordination agreements or deemed acceptance

### Phase 4: FCC License Grant (Month 18+)

**Requirement**: Coordination substantially complete before FCC grant

---

## Spectrum Management Plan

### Dynamic Spectrum Use

**Concept**: Real-time frequency management to avoid interference

**Implementation**:
1. **Spectrum Sensing**: Monitor Ka-band for interference
2. **Cognitive Algorithms**: Select least-congested channels
3. **Coordination Database**: Real-time sharing with other operators

**Technology**: Software-
