UES A7670C STUDIO — AMR EDITION
Unique Embedded Systems Pvt Ltd

THIS PACKAGE CAN CREATE A NORMAL WINDOWS INSTALLER
The previous build script produced a portable EXE only. This updated
build_windows.bat builds the EXE and, when Inno Setup 6 is installed,
automatically packages it into an installable Setup.exe.

ONE-TIME WINDOWS SETUP
1. Install Python 3.10 or newer.
2. Install Inno Setup 6: https://jrsoftware.org/isinfo.php
3. Extract this package to a normal folder on your Windows PC.
4. Double-click build_windows.bat and wait for completion.

OUTPUTS
- Portable application: dist\UES A7670C Studio.exe
- Installable Windows installer: installer\UES_A7670C_Studio_Setup.exe

INSTALLING LIKE A NORMAL WINDOWS APP
1. Double-click installer\UES_A7670C_Studio_Setup.exe.
2. Follow the Windows Setup wizard.
3. The app is installed under Program Files\Unique Embedded Systems.
4. It creates a Start Menu entry and an Uninstall entry in Windows Settings.
5. You can select the optional desktop shortcut during installation.

IMPORTANT
- This script builds a Windows installer on Windows. It cannot create a
  genuine Windows installer from Linux.
- The app is not code-signed, so Windows SmartScreen may show a warning.
- The generated installer is not yet digitally signed.
- AMR-only file selection and the existing modem transfer behavior are retained.


VERSION 1.2 — MODEM TEST SUITE ADDITIONS
- AT Command Tester with common preset commands and manual command entry.
- Outgoing call test (explicit confirmation), hang-up and call-status query.
- SMS send (explicit confirmation) and SMS inbox read.
- Network/SIM diagnostic snapshot: CPIN, CSQ, CEREG, CREG, COPS,
  CPSI, CGATT and CGDCONT.
- Modem family selector: A7670C-LASS, A7672S, SIM7600 and SIM800.
- One background serial job at a time, preventing app modules from opening
  the same COM port concurrently.

COMPATIBILITY NOTES
- The AT test tools use common SIMCom AT commands and may vary by model,
  firmware, network, SIM plan and enabled features. A command may return ERROR
  on a modem that does not implement it.
- The modem-family selector is a profile label for test context; it does not
  automatically rewrite every command or certify all features on all models.
- The EFS browser and AMR uploader retain A7670C-specific filesystem commands.
  Do not assume those EFS commands work on A7672S, SIM7600 or SIM800.
- Voice calls require a voice-capable modem/SIM/network and appropriate audio
  routing. SMS requires an active SIM and SMS service. Sending messages and
  placing calls can incur carrier charges.
- Manual AT console is powerful. Avoid factory reset, firmware update,
  band-lock, SIM PIN/PUK and other configuration-changing commands unless
  you have the exact firmware manual and recovery procedure.
- The app has been syntax-checked, but actual modem, call, SMS and network
  behavior must be verified on the target hardware and SIM.


STARTUP FIX (v1.2.1)
- Added missing QLineEdit widget import required by AT / Call / SMS pages.
- Reworked splash-to-main-window transition to use a single Qt event loop.
- Main window is now shown and activated before the splash screen closes.
- If main-window initialization fails, a visible startup error dialog is shown.


VERSION 1.2.3 — NAVIGATION AND MOBILE UI UPDATE
- Added a dedicated AT Communication Console item to the sidebar.
- Corrected sidebar navigation so each label maps to the matching stacked page.
- Corrected top page titles to follow the same page order.
- Reworked Call & SMS Tester into a mobile-style dial pad, call/end controls,
  SMS recipient, message composer, send control and inbox/result panel.
- Dial and SMS actions remain explicit user actions with confirmation prompts.
