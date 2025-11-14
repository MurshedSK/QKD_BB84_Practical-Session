# ⚛️ Quantum Cryptography Lab Report: BB84 Protocol

## Overview & Project Goal
This repository contains the source code and report files for a university project analyzing the security principle of the **BB84 (Bennett and Brassard, 1984) protocol** using polarization encoding.

The project validates the physical principles through a **classical optics analogy** (using a laser and optics) and verifies the security principle through a **Cirq simulation** of Eve’s intercept-resend attack.

---

### 1. Core Technical Principles
The experiment relies on the direct mathematical analogy between the quantum polarization state (qubit) and classical Jones vectors.

| Component | Function | Relationship (Q1.2) |
| :--- | :--- | :--- |
| **HWP (Alice/Encoder)** | Rotates the initial polarization state to encode the bit in the chosen basis. | Physical Polarization Angle ($\phi$) = $2 \times$ HWP Angle ($\theta$) |
| **PBS (Bob/Decoder)** | Performs a projective measurement by transmitting horizontal ($|0\rangle$) and reflecting vertical ($|1\rangle$) polarization. | N/A |

| Key Angles (HWP $\theta$) | HV Basis $|0\rangle / |1\rangle$ | DA Basis $|+\rangle / |-\rangle$ |

| **Alice's Preparation ($\Theta_A$)** | $0^{\circ}$ and $45^{\circ}$ | $22.5^{\circ}$ and $-22.5^{\circ}$ |
| **Bob's Measurement ($\Theta_B$)** | $0^{\circ}$ (Direct HV) | $22.5^{\circ}$ (Rotation to DA) |

---

### 2. Detailed Experimental Results

The project compares three scenarios, contrasting the theoretical prediction (25% QBER) with the experimental observations.

| Scenario | Data Sifted | Key/Error Rate | Significance |
| :--- | :--- | :--- | :--- |
| **1. Theoretical Abort Threshold (Q1.11)** | N/A | **25.00%** | The QBER at which Eve gains maximum information and the key must be discarded. |
| **2. Experimental Run (Without Eve, Q1.9)** | 7 bits | **0.00%** | Confirms the physical setup is calibrated perfectly (no noise or external errors). |
| **3. Simulation Run (With Eve, Q2.8)** | 12 bits | **16.67%** | **Validation:** This high, non-zero QBER is detectable and successfully proves that the intercept-resend attack violates the 0% error baseline, preventing Eve from gaining a secure key. |

---
