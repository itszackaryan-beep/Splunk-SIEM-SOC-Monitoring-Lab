# 8. Challenges and Troubleshooting

## Introduction

During the implementation of the SOC lab, several technical challenges were encountered while
configuring Splunk Enterprise, Windows Server, Ubuntu Linux, VMware Workstation, and Kali
Linux. Most issues related to virtual machine networking, log forwarding, firewall
configuration, and data ingestion. Each issue was analyzed and resolved systematically.

## Objectives

- Identify the major challenges encountered during the project.
- Explain the troubleshooting process.
- Describe the solutions implemented.
- Document lessons learned during implementation.

## Challenge 1 — VMware Network Connectivity

**Problem:** The Windows Server and Ubuntu virtual machines were unable to communicate with
each other. Network connectivity issues prevented log forwarding and remote communication.

**Troubleshooting:**
- Verified VMware network adapter settings.
- Checked whether all virtual machines were connected to the same NAT network.
- Verified IP address configuration:

```bash
ipconfig
ip addr
```

- Confirmed successful communication using the `ping` command.

**Solution:** After correcting the network configuration and assigning all virtual machines to
the same NAT network, communication between Windows Server, Ubuntu, and Kali Linux was
successfully established.

## Challenge 2 — Universal Forwarder Not Sending Logs

**Problem:** Windows Event Logs were not appearing in Splunk Enterprise.

**Troubleshooting:**
- Verified Universal Forwarder installation.
- Checked Forwarded Inputs.
- Confirmed receiving port configuration (`9997`).
- Restarted the Splunk Forwarder service.

**Solution:** After correcting the forwarding configuration, Windows Event Logs were
successfully indexed in the `soc_lab` index.

## Challenge 3 — Linux Syslog Not Received

**Problem:** Ubuntu Syslog events were not appearing in Splunk.

**Troubleshooting:**
- Verified `rsyslog` configuration.
- Confirmed UDP port `514` was configured in Splunk.
- Restarted the `rsyslog` service.
- Tested connectivity using the `logger` command:

```bash
sudo systemctl restart rsyslog
logger "SOC Lab Test Message"
```

**Solution:** After correcting the Syslog forwarding configuration and enabling the UDP input,
Linux logs were successfully received in Splunk.

## Challenge 4 — Firewall Log Collection

**Problem:** Firewall logs were not initially available in Splunk.

**Troubleshooting:**
- Verified firewall logging configuration.
- Checked Splunk Data Inputs.
- Confirmed the correct sourcetype and index.

**Solution:** After enabling firewall log collection and verifying the configuration, firewall
events were successfully indexed.

## Challenge 5 — Attack Simulation Verification

**Problem:** Attack simulation activities initially generated limited security events.

**Troubleshooting:**
- Verified connectivity between Kali Linux and target machines.
- Repeated Nmap scans and authentication activities.
- Confirmed that generated logs were indexed in Splunk.

**Solution:** After performing additional simulations and verifying the log sources, all
required events were successfully collected and analyzed.

## Lessons Learned

- Proper network configuration is essential for communication between virtual machines.
- Correct Splunk Data Input configuration is required for successful log collection.
- Universal Forwarder must be configured correctly to forward Windows Event Logs.
- Ubuntu Syslog forwarding depends on a properly configured `rsyslog` service.
- Attack simulations are useful for validating detection rules, alerts, and dashboards.
- Troubleshooting should always begin with network connectivity before checking
  application-level configurations.

## Summary

Throughout the development of the SOC lab, several configuration and networking challenges were
encountered. These issues were successfully resolved by verifying virtual machine networking,
correcting Splunk configurations, enabling log forwarding, and validating attack simulations.
The troubleshooting process improved the stability of the environment and ensured reliable log
collection and security monitoring throughout the project.
