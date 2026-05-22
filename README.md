# My CloudStream Repo

Ready-made CloudStream repo using prebuilt `.cs3` files originally from:
https://github.com/PopcornPlay/loveextenstion (branch: `builds`)

## How to use

1. Create a new public GitHub repo (e.g. `MyCloudRepo`).
2. Upload **all** files from this folder (keep filenames as-is — including `CNC Verse.cs3` with the space).
3. In `repo.json` and `plugins.json`, **find & replace**:
   - `USERNAME` → your GitHub username
   - `REPO`     → your repo name
   - `main`     → your default branch (only if not `main`)
4. Commit and push.
5. In CloudStream, add this repo URL:

   ```
   https://raw.githubusercontent.com/USERNAME/REPO/main/repo.json
   ```

   Or open this deep-link on your phone:

   ```
   cloudstreamrepo://raw.githubusercontent.com/USERNAME/REPO/main/repo.json
   ```

## Credits
All extensions © PopcornPlay — original repo:
https://github.com/PopcornPlay/loveextenstion
Licensed under GPLv3.

---

## REMADE / FIX NOTES

Repackaged for **PopcornPlay v38** (`com.popcornplay.app`).

Changes applied to every `.cs3`:
- Decompiled `classes.dex` with baksmali
- Replaced all references `com.lagradost.cloudstream3` → `com.popcornplay.app`
  (both dot and slash forms, in code + Kotlin metadata)
- Moved smali class tree `com/lagradost/cloudstream3/` → `com/popcornplay/app/`
- Reassembled with smali (full DEX rebuild — valid signature, checksum, map_list)
- Repacked `.cs3` with original `manifest.json`

`plugins.json` regenerated with correct `fileSize` and `fileHash` for every entry.

Remaining `com.lagradost.*` references (intentional, do NOT touch):
- `com.lagradost.nicehttp.*` — HTTP client library, present as-is in PopcornPlay
- `com.lagradost.api.Log` — logging API, present as-is in PopcornPlay
