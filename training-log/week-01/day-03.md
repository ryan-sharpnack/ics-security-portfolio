# Day 3 Summary - ICS Security Training

**Date:** 12/28/25  
**Status:** ✅ Complete  
**Total Time:** 4 hours

---

## Power Grid Operations (1 hour)

**Topic:** Distribution System

### Key Learnings:
- Step-down transformers convert transmission voltage to distribution levels
- Medium voltage: 12-35kV for industrial/commercial distribution
- Low voltage: <1kV for residential service
- Understanding voltage levels critical for impact assessment of attacks

### Practical Application:
Distribution systems are the final link between transmission and end-users. Compromising distribution equipment affects smaller areas but targets specific facilities (hospitals, data centers, industrial plants).

---

## Protocols (1 hour)

**Topic:** Modbus TCP vs RTU

### Key Learnings:
- **Modbus TCP:** Runs over Ethernet (TCP/IP), port 502
- **Modbus RTU:** Runs over serial (RS-485), binary encoding
- Packet format differences: TCP adds MBAP header, RTU uses CRC
- Deployment contexts: TCP for modern systems, RTU for legacy/field devices

### Practical Application:
Understanding both variants essential for firmware analysis. Many devices implement both protocols. Attack surface differs based on network vs serial access.

---

## Firmware Analysis (1 hour)

**Topic:** Ghidra Interface and Navigation

### Key Learnings:
- Symbol Tree: Overview of binary structure (functions, data, imports)
- Listing Window: Assembly code view with addresses
- Decompiler Window: Converts assembly to C-like pseudocode
- Navigation: Jumping between assembly and decompiled code seamlessly

### Practical Application:
Comfortable navigating Ghidra is foundational. Decompiler makes vulnerability identification faster by showing logic in readable format. Practice with sample binaries builds muscle memory for future firmware analysis.

### Tools Used:
- Ghidra (NSA)
- Sample binaries for practice

---

## Offensive Tools (1 hour)

**Topic:** Scapy Packet Manipulation

### Key Learnings:
- Packets are layered structures: `IP / TCP / Data`
- Layer stacking with `/` operator
- Field access: `packet[TCP].dport`
- Send/receive: `sr1()` for single response, `sr()` for multiple
- Layer examination: `.show()`, `.summary()`, `hexdump()`

### Practical Application:
Scapy enables custom packet crafting for protocol testing. Essential for:
- Testing Modbus/DNP3 implementations in firmware
- Fuzzing ICS protocol parsers
- Creating proof-of-concept exploits
- Understanding protocol internals at byte level

### Scripts Created:
```
REDACTED           - Packet creation
REDACTED     - Send/receive operations
REDACTED           - Layer analysis
```

### Key Commands:
```python
# Create packet
packet = IP(dst="192.168.X.X") / TCP(dport=502)

# Send and receive
response = sr1(packet, timeout=2)

# Examine layers
packet.show()
packet[TCP].dport
```

---

## Integration Notes

**Cross-Domain Connections:**
- Distribution system voltage levels → Modbus monitoring points
- Modbus TCP protocol → Future firmware analysis targets
- Scapy packet crafting → Testing Modbus implementations
- Ghidra navigation → Analyzing protocol handlers in binaries

**Analogy of the Day:**
Packet structure is like tire markings - standardized format where each field has specific meaning. Understanding the structure allows reading and modification of any field for legitimate testing purposes.

---

**Progress:** 3/365 days (Week 1, Day 3)  
**Momentum:** Building ⚡
