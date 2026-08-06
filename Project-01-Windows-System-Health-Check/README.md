# Project 01 - Windows System Health Check

## Project Overview

This project demonstrates a complete Windows health assessment carried out on my HP EliteBook 8470p as part of my IT Support portfolio.

The goal was to identify and resolve operating system issues using built-in Windows troubleshooting tools while documenting each step professionally.

---

## Device Information

- Device: HP EliteBook 8470p
- Operating System: Windows 10 Pro 22H2
- Storage: Samsung SSD 860 EVO 250GB
- RAM: 4GB

---

## Objectives

- Verify Windows system file integrity
- Check Windows component store health
- Inspect SSD health
- Verify disk file system
- Collect evidence for troubleshooting documentation

---

## Tools Used

- Command Prompt (Administrator)
- SFC
- DISM
- CHKDSK
- WMIC

---

## Commands Executed

### 1. System File Checker

```cmd
sfc /scannow
```

Result:

Windows Resource Protection found corrupt files and successfully repaired them.

---

### 2. DISM CheckHealth

```cmd
DISM /Online /Cleanup-Image /CheckHealth
```

Result:

No component store corruption detected.

---

### 3. DISM ScanHealth

```cmd
DISM /Online /Cleanup-Image /ScanHealth
```

Result:

No component store corruption detected.

---

### 4. Disk Information

```cmd
wmic diskdrive get model,size,status
```

Result:

Samsung SSD 860 EVO 250GB

Status: OK

---

### 5. Drive Capacity

```cmd
wmic logicaldisk get caption,freespace,size
```

Result:

Drive information successfully collected.

---

### 6. Disk Check

```cmd
chkdsk
```

Result:

Windows scanned the file system and found no problems.

0 KB in bad sectors.

---

## Outcome

System file corruption was successfully repaired using SFC.

DISM confirmed that the Windows component store is healthy.

CHKDSK confirmed there are no disk errors or bad sectors.

The SSD reports a healthy status.

Overall, the operating system is healthy after repairs.

---

## Skills Demonstrated

- Windows Troubleshooting
- Command Line Interface (CLI)
- System Diagnostics
- Windows Administration
- Documentation
- Problem Solving
