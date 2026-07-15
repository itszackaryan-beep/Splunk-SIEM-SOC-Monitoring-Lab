# 10. Conclusion

## Introduction

This project was carried out to design and implement a functional Security Operations Center
(SOC) monitoring environment using Splunk Enterprise. The project focused on collecting
security logs from multiple systems, monitoring events, performing attack simulations, creating
alerts, developing dashboards, and analyzing security data in a centralized platform.

The implementation demonstrated the practical use of a Security Information and Event
Management (SIEM) solution for security monitoring within a virtual lab environment.

## Project Achievements

- Splunk Enterprise was successfully installed and configured.
- Windows Event Logs were collected using Splunk Universal Forwarder.
- Ubuntu Linux Syslog events were forwarded using `rsyslog`.
- Firewall logs were integrated into Splunk.
- Security events were stored in the `soc_lab` index.
- Multiple SPL queries were executed to analyze collected logs.
- Controlled attack simulations were performed using Kali Linux.
- Security alerts were configured and tested.
- Detection rules were created for monitoring suspicious activity.
- A centralized SOC Monitoring Dashboard was developed using Dashboard Studio.

## Overall Outcome

The implemented SOC monitoring environment successfully centralized logs from Windows Server,
Ubuntu Linux, and Firewall sources. Splunk Enterprise provided efficient log collection,
indexing, searching, visualization, and alerting capabilities.

The project demonstrated how security events generated during attack simulations could be
detected, analyzed, and monitored through dashboards and detection rules. The implementation
also improved understanding of SIEM architecture, log management, and practical SOC operations.

## Learning Outcomes

- Splunk Enterprise installation and configuration.
- Windows Event Log collection.
- Linux Syslog forwarding.
- Firewall log integration.
- Search Processing Language (SPL).
- Alert configuration.
- Dashboard development using Dashboard Studio.
- Attack simulation using Kali Linux.
- Security event monitoring and analysis.
- Basic SOC operations and troubleshooting.

## Summary

This project successfully demonstrated the implementation of a small-scale SOC monitoring
environment using Splunk Enterprise. Security logs from multiple platforms were collected,
analyzed, and visualized through dashboards, while alerts and detection rules improved security
monitoring capabilities. The project achieved all defined objectives and provided practical
experience in SIEM deployment, log analysis, and SOC operations.
