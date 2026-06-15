# Kron4n CoH All-In-One Launcher Patch Notes

Patch notes for the Windows **Kron4n CoH All-In-One Launcher** from **v1.2** up to **v1.4.6**.

> Note: The older v1.2-v1.4.2 notes are written with history based on the known launcher feature path. The verified patch reports currently available cover v1.4.4, v1.4.5, v1.4.6, and the v1.4.6 hotfix.

---

## v1.2 - Core All-In-One Launcher Foundation

v1.2 focused on making the launcher usable as a proper all-in-one launcher for Company of Heroes Relaunch.

### Main features

- Added a main version/mod selection menu.
- Added support for launching the base game and supported mods from one BAT file.
- Added refresh-rate selection.
- Added optional launch settings.
- Added replay/performance handling.
- Added DirectX / `Local.ini` handling.
- Added desktop locked launcher creation.

### Supported menu entries

- Original
- Modern Combat
- Eastern Front
- Blitzkrieg
- EuropeInRuins
- Europe_At_War
- BackToBasics
- NHCmod
- Far East Mod

### Goal

The goal of this version was simple:

Make one launcher that can start the game or a supported mod without forcing users to manually edit shortcuts or remember launch arguments.

---

## v1.3 - Usability and Locked Launcher Improvements

v1.3 improved the day-to-day launcher flow.

### Main improvements

- Improved the locked launcher workflow.
- Made it easier to create launchers for one selected game/mod or for all supported entries.
- Improved how selected settings are saved into generated launcher files.
- Continued improving the normal launcher path so users can choose refresh rate, launch options, replay behavior, and DirectX settings in one flow.

### Goal

This version was about reducing repeated setup work.

Once a user found settings that worked, they could generate locked launchers and reuse them later.

---

## v1.4.0 - Steam / CoH Relaunch Detection Improvements

v1.4.0 focused on making the launcher better at finding the correct Steam and Company of Heroes Relaunch installation.

### Main improvements

- Improved Steam path detection.
- Improved Steam Library detection.
- Improved detection of the real `Company of Heroes Relaunch` folder.
- Reduced the chance of users accidentally launching or patching the wrong CoH folder.
- Continued separating the real modern CoH Relaunch folder from older or incorrect CoH folders.

### Goal

This version was about making the launcher safer and less dependent on users knowing exactly where Steam installed the game.

---

## v1.4.1 - Misplaced Mod Detection Work

v1.4.1 improved handling for cases where Steam or a mod installer puts mod files in the wrong location.

### Main improvements

- Added more logic for detecting misplaced mod folders.
- Improved checks for required `.module` files and mod folders.
- Improved warnings when a supported mod exists somewhere else but is missing from the real CoH Relaunch folder.
- Prepared the launcher for safer copy/fix behavior.

### Goal

This version started solving one of the most annoying CoH Relaunch problems:

A mod may be installed somewhere on disk, but not inside the actual folder the game uses.

---

## v1.4.2 - Replay, DirectX, and Safety Improvements

v1.4.2 continued improving the fix systems around the launcher.

### Main improvements

- Improved replay/performance fix behavior.
- Improved admin/write-check handling.
- Improved DirectX `Local.ini` handling.
- Improved cleanup behavior after launch.
- Improved safety around file operations.

### Goal

This version focused on stability and user safety.

The launcher should not blindly change files without checking write access or making sure the target folder is correct.

---

## v1.4.3 - Canonical Fixed Master

v1.4.3 became the important stable base for later work.

This version is treated as the canonical master for future patches.

### Main improvements

- Improved Steam detection.
- Improved CoH Relaunch folder detection.
- Added deeper misplaced mod search logic.
- Added safer copy/fix handling for misplaced mods.
- Added delete-source prompt after successful misplaced mod copy.
- Improved replay/performance fix with write testing.
- Improved admin behavior so admin is only needed when the launcher actually has to write protected files.
- Improved DirectX `Local.ini` creation and editing.
- Improved cleanup after launch.
- Improved wait loop around `RelicCOH.exe`.
- Preserved locked launcher generation.

### Goal

v1.4.3 was the version where the launcher became the safe patch base.

Future work should patch this file forward instead of rebuilding the launcher from memory.

---

## v1.4.4 - The Great War Support

v1.4.4 added support for **The Great War** mod.

### Added mod

```text
The Great War
```

### Mod details

```text
Steam/AppID folder: Company of Heroes Relaunch 314420
AppID: 314420
Module: tgw.module
Mod folder: tgw
Launch argument: -mod tgw
Locked launcher: Company_Of_Heroes_The_Great_War.bat
```

### Main changes

- Added **The Great War** as menu option `A`.
- Added The Great War to selected locked launcher creation.
- Added The Great War to create-all locked launchers.
- Added misplaced Steam folder fix data for AppID `314420`.
- Added safe cleanup support for `tgw1918.bat` and `tgw1918dev.bat`.

### Preserved

The patch did not remove existing labels or major systems.

Replay/performance fix, DirectX handling, misplaced mod fix, locked launcher creation, and run cleanup stayed intact.

---

## v1.4.5 - Local / Unofficial Mod Detection

v1.4.5 added a new second-page menu for local and unofficial mods.

Instead of filling the main menu with more entries, the launcher now has:

```text
Z. Detect unofficial / local mods
```

### Main changes

- Added a Z-menu for local/unofficial mods.
- The Z-menu scans the real detected `Company of Heroes Relaunch` folder.
- Only detected local mods are shown.
- Local mods force `-dev` automatically.
- Users are not asked whether they want `-dev` for these mods.
- Other optional launch settings are still available.

### Added local mod detection for

- Battle of the Bulge
- Cross Of Iron
- Decade / Decade Extended
- Indochine
- Indochine - death/corpses stay option
- HeeresgruppeNord
- Ritterkreuz
- Westfront

### Community help

Special thanks to **Kaien Cross / Nils** on Steam/Discord for helping collect and share several of the local/unofficial mod links used while building the Z-menu support.

Kaien also helped confirm practical details around these mods, including launch arguments and that several of them need `-dev` enabled to work correctly.

### Important

These local/unofficial mods need:

```text
-dev
```

The launcher forces it automatically in the Z-menu.

### Preserved

The patch preserved existing official mods, misplaced Steam mod fixes, replay/performance logic, DirectX logic, and cleanup behavior.

---

## v1.4.6 - GitHub Download + Install Support

v1.4.6 expanded the Z-menu so it can install missing supported local/unofficial mods directly from GitHub Release assets.

### Main changes

The Z-menu now shows each supported local mod as either:

```text
[Installed]
```

or:

```text
[Missing - Install]
```

If a mod is missing, the launcher can ask the user whether to download and install it.

### GitHub asset source

```text
https://github.com/KronanFTW/Kron4n-CoH-Mod-Downloads/releases/download/local-mod-assets-v1
```

### Manifest file

```text
Mod_Upload_Manifest.txt
```

### Added downloadable packages for

- Battle of the Bulge
- Cross Of Iron
- Decade / Decade Extended
- Indochine
- HeeresgruppeNord / N44 HGN
- Ritterkreuz
- Westfront

The Indochine death/corpses-stay option uses the same Indochine package as the normal Indochine option.

### Installer behavior

When a missing local mod is installed, the launcher:

1. Checks write access to the detected `Company of Heroes Relaunch` folder.
2. Downloads the needed ZIP assets.
3. Verifies each ZIP file with SHA256.
4. Extracts normal ZIP files using Windows PowerShell.
5. Copies extracted files into the correct CoH folder with `robocopy`.
6. Verifies that the required module and folder exist after installation.
7. Cleans temporary files after a successful install.

### No extra extractor required

No WinRAR or 7-Zip is required.

The GitHub assets are packed as normal ZIP files so Windows/PowerShell can extract them.

### Safety

If a ZIP file is corrupted, incomplete, changed, or does not match the expected SHA256 hash, the launcher stops the installation before copying files into the CoH folder.

### Community credit

The downloadable local mod support was built around the Z-menu mod list, with help from **Kaien Cross / Nils**, who shared collected mod sources and information during testing/planning.

---

## v1.4.6 Hotfix - Z-menu Empty Entry Fix

After testing v1.4.6, the Z-menu showed empty entries on some systems.

The problem looked like this:

```text
The system cannot find the batch label specified - DETECT_LOCAL_MODS
```

Because the detection routine did not run, the menu could show:

```text
1. []
2. []
3. []
```

### Fixed

- Removed the fragile dependency on `CALL :DETECT_LOCAL_MODS` inside the Z-menu flow.
- Inlined the local mod detection loop directly inside the Z-menu entry point.
- Kept the existing local mod info and install-check routines.
- Saved the BAT with Windows CRLF line endings for safer CMD behavior.

### Expected result

The Z-menu now correctly shows:

- Battle of the Bulge `[Installed]` or `[Missing - Install]`
- Cross Of Iron `[Installed]` or `[Missing - Install]`
- Decade / Decade Extended `[Installed]` or `[Missing - Install]`
- Indochine `[Installed]` or `[Missing - Install]`
- Indochine - death/corpses stay `[Installed]` or `[Missing - Install]`
- HeeresgruppeNord `[Installed]` or `[Missing - Install]`
- Ritterkreuz `[Installed]` or `[Missing - Install]`
- Westfront `[Installed]` or `[Missing - Install]`

The launcher version stays:

```text
v1.4.6
```

---

## Acknowledgements

Special thanks to **Kaien Cross / Nils** on Steam/Discord for helping collect, share, and explain several local/unofficial Company of Heroes mods used for the Z-menu support.

He provided useful mod references, download sources, and practical launch information while the local mod detection and GitHub download/install support was being built.

---

## Disclaimer

All mods belong to their original creators.

Kron4n CoH All-In-One Launcher is a community launcher project and is not affiliated with Relic Entertainment, SEGA, or the original mod creators.

The local mod download assets are provided only for launcher installation support.

---

## Summary

From v1.2 to v1.4.6, the launcher grew from a basic all-in-one CoH launcher into a safer full launcher system with:

- normal game/mod launching
- refresh-rate selection
- optional launch settings
- replay/performance fix
- DirectX `Local.ini` fix
- locked launcher creation
- Steam and CoH Relaunch detection
- misplaced mod fixing
- The Great War support
- local/unofficial mod detection
- GitHub download/install support
- SHA256 verification
- no WinRAR or 7-Zip requirement for local mod installs

The current stable branch is **v1.4.6 fixed**.
