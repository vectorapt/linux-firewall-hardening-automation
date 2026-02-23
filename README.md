# Linux Firewall Configuration & Security Hardening (firewalld)

## 📌 Overview

This project demonstrates host-based firewall configuration and security hardening using firewalld on a RHEL-based virtual machine. The system is treated as a minimal production-like server where only required services are exposed following least-privilege principles.

The project also includes troubleshooting exercises and lightweight Bash automation for firewall validation.

---

## 🎯 Objectives

- Configure firewall rules using firewalld
- Apply least-privilege security principles
- Understand runtime vs permanent rules
- Simulate firewall-related failures
- Perform structured troubleshooting
- Automate firewall checks using Bash

---

## 🖥 Environment

- Platform: VMware
- Operating System: RHEL 9
- Firewall Manager: firewalld
- Test Services: SSH, HTTP

---

## 🔥 Firewall Hardening Strategy

The firewall configuration follows a least-privilege model:

- Allow only required services
- Block all other inbound traffic by default

Allowed Services:

- SSH (administrative access)
- HTTP (simulated application traffic)

---

## ⚙ Firewall Configuration

Firewall configuration begins by identifying the active firewall zones and the default zone associated with the network interface. Required services are added using permanent rules to ensure persistence across reboots, followed by a firewall reload to apply changes.

Firewall state verification confirms that only intended services are exposed.

---

## ❌ Failure Simulation

SSH access is intentionally disrupted by removing the SSH firewall rule. This simulates a common administrative misconfiguration scenario where connectivity issues arise despite the service remaining operational.

Observed behavior:

- SSH connection attempts fail
- SSH daemon remains active

---

## 🛠 Troubleshooting Methodology

Connectivity issues are diagnosed using a structured approach:

- Inspect firewall configuration and allowed services
- Validate service state
- Verify listening ports
- Perform external validation

---

## ✅ Resolution

SSH connectivity is restored by correcting firewall rules and reloading the firewall configuration.

---

## 🔁 Persistence Testing

Firewall rules are verified after system reboot to ensure configuration persistence.

---

## 🤖 Bash Automation

A lightweight Bash script validates firewall configuration, detects missing services, and logs command outcomes.

---

## ✅ Skills Demonstrated

- firewalld configuration and management
- Firewall troubleshooting workflow
- Service versus network diagnostics
- Bash scripting for validation
