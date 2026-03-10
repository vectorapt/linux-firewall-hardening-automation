# Linux Firewall Configuration & Security Hardening (firewalld)

## Overview

This project demonstrates host-based firewall configuration and security hardening using **firewalld** on a RHEL 9 virtual machine.

The system is configured following **least-privilege principles**, exposing only required services.  
The project also includes failure simulation, troubleshooting, and a small Bash validation script.

---

## Objectives

• Configure firewall rules using firewalld  
• Apply least-privilege security principles  
• Simulate firewall misconfiguration scenarios  
• Perform structured troubleshooting  
• Validate firewall configuration with Bash automation

---

## Environment

Platform: VMware  
Operating System: RHEL 9  
Firewall Manager: firewalld  

Testing Setup:

Machine1 – Firewall Server (RHEL 9)  
Machine2 – External Client used for SSH validation

---

## Firewall Hardening Strategy

The firewall configuration follows a **least-privilege model**.

Only the following services are exposed:

SSH  
HTTP  

Default services such as **cockpit** and **dhcpv6-client** were removed to reduce unnecessary exposure and enforce a minimal access model.

---

## Firewall Validation

After applying the hardened configuration, external connectivity was tested.

SSH access from an external machine confirmed that the firewall allowed administrative access while restricting other services.

---

## Failure Simulation

To simulate a common misconfiguration scenario, the SSH firewall rule was intentionally removed.

An external SSH attempt was performed again, which resulted in a **connection failure**.

This demonstrates how firewall rules directly affect network accessibility.

---

## Troubleshooting

A structured troubleshooting approach was used to identify the cause of the failure:

• Verify SSH daemon status  
• Confirm SSH port is listening  
• Inspect firewall service rules  

The investigation confirmed that SSH traffic was blocked by the firewall configuration.

---

## Resolution

The SSH firewall rule was restored and the firewall configuration reloaded.

External SSH access was tested again and connectivity was successfully restored.

---

## Bash Automation

A lightweight Bash script was created to quickly validate firewall configuration.

The script checks:

• firewalld service status  
• currently allowed firewall services  

---

## Skills Demonstrated

• firewalld configuration and management  
• Linux firewall hardening  
• least-privilege security implementation  
• structured troubleshooting methodology  
• network service validation  
• Bash scripting for system checks

---

## Project Structure

```
linux-firewall-hardening
├── README.md
├── firewall-policy-check.sh
└── screenshots/
    ├── firewall-status&baseline-services.png
    ├── ssh-success.png
    ├── ssh-failure.png
    ├── troubleshooting.png
    ├── ssh-restored.png
    └── script-output.png
```

