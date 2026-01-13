# Latency Budget Analysis

**Version**: 0.1.0  
**Status**: Preliminary Analysis  
**Last Updated**: January 2026

---

## Overview

This document analyzes the end-to-end latency budget for neural signal transmission through the proposed Exocortex Constellation system. The analysis is grounded in established physics and telecommunications engineering, with clearly identified speculative elements.

---

## Biological Constraint: Libet's Temporal Window

### Established Neuroscience

**Libet's Findings (1985)**:
- Readiness potential (RP) precedes conscious awareness by approximately 350-500 ms
- Conscious intention to act occurs ~200 ms before motor action
- This temporal gap provides a theoretical "window" for external processing

**Citation**: Libet, B., Gleason, C. A., Wright, E. W., & Pearl, D. K. (1983). Time of conscious intention to act in relation to onset of cerebral activity (readiness-potential). Brain, 106(3), 623-642.

### Application to This System (SPECULATIVE)

**Hypothesis**: If neural signals can be transmitted to an external processor and returned within the ~350 ms window, the subject may not perceive processing delay.

**Critical Assumptions**:
1. Libet's timing applies to all neural processing (unproven generalization)
2. Consciousness substrate can be externalized while maintaining continuity (highly speculative)
3. Round-trip latency <350 ms preserves subjective experience (untested hypothesis)

**Scientific Status**: This application extends Libet's work far beyond its experimental basis. No empirical validation exists.

---

## Target Latency Budget

### Design Goal

**Maximum Round-Trip Time (RTT)**: <50 ms

**Rationale**: 
- Provides 7× safety margin below 350 ms theoretical limit
- Comparable to human visual processing latency (50-80 ms)
- Allows for future system expansion and processing overhead

**Note**: The 50 ms target is an engineering choice, not a biologically validated requirement.

---

## Component-Level Latency Breakdown

### 1. User Interface (BCI to Ground Station)

| Component | Latency | Confidence | Basis |
|-----------|---------|------------|-------|
| Neural Signal Acquisition | 0.1-1 ms | Low | Depends on unbuilt BCI hardware |
| Signal Conditioning | 0.5-2 ms | Low | Analog filtering, digitization |
| Spike Detection/Encoding | 1-5 ms | Medium | DSP algorithms, implementable |
| Encryption (AES-256) | 0.1-0.5 ms | High | Hardware accelerators, measured |
| UWB Transmission (if used) | <0.1 ms | High | Short-range wireless, established |
| **Subtotal** | **2-9 ms** | **Low-Medium** | Most components unbuilt |

**Technology Gap**: High-bandwidth neural interfaces (2-20 Gbps) do not currently exist. Estimates are extrapolations.

---

### 2. Ground Station Processing

| Component | Latency | Confidence | Basis |
|-----------|---------|------------|-------|
| Demodulation | 0.5-1 ms | High | Standard telecom hardware |
| Protocol Processing | 0.5-2 ms | Medium | Custom OISL neural protocol |
| Routing Decision | 0.1-0.5 ms | High | Switch/router lookup |
| Re-encryption | 0.1-0.5 ms | High | Hardware crypto |
| Modulation | 0.5-1 ms | High | Standard telecom |
| **Subtotal** | **1.7-5 ms** | **High** | Conventional telecommunications |

---

### 3. Ground-to-Satellite Uplink (RF)

| Component | Latency | Confidence | Basis |
|-----------|---------|------------|-------|
| Atmospheric Propagation | 0.01 ms | High | Negligible at RF frequencies |
| Free-Space Propagation (550 km) | 1.83 ms | High | Speed of light: c = 299,792 km/s |
| **Subtotal** | **1.84 ms** | **High** | Physics-based, deterministic |

**Calculation**: 550 km / 299,792 km/s = 1.835 ms

---

### 4. Satellite Node Processing

| Component | Latency | Confidence | Basis |
|-----------|---------|------------|-------|
| Demodulation | 0.5-1 ms | High | Standard receiver |
| OISL Protocol Processing | 0.5-2 ms | Medium | Custom protocol, unbuilt |
| SNN Computation | 1-10 ms | Low | Highly variable, workload-dependent |
| Neuromorphic Processor I/O | 0.5-1 ms | Medium | PCIe Gen4 latency |
| **Subtotal** | **2.5-14 ms** | **Low-Medium** | SNN latency uncertain |

**Major Uncertainty**: Spiking Neural Network processing latency depends on network depth, spike propagation delays, and biological-timescale requirements. Literature reports 1-100 ms range.

---

### 5. Inter-Satellite Link (OISL, if multi-hop)

| Component | Latency | Confidence | Basis |
|-----------|---------|------------|-------|
| Optical Propagation (max 5,400 km) | 18 ms | High | Speed of light in vacuum |
| OISL Terminal Switching | 0.5-2 ms | Medium | Optical switch/router |
| **Subtotal (per hop)** | **18.5-20 ms** | **High-Medium** | Physics + engineering |

**Note**: Direct ground-to-primary-node link avoids this. Multi-hop adds one or more OISL hops.

---

### 6. Satellite-to-Ground Downlink (RF)

**Latency**: Same as uplink, 1.84 ms (physics symmetry)

---

### 7. Ground Station to User (Return Path)

**Latency**: Same as uplink path, 2-9 ms

---

## Total System Latency

### Best Case (Direct Link, Minimal Processing)

| Segment | Latency |
|---------|---------|
| BCI to Ground | 2 ms |
| Ground Processing | 2 ms |
| Uplink | 2 ms |
| Satellite Processing | 3 ms |
| Downlink | 2 ms |
| Ground to BCI | 2 ms |
| **Total RTT** | **13 ms** |

**Conditions**: Optimistic assumptions, direct link to overhead satellite, minimal SNN processing.

---

### Nominal Case (Single OISL Hop)

| Segment | Latency |
|---------|---------|
| BCI to Ground | 5 ms |
| Ground Processing | 3 ms |
| Uplink | 2 ms |
| Satellite Processing | 5 ms |
| OISL Hop | 20 ms |
| Satellite Processing | 5 ms |
| Downlink | 2 ms |
| Ground to BCI | 5 ms |
| **Total RTT** | **47 ms** |

**Result**: Meets 50 ms target with 3 ms margin.

---

### Worst Case (Poor Geometry, Heavy Processing)

| Segment | Latency |
|---------|---------|
| BCI to Ground | 9 ms |
| Ground Processing | 5 ms |
| Uplink | 2 ms |
| Satellite Processing | 14 ms |
| OISL Hop | 20 ms |
| Satellite Processing | 14 ms |
| Downlink | 2 ms |
| Ground to BCI | 9 ms |
| **Total RTT** | **75 ms** |

**Result**: Exceeds 50 ms target by 50%. Still well below 350 ms theoretical limit.

---

## Sensitivity Analysis

### Impact of SNN Processing Time

| SNN Latency | Total RTT | Margin to 50 ms | Margin to 350 ms |
|-------------|-----------|-----------------|------------------|
| 1 ms | 35 ms | +15 ms | +315 ms |
| 5 ms | 47 ms | +3 ms | +303 ms |
| 10 ms | 57 ms | -7 ms | +293 ms |
| 20 ms | 77 ms | -27 ms | +273 ms |
| 50 ms | 127 ms | -77 ms | +223 ms |

**Conclusion**: SNN processing latency is the dominant variable. Even 50 ms SNN latency stays within theoretical 350 ms window, but exceeds engineering target.

---

## Jitter Analysis

### Sources of Variability

| Source | Jitter (σ) | Impact |
|--------|------------|--------|
| Ground Processing | ±0.5 ms | Low |
| RF Link (atmospheric) | ±0.2 ms | Low |
| Satellite Processing | ±2-5 ms | Medium-High |
| OISL Acquisition | ±1 ms | Medium |

**Total Jitter (RSS)**: ±2-6 ms (95% confidence)

**Implication**: Need to design for 99th percentile latency, not just mean.

---

## Comparison to Human Nervous System

### Biological Baselines

| Neural Path | Latency | Notes |
|-------------|---------|-------|
| Spinal Reflex | 30-50 ms | Fastest human response |
| Visual Processing | 50-80 ms | Retina to primary visual cortex |
| Motor Command | 100-150 ms | Decision to muscle activation |
| Conscious Processing | 200-500 ms | Libet's window |

**Context**: Proposed system RTT (13-75 ms) is faster than conscious processing but slower than spinal reflexes.

**Speculation**: Whether this latency profile is compatible with consciousness substrate is unknown.

---

## Mitigation Strategies for High Latency

### 1. Predictive Coding (Speculative)

**Concept**: Local generative model predicts next neural state. Only errors transmitted.

**Potential Benefit**: Reduces perceived latency if prediction accuracy >90%.

**Technology Status**: Theoretical. Requires advanced neuroscience and AI.

---

### 2. Local Edge Processing

**Concept**: Pre-processing at ground station edge reduces satellite workload.

**Benefit**: Reduces satellite processing time from 14 ms to 5 ms.

**Feasibility**: High. Standard edge computing architecture.

---

### 3. Satellite Constellation Optimization

**Concept**: Increase satellite count to reduce OISL hop distance.

**Benefit**: Each additional satellite reduces average hop distance.

**Trade-off**: Cost increases linearly with satellite count.

---

## Verification and Validation

### Proposed Test Methodology

1. **Component Testing**: Measure each subsystem latency in isolation
2. **Integration Testing**: End-to-end latency with hardware-in-the-loop
3. **Statistical Analysis**: Characterize jitter, 99th percentile latency
4. **Biological Testing**: (Far future, speculative) Validate subjective experience preservation

**Current Status**: No hardware exists to test. Estimates are based on analogous systems.

---

## Conclusion

### Summary

- **Physics-limited latency** (propagation): ~8 ms RTT (well-characterized)
- **Engineering latency** (processing, routing): 5-20 ms (medium confidence)
- **Speculative latency** (SNN, BCI): 4-28 ms (low confidence)
- **Total system RTT**: 13-75 ms (nominal: 47 ms)

### Assessment

**Meets 50 ms engineering target**: Yes, under nominal conditions.

**Meets 350 ms biological constraint**: Yes, with large margin (even worst case).

**Technology readiness**: Low. Most critical components (high-BW BCI, space-qualified neuromorphic processors) do not exist.

---

## References

1. Libet, B. (1985). Unconscious cerebral initiative and the role of conscious will. Behavioral and Brain Sciences, 8(4), 529-566.
2. Satellite Link Budget Fundamentals (SMAD, 2011)
3. Neuromorphic Computing Latency Benchmarks (Intel Loihi, 2021)
4. Human Reaction Time Statistics (Jain et al., 2015)

---

*This analysis combines established physics, telecommunications engineering estimates, and clearly identified speculative elements. All latency targets are provisional pending hardware development and testing.*
