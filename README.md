# Character 3D — Default 3D Character Models (OB55 PC)

<p align="center">
  <strong>English</strong> · <a href="./README.vi.md"><strong>Tiếng Việt</strong></a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Characters-74-blue" alt="Characters: 74" />
  <img src="https://img.shields.io/badge/GLB_Models-148-success" alt="GLB Models: 148" />
  <img src="https://img.shields.io/badge/Format-glTF_2.0_(.glb)-orange" alt="Format: glTF 2.0" />
  <img src="https://img.shields.io/badge/Validation-0_Errors_%7C_0_Warnings-brightgreen" alt="Validation: 0 Errors | 0 Warnings" />
  <a href="./LICENSE"><img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="License: MIT" /></a>
</p>

---

## Overview

This repository contains **74 default 3D character directories** (**148 `.glb` files** in total, including **6 Awakened variants**) extracted and assembled from the **OB55 PC** build.

Every `.glb` file is a complete, self-contained glTF 2.0 binary asset featuring:
- **Full skeletal rig** with bone hierarchy and skin weights
- **Embedded textures** and glTF PBR material approximations of in-game shaders
- **Two level-of-detail variants per character**:
  - `Lobby`: High-detail model used in the character lobby and showcase screens
  - `InGame`: Optimized model used during matches
- **2048 × 2048 preview renders** (`preview.png`) rasterized directly from the native GLB geometry and textures
- **Zero glTF validation issues**: All 148 models pass glTF 2.0 validation with **0 errors and 0 warnings**, verified by SHA-256 checksums

## Directory Structure

Each character has a dedicated folder named after the character (e.g., `Kelly/`, `Alok/`, `Hayato_Awakening/`):

```text
character-3d/
├── Kelly/
│   ├── Kelly_Default_Lobby.glb                  # High-detail Lobby 3D model
│   ├── Kelly_Default_InGame.glb                 # Match-optimized InGame 3D model
│   ├── Kelly_Default_Lobby.json                 # Export metadata & recipe info (Lobby)
│   ├── Kelly_Default_InGame.json                # Export metadata & recipe info (InGame)
│   ├── Kelly_Default_Lobby.glb.validation.json  # Khronos glTF validator report (Lobby)
│   ├── Kelly_Default_InGame.glb.validation.json # Khronos glTF validator report (InGame)
│   └── preview.png                              # 2048 × 2048 native preview render
├── ... (74 character folders)
├── characters.tsv                               # Tab-separated index of all models & SHA-256 hashes
├── coverage.json                                # Dataset coverage & validation summary statistics
├── errors.json                                  # Log of unavailable roster entries
├── manifest.json                                # Full metadata, file paths, and checksum manifest
├── organization.json                            # Repository file counts & checksum verification result
├── roster.json                                  # Raw character roster configuration data
├── README.md                                    # English documentation
├── README.vi.md                                 # Vietnamese documentation
└── LICENSE                                      # MIT License
```

## How to Use

1. **Blender**:
   - Open Blender (3.0+ recommended) and select **File → Import → glTF 2.0 (.glb/.gltf)**.
   - Choose either `<Character>_Default_Lobby.glb` (for high-res rendering/animation) or `<Character>_Default_InGame.glb` (for lightweight scenes).
   - Switch Viewport Shading to **Material Preview** or **Rendered** to see embedded textures.
2. **Game Engines & Web (Unity / Unreal Engine / Godot / Three.js)**:
   - Drag and drop the `.glb` file into your engine or load it via `GLTFLoader` in Three.js / Babylon.js.
3. **Notes on Shaders & Animations**:
   - Skeletal armatures and vertex skin weights are included, ready for custom rigging, retargeting, or posing.
   - Animations are **not** bundled inside these `.glb` files.
   - Custom game shaders are approximated using standard glTF 2.0 materials.

## Dataset Coverage & Notes

| Metric | Value |
| :--- | :--- |
| **Total Roster Entries** | 76 |
| **Exported Characters** | 74 (including 6 Awakening variants) |
| **Original Recipe Builds** | 73 |
| **Reconstructed Builds** | 1 (`CricketGuy`) |
| **Unavailable Entries** | 2 (`MMAFighter`, `Researcher`) |
| **Total GLB Files** | 148 (`243,885,124` bytes / ~232.6 MB) |
| **Validation Status** | 0 Errors, 0 Warnings |

- **Reconstructed Character (`CricketGuy`)**: Assembled from original source assets because the default recipe entry was missing from the build table. Recovery evidence and recipe mapping are included in [`CricketGuy/cricketguy_recipe_recovery.json`](./CricketGuy/cricketguy_recipe_recovery.json) and [`CricketGuy/cricketguy_recovery_evidence.json`](./CricketGuy/cricketguy_recovery_evidence.json).
- **Unavailable Characters (`Researcher`, `MMAFighter`)**: Could not be exported due to missing recipe definitions in the source data (recorded in [`errors.json`](./errors.json)).

## Root Metadata Files

- [`characters.tsv`](./characters.tsv): Quick lookup table with `character`, `avatar_id`, `variant`, `status`, relative `file` path, and `sha256`.
- [`manifest.json`](./manifest.json): Complete per-model manifest including game config, part recipes, validation summaries, and SHA-256 hashes.
- [`coverage.json`](./coverage.json) & [`organization.json`](./organization.json): Summary statistics and integrity verification status.
- [`roster.json`](./roster.json): Full character roster configuration definitions from the game data.
- [`errors.json`](./errors.json): Details on the 2 unexportable roster entries.

## License & Disclaimer

- The repository structure, manifests, metadata organization, and documentation are licensed under the [MIT License](./LICENSE).
- **Disclaimer**: All 3D character models, textures, and character names are the intellectual property of their respective copyright holders (Garena). This archive is provided for educational, research, 3D study, and fan-art reference purposes only.
