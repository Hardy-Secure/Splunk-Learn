# Splunk SIEM Homelab Breakdown

⚙️ The exercises and work in this lab environment were conducted utilizing Splunk Enterprise.

## Table of Contents

* [Introduction](#introduction)
* [Lab Environment](#lab-environment)
* [Network Configuration](#network-configuration)
* [Initial Environment Setup](#initial-environment-setup)
  * [Windows Machines](#windows-machines)
  * [Linux Machines](#linux-machines) 
* Placeholder

## Introduction
This document provides a comprehensive technical overview of the Splunk Core User lab exercises. It is intended to summarize the key activities, configurations, and workflows completed during the lab, providing a reference for understanding core Splunk functionalities, data ingestion processes, search operations, and reporting techniques.

The content is structured to give both a high-level perspective of the lab objectives and a detailed breakdown of the technical steps taken, including examples of searches, dashboards, and knowledge objects created. This overview serves as a practical guide for reinforcing Splunk core concepts and as a resource for future labs or real-world applications.

## Lab Environment

The lab environment was designed to simulate a small, multi-host infrastructure suitable for testing Splunk Enterprise data ingestion, forwarding, and analysis workflows. All systems were deployed as virtual machines running on Oracle VirtualBox, enabling isolated testing and controlled network communication between hosts.

#### 🖥️ Host System

The host system used to run the virtual machines is a desktop computer running **Windows 11 Pro**.

#### 📊 Splunk Platform

**Splunk Enterprise** was used as the primary platform for log ingestion, search, and visualization. The environment included both Windows and Linux systems to reflect common enterprise operating system diversity and support varied data sources.

#### 🧩 Virtual Machines

The following virtual machines were deployed as part of the lab environment:

* **Windows 11 Workstation** – IP Address: `192.168.127.`
  * Operating System: Windows 11 Pro 🪟
  * Role: Workstation log source for Windows-based event and system data
* **Windows 10 Workstation** - IP Address: `192.168.127.`
  * Operating System: Windows 10 Home 🪟
  * Role: Additional Windows workstation log source for comparative analysis and ingestion testing
* **Splunk** – IP Address: `192.168.127.`
  * Operating System: Ubuntu Server 🐧
  * Role: Primary Splunk Enterprise instance responsible for data indexing, searching, and visualization
* **SplunkFWD** – IP Address: `192.168.127.` 
  * Operating System: Ubuntu Server 🐧
  * Role: Dedicated forwarder system used to collect and send log data to the Splunk Enterprise instance

## Network Configuration

All virtual machines' network adapters were changed from "NAT" to "Bridged Adapter", and Promiscuous Mode was set to "Allow All" in their VirtualBox configuration settings.

*Insert VM Network Configuration Image

This configuration enabled testing of centralized log collection, cross-platform data ingestion, and basic forwarder-to-indexer communication within a virtualized lab environment. The setup provides a scalable foundation for expanding into more advanced Splunk use cases, including dashboards, alerts, and security-focused analysis.  

## Initial Environment Setup

#### Windows Machines

The Windows virtual machines (Windows 10 Workstation and Windows 11 Workstation) were deployed using standard Windows installation procedures. No custom configurations or additional software were applied during the initial setup phase beyond default system settings.

After installation, both systems were fully updated using Windows Update to ensure the latest security patches and system updates were applied. These machines were prepared to function as log-generating endpoints for Splunk data ingestion and analysis in later stages of the lab.

At this stage of the environment setup, the Windows systems were intentionally kept in a baseline configuration to reflect a typical enterprise workstation prior to log forwarding or agent installation.

#### Linux Machines

On the Linux virtual machines, once the operating system installation was completed, each system was logged into and fully updated to ensure it was running the latest available packages. This was accomplished using the following commands:

```bash
sudo apt update
sudo apt full-upgrade -y
```

After completing system updates, the OpenSSH server was installed to enable remote terminal access using the following command:

```bash
sudo apt install openssh-server
```

Installing OpenSSH allows remote connections to the Ubuntu servers from another Linux system via the terminal or from a Windows system using tools such as PuTTY.

To verify the status of the SSH service, the following command was executed:

```bash
systemctl status ssh
```

Initially, the SSH service was not running. The service was started using:

```bash
sudo systemctl start ssh
```

To ensure the SSH service starts automatically upon system boot, it was enabled using:

```bash
sudo systemctl enable ssh
```

This configuration ensured persistent remote access to the Linux-based Splunk systems throughout the duration of the lab.
