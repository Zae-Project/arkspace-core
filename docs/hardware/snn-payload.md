# SNN Payload Hardware Specification

**Version**: 1.0.0  
**Status**: Draft  
**Last Updated**: January 2026

---

## Overview

The SNN (Spiking Neural Network) Payload is the primary computational component of each Exocortex Constellation satellite node. It runs the Neutral Consciousness Engine software from **[theconsiousness.ai/core](https://theconsiousness.ai/core)** and serves as the synthetic neural substrate for consciousness transfer.

---

## Architecture

```
┌─────────────────────────────────────────────────────────────────────────────────┐
│                           SNN PAYLOAD BLOCK DIAGRAM                              │
├─────────────────────────────────────────────────────────────────────────────────┤
│                                                                                  │
│   ┌─────────────────────────────────────────────────────────────────────────┐   │
│   │                    NEUROMORPHIC PROCESSOR UNIT                           │   │
│   │  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐  ┌─────────────┐    │   │
│   │  │   Core      │  │   Core      │  │   Core      │  │   Core      │    │   │
│   │  │  Cluster    │  │  Cluster    │  │  Cluster    │  │  Cluster    │    │   │
│   │  │   0-255     │  │  256-511    │  │  512-767    │  │  768-1023   │    │   │
│   │  │  (32K LIF)  │  │  (32K LIF)  │  │  (32K LIF)  │  │  (32K LIF)  │    │   │
│   │  └──────┬──────┘  └──────┬──────┘  └──────┬──────┘  └──────┬──────┘    │   │
│   │         │                │                │                │            │   │
│   │         └────────────────┴────────────────┴────────────────┘            │   │
│   │                                   │                                      │   │
│   │                          Mesh Interconnect                               │   │
│   │                          (Spike Routing)                                 │   │
│   │                                   │                                      │   │
│   │  ┌────────────────────────────────┴────────────────────────────────┐    │   │
│   │  │                    MEMORY SUBSYSTEM                              │    │   │
│   │  │   ┌─────────────┐   ┌─────────────┐   ┌─────────────┐           │    │   │
│   │  │   │  Neuron     │   │  Synapse    │   │  Spike      │           │    │   │
│   │  │   │  State      │   │  Weights    │   │  Queues     │           │    │   │
│   │  │   │  (100 MB)   │   │  (128 MB)   │   │  (16 MB)    │           │    │   │
│   │  │   └─────────────┘   └─────────────┘   └─────────────┘           │    │   │
│   │  └──────────────────────────────────────────────────────────────────┘    │   │
│   └─────────────────────────────────────────────────────────────────────────┘   │
│                                   │                                              │
│                           PCIe Gen4 x8                                           │
│                                   │                                              │
│   ┌───────────────────────────────┴───────────────────────────────────────┐     │
│   │                         I/O SUBSYSTEM                                  │     │
│   │  ┌─────────────────┐  ┌─────────────────┐  ┌─────────────────────┐   │     │
│   │  │     OISL        │  │    Secure       │  │    Telemetry        │   │     │
│   │  │   Interface     │  │    Enclave      │  │    Controller       │   │     │
│   │  │   (4 ports)     │  │   (ARM TZ)      │  │                     │   │     │
│   │  └─────────────────┘  └─────────────────┘  └─────────────────────┘   │     │
│   └───────────────────────────────────────────────────────────────────────┘     │
│                                                                                  │
└──────────────────────────────────────────────────────────────────────────────────┘
```

---

## Neuromorphic Processor

### Architecture Selection

The payload uses a **Loihi-class neuromorphic processor** optimized for:
- Event-driven asynchronous computation
- Low power operation in space environment
- Real-time SNN execution (1:1 biological time)

### Neuron Model: Leaky Integrate-and-Fire (LIF)

The LIF neuron is the fundamental computational unit:

```
Membrane Dynamics:
─────────────────

τ_m × dV/dt = (V_rest - V) + R_m × I_input

Where:
  τ_m     = Membrane time constant (1-100 ms configurable)
  V       = Membrane potential
  V_rest  = Resting potential (-70 mV typical)
  R_m     = Membrane resistance
  I_input = Input current from synapses

Spike Generation:
─────────────────

If V > V_threshold:
    Emit spike
    V = V_reset
    Enter refractory period (1-10 ms)
```

### Capacity

| Parameter | Value | Notes |
|-----------|-------|-------|
| Total Neurons | 100,000,000 | 100M per satellite node |
| Total Synapses | 100,000,000,000 | 100B connections |
| Neurons per Core | 128 | Fine-grained parallelism |
| Core Count | 781,250 | ~780K cores |
| Synapses per Neuron | 1,000 avg (10,000 max) | Configurable connectivity |

### Performance

| Metric | Target | Maximum |
|--------|--------|---------|
| Spike Processing Rate | 10B spikes/second | 20B spikes/second |
| Real-Time Factor | 1.0× | 2.0× (accelerated mode) |
| Spike Latency | 100 ns | 1 μs |
| Time Resolution | 1 μs | 100 ns |

---

## Memory Architecture

### On-Chip Memory (SRAM)

| Allocation | Size | Purpose |
|------------|------|---------|
| Neuron State | 100 MB | V_m, refractory counters, last spike time |
| Synapse Weights | 128 MB | float16 weights, STDP traces |
| Spike Queues | 16 MB | Inter-core spike routing buffers |
| Learning Buffers | 8 MB | STDP eligibility traces |
| System | 4 MB | Configuration, diagnostics |
| **Total** | **256 MB** | |

**Bandwidth**: 1 TB/s (on-chip interconnect)  
**Latency**: 10 ns

### External Memory (LPDDR4X)

| Allocation | Size | Purpose |
|------------|------|---------|
| Full State Snapshot | 8 GB | Checkpoint storage |
| Model Storage | 4 GB | Alternative SNN models |
| Telemetry Buffer | 2 GB | Performance logs |
| Spare | 2 GB | Reserved |
| **Total** | **16 GB** | |

**Bandwidth**: 50 GB/s  
**Latency**: 100 ns

---

## Power Management

### Operating Modes

| Mode | Power | Neurons Active | Use Case |
|------|-------|----------------|----------|
| Full Active | 100W | 100% | Maximum consciousness workload |
| Active | 50W | 50% | Typical operation |
| Low Power | 20W | 20% | Power conservation |
| Standby | 5W | 1% | Maintaining state, minimal processing |
| Sleep | 1W | 0% | State preserved in external memory |

### Dynamic Scaling

The payload supports dynamic power management:

```
Power Scaling Strategies:
─────────────────────────

1. VOLTAGE SCALING
   - Core voltage: 0.7V (low) to 0.9V (high)
   - Linear power reduction with voltage²

2. FREQUENCY SCALING
   - Clock gating for inactive cores
   - Spike rate-dependent frequency adjustment

3. NEURON GATING
   - Disable neurons with no recent activity
   - Wake-on-spike mechanism for dormant neurons

4. THERMAL THROTTLING
   - Automatic spike rate reduction at 75°C
   - Prevents thermal runaway in orbit
```

---

## OISL Interface

### High-Speed Data Path

The payload connects to four OISL transceivers via PCIe Gen4:

| Parameter | Value |
|-----------|-------|
| Interface | PCIe Gen4 x8 |
| Bandwidth | 126 Gbps (bidirectional) |
| DMA Channels | 4 |
| Max Transfer | 64 MB |
| Scatter-Gather | Supported |

### Protocol Offload

Hardware acceleration for:
- **AES-256-GCM** encryption/decryption
- **LZ4** compression/decompression
- **CRC-32** checksum calculation

---

## Secure Enclave

### ARM TrustZone Implementation

The payload includes a hardware-isolated secure enclave:

```
┌─────────────────────────────────────────────────────────────┐
│                    SECURE ENCLAVE                            │
├─────────────────────────────────────────────────────────────┤
│                                                              │
│   ┌─────────────────────┐    ┌─────────────────────┐        │
│   │   KEY STORAGE       │    │   CRYPTO ENGINE     │        │
│   │   ─────────────     │    │   ─────────────     │        │
│   │   16 key slots      │    │   AES-256-GCM       │        │
│   │   AES-256 keys      │    │   SHA-256           │        │
│   │   X25519 keys       │    │   X25519 ECDH       │        │
│   │   Ed25519 keys      │    │   Ed25519 Sign      │        │
│   └─────────────────────┘    └─────────────────────┘        │
│                                                              │
│   ┌─────────────────────────────────────────────────────┐   │
│   │   SECURE BOOT                                        │   │
│   │   ─────────────                                      │   │
│   │   • Hardware root of trust (fused)                   │   │
│   │   • Multi-stage boot verification                    │   │
│   │   • Rollback protection                              │   │
│   │   • Tamper detection → Key zeroization               │   │
│   └─────────────────────────────────────────────────────┘   │
│                                                              │
└──────────────────────────────────────────────────────────────┘
```

### Security Features

| Feature | Implementation |
|---------|----------------|
| Root of Trust | Hardware-fused keys |
| Secure Boot | Multi-stage chain validation |
| Key Storage | 16 slots, tamper-protected |
| Encryption | 10 Gbps AES-GCM throughput |
| Remote Attestation | Quote generation in enclave |

---

## Radiation Tolerance

### Space Environment Challenges

| Threat | Mitigation |
|--------|------------|
| Total Ionizing Dose (TID) | 50 krad tolerance, rad-hard design |
| Single Event Upset (SEU) | ECC + TMR for critical registers |
| Single Event Latchup (SEL) | 75 MeV·cm²/mg threshold, protected |

### Error Correction

```
Error Correction Strategy:
──────────────────────────

MEMORY (SRAM + DRAM):
  └─► SECDED ECC (Single Error Correct, Double Error Detect)
      - 1-bit correction per 64-bit word
      - 2-bit detection per 64-bit word
      - <0.1% overhead

CRITICAL LOGIC:
  └─► Triple Modular Redundancy (TMR)
      - 3 copies of critical registers
      - Majority voting
      - Automatic recovery

SOFT ERROR RATE TARGET:
  └─► <1 uncorrected error per year
```

---

## Thermal Design

### Heat Dissipation

| Parameter | Value |
|-----------|-------|
| Maximum TDP | 100W |
| Typical Power | 50W |
| Package | Flip-chip BGA, 50×50 mm |
| Thermal Interface | Thermal paste to heat spreader |

### Cooling Path

```
PROCESSOR DIE
     │
     ▼
┌─────────────────┐
│  Thermal Paste  │  0.1 °C/W
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  Copper Heat    │  0.2 °C/W
│    Spreader     │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│   Heat Pipes    │  0.1 °C/W
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│    Radiator     │  Radiates to space
│   (0.1 m²)      │
└─────────────────┘
```

### Temperature Limits

| Component | Operating | Maximum |
|-----------|-----------|---------|
| Junction | 65°C target | 85°C |
| Case | 55°C target | 70°C |
| Board | 50°C target | 65°C |

---

## Software Interface

### SNN Runtime API

The payload exposes a high-level API for SNN management:

```python
# Neuron Operations
create_neuron(params: LIFParams) -> NeuronID
delete_neuron(id: NeuronID)
set_parameters(id: NeuronID, params: LIFParams)
get_state(id: NeuronID) -> NeuronState

# Synapse Operations
create_synapse(pre: NeuronID, post: NeuronID, weight: float16)
delete_synapse(id: SynapseID)
set_weight(id: SynapseID, weight: float16)
get_weight(id: SynapseID) -> float16

# Network Operations
load_model(path: str, format: ModelFormat)
save_model(path: str, format: ModelFormat)
start_simulation()
stop_simulation()
inject_spikes(neuron_ids: List[NeuronID], times: List[uint64])
read_spikes(since: uint64) -> List[SpikeEvent]

# State Operations
checkpoint_create() -> CheckpointID
checkpoint_restore(id: CheckpointID)
state_export(format: StateFormat) -> bytes
state_import(data: bytes, format: StateFormat)
```

### Model Formats

| Format | Description | Use Case |
|--------|-------------|----------|
| `nengo_compiled` | Compiled Nengo model | Primary deployment |
| `custom_binary` | Raw binary weights | Direct hardware access |
| `pytorch_snn_export` | Exported PyTorch SNN | Training pipeline |

---

## Physical Specifications

| Parameter | Value |
|-----------|-------|
| Dimensions | 100 × 100 × 20 mm |
| Mass | 500g |
| Mounting | Standard PC/104 |
| Power Connector | Micro-D 15-pin |
| Data Connector | Samtec FireFly (OISL) |
| Debug | 10-pin JTAG |

---

## Integration with TheConsciousness.ai/core

The SNN Payload runs the **Neutral Consciousness Engine** from [theconsiousness.ai/core](https://theconsiousness.ai/core):

### Deployed Components

| Component | Description |
|-----------|-------------|
| **The Connectome** | LIF neuron network with STDP plasticity |
| **The Dream Engine** | Predictive coding generative model |
| **The Guardian** | Neural Firewall with anomaly detection |

### Deployment Process

1. **Compile** SNN model using Nengo toolchain
2. **Sign** binary with trusted key
3. **Upload** via ground station
4. **Verify** integrity in secure enclave
5. **Load** into neuromorphic processor
6. **Validate** with self-test sequence
7. **Activate** for consciousness substrate operation

---

## References

- Intel Loihi 2 Architecture (2021)
- Neuromorphic Computing in Space: Challenges and Opportunities (2024)
- Radiation Effects on Neuromorphic Processors (2023)
- TheConsciousness.ai/core Technical Documentation

---

*Hardware specification maintained by ArkSpace.me infrastructure team in coordination with TheConsciousness.ai/core software team.*
