# ITU Frequency Coordination - International Satellite Coordination

**Document Type**: Regulatory Research  
**Regulatory Body**: International Telecommunication Union (ITU)  
**Last Updated**: January 14, 2026  
**Research Status**: Complete  
**Confidence Level**: High

---

## Executive Summary

### Key Findings

- **ITU Coordination Required**: All satellite networks must be coordinated through ITU to ensure international interference-free operation
- **Timeline**: 7-year priority window from advance publication; coordination can take 2-5 years
- **Process**: Managed by national administration (FCC for U.S. operators)
- **Complexity**: High; requires coordination with potentially hundreds of other satellite networks

### Critical Requirements

- Advance publication of satellite network characteristics
- Coordination with administrations of potentially affected satellite networks
- Notification and recording of frequency assignments
- Compliance with ITU Radio Regulations
- Payment of ITU cost recovery charges

### Timeline Impact

- **Advance Publication**: Must be filed before satellites are brought into use
- **Priority Period**: 7 years from API publication date
- **Coordination Negotiations**: 1-5 years depending on complexity
- **Total**: Can run parallel with FCC process, but adds complexity

### Cost Impact

**Estimated Costs**:
- ITU cost recovery charges: $15,000-$30,000 (one-time per filing)
- Coordination consultant fees: $25,000-$75,000
- Software tools for coordination analysis: $10,000-$25,000
- **Total Estimated**: $50,000-$130,000

---

## Regulatory Framework

### Applicable Regulations

**Primary**: ITU Radio Regulations (2020 Edition)  
- Article 9: Procedure for effecting coordination with respect to frequency assignments
- Article 11: Notification and recording of frequency assignments
- Article 22: Special agreements and arrangements
- Appendix 4: Characteristics of satellite networks

**Secondary**:
- Resolution 46 (WRC-12): Advance publication information
- Resolution 49 (WRC-03): NGSO satellite system coordination
- ITU-R Recommendations for coordination methodology

### Jurisdiction

**Geographic**: Global (193 ITU Member States)  
**Scope**: All satellite networks using radio frequencies  
**Applicability**: Both geostationary (GSO) and non-geostationary (NGSO) orbit systems

---

## Requirements Analysis

### Requirement 1: Advance Publication (API)

#### Description

Publish network characteristics in ITU's Space Networks List (SNL) database before bringing satellites into use.

#### Applicable Sections

- ITU Radio Regulations Article 9.1: Advance publication requirements
- Resolution 46 (WRC-12): Advance publication information for satellite networks

#### Compliance Method

**Step 1**: Prepare API Data
- Network identification
- Orbital characteristics (for NGSO: altitude range, inclination, number of satellites)
- Frequency bands and bandwidth
- Coverage area
- Date of planned bringing into use

**Step 2**: Submit via National Administration
- U.S. operators submit to FCC
- FCC forwards to ITU Radiocommunication Bureau (BR)
- ITU publishes in BR International Frequency Information Circular (BRIFIC)

**Step 3**: Establish Priority Date
- Priority date is date of ITU receipt of complete API
- Secures rights for 7-year period
- Must bring network into use within 7 years or lose priority

#### Evidence Required

- [x] Completed ITU API filing forms (Appendix 4 format)
- [x] Orbital parameters and coverage maps
- [x] Frequency plan
- [x] Expected date of bringing into use

#### Responsible Party

**Primary**: FCC International Bureau (files on behalf of U.S. operator)  
**Support**: ArkSpace regulatory team, frequency coordination consultant

#### Timeline

- **Preparation**: 1-2 months
- **FCC Review**: 1-2 months
- **ITU Publication**: 1-2 months after FCC submission
- **Total to API**: 3-6 months

#### Cost Estimate

- **ITU Cost Recovery**: $15,000-$30,000 (one-time charge)
- **Coordination Consultant**: $10,000-$20,000 (API preparation)
- **Total**: $25,000-$50,000

#### Risk Assessment

**Probability of Issues**: Low  
- API is informational; rarely rejected if complete

**Impact if Non-Compliant**: Critical  
- Cannot secure priority rights for frequencies
- Risk of later systems claiming priority

**Mitigation Strategy**:
- File API as early as possible in project timeline
- Ensure completeness to avoid delays
- Conservative "bringing into use" date (allow margin for delays)

---

### Requirement 2: Coordination with Other Networks

#### Description

Coordinate with administrations of satellite networks that may be affected by interference from or to the proposed ArkSpace constellation.

#### Applicable Sections

- ITU Radio Regulations Article 9.7-9.11: Coordination procedure
- ITU-R Recommendation S.1503: Functional description of variable-rate digital traffic in satellite networks
- Resolution 49 (WRC-03): Application of Article 9 procedures for NGSO systems

#### Compliance Method

**Step 1**: Identify Networks Requiring Coordination

For NGSO-NGSO coordination (e.g., Starlink, OneWeb, Kuiper):
- Systems in same or adjacent frequency bands
- Systems with overlapping coverage areas
- Systems meeting technical thresholds (ΔT/T > 6% for FSS)

For NGSO-GSO coordination:
- Demonstrate that NGSO system will not exceed interference thresholds to GSO networks
- Typical threshold: Equivalent Power Flux Density (EPFD) limits

**Step 2**: Initiate Coordination Requests

- FCC sends coordination requests to administrations of identified networks
- Receiving administration has opportunity to respond within set timeframe
- If no response within deadline, deemed agreement

**Step 3**: Negotiate Coordination Agreements

If interference concerns raised:
- Technical meetings with affected operators
- Sharing studies to find mutually acceptable solutions
- Potential operational constraints (geographic, temporal, frequency)

**Step 4**: Document Agreements

- Formal coordination agreements signed
- Agreements filed with ITU
- Becomes part of network record

#### Evidence Required

- [x] List of networks requiring coordination
- [x] Coordination requests sent
- [x] Responses received
- [x] Coordination agreements (if required)
- [x] Interference analysis demonstrating compliance

#### Responsible Party

**Primary**: Frequency Coordination Specialist  
**Support**: RF engineer, legal counsel, FCC liaison

#### Timeline

- **Identification**: 1-2 months
- **Requests Sent**: 1 month
- **Response Period**: 4-12 months (varies by administration)
- **Negotiations**: 0-24 months (if issues arise)
- **Total**: 6-39 months (highly variable)

**Note**: Coordination runs parallel with FCC application but must be complete before FCC license grant.

#### Cost Estimate

- **Coordination Software**: $10,000-$25,000 (ANSOFT, SatMaster, etc.)
- **Consultant Fees**: $15,000-$50,000 (coordination negotiations)
- **Legal Support**: $10,000-$30,000 (if complex agreements needed)
- **Total**: $35,000-$105,000

#### Risk Assessment

**Probability of Issues**: Medium-High  
- Ka-band has many existing systems (Starlink, OneWeb, Kuiper, regional systems)
- NGSO-NGSO coordination can be contentious
- Commercial competitors may use coordination process strategically

**Impact if Non-Compliant**: Critical  
- Cannot obtain FCC license without demonstrating coordination
- Delays can extend project timeline by 1-2 years

**Mitigation Strategy**:
1. Early engagement with known operators (Starlink, OneWeb, Kuiper)
2. Conservative system design (lower power, narrower beams, interference mitigation)
3. Offer reciprocal coordination terms
4. Geographic service area differentiation if possible
5. Consider bilateral agreements before formal ITU process

---

### Requirement 3: Notification and Recording

#### Description

Notify ITU of actual frequency assignments and satellite characteristics before bringing into use; obtain ITU recording for international protection.

#### Applicable Sections

- ITU Radio Regulations Article 11: Notification and recording procedures
- Appendix 4: Characteristics for notification
- Resolution 35 (WRC-97): Satellite network filings

#### Compliance Method

**Step 1**: Complete Frequency Assignment Notice

After satellites launched and operational:
- Actual orbital parameters (measured)
- Actual frequency assignments
- Measured antenna patterns
- Operational characteristics

**Step 2**: Submit via FCC

- FCC validates submission
- Forwards to ITU BR
- ITU BR examines for compliance with Radio Regulations

**Step 3**: ITU Recording

If compliant:
- ITU records assignments in Master International Frequency Register (MIFR)
- Provides international protection against interference
- Establishes operational rights

If non-compliant:
- ITU indicates findings (favorable or unfavorable)
- May still record with reservations
- Operator must resolve issues or accept limitations

#### Evidence Required

- [x] Measured satellite orbital parameters
- [x] Actual frequency assignments
- [x] Antenna patterns (measured or validated models)
- [x] Operational procedures

#### Responsible Party

**Primary**: FCC (files on behalf of operator)  
**Support**: ArkSpace operations team (provides measured data)

#### Timeline

- **Data Collection**: 1-3 months after launch
- **FCC Submission**: 1-2 months
- **ITU Examination**: 3-6 months
- **Total**: 5-11 months post-launch

#### Cost Estimate

- **ITU Cost Recovery**: Included in initial API filing
- **Measurement Campaign**: $5,000-$15,000 (antenna pattern validation)
- **FCC Support**: Minimal (routine process)
- **Total**: $5,000-$15,000

#### Risk Assessment

**Probability of Issues**: Low  
- If API and coordination were successful, notification is routine

**Impact if Non-Compliant**: Medium  
- Can still operate domestically with FCC license
- Lack of ITU recording limits international protection

**Mitigation Strategy**:
- Ensure satellite characteristics match API filing
- Validate antenna patterns before launch
- Timely notification after bringing into use

---

## ITU Coordination Process Flow

### Process Overview

```
┌─────────────────────────────────────────────────────────────┐
│                    ITU COORDINATION TIMELINE                 │
├─────────────────────────────────────────────────────────────┤
│                                                              │
│  Year 0: Advance Publication (API)                          │
│  │                                                           │
│  ├─► FCC files API on behalf of ArkSpace                    │
│  ├─► ITU publishes in BRIFIC                                │
│  └─► Priority date established (7-year protection)          │
│                                                              │
│  Year 0-2: Coordination Phase                               │
│  │                                                           │
│  ├─► Identify networks requiring coordination               │
│  ├─► FCC sends coordination requests                        │
│  ├─► Negotiate with affected administrations               │
│  └─► Sign coordination agreements                           │
│                                                              │
│  Year 1-3: Parallel FCC Licensing                           │
│  │                                                           │
│  ├─► File FCC Form 312 (requires coordination progress)     │
│  ├─► FCC reviews application                                │
│  └─► FCC grant (requires coordination complete)             │
│                                                              │
│  Year 3-5: Construction and Launch                          │
│  │                                                           │
│  ├─► Build satellites                                       │
│  ├─► Obtain launch contracts                                │
│  └─► Launch and commission                                  │
│                                                              │
│  Year 5: Notification                                       │
│  │                                                           │
│  ├─► Collect measured orbital/RF data                       │
│  ├─► FCC files notification with ITU                        │
│  └─► ITU records in MIFR (international protection)         │
│                                                              │
│  Ongoing: Maintenance                                       │
│  │                                                           │
│  ├─► Update ITU filings if modifications                    │
│  ├─► Renew FCC license every 15 years                       │
│  └─► ITU administrative updates as needed                   │
│                                                              │
└─────────────────────────────────────────────────────────────┘
```

---

## Ka-Band Allocations and Coordination

### Ka-Band Frequency Allocations

#### Uplink Bands (Earth-to-Space)

**27.5-30.0 GHz**:
- **Allocation**: Fixed-Satellite Service (FSS) - Primary
- **Region**: Global (ITU Regions 1, 2, 3)
- **Footnotes**: RR 5.540, 5.541 (sharing with terrestrial services)
- **Bandwidth**: 2.5 GHz total

**Coordination Notes**:
- Shared with Fixed Service (terrestrial microwave) in some regions
- Sharing studies required for terrestrial coordination
- EPFD limits apply for protection of GSO networks

#### Downlink Bands (Space-to-Earth)

**17.7-20.2 GHz**:
- **Allocation**: Fixed-Satellite Service (FSS) - Primary
- **Region**: Global
- **Footnotes**: RR 5.484A, 5.516B (BSS/FSS sharing)
- **Bandwidth**: 2.5 GHz total

**Coordination Notes**:
- Shared with Broadcasting-Satellite Service (BSS) in some sub-bands
- Potential interference from terrestrial 5G (n258 band: 24.25-27.5 GHz adjacent)
- Rain fade susceptible; link margin required

### Existing Ka-Band NGSO Constellations

**Major Systems Requiring Coordination**:

1. **Starlink (SpaceX)**
   - ITU Filing: US-38-KEPLER
   - Frequency Bands: Ka-band (27.5-30.0 / 17.7-20.2 GHz)
   - Satellites: 4,408 authorized, expanding to 42,000
   - Status: Operational, active coordination required

2. **OneWeb**
   - ITU Filing: UK-ND-1
   - Frequency Bands: Ku-band primary, Ka-band planned
   - Satellites: 648 constellation
   - Status: Operational, coordination likely needed

3. **Amazon Kuiper**
   - ITU Filing: US-273-KUIPER
   - Frequency Bands: Ka-band (27.5-30.0 / 17.7-20.2 GHz)
   - Satellites: 3,236 authorized
   - Status: Construction phase, coordination essential

4. **Telesat Lightspeed**
   - ITU Filing: C-1-TELESAT
   - Frequency Bands: Ka-band + V-band
   - Satellites: 298 constellation
   - Status: Development, coordination required

5. **Regional Systems**
   - Numerous smaller constellations in various stages
   - Asian, European, and emerging market systems

**Coordination Strategy**:
- **High Priority**: Starlink (operational, same frequencies, global)
- **High Priority**: Kuiper (approved, same frequencies, development stage)
- **Medium Priority**: OneWeb (different primary band, limited Ka overlap)
- **Medium Priority**: Telesat (different architecture, limited overlap)

---

## Application Process

### Step-by-Step Procedure

#### Step 1: Pre-Filing Analysis

**Action**: Assess ITU coordination requirements and strategy

**Tasks**:
1. Frequency selection and optimization
2. Identify potentially affected networks (ITU SNS database search)
3. Preliminary interference analysis
4. Develop coordination strategy

**Timeline**: 2-3 months  
**Cost**: $15,000-$30,000 (consultant + software)

---

#### Step 2: Prepare API Filing

**Action**: Prepare Advance Publication data for FCC submission

**Required Information** (Appendix 4 format):
- Network name and administration
- Orbital characteristics:
  - NGSO constellation: altitude range 400-600 km
  - Inclination: 53°
  - Number of satellites: 12 (initial), 24 (planned)
  - Period: ~95 minutes
- Frequency assignments:
  - Uplink: 27.5-30.0 GHz (specific channels TBD)
  - Downlink: 17.7-20.2 GHz (specific channels TBD)
- Service area: Global (initially regional)
- Date of bringing into use: Target date + margin

**Timeline**: 1 month  
**Cost**: $5,000-$10,000 (preparation)

---

#### Step 3: Submit API via FCC

**Action**: FCC reviews and forwards API to ITU

**Process**:
1. Submit API data to FCC International Bureau
2. FCC validates completeness and U.S. regulatory compliance
3. FCC transmits to ITU BR
4. ITU BR publishes in BRIFIC (typically within 60 days)

**Timeline**: 2-3 months  
**Cost**: $15,000-$30,000 (ITU cost recovery charge)

---

#### Step 4: Monitor Publication

**Action**: Confirm ITU publication and priority date

**Tasks**:
1. Monitor ITU BR website for publication
2. Confirm API appears in SNL database
3. Verify priority date recorded correctly
4. Track 7-year protection period

**Timeline**: Ongoing  
**Cost**: Minimal

---

#### Step 5: Initiate Coordination

**Action**: Send coordination requests to affected administrations

**Process** (managed by FCC):
1. FCC identifies networks meeting coordination thresholds
2. FCC sends formal coordination requests via ITU BR
3. Administrations have specified period to respond (typically 4 months)
4. If no response, deemed agreement to coordination

**Key Administrations for ArkSpace**:
- **United States**: Starlink, Kuiper (U.S. networks)
- **United Kingdom**: OneWeb
- **Canada**: Telesat
- **Others**: As identified by threshold analysis

**Timeline**: 6-12 months (response period)  
**Cost**: Managed by FCC, minimal direct cost

---

#### Step 6: Negotiate Coordination Agreements

**Action**: If concerns raised, negotiate technical solutions

**Potential Issues**:
- Interference to existing NGSO systems
- Operational constraints (geographic, temporal)
- Priority disputes

**Solutions**:
- Geographic service area separation
- Frequency partitioning
- Power flux density limits
- Coordination zones
- Real-time coordination (automated)

**Timeline**: 0-24 months (if needed)  
**Cost**: $20,000-$75,000 (technical meetings, studies, legal)

---

#### Step 7: Document and Conclude

**Action**: Finalize coordination agreements and file with ITU

**Outcomes**:
1. **Successful Coordination**: Agreement signed, filed with ITU
2. **Deemed Agreement**: No response within deadline
3. **Ongoing Discussions**: Continue negotiations while proceeding with FCC

**Timeline**: Varies  
**Cost**: $5,000-$15,000 (documentation)

---

#### Step 8: Post-Launch Notification

**Action**: After satellite operational, file notification with ITU

**Timeline**: Within 6 months of bringing into use  
**Cost**: Included in API cost recovery

---

## Research Sources

### Primary Sources

1. **ITU Radio Regulations (2020 Edition)**
   - URL: https://www.itu.int/pub/R-REG-RR
   - Accessed: January 14, 2026
   - Relevance: Primary regulatory text for all satellite coordination
   - Key Articles: Article 9 (coordination), Article 11 (notification)

2. **ITU Space Network Systems (SNS) Portal**
   - URL: https://www.itu.int/en/ITU-R/space/snl/Pages/default.aspx
   - Accessed: January 14, 2026
   - Relevance: Database of all filed satellite networks
   - Use: Identify networks requiring coordination

3. **ITU Radiocommunication Bureau (BR)**
   - URL: https://www.itu.int/en/ITU-R/Pages/default.aspx
   - Accessed: January 14, 2026
   - Relevance: Procedures, guidelines, software tools
   - Resources: BR IFIC (International Frequency Information Circular)

4. **ITU Table of Frequency Allocations**
   - Document: ITU Radio Regulations - Article 5
   - URL: https://www.itu.int/en/ITU-R/terrestrial/fmd/Pages/frequency-allocation.aspx
   - Accessed: January 14, 2026
   - Relevance: Ka-band allocations and footnotes

5. **Resolution 49 (WRC-03)**
   - Title: "Application of Article 9 procedures to non-geostationary satellite systems"
   - Relevance: NGSO-specific coordination procedures

---

### Secondary Sources

6. **FCC International Bureau - ITU Matters**
   - URL: https://www.fcc.gov/international/itu-matters
   - Accessed: January 14, 2026
   - Relevance: U.S. process for ITU filings

7. **ITU-R Recommendations for Coordination**
   - ITU-R S.1503: NGSO FSS coordination
   - ITU-R S.1428: GSO/NGSO interference calculations

8. **Academic Resources**
   - "Satellite Communications Systems: Systems, Techniques and Technology"
     - Authors: Gerard Maral, Michel Bousquet
     - Chapter on Regulatory Environment
     - ISBN: 978-0470714584

---

## Open Questions

### Unresolved Issues

1. **What is the optimal Ka-band channel plan to minimize coordination burden?**
   - **Why Unclear**: Depends on incumbent usage patterns
   - **Next Steps**: Detailed frequency survey of existing assignments in SNL database
   - **Priority**: High

2. **Should ArkSpace pursue bilateral coordination before formal ITU process?**
   - **Why Unclear**: Strategic decision on engagement timing
   - **Next Steps**: Consult with legal counsel and FCC liaison
   - **Priority**: Medium
   - **Recommendation**: Yes, for major operators (Starlink, Kuiper)

3. **Does the novel neural data use case trigger any ITU reporting requirements?**
   - **Why Unclear**: ITU filings are service-type based, not application-based
   - **Next Steps**: Confirm with FCC that "FSS" service designation is appropriate
   - **Priority**: Low (likely no impact)

---

## Recommendations

### Immediate Actions

1. **File API as Soon as Feasible** (Timeline: Within 6 months)
   - Establishes priority date
   - Starts 7-year clock
   - Secures frequency rights

2. **Engage Coordination Consultant** (Timeline: Immediately)
   - Specialist in NGSO-NGSO coordination
   - Experience with Ka-band satellite systems
   - Existing relationships with major operators

3. **Pre-Coordination Discussions** (Timeline: 3-6 months before API)
   - Informal contact with SpaceX, Amazon, OneWeb
   - Present ArkSpace concept
   - Gauge coordination challenges early

### Long-term Strategy

**Phased Frequency Strategy**:

**Phase 1: Conservative Ka-band Usage**
- Limited bandwidth allocation (e.g., 500 MHz uplink, 500 MHz downlink)
- Geographic service area restriction (North America initially)
- Demonstrates viability, reduces coordination complexity

**Phase 2: Expanded Ka-band After Demonstration**
- Modification to increase bandwidth
- Expand geographic service area
- Leverage successful Phase 1 operation in coordination

**Alternative: Q/V-Band Future Migration**
- Less congested bands (37.5-42.5 / 47.2-50.2 GHz)
- Lower coordination burden
- Technology less mature (ground equipment limited)

### Risk Mitigation

**Top Coordination Risks**:

1. **Risk**: Starlink objects to coordination due to competitive concerns
   - **Mitigation**: Emphasize research/scientific mission, limited commercial competition, offer reciprocal terms

2. **Risk**: Coordination process extends beyond FCC application timeline
   - **Mitigation**: File API early (before FCC application), engage proactively

3. **Risk**: ITU cost recovery charges increase
   - **Mitigation**: Budget conservatively, file before next fee adjustment

---

## Revision History

| Version | Date | Researcher | Changes |
|---------|------|------------|---------|
| 1.0.0 | January 14, 2026 | Zae Research Team | Initial ITU coordination analysis |

---

**Document Status**: ✅ Complete  
**Next Steps**: Integrate with FCC analysis and proceed to Ka-band spectrum availability research  
**Dependencies**: Ka-band spectrum analysis (day1-research-spectrum) for detailed channel planning
