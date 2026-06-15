# Kron4n CoH All-In-One Launcher Patch Notes

These patch notes cover the local/unofficial mod support added to the Kron4n CoH All-In-One Launcher.

---

## v1.4.5 - Local / Unofficial Mod Detection

Version 1.4.5 added a new second-page menu for local and unofficial Company of Heroes mods.

Instead of filling the main launcher menu with more and more entries, the launcher now has:

```text
Z. Detect unofficial / local mods
```

This menu scans the real detected `Company of Heroes Relaunch` folder and only shows supported local mods that are actually installed there.

### Added local mod detection for

- Battle of the Bulge
- Cross Of Iron
- Decade / Decade Extended
- Indochine
- Indochine - death/corpses stay option
- HeeresgruppeNord
- Ritterkreuz
- Westfront

### Important change

These local/unofficial mods require:

```text
-dev
```

The launcher now forces `-dev` automatically for the Z-menu mods.

Users are not asked whether they want to enable `-dev` for these mods, because the mods may not work correctly without it.

Other optional launch settings are still available, such as:

- `-nomovies`
- `-unlock_all_missions`
- `-forceactive`
- `-fullwindow`
- `-novsync -notriplebuffer`

### Preserved from earlier versions

The update was added without removing the existing launcher systems:

- Official Steam/AppID mod support
- Misplaced Steam mod fix logic
- Replay/performance fix
- DirectX `Local.ini` fix
- Launch cleanup and `RelicCOH.exe` wait loop

---

## v1.4.6 - GitHub Download + Install Support

Version 1.4.6 expanded the Z-menu so it can install missing local/unofficial mods directly from GitHub Release assets.

The Z-menu now shows supported mods as:

```text
[Installed]
```

or:

```text
[Missing - Install]
```

If a supported mod is missing, the launcher can ask the user if they want to download and install it.

### Added GitHub asset support

The launcher now uses GitHub Release assets from:

```text
https://github.com/KronanFTW/Kron4n-CoH-Mod-Downloads/releases/download/local-mod-assets-v1
```

The manifest file used for reference/debug visibility is:

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

When installing a missing local mod, the launcher now:

1. Checks write access to the detected `Company of Heroes Relaunch` folder.
2. Downloads the required ZIP assets from GitHub Releases.
3. Verifies each ZIP file with SHA256.
4. Extracts normal ZIP files using Windows PowerShell.
5. Copies the extracted files into the correct CoH folder.
6. Verifies that the required module and folder exist after installation.
7. Cleans up temporary files after a successful install.

No WinRAR or 7-Zip is required, because the release assets are normal ZIP files.

### Safety

If a download is incomplete, corrupted, changed, or does not match the expected SHA256 hash, the launcher stops the installation before copying files into the CoH folder.

This prevents broken or wrong files from being installed silently.

### Preserved from earlier versions

The following existing systems were kept intact:

- Steam detection
- Company of Heroes Relaunch detection
- Official mod launch support
- The Great War support
- Misplaced mod fix
- Replay/performance fix
- DirectX `Local.ini` fix
- Cleanup after launch
- Locked launcher logic

---

## v1.4.6 Hotfix - Z-menu Fix

A hotfix was made for v1.4.6 after testing showed that the Z-menu could display empty entries.

The problem looked like this:

```text
The system cannot find the batch label specified - DETECT_LOCAL_MODS
```

Because that detection label did not run correctly, the Z-menu could show empty options like:

```text
1. []
2. []
3. []
```

### Fixed

The Z-menu detection logic was changed so the local mod detection runs directly inside the Z-menu entry point.

The launcher now correctly shows:

- Battle of the Bulge `[Installed]` or `[Missing - Install]`
- Cross Of Iron `[Installed]` or `[Missing - Install]`
- Decade / Decade Extended `[Installed]` or `[Missing - Install]`
- Indochine `[Installed]` or `[Missing - Install]`
- Indochine - death/corpses stay `[Installed]` or `[Missing - Install]`
- HeeresgruppeNord `[Installed]` or `[Missing - Install]`
- Ritterkreuz `[Installed]` or `[Missing - Install]`
- Westfront `[Installed]` or `[Missing - Install]`

The official launcher version remains:

```text
v1.4.6
```

---

## Summary

The main goal of these updates was to make the launcher closer to a real all-in-one Company of Heroes launcher.

The main menu stays clean, while the Z-menu handles local and unofficial mods separately.

The launcher can now detect, install, verify, and launch supported local mods without requiring users to manually install WinRAR, 7-Zip, or extra tools.
