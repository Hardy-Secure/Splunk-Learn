# Splunk SIEM Homelab Breakdown

⚙️ The exercises and work in this lab environment were conducted utilizing Splunk Enterprise.

## Table of Contents

* [Introduction](#introduction)
* [Lab Environment](#lab-environment)

## Introduction
This document provides a comprehensive technical overview of the Splunk Core User lab exercises. It is intended to summarize the key activities, configurations, and workflows completed during the lab, providing a reference for understanding core Splunk functionalities, data ingestion processes, search operations, and reporting techniques.

The content is structured to give both a high-level perspective of the lab objectives and a detailed breakdown of the technical steps taken, including examples of searches, dashboards, and knowledge objects created. This overview serves as a practical guide for reinforcing Splunk core concepts and as a resource for future labs or real-world applications.

## Lab Environment

The lab environment was designed to simulate a small, multi-host infrastructure suitable for testing Splunk Enterprise data ingestion, forwarding, and analysis workflows. All systems were deployed as virtual machines running on Oracle VirtualBox, enabling isolated testing and controlled network communication between hosts.

Splunk Enterprise was used as the primary platform for log ingestion, search, and visualization. The environment included both Windows and Linux systems to reflect common enterprise operating system diversity and support varied data sources.

The following virtual machines were deployed as part of the lab environment:

* Windows 11 Workstation – IP Address: `192.168.127.`
  * Operating System: Windows 11 Pro 🪟
  * Role: Workstation log source for Windows-based event and system data
* Windows 10 Workstation - IP Address: `192.168.127.`
  * Operating System: Windows 10 Home 🪟
  * Role: Additional Windows workstation log source for comparative analysis and ingestion testing
* Splunk – IP Address: `192.168.127.`
  * Operating System: Ubuntu Server 🐧
  * Role: Primary Splunk Enterprise instance responsible for data indexing, searching, and visualization
* SplunkFWD – IP Address: `192.168.127.` 
  * Operating System: Ubuntu Server 🐧
  * Role: Dedicated forwarder system used to collect and send log data to the Splunk Enterprise instance

All virtual machines' network adapters were set to ""in VirtualBox.

This configuration enabled testing of centralized log collection, cross-platform data ingestion, and basic forwarder-to-indexer communication within a virtualized lab environment. The setup provides a scalable foundation for expanding into more advanced Splunk use cases, including dashboards, alerts, and security-focused analysis.  

---

On the Linux virtual machines, once the operating system is installed, the machine is logged into and updated using the commands "sudo apt update" and "sudo apt full-upgrade -y"
