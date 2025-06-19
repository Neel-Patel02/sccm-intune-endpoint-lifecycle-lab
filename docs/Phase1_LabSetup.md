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

---

## 📸 Screenshot Placeholders

> (*Replace these with actual screenshots in your `/screenshots` folder*)

* `screenshots/lab-topology.png` — VMware network + VM layout
* `screenshots/domain-setup.png` — AD/DNS installation
* `screenshots/adk-install.png` — ADK + WinPE install confirmation
* `screenshots/sql-config.png` — SQL instance + static port
* `screenshots/sccm-prereq-check.png` — Passed all checks
* `screenshots/sccm-install-complete.png` — Final wizard summary

---

## 🧠 Notes & Gotchas

* SCCM setup **will fail** if SQL runs under `NT SERVICE\MSSQLSERVER` — must be a valid domain/local user or `NETWORK SERVICE`
* Ensure Win11 client has VMware tools and DNS points to `LAB-DC01`
* Use `mshta.exe` with `runas` to launch `splash.hta` under correct permissions

---

## ✅ Phase 1 Complete — What’s Next?

Proceed to **Phase 2: Device Enrollment**

* Configure discovery
* Create boundaries and collections
* Deploy SCCM client to WIN11-CLIENT01
* Begin Intune and Azure AD setup

