# Phase 1: Lab Setup and Core SCCM Installation

## 🎯 Objective

Set up a fully functional on-prem lab environment using VMware Workstation Pro to simulate real-world endpoint lifecycle management scenarios using:

* Microsoft Endpoint Configuration Manager (SCCM)
* Intune (later phases)

---

## 🖥️ Lab Environment Overview

| Component         | OS Version            | Hostname       | Purpose                         |
| ----------------- | --------------------- | -------------- | ------------------------------- |
| Domain Controller | Windows Server 2019   | LAB-DC01       | AD DS, DNS                      |
| SCCM Server       | Windows Server 2019   | LAB-CM01       | SQL + SCCM Site Server          |
| Client VM         | Windows 11 Enterprise | WIN11-CLIENT01 | Endpoint for testing deployment |

> 💡 All VMs are hosted on **VMware Workstation Pro** with an **internal host-only network (VMnet2)** to simulate enterprise networking.

---

## 🔧 Phase 1 Tasks Completed

### ✅ Base OS + Networking

* [x] Created internal-only virtual network in VMware (`VMnet2`)
* [x] Installed Windows Server 2019 on LAB-DC01
* [x] Installed Windows Server 2019 on LAB-CM01
* [x] Installed Windows 11 Enterprise on WIN11-CLIENT01

### ✅ Domain Configuration

* [x] Promoted LAB-DC01 to Domain Controller (`lab.local`)
* [x] Joined LAB-CM01 and WIN11-CLIENT01 to domain

### ✅ Prerequisite Tools

* [x] Installed Windows ADK (Deployment Tools + USMT)
* [x] Installed WinPE Add-on

### ✅ SQL Server Setup

* [x] Installed SQL Server 2019 (default instance)
* [x] Set static port `1433`
* [x] Set SQL Server service to run as `NETWORK SERVICE` (to satisfy SCCM requirements)

### ✅ SCCM Installation

* [x] Downloaded and extracted SCCM 2403 (latest available)
* [x] Installed SCCM as standalone primary site
* [x] Passed all prerequisite checks
* [x] Completed core installation:

  * ✅ Management Point
  * ✅ Distribution Point
  * ✅ Boot Image
  * ✅ Configuration Manager Console



