# FreeWorthyFort — Analogically Isolated Autonomous Hardware Security Module (HSM)

Welcome to the official repository for FreeWorthyFort, a revolutionary, battery-free, plug-and-play hardware security solution designed to protect computers from high-level cyber threats, ransomware, and unauthorized physical tampering. 

By repurposing the traditionally overlooked and underutilized 3,5 mm analog audio port (AUX jack), FreeWorthyFort operates completely outside the computer’s digital buses. It establishes a 100% hacker-immune Hardware Air-Gap that cannot be bypassed by any remote software exploit, zero-day vulnerability, or administrative privilege escalation.

---

## Table of Contents
1. Executive Summary
2. Core Technical Specifications
3. Comprehensive Feature Set
4. Why FreeWorthyFort is Superior to USB Modules
5. Acoustic Engineering & Health Safety
6. Hardware Component Breakdown
7. Installation & Setup
8. Author & Licensing

---

## Executive Summary

Modern cybersecurity relies heavily on software-level defense mechanisms (antiviruses, firewalls) or digital hardware keys (USB tokens). However, if an advanced attacker achieves kernel-level access (Ring 0), digital defenses can be blinded, bypassed, or falsified.

FreeWorthyFort completely disrupts this paradigm. It acts as an autonomous analog watchdog. It consumes power harvested entirely from a highly optimized, completely silent 19 kHz audio frequency wave pushed through the computer's built-in DAC. Inside the 3,5 mm jack is a high-efficiency Texas Instruments MSPM0 32-bit ARM Cortex-M0+ microchip running at 80 MHz. It continuously communicates with a low-level OS kernel service via time-based rolling cryptographic keys (TOTP). 

If the computer freezes, gets hacked, or attempts to stop the security stream, FreeWorthyFort instantly detects it through physical and electrical laws. It then activates a hardware-level hard reset or a temporary volatile RAM-memory wiping panic sequence to isolate cryptographic keys before malware can harvest them, protecting permanent storage and files from corruption. It does all of this completely battery-free and 100% silently, with zero risk to human health.

---

## Core Technical Specifications

| Parameter | Specification | Details |
| :--- | :--- | :--- |
| Interface | 3.5 mm TRRS (Tip, Ring 1, Ring 2, Sleeve) | Works on standard stereo + microphone ports |
| Host System Requirement | Standard audio output DAC capabilities | Universal compatibility (Windows, Mac, Linux) |
| Power Input Method | Acoustic Energy Harvesting (AC to DC) | No internal or external batteries required |
| Carrier Frequency | 19,000 Hz (+/- 5 Hz) Sinusoidal | High-power output zone, completely human-silent |
| Gross Harvested Power | 30.00 mW | Achieved via differential 180 degree phase-inverted drive |
| Processor Module | Texas Instruments MSPM0 32-bit ARM | Integrated AES Hardware Cryptographic Engine |
| Processor Clock Speed | 80 MHz | Up to 80 million instructions per second |
| Fallback Energy Reservoir| 0.1 Farad Ultra-Low-Leakage Supercap | Provides 1 to 3 minutes of total blackout survival |
| Hardware Encapsulation | Deep Industrial Epoxy Potting | 100% vibration, moisture, and sound-leak proof |

---

## Comprehensive Feature Set

FreeWorthyFort's hyper-optimized architecture allows it to run a massive array of concurrent hardware protections on a minimal power footprint:

### 1. Hardware Watchdog & Anti-Freeze Loop
FreeWorthyFort monitors a low-amplitude hardware heartbeat transmitted within the 19 kHz power wave. If the host computer crashes into a Blue Screen of Death (BSOD), experiences a kernel panic, or gets frozen by an automated script, the heartbeat immediately stops. Within milliseconds, FreeWorthyFort triggers a physical reset sequence.

### 2. Time-Based Rolling Cryptographic Keys (TOTP)
To prevent advanced software spoofing (where malware takes control of the OS and fakes a "healthy" state to the port), FreeWorthyFort and the host service execute a high-speed cryptographic challenge-response mechanism. Using shared secret seeds, they calculate a matching rolling key every second. If an attacker tampers with the kernel code, the response timing or mathematical accuracy fails, violating the latency verification check (<= 20 ms windows), and safety protocols engage.

### 3. Physical Panic Button & Volatile Memory Protection
The exterior housing features an ultra-low-profile tactile interrupt button. Pressing it (or triggering an automatic security flag) prompts FreeWorthyFort to manipulate the analog ground impedance of the 3.5mm line. This triggers a hardware-level power cutoff via the motherboard's power management rails, instantly clearing the volatile RAM-muisti (temporary memory) to protect your decryption keys and passwords while keeping your physical hard drive data safe.

### 4. Hardware Air-Gapped Black Box Logger
FreeWorthyFort contains an isolated, non-volatile EEPROM memory sector. It serves as a secure syslog repository. The host computer continuously writes critical system signatures and connection states to FreeWorthyFort. Since this memory is physically separated from all digital buses, no hacker or malicious code can delete or modify these logs. Even if the computer is wiped clean, FreeWorthyFort retains the exact forensics of the breach.

### 5. Sub-GHz Wireless Emergency Beacon (LoRa)
In high-security enterprise environments where an attacker might disconnect the infected computer from local Wi-Fi or Ethernet to isolate it, FreeWorthyFort can deploy a long-range wireless broadcast. Operating over low-power LoRa/Sub-GHz frequencies, it transmits an encrypted alert signal ("System Compromised!") to a remote security terminal or smartphone up to 1 km away—completely autonomously.

### 6. Active Audio Shielding & EMI Shunt
When headphones or external audio lines are connected through FreeWorthyFort, the device uses its remaining current to dynamically filter out Electromagnetic Interference (EMI) and coil whine originating from the motherboard, high-draw graphics cards, or mouse movements. It cleans the analog line, improving baseline audio fidelity.

### 7. Environmental Safeguards & Anti-Theft
FreeWorthyFort integrates a highly efficient MEMS-based ambient light sensor and an ambient gas (VOC/CO2) monitoring element. If an adversary attempts to steal a laptop directly out of a backpack or workspace, the rapid light or movement change triggers an immediate lockdown. In normal office scenarios, it tracks carbon dioxide levels, pulsing its status LED yellow when it is time to ventilate the room.

### 8. Automated Acoustic Self-Cleaning
When the port is left unused for long intervals, FreeWorthyFort's firmware can execute an ultrasonic micro-pulse blast. This generates microscopic, unhearable structural vibrations along the internal leaf springs, shaking loose any trapped pocket lint or dust particles to maintain perfect contact resistivity.

---

## Why FreeWorthyFort is Superior to USB Modules

While USB security tokens (like traditional hardware keys) are common, they are fundamentally vulnerable on an architectural level. FreeWorthyFort offers four decisive advantages over any USB-based device:

*   **Absolute Immunity to Digital Exploits (No BadUSB):** A USB port connects directly to the computer's high-speed data buses and system kernel. Attackers can exploit USB drivers or inject malicious firmware (BadUSB) to spoof a keyboard and compromise your machine. FreeWorthyFort utilizes a 100% analog audio interface. It possesses no digital data path to command the CPU or read storage, maintaining a pure physical Air-Gap.
*   **Zero Bus Latency for Active Filtering:** Implementing active audio shielding or environment tracking over USB requires digital encoding, serialization, processing, and decoding, introducing severe latency. FreeWorthyFort interacts at the speed of analog circuitry directly inside the audio pathway, allowing real-time EMI cancellation without lag.
*   **Operating System Independent Failsafe:** If malware compromises the OS or triggers a kernel freeze, the USB controllers usually stop processing or fail entirely, rendering USB-based safety watchdogs useless. Because the 3,5 mm port's electrical and impedance traits remain independent of OS crashes, FreeWorthyFort can still safely cycle system power even during a total OS freeze.
*   **Zero Impact on Valuable Ports:** Modern laptops suffer from a severe shortage of USB-C and USB-A ports, which are constantly reserved for chargers, docks, or external drives. FreeWorthyFort utilizes the 3.5 mm auxiliary port—a resource left 100% empty and unused by the vast majority of users due to wireless Bluetooth headphones.

---

## Acoustic Engineering & Health Safety

A primary concern when deploying continuous acoustic energy harvesting is audible noise contamination and human health. FreeWorthyFort has been meticulously designed to alleviate these factors entirely:

*   **The 19,000 Hz Choice:** The human audibility spectrum nominally ranges from 20 Hz to 20,000 Hz. However, the upper threshold degrades rapidly with age. The 19 kHz frequency was explicitly chosen because it resides completely outside the perceptual range of adult humans, while still remaining safely below the steep low-pass hardware filters embedded in standard computer DACs (which usually drop sharply above 20 kHz).
*   **Total Electronic Isolation:** FreeWorthyFort does not feature any acoustic diaphragms, speakers, or piezo-transducers configured to vibrate the open air. The 19 kHz frequency is strictly contained as a sifting alternate current (AC) within the copper traces and internal components of the device. 
*   **100% Silent Epoxy Potting:** To eliminate any possibility of coil whine or microscopic mechanical vibrations generated inside the capacitors or Schottky diodes, the entire internal layout is vacuum-sealed in a dense, sound-damping industrial epoxy compound. Not a single decibel of acoustic energy is radiated into the environment. 
*   **Absolute Compliance & Safety:** Because the frequency remains safely sequestered in the electrical domain and emits 0 dB of external noise, it is 100% safe for prolonged daily use. It causes absolutely no neurological fatigue, nausea, or headaches, and is completely undetectable and harmless to highly sensitive environments containing infants, children, or domestic pets (cats/dogs).

---

## Hardware Component Breakdown

Should you wish to review, audit, or construct a prototype of the FreeWorthyFort architecture, the hardware BOM (Bill of Materials) requires:

1.  **Microcontroller:** Texas Instruments MSPM0G3507 (32-bit ARM Cortex-M0+, 80 MHz, ultra-low standby, integrated AES cryptographic hardware block).
2.  **Rectification Matrix:** 4x BAT54S Ultra-Fast Schottky Diodes arranged in a high-efficiency H-Bridge layout to convert high-frequency AC to steady DC.
3.  **Energy Reservoir:** AVX / Elna 0.1F 5.5V Supercapacitor (Ultra-low internal leakage variant).
4.  **Wireless Unit:** Semtech SX1262 LoRa Transceiver, optimized via software to operate at minimal current output states.
5.  **Gas Analysis:** Bosch BME680 Environmental Sensor running on specialized pulsed micro-heating profiles.

---

## Installation & Setup

FreeWorthyFort does not require complex internal modifications or voiding device warranties.

1.  **Hardware Connection:** Insert FreeWorthyFort firmly into the primary 3,5 mm headphone port on your computer, laptop, or server blade.
2.  **Service Installation:** Deploy the lightweight background service (worthyfortd) matching your operating system package manager:
    ```bash
    # Linux (Systemd)
    sudo make install && sudo systemctl enable worthyfort.service --now
    
    # macOS
    brew install worthyfort && brew services start worthyfort
    ```
3.  **Initialization:** Follow the software initialization wizard to link FreeWorthyFort to your operating system's secure embedded sector.
4.  **Verification:** The status LED on the FreeWorthyFort casing will glow solid green. The analog fortress is now active, monitoring your machine 24/7.

---

## Author & Licensing

*   **Author:** Juho Artturi Hemminki
*   **Licensing:** This project is licensed under the terms of the Apache License 2.0.
