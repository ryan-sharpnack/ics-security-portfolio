Week 1 - Day 1
Date: December 26, 2025

Domains Completed
✓ Power Grid Operations
✓ Protocols
✓ Firmware Analysis
✓ Offensive Tools

Power Grid Operations
Topic: Power generation basics
Key Concepts:

Most power generation uses turbines spinning generators (electromagnetic induction)
Thermal plants (coal, gas, nuclear) follow: Heat → Steam → Turbine → Generator
Baseload vs peaking power: Nuclear/coal are slow to start (baseload), gas turbines ramp quickly (peaking)
Grid frequency (60 Hz in North America) must be maintained by constantly balancing supply and demand
Generation voltages are low (10-25 kV) for safety and equipment design

Security Implications:

Physical processes are slow - plants take hours to ramp up/down
Safety systems are critical - overheating or pressure issues can cause explosions
SCADA systems control temperatures, pressures, valve positions, turbine speeds


Protocols
Topic: ICS vs IT protocols, Modbus fundamentals
Key Concepts:

ICS protocols prioritize reliability and real-time performance over security
Designed for air-gapped networks with physical security (1960s-1990s)
No authentication, encryption, or logging by design - trust-based model
Modbus (1979): Simple, open, ubiquitous - deployed in billions of devices
Master-slave architecture, four data tables (coils, discrete inputs, holding registers, input registers)

Real-World Attacks:

Stuxnet (2010) - Modified Modbus commands to destroy centrifuges
CRASHOVERRIDE (2016) - Used ICS protocols to black out Ukraine
TRITON (2017) - Targeted safety systems via protocol vulnerabilities

Security Challenge:

Can't fix the protocols (too much legacy equipment)
Must secure the environment: segmentation, firewalls, anomaly detection
Legitimate traffic looks identical to malicious traffic


Firmware Analysis
Topic: What is firmware, why analyze it, common vulnerabilities
Key Concepts:

Firmware = low-level software controlling hardware directly
Stored in non-volatile memory, boots before OS, rarely updated
Common ICS vulnerabilities: hardcoded credentials, buffer overflows, command injection, authentication bypasses
Research methodology: Acquire → Identify → Extract → Analyze → Disclose

Notable CVEs:

CVE-2018-7522 (Triconex/TRITON) - Hardcoded credentials enabled safety system attack
CVE-2022-38465 (Siemens S7-1200/1500) - Authentication bypass in widely deployed PLCs
CVE-2020-15782 (Schneider Modicon) - Hardcoded crypto key across all devices

Why It Matters:

Firmware vulnerabilities persist for decades (devices run 20-30 years)
Few professionals can reverse engineer firmware
Finding vulnerabilities before attackers do is critical


Offensive Tools
Topic: Python environment setup for ICS security research
Completed:

Installed Python 3.13.11 on Kali Linux
Created virtual environment (ics-env)
Installed libraries: scapy, pymodbus 3.11.4, pyserial
Verified all imports with test script

Lab Environment:

Ubuntu Server (192.168.X.X) - OpenPLC
Windows 10 (192.168.X.X) - HMI
Kali Linux (192.168.X.X) - Attack platform
Isolated vboxnet0 network (192.168.X.X/24)


Key Takeaways

Understanding the physical systems (power generation) is essential for understanding attack impact
ICS protocols were intentionally designed without security for operational reasons
Firmware analysis is a rare, high-value skill in ICS security
Python + isolated lab environment provides safe testing platform
