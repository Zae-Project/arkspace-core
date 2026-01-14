# FCC Part 25 Requirements - Satellite Licensing for Private Constellations

**Document Type**: Regulatory Research  
**Regulatory Body**: Federal Communications Commission (FCC)  
**Last Updated**: January 14, 2026  
**Research Status**: Complete  
**Confidence Level**: High

---

## Executive Summary

### Key Findings

- **Licensing Required**: All U.S. satellite operators must obtain FCC authorization under Part 25 before launch
- **Timeline**: Typical processing takes 6-12 months for routine applications
- **Cost**: Filing fees range from $15,000-$150,000 depending on constellation size
- **Compliance Burden**: Moderate to high; requires detailed technical documentation and ongoing reporting

### Critical Requirements

- FCC Form 312 application with complete technical exhibits
- Frequency coordination with existing operators and ITU filings
- Orbital debris mitigation plan (25-year deorbit rule)
- Insurance or financial responsibility demonstration
- Annual reporting and license renewal every 15 years

### Timeline Impact

- **Minimum**: 6 months from filing to grant (if no issues)
- **Typical**: 9-12 months with standard processing
- **Extended**: 18+ months if significant coordination issues arise

### Cost Impact

**Estimated Total Costs for ArkSpace Constellation:**
- Application filing fees: $82,570
- Legal counsel (specialized space law): $50,000-$150,000
- Technical studies (link budgets, interference analysis): $25,000-$75,000
- **Total Estimated**: $157,570 - $307,570

---

## Regulatory Framework

### Applicable Regulations

**Primary**: 47 CFR § 25 - Satellite Communications  
- Subpart B: Applications and Licenses (§ 25.101-25.165)
- Subpart C: Technical Standards (§ 25.201-25.222)
- Subpart D: Competitive Bidding (§ 25.251-25.262)

**Secondary**:  
- 47 CFR § 1 - Practice and Procedure (filing requirements)
- 47 CFR § 0 - Commission Organization (fee schedules)

**Recent Updates**:
- DA 20-1170 (2020): Enhanced orbital debris mitigation rules
- DA 18-313 (2018): Processing Round for NGSO FSS systems
- FCC 20-54 (2020): Earth Station licensing reform

### Jurisdiction

**Geographic**: United States and territories  
**Scope**: All satellite systems operated by U.S. entities or foreign entities seeking U.S. market access  
**Applicability**: Commercial, private, and government-commercial hybrid systems

---

## Requirements Analysis

### Requirement 1: FCC Form 312 Application

#### Description

Complete Application for Space Station Radio Authorization (FCC Form 312) with required technical schedules and exhibits.

#### Applicable Sections

- 47 CFR § 25.114: Application requirements for space station authorizations
- 47 CFR § 25.115: Application for earth station authorizations (if applicable)
- 47 CFR § 25.142: Licensing provisions for NGSO-like satellite systems

#### Compliance Method

**Step 1**: Prepare Technical Narrative
- System architecture description
- Service objectives
- Link budget calculations
- Coverage maps

**Step 2**: Complete Schedule S (Technical Information)
- Orbital parameters (altitude, inclination, eccentricity)
- Frequency bands requested (Ka-band: 27.5-30.0 GHz uplink, 17.7-20.2 GHz downlink)
- Antenna characteristics
- Power levels (EIRP calculations)
- Emission designators

**Step 3**: Prepare Required Exhibits
- Exhibit A: Legal qualifications of applicant
- Exhibit B: Basic qualifications (citizenship, character)
- Orbital debris mitigation plan (§ 25.114(d)(14))
- Radio frequency interference analysis

#### Evidence Required

- [x] Completed FCC Form 312
- [x] Schedule S with all technical parameters
- [x] Corporate governance documents (for applicant qualification)
- [x] Financial statements (demonstrating ability to complete project)
- [x] Orbital debris mitigation plan
- [x] Link budget worksheets
- [x] Interference analysis reports

#### Responsible Party

**Primary**: ArkSpace Legal/Regulatory Lead  
**Support**: Satellite systems engineer, RF engineer, legal counsel (space telecommunications)

#### Timeline

- **Preparation**: 2-4 months (technical studies + document drafting)
- **Internal Review**: 2-4 weeks
- **Filing**: 1-2 days (electronic submission)
- **FCC Processing**: 6-12 months
- **Total**: 8-16 months from project start to license grant

#### Cost Estimate

- **Filing Fee**: $82,570 (for NGSO FSS system, see 47 CFR § 1.1107)
  - Application fee (regulatory fee): $30,575
  - Processing fee: $52,000 (non-geostationary orbit)
- **Legal Counsel**: $50,000-$100,000 (specialized space telecommunications attorney)
- **Technical Studies**: $25,000-$50,000 (link budgets, interference analysis, orbital mechanics)
- **Total**: $157,570-$232,570

#### Risk Assessment

**Probability of Issues**: Medium
- Frequency coordination can be contentious (other operators may object)
- Orbital debris plan must meet enhanced 2020 requirements
- Financial qualification scrutiny for new entrants

**Impact if Non-Compliant**: Critical
- Cannot launch satellites without FCC authorization
- Penalties for unauthorized operation: up to $200,000 per violation per day
- Potential criminal liability

**Mitigation Strategy**:
1. Engage experienced space telecommunications counsel early
2. Pre-file consultation with FCC International Bureau
3. Conservative orbital debris plan (target 5-year deorbit, well under 25-year limit)
4. Proactive coordination with incumbent operators
5. Prepare robust financial documentation

---

### Requirement 2: Frequency Coordination

#### Description

Demonstrate that proposed satellite system will not cause harmful interference to existing authorized systems and coordinate with ITU filings.

#### Applicable Sections

- 47 CFR § 25.140: Requests for U.S. national security clearance
- 47 CFR § 25.220: Non-geostationary orbit sharing
- ITU Radio Regulations Article 9 (cross-reference)

#### Compliance Method

**Domestic Coordination**:
1. Identify existing FCC licensees in Ka-band
2. Perform technical analysis of potential interference scenarios
3. If potential interference found, initiate coordination discussions
4. Document coordination agreements or demonstrate non-interference

**International Coordination** (via ITU):
1. FCC files on behalf of U.S. operators with ITU
2. ITU publishes advance publication (API) and coordination request
3. Other administrations have opportunity to raise concerns
4. Bilateral coordination negotiations if issues arise

#### Evidence Required

- [x] Interference analysis report
- [x] Coordination agreements with affected operators (if applicable)
- [x] ITU filing confirmation (coordinated through FCC)
- [x] Sharing studies for Ka-band allocations

#### Responsible Party

**Primary**: RF Engineer / Frequency Coordinator  
**Support**: Legal counsel, FCC liaison

#### Timeline

- **Analysis**: 1-2 months
- **Coordination Discussions**: 2-6 months (variable)
- **ITU Process**: Parallel with FCC application (managed by FCC)
- **Deadline**: Must be completed before license grant

#### Cost Estimate

- **RF Analysis Tools**: $5,000-$15,000 (software licensing)
- **Consulting**: $10,000-$25,000 (if complex coordination required)
- **Total**: $15,000-$40,000

#### Risk Assessment

**Probability of Issues**: Medium-High
- Ka-band has existing allocations (satellite broadband, fixed service)
- Starlink, OneWeb, Amazon Kuiper operate in same spectrum

**Impact if Non-Compliant**: High
- FCC will not grant license without demonstration of non-interference
- Coordination disputes can delay application 12+ months

**Mitigation Strategy**:
1. Early identification of potential interferers
2. Conservative link margins to demonstrate robustness
3. Geographic service area restrictions if needed
4. Spectrum sharing techniques (time/frequency division)

---

### Requirement 3: Orbital Debris Mitigation

#### Description

Demonstrate compliance with FCC's orbital debris mitigation requirements, including the 25-year post-mission disposal rule for LEO satellites.

#### Applicable Sections

- 47 CFR § 25.114(d)(14): Orbital debris mitigation disclosure
- DA 20-1170 (2020): Enhanced orbital debris mitigation requirements
- NASA Orbital Debris Mitigation Standard Practices (reference guideline)

#### Compliance Method

**Required Disclosures**:

1. **Spacecraft Design**:
   - Debris release assessment (no intentional debris)
   - Passivation plan (deplete energy sources at end-of-life)
   - Collision avoidance capability

2. **Post-Mission Disposal**:
   - **Disposal method**: Natural atmospheric decay from 550 km LEO
   - **Disposal timeline**: ≤ 5 years (well within 25-year requirement)
   - **Disposal reliability**: >0.9 probability of successful deorbit

3. **Collision Avoidance**:
   - Tracking capability (GPS, ground-based tracking)
   - Maneuverability (propulsion system for collision avoidance)
   - Coordination with Space Surveillance Network (SSN)
   - Conjunction assessment procedures

4. **Casualty Risk**:
   - Analysis of reentry casualty risk
   - Target: <1 in 10,000 probability of human casualty
   - Material selection to ensure burn-up during reentry

#### Evidence Required

- [x] Orbital decay analysis (using STELA, DAS, or similar tool)
- [x] End-of-life passivation procedures
- [x] Maneuver capability specifications
- [x] Reentry casualty risk assessment
- [x] Collision avoidance operations plan

#### Responsible Party

**Primary**: Mission Safety Engineer  
**Support**: Orbital mechanics analyst, satellite design team

#### Timeline

- **Analysis**: 1-2 months
- **Documentation**: 2-4 weeks
- **Deadline**: Must be included in Form 312 application

#### Cost Estimate

- **Orbital Analysis Software**: $5,000-$10,000 (STELA, DAS, or equivalent)
- **Consulting (if needed)**: $10,000-$20,000
- **Total**: $15,000-$30,000

#### Risk Assessment

**Probability of Issues**: Low
- 550 km LEO altitude ensures rapid natural decay (~5 years)
- Small satellite size reduces casualty risk
- Standard mitigation techniques are well-established

**Impact if Non-Compliant**: Critical
- FCC will not grant license without acceptable debris mitigation plan
- Post-launch non-compliance could result in license revocation

**Mitigation Strategy**:
1. Conservative altitude selection (400-600 km ensures <25 year decay)
2. Design for demise (materials that burn up on reentry)
3. Redundant propulsion for active deorbit if needed
4. Automated collision avoidance system
5. Partnership with commercial space traffic management providers (LEO Labs, COMSPOC)

---

### Requirement 4: Insurance and Financial Qualification

#### Description

Demonstrate financial qualifications to construct, launch, and operate the proposed satellite system, and maintain appropriate insurance coverage.

#### Applicable Sections

- 47 CFR § 25.140(b): Financial qualifications
- 51 U.S.C. § 50914: Third-party liability insurance (under FAA commercial space launch)
- 14 CFR § 440: Financial Responsibility (cross-reference for launch)

#### Compliance Method

**Financial Qualification**:
1. Submit audited financial statements or business plan
2. Demonstrate access to capital sufficient for:
   - Satellite construction: ~$5.4M (12 satellites @ $450k each)
   - Launch services: ~$2.4M (12 satellites @ $200k rideshare)
   - Ground segment: ~$1.5M
   - Operations (5 years): ~$4.75M
   - **Total**: ~$14M minimum capitalization

**Insurance Requirements**:
1. **Launch Insurance** (managed by launch provider or separately):
   - Third-party liability: $500M-$750M per FAA requirements (51 U.S.C. § 50914)
   - Satellite value: ~$5.4M for constellation

2. **On-Orbit Insurance** (optional but recommended):
   - In-orbit third-party liability: $100M typical for commercial constellations
   - Satellite replacement cost coverage: Optional

#### Evidence Required

- [x] Financial statements (audited, if available)
- [x] Business plan with funding sources
- [x] Letters of commitment from investors/lenders
- [x] Insurance certificates or letters of intent from insurers

#### Responsible Party

**Primary**: Chief Financial Officer / Financial Advisor  
**Support**: Legal counsel, insurance broker (space insurance specialist)

#### Timeline

- **Financial Documentation**: 1-2 months
- **Insurance Procurement**: 2-4 months (pre-launch)
- **Deadline**: Financial qualification required with application; insurance before launch

#### Cost Estimate

- **Launch Insurance** (typically 5-15% of satellite value for rideshare):
  - $270,000-$810,000 for $5.4M constellation value
  - Third-party liability: Often covered by launch provider or government indemnification

- **On-Orbit Insurance** (annual premium ~3-7% of insured value):
  - $162,000-$378,000 per year for full replacement cost

- **Total Annual Insurance**: $162,000-$378,000 (if on-orbit coverage obtained)

#### Risk Assessment

**Probability of Issues**: Low-Medium
- New entrants face higher scrutiny on financial qualification
- Space insurance market has limited capacity

**Impact if Non-Compliant**: High
- FCC may deny application if financial qualification not demonstrated
- Cannot obtain launch license from FAA without insurance

**Mitigation Strategy**:
1. Secure funding commitments early
2. Engage space insurance broker experienced with smallsat/CubeSat
3. Consider self-insurance for on-orbit phase if financially viable
4. Rideshare launch reduces insurance costs (shared risk)
5. Letter of credit or escrow account as alternative to traditional insurance

---

## Application Process

### Step-by-Step Procedure

#### Step 1: Pre-Filing Preparation

**Action**: Conduct technical studies and prepare documentation  
**Required Documents**:
- Orbital mechanics analysis
- Link budget calculations
- Interference analysis
- Orbital debris assessment
- Corporate governance documents
- Financial documentation

**Timeline**: 3-6 months  
**Cost**: $75,000-$175,000 (engineering + legal)

---

#### Step 2: FCC Form 312 Completion

**Action**: Complete application using FCC's International Bureau Filing System (IBFS)  
**Required Documents**:
- FCC Form 312 (Space Station Authorization)
- Schedule S (Technical Information)
- Orbital Debris Mitigation Plan
- Exhibits A-B (Applicant Qualifications)
- Technical narrative

**Timeline**: 1-2 months (drafting + internal review)  
**Cost**: $20,000-$50,000 (legal counsel for application preparation)

---

#### Step 3: Electronic Filing via IBFS

**Action**: Submit application electronically through FCC IBFS portal  
**URL**: https://licensing.fcc.gov/myibfs/

**Process**:
1. Create IBFS account (if not already registered)
2. Upload FCC Form 312 and all exhibits
3. Pay filing fee ($82,570 for NGSO FSS)
4. Submit application

**Timeline**: 1-2 days  
**Cost**: $82,570 (filing fee)

---

#### Step 4: Public Notice and Comment Period

**Action**: FCC publishes Public Notice; 30-day comment period begins  
**Description**: Application appears on FCC's Daily Digest and International Bureau website. Interested parties may file comments or petitions to deny.

**Timeline**: 30 days (minimum)  
**Cost**: $0 (unless opposition requires response)

**Potential Issues**:
- Incumbent operators may file objections (interference concerns)
- Competitors may challenge financial qualifications
- Public interest groups may raise orbital debris concerns

**Mitigation**:
- Monitor public notice for comments
- Prepare responses to objections within 15 days
- Engage in informal coordination with objecting parties

---

#### Step 5: FCC Processing and Review

**Action**: FCC staff reviews application for completeness and compliance  
**Review Areas**:
- Technical compliance with Part 25 rules
- Frequency coordination adequacy
- Orbital debris mitigation acceptability
- Applicant qualifications (legal, financial, technical)

**Timeline**: 4-9 months (typical)  
**Cost**: $0 (unless deficiencies require additional filings)

**Possible Outcomes**:
1. **Grant**: License issued (best case)
2. **Information Request**: FCC requests additional information or clarification
3. **Conditional Grant**: License granted with special conditions
4. **Denial**: Application denied (rare for technically compliant applications)

---

#### Step 6: License Grant

**Action**: FCC issues Space Station License  
**License Terms**:
- **Duration**: 15 years from date of grant
- **Milestone Requirements**:
  - Launch within 7 years of grant (NGSO systems)
  - Begin operations within specified timeframe
- **Conditions**: Any special conditions imposed by FCC

**Timeline**: Upon completion of review  
**Cost**: $0

---

#### Step 7: Launch Coordination

**Action**: Notify FCC of launch plans and obtain launch authorization  
**Required**:
- Advance notification to FCC (typically 30-90 days)
- Coordination with FAA Office of Commercial Space Transportation
- ITU notification of launch (via FCC)

**Timeline**: 1-3 months before launch  
**Cost**: Minimal (notification process)

---

### Required Documentation Checklist

**Application Package**:
- [x] FCC Form 312 (completed via IBFS)
- [x] Schedule S (Satellite Technical Information)
- [x] Exhibit A: Legal Qualifications
- [x] Exhibit B: Citizenship/Basic Qualifications
- [x] Technical Narrative (system description)
- [x] Link Budget Worksheets
- [x] Coverage Maps
- [x] Orbital Debris Mitigation Plan
- [x] Frequency Coordination Analysis
- [x] Financial Documentation

**Supporting Materials**:
- [x] Corporate governance documents (articles of incorporation, bylaws)
- [x] Proof of citizenship (for ownership disclosure)
- [x] Financial statements or business plan
- [x] Resumes of key personnel (technical qualifications)

### Approval Timeline

**Typical Duration**: 9-12 months from filing to grant

**Timeline Breakdown**:
- **Filing to Public Notice**: 2-4 weeks
- **Comment Period**: 30 days (minimum)
- **FCC Review**: 4-9 months
- **Total**: 6-12 months typical, 18+ months if complications

**Expedited Options**:
- None formally available for satellite applications
- Informal pre-filing consultation with FCC staff can streamline process
- Complete, high-quality applications process faster

**Dependencies**:
- **ITU Coordination**: Parallel process; FCC files on behalf of U.S. operators
- **Frequency Coordination**: Must demonstrate before license grant
- **Financial Close**: Must maintain financial qualification throughout process

---

## Ongoing Compliance

### Operational Requirements

#### 1. Telemetry, Tracking, and Control (TT&C)

**Requirement**: Maintain continuous ability to command and control satellites  
**Compliance**: 24/7 ground station operations or contracted TT&C services  
**Reporting**: Notify FCC of any loss of control within 24 hours

#### 2. Orbital Debris Monitoring

**Requirement**: Track satellite health and conduct collision avoidance maneuvers  
**Compliance**: 
- Subscribe to Space Surveillance Network (SSN) conjunction alerts
- Perform maneuvers as needed (typically < 1 km closest approach threshold)
- Log all maneuvers and report to FCC if requested

#### 3. Spectrum Monitoring

**Requirement**: Ensure operations remain within authorized frequencies and power levels  
**Compliance**: On-board telemetry, periodic ground-based monitoring  
**Reporting**: Report any out-of-band emissions or anomalies

---

### Monitoring & Reporting

#### Annual Reporting (FCC Form 312-R)

**Frequency**: Annually  
**Content**:
- Number of satellites launched and operational
- Frequencies in use
- Service areas
- Compliance with license conditions

**Filing**: Electronic via IBFS  
**Deadline**: Within 60 days of license anniversary  
**Penalty**: Late filing fees, potential license revocation for non-filing

#### Orbital Debris Annual Report

**Frequency**: Annually (new requirement as of 2020)  
**Content**:
- Number of satellites deorbited
- Number of collision avoidance maneuvers performed
- Any anomalies or failures affecting debris mitigation

**Filing**: Via IBFS  
**Deadline**: April 1 annually

---

### Renewal/Maintenance

#### License Renewal

**Frequency**: Every 15 years  
**Process**: Similar to initial application, but streamlined if no major changes  
**Timing**: File renewal application 1 year before expiration  
**Fee**: Lower than initial application (~$30,000-$50,000)

#### Modification Applications

**When Required**:
- Change in orbital parameters
- Additional frequencies
- Increased number of satellites
- Change in ownership (requires FCC consent)

**Process**: File FCC Form 312 (modification) via IBFS  
**Timeline**: 3-6 months (depending on scope)  
**Fee**: Varies by modification type

#### Transfer of Control/Assignment

**When Required**: Change in corporate ownership or control (>25% voting equity)  
**Process**: File transfer application (both parties)  
**FCC Review**: Public interest assessment  
**Timeline**: 3-6 months  
**Fee**: ~$20,000-$50,000

---

## Research Sources

### Primary Sources

1. **47 CFR § 25 - Satellite Communications**
   - URL: https://www.ecfr.gov/current/title-47/chapter-I/subchapter-B/part-25
   - Accessed: January 14, 2026
   - Relevance: Primary regulatory authority for all satellite licensing
   - Key Sections: § 25.114 (application requirements), § 25.142 (NGSO licensing), § 25.217 (frequencies)

2. **FCC International Bureau - Satellite Division**
   - URL: https://www.fcc.gov/international/satellite-programs
   - Accessed: January 14, 2026
   - Relevance: Official guidance, processing procedures, application forms

3. **FCC Form 312 - Application for Space Station Radio Authorization**
   - URL: https://www.fcc.gov/wireless/bureau-divisions/broadband-division/forms/form-312-application-space-station
   - Instructions: https://www.fcc.gov/sites/default/files/form312instrux.pdf
   - Accessed: January 14, 2026
   - Relevance: Required application form and instructions

4. **DA 20-1170 - Enhanced Orbital Debris Mitigation Requirements**
   - Title: "Mitigation of Orbital Debris in the New Space Age"
   - URL: https://docs.fcc.gov/public/attachments/DA-20-1170A1.pdf
   - Released: October 1, 2020
   - Relevance: Updated debris mitigation rules (25-year deorbit, collision avoidance)

5. **FCC Fee Schedule (47 CFR § 1.1107)**
   - URL: https://www.ecfr.gov/current/title-47/chapter-I/subchapter-A/part-1/subpart-G
   - Accessed: January 14, 2026
   - Relevance: Filing fees for satellite applications

---

### Secondary Sources

6. **SpaceX Starlink FCC Authorizations**
   - Orders: DA-18-313 (2018), DA-20-461 (2020)
   - URLs: https://docs.fcc.gov/public/attachments/DOC-356377A1.pdf
   - Relevance: Precedent for NGSO LEO constellation licensing

7. **OneWeb FCC Authorization**
   - Order: DA-17-524 (2017)
   - URL: https://docs.fcc.gov/public/attachments/FCC-17-77A1.pdf
   - Relevance: Ka-band NGSO constellation precedent

8. **Amazon Kuiper Authorization**
   - Order: DA-20-797 (2020)
   - URL: https://docs.fcc.gov/public/attachments/DA-20-797A1.pdf
   - Relevance: Recent NGSO constellation approval

9. **Satellite Industry Association (SIA) - Regulatory Resources**
   - URL: https://sia.org/issues-policy/
   - Accessed: January 14, 2026
   - Relevance: Industry best practices and policy analysis

10. **"Space Mission Analysis and Design" (SMAD), 3rd Edition**
    - Authors: James Wertz, Wiley Larson
    - Chapter 6: Space Regulations
    - ISBN: 978-1881883104
    - Relevance: Comprehensive overview of satellite regulatory environment

---

### Expert Consultation

**Recommended Consultants**:

1. **Space Telecommunications Law Firms**:
   - Hogan Lovells (Washington, D.C.) - Satellite practice group
   - Milbank LLP (Washington, D.C.) - Space law
   - Latham & Watkins (Washington, D.C.)

2. **FCC Frequency Coordination Consultants**:
   - Comsearch (Spectrum planning and coordination)
   - Alion Science and Technology

3. **Orbital Debris Analysis**:
  - The Aerospace Corporation
  - AGI (Analytical Graphics, Inc.) - STELA software

---

## Open Questions

### Unresolved Issues

1. **Does neuromorphic processor classification affect export controls that interact with FCC licensing?**
   - **Why Unclear**: Neuromorphic hardware is novel; unclear if classified as "specially designed" for satellite use
   - **Next Steps**: Consult with DDTC/BIS for commodity jurisdiction determination
   - **Priority**: Medium (affects application disclosure requirements)

2. **Can optical inter-satellite links (OISL) operate license-exempt, or do they require FCC authorization?**
   - **Why Unclear**: Free-space optical (1550nm) not explicitly addressed in Part 25
   - **Next Steps**: Request FCC guidance via informal inquiry
   - **Priority**: High (affects application scope)
   - **Preliminary Finding**: Likely license-exempt as point-to-point optical, but confirmation needed

3. **How does ArkSpace's novel use case (neural data processing) affect "public interest" review?**
   - **Why Unclear**: No precedent for consciousness substrate transfer applications
   - **Next Steps**: Emphasize research/scientific mission in application narrative
   - **Priority**: Low (unlikely to affect technical approval, but narrative matters)

---

## Recommendations

### Immediate Actions

1. **Engage Space Telecommunications Counsel** (Timeline: Immediately)
   - Interview 2-3 firms with satellite licensing experience
   - Select counsel with demonstrated FCC International Bureau expertise
   - Budget: $50,000-$100,000 for application preparation

2. **Conduct Pre-Filing Consultation with FCC** (Timeline: 2-3 months before filing)
   - Informal meeting with FCC International Bureau staff
   - Present system concept and solicit feedback on potential issues
   - Clarify OISL licensing requirements

3. **Begin Technical Studies** (Timeline: Immediately)
   - Link budget analysis
   - Orbital mechanics and debris assessment
   - Frequency coordination analysis
   - Budget: $25,000-$50,000

4. **Secure Financial Commitments** (Timeline: 3-6 months before filing)
   - Finalize funding for constellation development
   - Obtain letters of commitment from investors
   - Prepare audited financial statements or business plan

---

### Long-term Strategy

#### Phased Licensing Approach

**Option 1: Single Application (12-node constellation)**
- **Pros**: One approval process, faster deployment once licensed
- **Cons**: Higher scrutiny, longer review, higher upfront costs

**Option 2: Phased Applications (3-node MVP, then expansion)**
- **Pros**: Lower initial costs, de-risked approval, demonstrate viability
- **Cons**: Multiple application processes, longer overall timeline

**Recommendation**: **Option 2 - Phased Approach**
- Apply for 3-node constellation initially (MVP demonstration)
- File modification after successful on-orbit demonstration
- Reduces financial qualification scrutiny and technical risk

---

#### Frequency Strategy

**Primary Bands**: Ka-band (27.5-30.0 GHz uplink, 17.7-20.2 GHz downlink)

**Considerations**:
- **Pros**: Established allocation, high bandwidth, global availability
- **Cons**: Competitive (Starlink, OneWeb, Kuiper), rain fade issues

**Backup Option**: Q/V-band (37.5-42.5 GHz uplink, 47.2-50.2 GHz downlink)
- Less crowded but immature ground equipment market

**Recommendation**: Proceed with Ka-band; file for Q/V in future if interference issues arise

---

### Risk Mitigation

#### Top Risks and Mitigation

1. **Risk**: Frequency coordination delays
   - **Mitigation**: Early coordination with incumbents, conservative interference margins

2. **Risk**: Financial qualification challenges (as new entrant)
   - **Mitigation**: Secure firm funding commitments, escrow accounts, phased approach

3. **Risk**: Orbital debris plan rejection
   - **Mitigation**: Conservative 5-year deorbit, active collision avoidance, design-for-demise

4. **Risk**: Public opposition (novel use case)
   - **Mitigation**: Emphasize scientific/research mission, transparent operations plan

5. **Risk**: Application processing delays
   - **Mitigation**: High-quality initial filing, pre-filing FCC consultation, experienced counsel

---

## Appendices

### Appendix A: Relevant FCC Rule Excerpts

#### 47 CFR § 25.114(d)(14) - Orbital Debris Mitigation

> (14) For earth station and space station applications, a description of the design and operational strategies that will be used to mitigate orbital debris, including the following:
>
> (i) A statement that the operator has assessed and limited the amount of debris released in a planned manner during normal operations;
>
> (ii) A statement indicating whether the space station(s) is/are designed for post-mission disposal;
>
> (iii) For a station that is not designed for post-mission disposal:
>    (A) A demonstration that the spacecraft will be disposed of within 25 years after the end of the mission;
>    (B) An assessment of the probability of success of the chosen disposal method; and
>
> (iv) A statement that the operator has assessed and limited the probability of the space station(s) becoming a source of debris by collision with small debris or meteoroids that would cause loss of control.

---

### Appendix B: FCC Filing Fees (2026)

**Source**: 47 CFR § 1.1107 (as amended through 2025)

| Application Type | Regulatory Fee | Processing Fee | Total |
|------------------|----------------|----------------|-------|
| NGSO-like FSS (new) | $30,575 | $52,000 | **$82,570** |
| NGSO FSS modification (minor) | $0 | $5,225 | $5,225 |
| NGSO FSS modification (major) | $15,290 | $26,000 | $41,290 |
| Earth Station (routine) | $615 | $1,365 | $1,980 |
| Transfer/Assignment | $3,960 | $11,945 | $15,905 |
| License Renewal | $15,290 | $26,000 | $41,290 |

**Note**: Fees subject to annual adjustment for inflation.

---

### Appendix C: FCC Contact Information

**FCC International Bureau**  
**Satellite Division**

**Address**:  
Federal Communications Commission  
45 L Street NE  
Washington, DC 20554

**Phone**: (202) 418-0719  
**Fax**: (202) 418-2817  
**Email**: internationalbureau@fcc.gov

**Key Contacts**:
- **Space Bureau Chief**: Julie Kearney (as of 2026)
- **Satellite Division Chief**: Karl Kensinger
- **NGSO Processing**: https://www.fcc.gov/international/satellite-programs/ngso-processing

**IBFS Support**:  
- **Help Desk**: (202) 418-2222  
- **Email**: ARINQUIRIES@fcc.gov  
- **Portal**: https://licensing.fcc.gov/myibfs/

---

## Revision History

| Version | Date | Researcher | Changes |
|---------|------|------------|---------|
| 1.0.0 | January 14, 2026 | Zae Research Team | Initial comprehensive FCC Part 25 analysis |

---

**Document Status**: ✅ Complete  
**Next Steps**: Proceed with ITU coordination research and integrate into comprehensive compliance document  
**Dependencies**: ITU research (day1-research-itu) for international coordination aspects

