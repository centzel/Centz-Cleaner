# 🧼✨ CENTZ CLEANER — The Ultimate Windows Cleanup Utility ✨🧼

Welcome to **CENTZ CLEANER - PS Edition** — a powerful Windows cleanup tool built to help you clear junk, free up space, and give your PC a cleaner, smoother experience. 🚀💻

Whether you want a **quick cleanup**, a **targeted task**, or the **full run-all treatment**, this utility gives you control over how deep you want to clean. 🛠️

---

## 🔥 What This Tool Does

CENTZ CLEANER can help clean and manage:

- 🗂️ Temporary files
- 🌐 Browser cache
- 🧠 Memory dumps
- ♻️ Recycle Bin
- 🧾 Registry history
- 📥 Old Downloads
- 🧱 Old Windows Update files
- 🪟 `Windows.old`
- 🎮 GPU shader cache
- 🎵 Spotify cache
- 💬 Discord cache
- 🧷 Old `.bak` backup files
- 📁 AppData folders matching `*Digital*`
- ...and more ✅

---

## ⚠️ IMPORTANT WARNING

This script performs **real system cleanup actions**.
Some actions are **permanent** and may remove:

- backup files
- restore history
- cached app/browser data
- rollback data
- old downloads
- crash dumps

### Please read this carefully:
- ✅ A restore point is attempted before cleanup begins
- ✅ The script asks for confirmation on sensitive actions
- ⚠️ Some actions cannot be undone
- ⚠️ You should review tasks before running **ALL** tasks
- ⚠️ After reviewing generated log files, it is recommended to delete old logs so they do not pile up over time

**Use at your own risk.**

---

# 🚀 How To Run

## ✅ Requirements

- Windows
- PowerShell **5.1 or later**
- Administrator access recommended

---

## 🖱️ Option 1 — Easiest Method

Run the batch launcher:

```bat name=CentzZhop.batch.bat url=https://github.com/centzel/Centz-Cleaner/blob/main/CentzZhop.batch.bat
@echo off
setlocal
set "SCRIPT=%~dp0Centz_Zhop_Cleanup.ps1"

if not exist "%SCRIPT%" (
    echo Cleanup script not found:
    echo %SCRIPT%
    pause
    exit /b 1
)

powershell.exe -NoProfile -ExecutionPolicy Bypass -File "%SCRIPT%"
set "EXITCODE=%ERRORLEVEL%"

if not "%EXITCODE%"=="0" (
    echo.
    echo PowerShell cleaner exited with code %EXITCODE%.
    pause
)

exit /b %EXITCODE%
```

### Steps:
1. Download or clone the repository
2. Make sure these files are in the **same folder**:
   - `CentzZhop.batch.bat`
   - `Centz_Zhop_Cleanup.ps1`
3. Double-click `CentzZhop.batch.bat`

That’s it. 🎉

---

## 💻 Option 2 — Run From PowerShell

Open PowerShell in the repo folder and run:

```powershell name=run-cleaner.ps1
powershell.exe -NoProfile -ExecutionPolicy Bypass -File ".\Centz_Zhop_Cleanup.ps1"
```

Example:

```powershell name=run-from-folder.ps1
cd "C:\Path\To\Centz-Cleaner"
powershell.exe -NoProfile -ExecutionPolicy Bypass -File ".\Centz_Zhop_Cleanup.ps1"
```

---

# 🛡️ What Happens When You Start It

When you launch the script, it will:

1. 🔐 Check for administrator privileges
2. ⬆️ Request elevation if needed
3. 📝 Create a log file in your Downloads folder
4. ⚠️ Show a critical startup warning
5. ✍️ Ask you to type **`I UNDERSTAND`**
6. 💾 Attempt to create a system restore point
7. 📊 Ask you to choose a logging mode
8. 🧭 Show the startup menu

---

## 📝 Log File Location

Logs are created here:

```text
C:\Users\<YourUser>\Downloads\Centz_Zhop_Logs
```

Each session creates a timestamped log file like:

```text
cleanup_YYYYMMDD_HHMMSS.log
```

Perfect for checking what happened during cleanup. 📂

### ⚠️ Log Cleanup Warning
After you review the logs, it is recommended to delete older log files from the log folder so they do not build up and take unnecessary space over time.

---

# 🎛️ Startup Menu Options

When the tool starts, you’ll see options like:

- `S` — Single task mode / menu
- `I` — Feature descriptions and impact
- `M` — Multi-select mode
- `A` — Run ALL tasks now
- `Q` — Quit

### ✅ Recommended First-Time Path
If it’s your first time using the tool:

1. Choose `I` to read feature descriptions
2. Start with a few low-risk tasks
3. Avoid `A` (Run ALL) until you understand every option

---

# 🧼 Available Cleanup Features

## Core Tasks

1. 🗂️ Temp Files  
2. ⚡ Prefetch  
3. 🕘 Recent Files  
4. 🌐 Browser Cache  
5. 🧠 Memory Dumps  
6. 🪟 Old Windows Updates  
7. 🌍 DNS Cache  
8. ♻️ Recycle Bin  
9. 🧾 Registry Cleanup  
10. 🛟 Old System Restore Points  
11. 📥 Old Downloads  
12. 📦 Installer Files  
13. 🪟 `Windows.old` Files  
14. 📄 Error Reporting Files  
15. 🎮 GPU Shader Cache  
16. 🧹 Disk Cleanup  
17. 💽 Driver Defragmentation / Optimize Drives  
18. 🎵 Spotify Cache  
19. 💬 Discord Cache  
20. 🧷 Old `.bak` Backup Files  
21. 📁 `*Digital*` AppData Folders  

---

# ✅ Safer Tasks for Beginners

If you want a more cautious first run, start with these:

- `1` Temp Files
- `3` Recent Files
- `4` Browser Cache
- `7` DNS Cache
- `8` Recycle Bin
- `14` Error Reporting Files
- `15` GPU Shader Cache
- `18` Spotify Cache
- `19` Discord Cache

These are generally easier to recover from and lower risk than some deeper cleanup options. 👍

---

# ⚠️ Higher-Risk Tasks

Use extra caution with these:

- `9` Registry Cleanup
- `10` Old System Restore Points
- `11` Old Downloads
- `12` Installer Files
- `13` `Windows.old`
- `20` `.bak` file cleanup
- `21` `*Digital*` folder cleanup
- `A` Run ALL tasks

These can remove rollback data, backups, old files, or app-specific data. 🚨

---

# 🎯 How To Run Specific Tasks

## Run a Single Task
From the main menu:
1. Enter a task number
2. Press Enter
3. Confirm any warnings if prompted

Example:
- Enter `4` for Browser Cache
- Then choose the browser you want to clean

Browser options include:
- Chrome
- Edge
- Firefox
- Opera
- Opera GX
- Brave
- All browsers

---

## Run Multiple Tasks
Choose `M` and enter task numbers separated by commas.

Example:

```text
1,4,8,14,15
```

This runs:
- Temp Files
- Browser Cache
- Recycle Bin
- Error Reporting Files
- GPU Shader Cache

---

## Run Everything
Choose:

```text
A
```

This runs **all cleanup tasks** in sequence. 🔥

### But be careful:
This includes more aggressive cleanup actions like:
- restore point cleanup
- old downloads cleanup
- `.bak` deletion
- `Windows.old` deletion
- installer cache cleanup
- Digital folder cleanup

Only use this if you fully understand the impact. ⚠️

---

# 🧯 Troubleshooting

## ❌ “Cleanup script not found”
Make sure both files are in the same folder:

- `CentzZhop.batch.bat`
- `Centz_Zhop_Cleanup.ps1`

---

## ❌ PowerShell script blocked
Run manually with:

```powershell name=run-bypass.ps1
powershell.exe -NoProfile -ExecutionPolicy Bypass -File ".\Centz_Zhop_Cleanup.ps1"
```

---

## ❌ Admin prompt was denied
The script may continue without admin rights, but some tasks may fail or be limited.

For best results:
- right-click the batch file
- choose **Run as administrator**

---

# 🌟 Suggested First-Time Workflow

If you want the smoothest and safest first run:

1. Launch `CentzZhop.batch.bat`
2. Accept the admin prompt
3. Type `I UNDERSTAND`
4. Let it try to create a restore point
5. Choose logging mode `2`
6. Choose `I` to review features
7. Start with:
   - `1`
   - `4`
   - `8`
   - `14`
   - `15`
8. Review the logs after completion
9. Delete older logs you no longer need so they do not pile up
10. Explore the heavier cleanup tasks later

---

# 💜 Join the Community

The script promotes the **CENTZ ZHOP OPTIMIZATIONS SERVER** community inside the app.

Community link:

```text
https://discord.gg/KgGDMN82YN
```

---

# 🏁 Final Notes

CENTZ CLEANER is built for users who want:

- more free disk space 💾
- cleaner cache and temp storage 🧼
- better system organization 🧠
- a more guided cleanup experience 🛠️

If you use it carefully, it can be a handy all-in-one cleanup utility for Windows. ✨

---

## 📌 Disclaimer

This project performs permanent cleanup tasks on a Windows machine. Always review what you are running before using aggressive cleanup options.

**You are responsible for any changes made to your system.**
