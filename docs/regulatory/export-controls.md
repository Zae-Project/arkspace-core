# ITAR/EAR Export Controls - Satellite Technology Compliance

**Document Type**: Regulatory Research  
**Regulatory Bodies**: DDTC (ITAR), BIS (EAR)  
**Last Updated**: January 14, 2026  
**Research Status**: Complete  
**Confidence Level**: High

---

## Executive Summary

### Key Findings

- **Satellites are export-controlled** under either ITAR or EAR
- **ITAR applies** to most spacecraft and related components (Category XV)
- **Encryption technology** adds complexity (Category XIII / ECCN 5A002)
- **Neuromorphic processors**: Classification TBD (potentially dual-use)

### Critical Requirements

- ITAR registration required if ITAR-controlled items used
- Export licenses required for non-U.S. persons access
- Encryption items require additional classification
- Strict record-keeping and compliance programs mandatory

### Timeline Impact

- **ITAR Registration**: 2-4 weeks
- **Commodity Jurisdiction (CJ) Determination**: 2-6 months
- **Export License (if required)**: 2-6 months
- **Total potential delay**: 4-12 months for complex items

### Cost Impact

**Estimated Costs**:
- ITAR registration: $2,250 annually
- Legal counsel (export compliance): $25,000-$75,000
- Compliance program setup: $15,000-$50,000
- CJ determinations: $5,000-$15,000 per item
- **Total Estimated**: $47,250-$140,250

---

## Regulatory Framework

### International Traffic in Arms Regulations (ITAR)

**Authority**: 22 CFR Parts 120-130  
**Agency**: Directorate of Defense Trade Controls (DDTC), U.S. Department of State

**Scope**: Defense articles, defense services, and related technical data

**Key Category for ArkSpace**: Category XV - Spacecraft and Related Articles

### Export Administration Regulations (EAR)

**Authority**: 15 CFR Parts 730-774  
**Agency**: Bureau of Industry and Security (BIS), U.S. Department of Commerce

**Scope**: Dual-use items (commercial and military applications)

**Key Categories for ArkSpace**:
- ECCN 9A004: Spacecraft and related equipment
- ECCN 5A002: Information security systems (encryption)

---

## Requirements Analysis

### Requirement 1: Determine ITAR vs. EAR Classification

#### Description

Determine whether ArkSpace satellites and components are ITAR-controlled (defense articles) or EAR-controlled (dual-use).

#### Classification Process

**Step 1: Review USML Category XV**

ITAR Category XV covers:
- Spacecraft (XV.a)
- Ground control stations (XV.b)
- Related commodities specially designed for spacecraft (XV.c)
- Technical data (XV.d)
- Defense services (XV.e)

**Step 2: Check Exclusions (XV.a Note 1)**

Spacecraft may be excluded from ITAR if:
- Not specifically designed or modified for military use
- Commercial communications, remote sensing, or scientific
- Not specially designed for military government end-users

**Step 3: Commodity Jurisdiction (CJ) Request**

If unclear, submit CJ request to DDTC/BIS:
- Detailed technical description
- Intended use
- Customer base
- Military vs. commercial design

**Timeline**: 2-6 months for determination

#### Evidence Required

- [ ] Technical specifications of satellites
- [ ] Design rationale (commercial vs. military)
- [ ] Intended customer base
- [ ] CJ determination letter (if obtained)

#### Responsible Party

**Primary**: Legal Counsel (Export Compliance Specialist)  
**Support**: Engineering team, Regulatory Affairs

#### Risk Assessment

**Probability of ITAR Classification**: Medium-High
- Satellites historically ITAR-controlled
- Recent reforms moved some commercial satellites to EAR
- ArkSpace's unique use case may trigger ITAR

**Mitigation**:
- Emphasize commercial/research nature
- Design satellites without military-specific features
- Request CJ determination early

---

### Requirement 2: ITAR Registration (If Applicable)

#### Description

If any ArkSpace items are ITAR-controlled, company must register with DDTC.

#### Compliance Method

**Registration Process**:
1. Submit DS-2032 Statement of Registration
2. Pay annual registration fee ($2,250)
3. Appoint empowered official
4. Maintain registration (renew annually)

**Timeline**: 2-4 weeks for initial registration

#### Evidence Required

- [ ] Completed DS-2032 form
- [ ] Registration fee payment
- [ ] Empowered official designation

#### Responsible Party

**Primary**: Legal/Compliance Officer  
**Support**: Executive team

#### Cost

- **Annual Fee**: $2,250
- **Legal Support**: $5,000-$15,000 (initial setup)

---

### Requirement 3: Encryption Technology Classification

#### Description

If satellites include encryption (for security, as planned), encryption technology is separately controlled.

#### Classification

**ITAR**: Category XIII - Encryption items designed for military use

**EAR**: ECCN 5A002 - Information security systems (commercial encryption)

**Key Distinction**:
- AES-256 for commercial use: Likely EAR 5A002
- NSA Suite B algorithms: Potentially ITAR Category XIII

#### Compliance Method

**For EAR-controlled encryption (5A002)**:
1. File one-time encryption registration with BIS
2. Submit annual self-classification reports
3. License Exception ENC typically available for most destinations

**Timeline**: 1-2 months for registration

#### Evidence Required

- [ ] Encryption classification request
- [ ] Technical specifications of encryption
- [ ] Intended use cases

---

### Requirement 4: Export Licenses

#### Description

Exporting ITAR or EAR-controlled items requires licenses, except for exemptions.

#### When Required

**ITAR**: Any export to foreign persons (even in U.S.) requires authorization

**EAR**: Depends on item, destination, end-user, and end-use

#### Compliance Method

**For ITAR**:
- Submit DSP-5 (permanent export) or DSP-73 (temporary export)
- Justify export purpose
- Provide end-user information
- **Timeline**: 60-120 days

**For EAR**:
- Determine if license exception applies (e.g., ENC for encryption)
- If not, submit export license application via SNAP-R
- **Timeline**: 30-90 days

#### Risk Assessment

**Foreign Personnel Access Risk**: High
- If non-U.S. persons work on satellites, deemed export occurs
- Requires ITAR license or TAA (Technical Assistance Agreement)

**Mitigation**:
- Use U.S. persons only for ITAR-controlled work
- Obtain TAAs for foreign collaborators
- Segregate non-export-controlled work

---

## Neuromorphic Processor Considerations

### Classification Challenge

**Issue**: Neuromorphic hardware is novel; export classification unclear

**Possible Classifications**:
1. **EAR 3A001**: Electronic components (if general-purpose)
2. **EAR 4A003**: Digital computers (if high-performance)
3. **ITAR Category XV.c**: If "specially designed" for spacecraft

### Recommended Approach

**Step 1**: Request Commodity Jurisdiction (CJ) Determination
- Describe neuromorphic processor in detail
- Emphasize commercial availability (Intel Loihi, etc.)
- Argue not "specially designed" for spacecraft (adaptable design)

**Step 2**: If EAR-controlled, determine ECCN
- Submit classification request to BIS
- Likely 3A001 or 4A003

**Timeline**: 3-6 months total

---

## Compliance Program Requirements

### ITAR Compliance Program

**Required Elements**:
1. Written compliance procedures
2. Export authorization tracking
3. Record retention (5 years minimum)
4. Employee training
5. Internal audits
6. Empowered official oversight

**Cost**: $15,000-$50,000 (setup) + $10,000-$25,000 annual maintenance

### EAR Compliance Program

**Best Practices** (not legally required but recommended):
1. Know your customer (KYC) procedures
2. Export classification tracking
3. Restricted party screening
4. Recordkeeping
5. Training

**Cost**: $10,000-$30,000 (setup) + $5,000-$15,000 annual

---

## Research Sources

### Primary Sources

1. **ITAR (22 CFR Parts 120-130)**
   - URL: https://www.ecfr.gov/current/title-22/chapter-I/subchapter-M
   - Category XV: https://www.ecfr.gov/current/title-22/section-121.1#p-121.1(Category%20XV)

2. **EAR (15 CFR Parts 730-774)**
   - URL: https://www.bis.doc.gov/index.php/regulations/export-administration-regulations-ear
   - Commerce Control List: https://www.ecfr.gov/current/title-15/subtitle-B/chapter-VII/subchapter-C/part-774

3. **DDTC - Directorate of Defense Trade Controls**
   - URL: https://www.pmddtc.state.gov/
   - Registration: https://www.pmddtc.state.gov/ddtc_public/ddtc_public?id=ddtc_public_portal_registration_landing

4. **BIS - Bureau of Industry and Security**
   - URL: https://www.bis.doc.gov/
   - Encryption: https://www.bis.doc.gov/index.php/policy-guidance/encryption

---

## Recommendations

### Immediate Actions

1. **Engage Export Compliance Counsel** (Timeline: Immediately)
   - Specialized in ITAR/EAR for aerospace
   - Budget: $25,000-$50,000

2. **File Commodity Jurisdiction Request** (Timeline: Month 2-3)
   - For satellite platform
   - For neuromorphic processor
   - Budget: $10,000-$20,000

3. **ITAR Registration** (Timeline: Month 1, if advised by counsel)
   - Proactive registration
   - Cost: $2,250 annually

### Long-Term Strategy

**Design for EAR Control**:
- Use commercial-off-the-shelf components where possible
- Avoid military-specific features
- Document commercial design intent

**Conservative Approach**:
- Assume ITAR until CJ determination proves otherwise
- Implement ITAR-compliant procedures from start
- Easier to relax controls than impose later

---

## Revision History

| Version | Date | Researcher | Changes |
|---------|------|------------|---------|
| 1.0.0 | January 14, 2026 | Zae Research Team | Initial export control analysis |

---

**Document Status**: ✅ Complete  
**Next Steps**: Engage export compliance counsel, file CJ requests  
**Dependencies**: Satellite design finalization for accurate classification
