

# Project 01 – Troubleshooting Slow Windows Performance and Windows Update Issues

**Role:** IT Support Trainee

**Project Type:** Windows Troubleshooting Case Study

**Date:** August 2026

---

# Device Information

| Item | Details |
|------|---------|
| Computer | HP EliteBook 8470p |
| Operating System | Windows 10 Pro Version 22H2 |
| Storage | Samsung SSD 860 EVO 250GB |
| Memory | 4 GB RAM |
| Architecture | 64-bit |

---

# Background

While using my HP EliteBook 8470p, I noticed that the computer had become noticeably slow during everyday tasks.

At the same time, Windows Update was not completing successfully. The Windows 10 Version 22H2 update remained stuck during download and installation, making it difficult to determine whether the issue was caused by Windows Update itself, damaged system files, storage problems, or another underlying system issue.

Instead of immediately reinstalling Windows, I decided to approach the issue like an IT Support Technician by following a structured troubleshooting process, documenting each step, collecting evidence, and verifying every result.

---

# Problem Statement

The computer presented the following symptoms:

- Slow overall performance
- Windows Update issues
- Windows 10 Version 22H2 update stalled during download
- Concern that Windows system files might be corrupted

---

# Project Objectives

The objective of this project was to:

- Identify the root cause of the performance issues.
- Verify Windows system integrity.
- Determine whether Windows Update failures were caused by operating system corruption.
- Assess storage health.
- Verify file system integrity.
- Document each troubleshooting step as evidence.

---

# Troubleshooting Timeline

## Step 1 – Gather System Information

### Command

```cmd
systeminfo
```

### Purpose

Collected information about:

- Windows Version
- Installed RAM
- Processor
- BIOS Version
- System Type
- Installed Updates
- Computer Model

This established the environment before beginning troubleshooting.

---

## Step 2 – Windows Update Investigation

### Observation

Windows Update for Version 22H2 remained at 0% for an extended period.

Later, the download reached 100%, but installation still did not complete successfully.

Because Windows Update often depends on healthy operating system files, additional diagnostics were performed.

---

## Step 3 – Scan Windows System Files

### Command

```cmd
sfc /scannow
```

### Result

Windows Resource Protection found corrupt files and successfully repaired them.

### Analysis

This confirmed that Windows system files had become corrupted.

System File Checker automatically repaired the damaged files.

---

## Step 4 – Verify System File Repair

The System File Checker was executed again after repairs.

### Result

Windows did not find any integrity violations.

### Analysis

This confirmed that the corrupted system files had been successfully repaired.

---

## Step 5 – Windows Image Investigation

The next step was to verify the Windows Component Store using DISM.

During the first attempt, the command returned **Error 87**.

### Root Cause

The command contained a typing mistake:

```
/Clean-Image
```

instead of

```
/Cleanup-Image
```

The command was corrected before continuing.

---

## Step 6 – Check Windows Component Store

### Command

```cmd
DISM /Online /Cleanup-Image /CheckHealth
```

### Result

No component store corruption detected.

### Analysis

The Windows image was healthy.

---

## Step 7 – Deep Windows Image Scan

### Command

```cmd
DISM /Online /Cleanup-Image /ScanHealth
```

### Result

No component store corruption detected.

### Analysis

A deeper scan confirmed there was no corruption inside the Windows image.

---

## Step 8 – Verify SSD Health

### Command

```cmd
wmic diskdrive get model,size,status
```

### Result

Samsung SSD 860 EVO 250GB

Status: **OK**

### Analysis

The SSD reported healthy hardware status.

---

## Step 9 – Verify Disk Capacity

### Command

```cmd
wmic logicaldisk get caption,freespace,size
```

### Result

Drive information successfully collected.

Approximately 173 GB of free space remained.

### Analysis

Storage capacity was not contributing to the performance issues.

---

## Step 10 – Review Network Configuration

### Command

```cmd
ipconfig /all
```

### Findings

Windows successfully detected:

- Intel Wireless Adapter
- Intel Ethernet Adapter
- Bluetooth Adapter
- Microsoft Wi-Fi Direct Adapter

---

## Step 11 – Network Connectivity Test

### Command

```cmd
ping 8.8.8.8
```

### Result

General Failure

### Analysis

The laptop was not connected to an active network during testing.

---

## Step 12 – Verify File System Integrity

### Command

```cmd
chkdsk
```

### Result

Windows scanned the file system and found no problems.

0 KB in bad sectors.

### Analysis

The SSD and Windows file system were healthy.

---

# Root Cause

The investigation determined that Windows system files had become corrupted.

These corrupted files were successfully repaired using System File Checker.

Further investigation confirmed that:

- the Windows Component Store was healthy,
- the SSD was healthy,
- the file system contained no errors,
- available storage space was sufficient.

---

# Resolution

The corrupted Windows system files were repaired successfully.

Windows image health was verified using DISM.

Storage health and file system integrity were confirmed.

Windows Update later reported that the operating system was up to date.

---

## Final Verification

After completing the troubleshooting process, Windows Update was checked again.

### Result

Windows Update reported:

**"You're up to date."**

### Analysis

This confirmed that Windows was functioning normally after the repair process and that no additional operating system updates were pending.

---

# Skills Demonstrated

- Windows Troubleshooting
- Windows Administration
- Command Prompt
- System Diagnostics
- Root Cause Analysis
- Windows Update Troubleshooting
- SFC
- DISM
- CHKDSK
- Storage Health Verification
- Network Diagnostics
- Technical Documentation

---

# Lessons Learned

This project reinforced the importance of following a structured troubleshooting methodology instead of making assumptions.

Rather than reinstalling Windows immediately, I collected evidence, verified each system component, identified the source of the issue, corrected command-line errors, and confirmed that Windows returned to a healthy state.

This project strengthened my understanding of Windows troubleshooting tools and improved my confidence in documenting technical investigations.

---

# Evidence

The screenshots collected during this project are available in the **screenshots** folder within this repository.

---

# Reflection

This project represents my first documented Windows troubleshooting case study as I build practical experience toward becoming an IT Support Specialist.

It demonstrates my ability to investigate technical issues systematically, interpret diagnostic results, and document findings in a professional manner.
