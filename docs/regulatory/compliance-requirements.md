# Regulatory Compliance Requirements - ArkSpace Constellation

**Document Type**: Compliance Roadmap  
**Status**: Active  
**Last Updated**: January 14, 2026  
**Scope**: Complete regulatory compliance for LEO neuromorphic satellite constellation

---

## Executive Summary

This document consolidates all regulatory research for the ArkSpace constellation into a comprehensive compliance roadmap. It serves as the master reference for navigating U.S. and international satellite licensing, spectrum allocation, export controls, and orbital debris mitigation requirements.

### Quick Reference

| Regulatory Domain | Primary Authority | Timeline | Est. Cost | Status |
|-------------------|-------------------|----------|-----------|---------|
| **Satellite Licensing** | FCC Part 25 | 6-12 months | $158k-$308k | Not started |
| **Frequency Coordination** | ITU Article 9 | 12-18 months | $75k-$150k | Not started |
| **Spectrum Allocation** | FCC/ITU Ka-band | Concurrent with above | Included | Not started |
| **Export Controls** | DDTC/BIS | 3-6 months | $25k-$75k | Not started |
| **Orbital Debris** | FCC/NASA | Concurrent with licensing | $25k-$50k | Not started |
| **TOTAL** | - | **18-24 months** | **$283k-$583k** | - |

### Critical Path

1. **Months 1-3**: Prepare FCC Form 312 application + technical exhibits
2. **Months 2-6**: File ITU advance publication (parallel track)
3. **Months 4-9**: FCC review + ITU coordination
4. **Months 6-12**: Address coordination comments + DDTC commodity jurisdiction
5. **Months 12-18**: License grant + ITU filing completion
6. **Months 18-24**: Buffer for delays + final approvals

### Mission-Critical Requirements

**Before Launch**:
- ✅ FCC space station license granted
- ✅ ITU frequency coordination completed
- ✅ ITAR/EAR export determination finalized
- ✅ Orbital debris mitigation plan approved
- ✅ Insurance/bonding secured ($100M recommended)

---

## 1. FCC Part 25 - Satellite Licensing

**Full Details**: See [fcc-part25-requirements.md](./fcc-part25-requirements.md)

### Overview

The Federal Communications Commission (FCC) requires all U.S. satellite operators to obtain authorization under 47 CFR § 25 before launching any spacecraft. This is the **primary regulatory bottleneck** for ArkSpace deployment.

### Key Requirements

| Requirement | Description | Deadline |
|-------------|-------------|----------|
| **FCC Form 312** | Complete space station authorization application | Before filing |
| **Technical Exhibits** | Orbital parameters, frequencies, link budgets, coverage maps | With Form 312 |
| **Debris Mitigation** | Plan for 25-year post-mission disposal or natural decay | With Form 312 |
| **Financial Qualifications** | Demonstrate funding for construction + operations | With Form 312 |
| **ITU Coordination** | Evidence of international frequency coordination | During review |

### Timeline

- **Application Preparation**: 2-3 months
- **FCC Review**: 6-12 months (routine processing)
- **Total**: **8-15 months**

### Costs

| Item | Cost Range |
|------|------------|
| Filing fees (FCC) | $82,570 |
| Legal counsel (space law firm) | $50,000 - $150,000 |
| Technical studies (link budgets, interference) | $25,000 - $75,000 |
| **TOTAL** | **$157,570 - $307,570** |

### ArkSpace-Specific Considerations

**Constellation Parameters**:
- Altitude: 550 km (LEO)
- Orbital planes: 3 planes, 60° inclination
- Number of satellites: 9 initial deployment (3 per plane)
- Frequency: Ka-band NGSO FSS

**Potential Issues**:
- ⚠️ **Frequency coordination with Starlink, Kuiper, OneWeb**: High traffic in Ka-band requires careful coordination
- ⚠️ **Novel payload (neuromorphic processors)**: May require additional technical explanation
- ⚠️ **Inter-satellite links (OISL)**: Optical links currently under FCC review for streamlined licensing

**Mitigation Strategy**:
- File early (months before planned launch date)
- Engage specialized space law firm (recommendations: Hogan Lovells, Milbank)
- Proactively coordinate with existing NGSO operators
- Prepare detailed OISL technical narrative

---

## 2. ITU Frequency Coordination

**Full Details**: See [itu-coordination.md](./itu-coordination.md)

### Overview

The International Telecommunication Union (ITU) governs global spectrum allocation and requires coordination between satellite operators to prevent harmful interference. This process runs **parallel** to FCC licensing.

### Key Requirements

| Requirement | Description | Deadline |
|-------------|-------------|----------|
| **Advance Publication (API)** | File 7 years before planned launch | ASAP for priority |
| **Coordination Under Article 9** | Negotiate with affected administrations | After API |
| **Bringing Into Use (BIU)** | Notify ITU within 7 years of API | After launch |

### Timeline

- **API Filing**: Immediate (to secure priority)
- **Coordination Period**: 6-12 months
- **Total**: **12-18 months** (parallel with FCC)

### Costs

| Item | Cost Range |
|------|------------|
| ITU filing fees | $5,000 - $15,000 |
| Coordination meetings/consultants | $50,000 - $100,000 |
| Legal support (international) | $20,000 - $35,000 |
| **TOTAL** | **$75,000 - $150,000** |

### ArkSpace-Specific Considerations

**Frequency Bands Requested**:
- **Uplink**: 27.5-30.0 GHz (Earth-to-space)
- **Downlink**: 17.7-20.2 GHz (space-to-Earth)
- **OISL**: 1550 nm optical (no ITU coordination required)

**Coordination Obligations**:
- Must coordinate with all administrations within:
  - ±2.5° orbital separation for co-frequency NGSO systems
  - Visible coverage area for GSO systems

**Known Conflicts**:
- Starlink (SpaceX): ~6,000 satellites in Ka-band
- Kuiper (Amazon): 3,236 satellites planned
- OneWeb: 648 satellites (Ku-band, lower conflict risk)

**Strategy**:
- File API through U.S. State Department → FCC → ITU
- Engage coordination consultant (recommendation: Transfinite Systems, Steptoe & Johnson)
- Leverage existing coordination agreements between U.S. and major administrations

---

## 3. Ka-Band Spectrum Allocation

**Full Details**: See [ka-band-spectrum.md](./ka-band-spectrum.md)

### Overview

Ka-band (26.5-40 GHz) is heavily congested but offers high bandwidth necessary for neural data transmission. ArkSpace requires Non-Geostationary Satellite Orbit Fixed-Satellite Service (NGSO-FSS) allocation.

### Allocated Bands

| Band | Frequency Range | Allocation | Status |
|------|----------------|------------|---------|
| **Ka-band Uplink** | 27.5-30.0 GHz | NGSO FSS (primary) | Available |
| **Ka-band Downlink** | 17.7-20.2 GHz | NGSO FSS (primary) | Available |
| **Q/V-band** | 37.5-42.5 GHz / 47.2-50.2 GHz | Future expansion | Optional |

### Interference Environment

**Existing Ka-band NGSO Systems**:
- SpaceX Starlink: 29,988 authorized satellites
- Amazon Kuiper: 3,236 planned satellites
- Telesat Lightspeed: 298 satellites
- OneWeb Gen 2: Expansion planned

**Equivalent Power Flux Density (EPFD) Limits**:
- Must not exceed ITU Radio Regulations limits
- ArkSpace edge node network distribution reduces individual satellite EPFD

### ArkSpace Bandwidth Budget

**Per-Satellite Links**:
- Ground-to-satellite uplink: 1-10 Gbps
- Satellite-to-ground downlink: 1-10 Gbps
- OISL (optical): 60-200 Gbps (no RF interference)

**Justification for Spectrum Request**:
- Neural data streams: 100 Mbps - 1 Gbps per user
- Distributed SNN state synchronization: 10-60 Gbps inter-satellite
- Low-latency requirement (<10ms) necessitates LEO + high bandwidth

---

## 4. Export Controls - ITAR/EAR

**Full Details**: See [export-controls.md](./export-controls.md)

### Overview

Satellite technology and neuromorphic processors may be subject to **International Traffic in Arms Regulations (ITAR)** or **Export Administration Regulations (EAR)**. Misclassification can result in criminal penalties.

### Classification Process

**Step 1: Commodity Jurisdiction (CJ) Request**
- Submit CJ-1 form to Directorate of Defense Trade Controls (DDTC)
- Describe: Satellite bus, neuromorphic payload, OISL, encryption
- Timeline: 45-90 days for determination

**Step 2: Registration**
- If ITAR: Register with DDTC ($2,250 annual fee)
- If EAR: No registration required, but must comply with export licensing

### Likely Classification

| Component | Likely Classification | Rationale |
|-----------|----------------------|-----------|
| **Satellite Bus** | ITAR Category XV | Spacecraft systems typically ITAR-controlled |
| **Neuromorphic Processor** | EAR ECCN 3A001 or 4A003 | May qualify for EAR if commercial AI/ML technology |
| **OISL System** | ITAR Category XII(c) | Laser communication systems often ITAR |
| **Encryption** | EAR ECCN 5A002/5D002 | Cryptographic equipment (may require TSU review) |

### Costs

| Item | Cost Range |
|------|------------|
| DDTC registration (if ITAR) | $2,250/year |
| CJ request legal support | $15,000 - $50,000 |
| Export license applications | $5,000 - $20,000 |
| Compliance program development | $10,000 - $25,000 |
| **TOTAL** | **$25,000 - $75,000** (Year 1) |

### ArkSpace Strategy

**Recommended Approach**:
1. Submit CJ requests **early** (before finalizing hardware suppliers)
2. Argue for EAR classification where possible (easier compliance)
3. If ITAR: Restrict foreign person access during development
4. Implement Technology Control Plan (TCP) for mixed teams

**Foreign Collaboration Considerations**:
- If international partners involved → likely ITAR license required
- Consider International Traffic in Arms Regulations (ITAR) § 120.22 ("Significant Military Equipment")

---

## 5. Orbital Debris Mitigation

**Full Details**: See [orbital-debris.md](./orbital-debris.md)

### Overview

FCC requires all satellite operators to demonstrate compliance with orbital debris mitigation guidelines, codified in DA 20-1170 (2020). The **25-year deorbit rule** is the primary requirement.

### Key Requirements

| Requirement | Description | ArkSpace Compliance |
|-------------|-------------|---------------------|
| **25-Year Disposal** | Spacecraft must deorbit or move to graveyard within 25 years post-mission | ✅ Natural decay in ~5 years at 550 km |
| **Collision Avoidance** | Active tracking and maneuver capability | ✅ Propulsion system required |
| **Passivation** | Depletion of stored energy after mission | ✅ Battery discharge + propellant venting |
| **Casualty Risk** | <1:10,000 risk of human casualty from reentry | ✅ Small satellites (<100 kg) typically compliant |

### ArkSpace Orbital Parameters

**Constellation Design**:
- Altitude: **550 km** (LEO)
- Inclination: 60°
- Satellite mass: ~50 kg (6U CubeSat class)

**Natural Decay Time**:
- At 550 km: **~5 years** (well under 25-year limit)
- No active deorbit propulsion needed if mission life <4 years
- Backup propulsion: Cold gas thrusters (50 m/s ΔV)

### Analysis Tools

**NASA DAS (Debris Assessment Software)**:
- Free download: https://orbitaldebris.jsc.nasa.gov/mitigation/debris-assessment-software.html
- Required for FCC filing
- Run analysis early to identify issues

**IADC Guidelines**:
- International coordination body for debris mitigation
- Voluntary compliance demonstrates best practices

### Costs

| Item | Cost Range |
|------|------------|
| NASA DAS analysis | $5,000 - $15,000 (consultant) |
| Propulsion system (if needed) | $10,000 - $30,000 per satellite |
| Tracking/conjunction analysis service | $5,000 - $10,000/year |
| **TOTAL** | **$25,000 - $50,000** |

---

## Compliance Timeline - Integrated View

```
MONTH    FCC PART 25              ITU COORDINATION         EXPORT CONTROLS          DEBRIS MITIGATION
─────────────────────────────────────────────────────────────────────────────────────────────────────
0-3      • Prepare Form 312       • File API               • File CJ requests       • Run NASA DAS
         • Draft exhibits         • Notify affected        • DDTC registration      • Design passivation
         • Engage legal counsel     administrations          (if ITAR)                system

3-6      • Submit Form 312        • Begin coordination     • Receive CJ             • Finalize debris plan
         • FCC assigns case         meetings                 determination          • Include in Form 312
         • Initial review         • Negotiate agreements   • Apply for export         exhibits
                                                              licenses (if needed)

6-9      • FCC technical review   • Resolve objections     • Implement TCP          • Address FCC questions
         • Respond to questions   • Document coordination  • Train team on          • Update analysis if
         • ITU coordination       • BRIFIC publication       compliance               design changes
           evidence

9-12     • Public comment period  • Finalize agreements    • Export license         • Final approval
         • Address oppositions    • File coordination        granted                • Include in
         • FCC decision             results with FCC                                  operations manual

12-18    • LICENSE GRANTED        • BIU notification       • Ongoing compliance     • Pre-launch review
         • Post-grant filings       (after launch)         • Annual DDTC reports    • Tracking contract
                                                                                       signed
```

---

## Risk Assessment

### High-Risk Items

| Risk | Impact | Likelihood | Mitigation |
|------|--------|------------|------------|
| **FCC coordination delays with Starlink/Kuiper** | 6+ month delay | Medium | Proactive coordination, file early |
| **ITAR classification of neuromorphic hardware** | Foreign talent restrictions | Medium | Pursue EAR classification, file CJ early |
| **ITU coordination failures** | Cannot operate in frequency | Low | Hire experienced ITU consultant |
| **Debris plan rejection** | Redesign propulsion system | Low | Conservative design, use NASA DAS early |

### Medium-Risk Items

- **Legal costs exceed budget**: Engage fixed-fee arrangements where possible
- **Timeline delays**: Build 6-month buffer into launch schedule
- **Regulatory changes**: Monitor FCC rulemaking dockets

### Low-Risk Items

- Technical qualifications (well-established CubeSat heritage)
- Financial qualifications (demonstrate seed funding)
- Launch provider licensing (use licensed provider like SpaceX/RocketLab)

---

## Recommended Next Steps

### Immediate Actions (Week 1-4)

1. **Engage Legal Counsel**
   - Interview 3+ space law firms
   - Select firm with FCC Part 25 + ITU experience
   - Budget: $50k-$150k for full licensing support

2. **File ITU API**
   - Prepare API form (via FCC ICFS system)
   - File through U.S. State Department
   - Cost: $5,000 - $10,000
   - **Critical**: Start 7-year priority clock

3. **Initiate CJ Process**
   - Prepare detailed hardware descriptions
   - File CJ-1 with DDTC
   - Parallel track: consult with BIS on EAR classification

### Near-Term Actions (Month 2-6)

4. **Prepare FCC Form 312**
   - Complete Schedule S (technical)
   - Draft narrative exhibits
   - Run link budget analysis
   - Create coverage maps

5. **Run NASA DAS Analysis**
   - Input orbital parameters
   - Calculate casualty risk
   - Generate debris mitigation report

6. **Begin ITU Coordination**
   - Identify affected administrations
   - Schedule coordination meetings
   - Prepare frequency plans

### Long-Term Actions (Month 6-18)

7. **Submit FCC Application**
   - File Form 312 with all exhibits
   - Pay filing fees ($82,570)
   - Monitor case status via ICFS

8. **Coordinate with Existing Operators**
   - SpaceX, Amazon, Telesat
   - Document agreements
   - Update FCC with coordination results

9. **Finalize Export Compliance**
   - Receive CJ determination
   - Apply for export licenses (if needed)
   - Implement Technology Control Plan

---

## Budget Summary

| Category | Low Estimate | High Estimate | Notes |
|----------|-------------|---------------|-------|
| **FCC Licensing** | $157,570 | $307,570 | Includes fees, legal, technical studies |
| **ITU Coordination** | $75,000 | $150,000 | Consultant, meetings, legal |
| **Export Controls** | $25,000 | $75,000 | CJ process, registration, licenses |
| **Debris Mitigation** | $25,000 | $50,000 | Analysis, propulsion, tracking |
| **Contingency (15%)** | $42,385 | $87,385 | Unexpected delays, additional studies |
| **TOTAL** | **$324,955** | **$669,955** | 18-24 month process |

**Recommended Budget**: $500,000 (mid-range + contingency)

---

## Responsible Parties

| Domain | Internal Lead | External Support |
|--------|--------------|------------------|
| **FCC Licensing** | Chief Technology Officer | Space law firm (Hogan Lovells, Milbank) |
| **ITU Coordination** | Spectrum Manager | ITU consultant (Transfinite, Steptoe) |
| **Export Controls** | Chief Compliance Officer | Export counsel (Berliner Corcoran) |
| **Debris Mitigation** | Chief Engineer | Orbital analyst (AGI/Slingshot) |
| **Overall Program** | VP Regulatory Affairs | - |

---

## References

### Internal Documents
- [FCC Part 25 Requirements](./fcc-part25-requirements.md)
- [ITU Coordination Process](./itu-coordination.md)
- [Ka-Band Spectrum Analysis](./ka-band-spectrum.md)
- [Export Controls Guide](./export-controls.md)
- [Orbital Debris Mitigation](./orbital-debris.md)

### External Resources
- FCC International Bureau: https://www.fcc.gov/international
- ITU Radiocommunication Bureau: https://www.itu.int/en/ITU-R/
- DDTC (State Dept): https://www.pmddtc.state.gov/
- NASA Orbital Debris: https://orbitaldebris.jsc.nasa.gov/

### Key Regulations
- 47 CFR § 25 (FCC Satellite Rules)
- ITU Radio Regulations Article 9
- 22 CFR § 120-130 (ITAR)
- 15 CFR § 730-774 (EAR)

---

**Document Status**: Active  
**Next Review**: Monthly during application process  
**Owner**: VP Regulatory Affairs  
**Classification**: Internal Use Only
