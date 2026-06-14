# Kron4n-CoH-Mod-Downloads
Download assets for **Kron4n CoH All-In-One Launcher** local/unofficial mod installer. https://steamcommunity.com/app/228200/discussions/0/805723742332378810/

This repository contains ZIP assets used by the launcher to download and install supported local **Company of Heroes Relaunch** mods.

The files are meant to be used through the launcher, not installed manually from the repository.

---

## Supported Local / Unofficial Mods

The current asset release supports:

- Battle of the Bulge
- Cross Of Iron
- Decade / Decade Extended
- Indochine
- Indochine - death/corpses stay option
- HeeresgruppeNord / N44 HGN
- Ritterkreuz
- Westfront

---

## Launcher Support

These assets are used by:

**Kron4n CoH All-In-One Launcher v1.4.6 and newer**

Launcher feature:

```text
Z. Detect unofficial / local mods
```

The launcher checks the detected `Company of Heroes Relaunch` folder and shows each supported local mod as either:

```text
[Installed]
```

or:

```text
[Missing - Install]
```

If a supported mod is missing, the launcher can download the required ZIP files from the GitHub Release assets, extract them into the correct `Company of Heroes Relaunch` folder, and verify that the required module/folder exists after installation.

---

## Important

Local/unofficial mods launched from the Z-menu require:

```text
-dev
```

The launcher forces `-dev` automatically for these mods.

Users do not need to manually enable `-dev` for these local mods.

---

## Asset Release

Current asset release:

```text
local-mod-assets-v1
```

Included files:

```text
Battle_of_the_Bulge_part01.zip
Battle_of_the_Bulge_part02.zip
Battle_of_the_Bulge_part03.zip

Cross_Of_Iron.zip

decade_extended_part01.zip
decade_extended_part02.zip

Indochine_Mod_part01.zip
Indochine_Mod_part02.zip

N44_HGN_part01.zip
N44_HGN_part02.zip

Ritterkreuz.zip

Westfront.zip

Mod_Upload_Manifest.txt
```

The launcher uses `Mod_Upload_Manifest.txt` and built-in SHA256 values to verify downloads before installation.

If a file is corrupted, incomplete, changed, or does not match the expected SHA256 hash, the launcher stops the installation before extracting or copying files.

---

## Patch Notes

### Asset Release: local-mod-assets-v1

Initial GitHub Release asset package for the local/unofficial mod installer.

Added downloadable assets for:

- Battle of the Bulge
- Cross Of Iron
- Decade / Decade Extended
- Indochine
- HeeresgruppeNord / N44 HGN
- Ritterkreuz
- Westfront

Added SHA256 manifest:

```text
Mod_Upload_Manifest.txt
```

---

### Launcher v1.4.4

Added support for:

```text
The Great War
```

Includes support for:

```text
tgw.module
tgw\
-mod tgw
```

---

### Launcher v1.4.5

Added:

```text
Z. Detect unofficial / local mods
```

This added a second menu page for local/unofficial mods instead of filling the main launcher menu with too many entries.

Local mods are detected from the real detected:

```text
Company of Heroes Relaunch
```

folder.

---

### Launcher v1.4.6

Added download and install support for missing local/unofficial mods.

The launcher can now:

- detect installed local mods
- show missing supported mods
- download missing mod ZIP assets from GitHub Releases
- verify SHA256 hashes
- extract ZIP files using Windows/PowerShell
- copy files into the detected `Company of Heroes Relaunch` folder
- verify installation after extraction
- force `-dev` automatically for local mods

No WinRAR or 7-Zip is required.

---

## Disclaimer

All mods belong to their original creators.

This repository only provides download assets for launcher installation support.

Kron4n CoH All-In-One Launcher is a community launcher project and is not affiliated with Relic Entertainment, SEGA, or the original mod creators.
