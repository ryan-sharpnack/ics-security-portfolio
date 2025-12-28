Week 1 - Day 2: Transmission Systems, Modbus Protocol, Ghidra Installation, and Socket Programming
Overview
Completed four core competency areas: power grid transmission architecture, Modbus protocol fundamentals, Ghidra reverse engineering environment setup, and TCP socket programming for offensive security tools.

Power Grid Operations (1 hour)
Topic: Transmission System Architecture
Key Learnings

Studied high voltage transmission line specifications ranging from 69kV to 765kV
Examined step-up transformer operations at generation facilities
Understanding how generated electricity is transformed to high voltage for efficient long-distance transmission

Deliverable

Created generation-to-transmission system diagram illustrating power flow from generation plant through step-up transformers to transmission lines

Relevance to Security Research
Transmission infrastructure represents critical attack surface in power grid operations. Understanding system architecture enables identification of high-value targets and cascading failure scenarios in cyber-physical attacks.

Protocols (1 hour)
Topic: Modbus History and Deployment
Key Learnings

Reviewed Modbus specification documentation from Modbus.org
Studied historical context: Modbus developed in 1979 by Modicon for PLC communication
Analyzed why Modbus remains ubiquitous despite age: simplicity, reliability, open standard
Researched deployment across industries: manufacturing, building automation, energy management, water treatment, and power generation

Security Implications

Modbus protocol designed without security considerations (pre-internet era)
No native authentication, encryption, or integrity checking
Legacy deployment makes it primary attack vector in ICS environments
Understanding Modbus essential for firmware vulnerability research in power sector equipment


Firmware Analysis (1 hour)
Topic: Ghidra Installation and Configuration
Accomplishments

Successfully resolved Java JDK 21 PATH configuration issues on Kali Linux VM
Migrated Ghidra installation to Ubuntu host system for improved stability
Downloaded Ghidra 11.2.1 (stable release) from NSA GitHub repository
Completed successful installation and initial launch

Technical Notes

Configured JAVA_HOME environment variable: /usr/lib/jvm/java-21-openjdk-amd64
Verified Java Runtime Environment compatibility
Selected Ghidra 11.2.1 over 12.0 for production stability

Offensive Capability Development
Now equipped to perform static analysis on ICS/OT firmware binaries to identify vulnerabilities including buffer overflows, hardcoded credentials, authentication bypasses, and unsafe function usage.

Offensive Tools (1 hour)
Topic: Basic TCP Socket Programming
Code Developed

TCP Server (Python): Listens on localhost:9999, accepts connections, receives messages, sends responses
TCP Client (Python): Connects to server, transmits data, receives acknowledgment

Implementation Details

Used Python socket library for network programming
Implemented proper error handling and connection management
Demonstrated TCP three-way handshake and reliable data transfer
Tested client-server communication successfully on Kali Linux VM

Security Testing Applications
Socket programming forms foundation for:

ICS protocol fuzzing (Modbus, DNP3, IEC 61850)
Custom exploit development for network-based vulnerabilities
Traffic interception and protocol analysis
Denial-of-service testing against industrial control systems

Conceptual Understanding

Reinforced TCP guaranteed delivery vs UDP best-effort models
Identified attack vectors: malformed packets, protocol confusion, information disclosure, resource exhaustion
Recognized critical lack of authentication/trust in legacy ICS protocols
Connected socket programming to firmware analysis: server-side code in embedded systems handles these connections and represents primary attack surface


Tools and Environment

Host System: Ubuntu (Ghidra development environment)
VM: Kali Linux (offensive tool development and testing)
Primary Tools: Ghidra 11.2.1, Python 3, OpenJDK 21

Career Development Notes
Completed Day 2 of 18-week training program focused on Power Malware Engineering with specialization in Firmware Security Research. Current trajectory points toward career path as Firmware Security Researcher in ICS/OT sector with emphasis on power grid critical infrastructure protection.
Strategic Focus

Building technical foundation for CVE discovery and responsible disclosure
Developing expertise in power sector equipment and protocols
Preparing for firmware vulnerability research without hardware requirements (static analysis focus)
Long-term goal: Protect U.S. critical infrastructure through proactive security research
