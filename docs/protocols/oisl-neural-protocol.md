# OISL Neural Protocol Specification

**Version**: 0.1.0  
**Status**: Draft  
**Last Updated**: January 2026

---

## Overview

The **OISL Neural Protocol** defines how neural data is transmitted between satellite nodes and between ground stations and satellites in the Exocortex Constellation. It is optimized for:

1. **Low latency** (<50ms RTT)
2. **High bandwidth** (2-20 Gbps neural data)
3. **Security** (encrypted at all times)
4. **Reliability** (error detection and correction)

---

## Protocol Stack

```
┌─────────────────────────────────────────────────────────────────┐
│                    APPLICATION LAYER                             │
│            Neural State Transfer / SNN Commands                  │
├─────────────────────────────────────────────────────────────────┤
│                    PRESENTATION LAYER                            │
│            Spike Encoding / Compression / Encryption             │
├─────────────────────────────────────────────────────────────────┤
│                    SESSION LAYER                                 │
│            Connection Management / Authentication                │
├─────────────────────────────────────────────────────────────────┤
│                    TRANSPORT LAYER                               │
│            Reliable Delivery / Flow Control                      │
├─────────────────────────────────────────────────────────────────┤
│                    NETWORK LAYER                                 │
│            Routing / Addressing (Node IDs)                       │
├─────────────────────────────────────────────────────────────────┤
│                    DATA LINK LAYER                               │
│            Framing / Error Detection                             │
├─────────────────────────────────────────────────────────────────┤
│                    PHYSICAL LAYER                                │
│            OISL (Laser) / RF (Ka-band backup)                    │
└─────────────────────────────────────────────────────────────────┘
```

---

## Packet Format

### Neural Data Packet

```
 0                   1                   2                   3
 0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1 2 3 4 5 6 7 8 9 0 1
├─┴─┴─┴─┴─┴─┴─┴─┴─┴─┴─┴─┴─┴─┴─┴─┴─┴─┴─┴─┴─┴─┴─┴─┴─┴─┴─┴─┴─┴─┴─┴─┤
│                         HEADER (64 bytes)                      │
├───────────────────────────────────────────────────────────────┤
│  Version  │   Type    │           Flags           │  Priority │
│  (4 bits) │  (4 bits) │         (16 bits)         │  (8 bits) │
├───────────────────────────────────────────────────────────────┤
│                    Sequence Number (32 bits)                   │
├───────────────────────────────────────────────────────────────┤
│                    Timestamp (64 bits)                         │
│                    (nanosecond precision)                      │
├───────────────────────────────────────────────────────────────┤
│    Source Node ID     │   Destination Node ID     │  Reserved │
│      (16 bits)        │       (16 bits)           │ (32 bits) │
├───────────────────────────────────────────────────────────────┤
│                    Session ID (64 bits)                        │
├───────────────────────────────────────────────────────────────┤
│                    Payload Length (32 bits)                    │
├───────────────────────────────────────────────────────────────┤
│                    Checksum (32 bits)                          │
├───────────────────────────────────────────────────────────────┤
│                         PAYLOAD                                │
│                    (Variable length)                           │
│                                                                │
│         ┌─────────────────────────────────────────┐           │
│         │  Encrypted Neural Data Block            │           │
│         │  (Spike trains / Neural state)          │           │
│         └─────────────────────────────────────────┘           │
│                                                                │
├───────────────────────────────────────────────────────────────┤
│                    AUTHENTICATION TAG (16 bytes)               │
│                    (AES-GCM or similar)                        │
└───────────────────────────────────────────────────────────────┘
```

### Packet Types

| Type Code | Name | Description |
|-----------|------|-------------|
| 0x0 | SPIKE_STREAM | Real-time spike train data |
| 0x1 | STATE_SNAPSHOT | Full neural state dump |
| 0x2 | STATE_DELTA | Incremental state update |
| 0x3 | PREDICTION_ERROR | Generative model error signal |
| 0x4 | CONTROL | Session management |
| 0x5 | ACK | Acknowledgment |
| 0x6 | HEARTBEAT | Keep-alive |
| 0x7-0xF | Reserved | Future use |

### Flags

| Bit | Name | Description |
|-----|------|-------------|
| 0 | ENCRYPTED | Payload is encrypted |
| 1 | COMPRESSED | Payload is compressed |
| 2 | URGENT | High priority delivery |
| 3 | RETRANSMIT | This is a retransmission |
| 4 | FRAGMENTED | Part of fragmented message |
| 5 | LAST_FRAGMENT | Last fragment of message |
| 6-15 | Reserved | Future use |

---

## Spike Encoding

### Spike Train Format

Neural spikes are encoded using **Address-Event Representation (AER)**:

```
SPIKE EVENT (8 bytes per spike):
┌───────────────────────────────────────────────────────────────┐
│   Neuron Address (32 bits)   │   Timestamp Offset (32 bits)   │
│   (Which neuron fired)       │   (Relative to packet time)    │
└───────────────────────────────────────────────────────────────┘
```

### Compression: Run-Length Encoding

For periods of silence, use run-length encoding:

```
SILENCE MARKER (4 bytes):
┌───────────────────────────────────────────────────────────────┐
│  Marker (0xFFFFFFFF)  │     Duration (microseconds)           │
└───────────────────────────────────────────────────────────────┘
```

### Bandwidth Calculation

| Scenario | Spike Rate | Bandwidth Required |
|----------|------------|-------------------|
| Idle | 10 Hz average | ~80 kbps |
| Active | 100 Hz average | ~800 kbps |
| Burst | 1000 Hz peak | ~8 Mbps |
| Full Corpus Callosum | 10 Hz × 200M neurons | ~16 Gbps |

**Note**: Generative Model reduces this by transmitting only prediction errors.

---

## Generative Model Optimization

### Concept

Instead of transmitting all spikes, the satellite's Generative Model predicts expected spike patterns. Only the **prediction error** (difference between predicted and actual) is transmitted.

```
PREDICTION ERROR FORMAT:
┌───────────────────────────────────────────────────────────────┐
│                    EXPECTED SPIKE (not sent)                   │
│                            ─                                   │
│                    ACTUAL SPIKE (observed)                     │
│                            =                                   │
│                    ERROR (transmitted)                         │
└───────────────────────────────────────────────────────────────┘
```

### Bandwidth Reduction

| Mode | Bandwidth | Reduction |
|------|-----------|-----------|
| Full spike stream | 16 Gbps | Baseline |
| With prediction | 1-2 Gbps | 90%+ |
| Steady state | 100-500 Mbps | 97%+ |

---

## Encryption

### Real-Time Stream (AES-256-GCM)

For spike streams requiring <1ms encryption latency:

```
ENCRYPTED PAYLOAD:
┌───────────────────────────────────────────────────────────────┐
│  IV/Nonce (12 bytes)  │  Ciphertext (variable)  │  Tag (16b) │
└───────────────────────────────────────────────────────────────┘
```

### Key Exchange (X25519 + Kyber)

Post-quantum hybrid key exchange for session establishment:

```
KEY EXCHANGE FLOW:
    Client                              Server
       │                                   │
       │──── ClientHello + X25519 ────────►│
       │◄─── ServerHello + X25519 + Kyber ─│
       │──── Kyber Encapsulation ─────────►│
       │                                   │
       │◄═══ Shared Secret Derived ═══════►│
       │                                   │
```

---

## Latency Budget

### Target: <50ms RTT

| Component | Budget | Notes |
|-----------|--------|-------|
| BCI → Transceiver | 2ms | On-chip processing |
| Transceiver → Ground | 3ms | UWB local link |
| Ground Processing | 1ms | Encryption, routing |
| Ground → Satellite | 8ms | LEO uplink (550km) |
| OISL Processing | 1ms | Routing decision |
| Satellite SNN | 5ms | Neural computation |
| Return Path | 20ms | Same path reversed |
| **Total RTT** | **~40ms** | Within 50ms target |

### Priority Classes

| Class | Max Latency | Use Case |
|-------|-------------|----------|
| CRITICAL | 20ms | Safety signals, kill switch |
| REALTIME | 50ms | Normal neural stream |
| BULK | 500ms | State snapshots, logs |
| BACKGROUND | 5s | Telemetry, updates |

---

## Error Handling

### Forward Error Correction (FEC)

Reed-Solomon coding for critical data:

```
FEC BLOCK:
┌─────────────────────────────────────────┐
│  Data Symbols (223 bytes)  │  Parity (32 bytes)  │
└─────────────────────────────────────────┘

Correction Capability: Up to 16 byte errors per block
```

### Retransmission

For packets failing FEC:

```
RETRANSMIT REQUEST:
┌───────────────────────────────────────────────────────────────┐
│  Type: ACK  │  Flags: NACK  │  Missing Sequence Numbers...    │
└───────────────────────────────────────────────────────────────┘
```

### Timeout Values

| Operation | Timeout | Action on Timeout |
|-----------|---------|-------------------|
| Packet ACK | 100ms | Retransmit |
| Session Heartbeat | 1s | Send heartbeat |
| Session Timeout | 10s | Reconnect |
| Link Failure | 30s | Switch to backup |

---

## Security Considerations

### Threat: Packet Injection

**Mitigation**: All packets authenticated with AES-GCM tag.

### Threat: Replay Attack

**Mitigation**: Timestamp + sequence number validation. Reject packets >1s old.

### Threat: Man-in-the-Middle

**Mitigation**: Mutual authentication during key exchange. Certificate pinning.

### Threat: Side-Channel

**Mitigation**: Constant-time cryptographic operations. Traffic padding.

---

## Protocol State Machine

```
                    ┌─────────────┐
                    │    IDLE     │
                    └──────┬──────┘
                           │ connect()
                           ▼
                    ┌─────────────┐
             ┌─────►│  CONNECTING │◄─────┐
             │      └──────┬──────┘      │
             │             │ success     │ timeout
             │             ▼             │
             │      ┌─────────────┐      │
             │      │   ACTIVE    │──────┘
             │      └──────┬──────┘
             │             │
             │    ┌────────┼────────┐
             │    │        │        │
             │    ▼        ▼        ▼
             │ STREAMING  TRANSFER  SYNC
             │    │        │        │
             │    └────────┼────────┘
             │             │
             │             │ close()
             │             ▼
             │      ┌─────────────┐
             └──────│   CLOSING   │
                    └──────┬──────┘
                           │
                           ▼
                    ┌─────────────┐
                    │   CLOSED    │
                    └─────────────┘
```

---

## Implementation Notes

### Software Interface (Pseudocode)

```python
class OISLNeuralProtocol:
    def __init__(self, node_id, encryption_key):
        self.node_id = node_id
        self.crypto = AESGCMCipher(encryption_key)
        self.sequence = 0
    
    def send_spikes(self, spike_events: List[SpikeEvent]) -> None:
        """Send real-time spike train."""
        encoded = self.encode_aer(spike_events)
        compressed = self.compress(encoded)
        encrypted = self.crypto.encrypt(compressed)
        packet = self.build_packet(
            type=SPIKE_STREAM,
            payload=encrypted,
            priority=REALTIME
        )
        self.transmit(packet)
    
    def send_state(self, neural_state: NeuralState) -> None:
        """Send full neural state snapshot."""
        serialized = neural_state.serialize()
        compressed = self.compress(serialized)
        encrypted = self.crypto.encrypt(compressed)
        packets = self.fragment(encrypted, max_size=65000)
        for packet in packets:
            self.transmit(packet)
```

### Hardware Requirements

| Component | Minimum | Recommended |
|-----------|---------|-------------|
| Processing | ARM Cortex-A72 | FPGA for FEC |
| Memory | 4 GB | 16 GB |
| Crypto Accelerator | AES-NI | Dedicated HSM |
| Network | 10 Gbps | 100 Gbps |

---

## Testing & Validation

### Conformance Tests

1. **Packet Format**: Verify all fields encoded correctly
2. **Encryption**: Verify encrypt/decrypt round-trip
3. **Timing**: Verify latency within budget
4. **Error Handling**: Verify FEC correction
5. **State Machine**: Verify all transitions

### Performance Benchmarks

| Test | Target | Measurement |
|------|--------|-------------|
| Packet encoding | <100μs | Time to encode spike packet |
| Encryption | <500μs | Time to encrypt 64KB |
| Throughput | 10 Gbps | Sustained data rate |
| Latency | <5ms | Protocol overhead |

---

## Versioning

### Version Number Format

`MAJOR.MINOR.PATCH`

- MAJOR: Breaking changes
- MINOR: New features, backward compatible
- PATCH: Bug fixes

### Current Version

**0.1.0** - Initial draft specification

### Planned Versions

- 0.2.0: Add multicast support
- 0.3.0: Add QoS differentiation
- 1.0.0: Production release

---

## References

1. Address-Event Representation (AER) standard
2. AES-GCM (NIST SP 800-38D)
3. X25519 (RFC 7748)
4. Reed-Solomon coding
5. CCSDS Space Packet Protocol

---

*Protocol specification maintained by ArkSpace.me team*
