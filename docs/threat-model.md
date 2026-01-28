# Threat Model — System Hardening Labs

## Scope and Objectives

This repository documents practical system hardening experiments and notes across Linux, networking, and Android-based systems.  
The purpose of this threat model is to define **what is being protected**, **against whom**, and **under which assumptions**, in order to guide technical decisions throughout the project.

The focus is on **operating system–level security**, not application-layer security alone.

---

## Assets

The primary assets considered in this project are:

- Integrity of the operating system (kernel, core services, system configuration)
- Confidentiality of user and system data
- Availability and reliability of system services
- Isolation boundaries between processes, users, and network namespaces
- Trustworthiness of the execution environment

---

## Threat Actors

This project considers the following threat actors:

### 1. Remote Network Adversaries
- Untrusted external hosts
- Attackers exploiting exposed services, open ports, or protocol weaknesses
- Capable of packet injection, scanning, and traffic analysis

### 2. Local Unprivileged Adversaries
- Malicious or compromised user-space processes
- Attempts to escalate privileges or escape isolation boundaries
- Abuse of Linux capabilities, misconfigured permissions, or weak sandboxing

### 3. Supply Chain and Software Risks
- Vulnerabilities in third-party components
- Misconfigurations introduced during system updates
- Unsafe default settings inherited from upstream projects

### 4. Physical or Semi-Trusted Access
- Brief physical access to a device
- Access via debugging interfaces or recovery environments (where applicable)

---

## Out of Scope

The following are explicitly out of scope for this repository:

- Social engineering attacks
- Phishing or user-behavior-based threats
- Advanced hardware attacks (e.g., invasive side-channel analysis)
- Nation-state–level adversaries with unlimited resources

---

## Assumptions

- The system starts from a reasonably trusted baseline (e.g., official Linux distributions or AOSP-based builds)
- Secure boot and firmware integrity are assumed unless otherwise stated
- Users follow basic operational security practices
- The goal is **risk reduction**, not absolute security

---

## Security Principles Applied

This project is guided by the following principles:

- **Least Privilege**: Minimize permissions, capabilities, and exposed interfaces
- **Defense in Depth**: Multiple independent layers of protection
- **Attack Surface Reduction**: Disable or restrict unnecessary services and features
- **Strong Isolation**: Use namespaces, permissions, and sandboxing effectively
- **Explicit Trust Boundaries**: Clearly define and document isolation limits
- **Auditable Configuration**: Prefer transparent and reviewable system settings

---

## Mapping to Project Areas

This threat model informs the following areas:

- **Linux**
  - Permissions, capabilities, namespaces, and kernel hardening
- **Networking**
  - Firewall rules, traffic visibility, protocol exposure, and filtering
- **Android**
  - AOSP security model, application isolation, and system service exposure

Each lab or note in this repository should implicitly or explicitly relate back to this threat model.

---

## Non-Goals

- Creating exploit code
- Bypassing protections for offensive purposes
- Benchmarking performance at the cost of security

The emphasis is on **understanding, documenting, and improving system security posture**.

---

## Living Document

This threat model is a **living document**.  
It may evolve as new attack surfaces, technologies, or constraints are explored.

Changes should be justified by new findings or shifts in assumptions.
