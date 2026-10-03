# Anatomy assets

Rigged 3D anatomy for the SphericalWave fitness apps, derived from **Z-Anatomy**
and shared under the same licence, **CC BY-SA 4.0** (see `LICENSE`).

Only the 3D files are here. The apps that use them are separate works and are
not covered by this licence.

## Files

| File | Contents |
|---|---|
| `usdz/skeleton.usdz` | 271 bone, tooth and cartilage meshes, each rigidly bound to its rig bone |
| `usdz/fascia.usdz` | Fascia sheets (thoracolumbar fascia, fascia lata, crural fascia …) |
| `usdz/muscles-head-neck.usdz` | Muscles of the head and neck |
| `usdz/muscles-trunk.usdz` | Muscles of the trunk |
| `usdz/muscles-upper-limb.usdz` | Muscles of the arms and hands |
| `usdz/muscles-lower-limb.usdz` | Muscles of the hips, legs and feet |
| `manifest.json` | Every mesh: prim name → anatomy ID, side, layer, file, and source Z-Anatomy object |

- **Format:** USDZ, Y-up, metres, body facing +Z, the body's left on +X.
- **Rig:** every file carries the same 237-joint skeleton (from Z-Biomechanics) and a baked
  2-second bodyweight squat at 24 fps. The rig's constraints are baked to keyframes, so any
  USD player shows the same motion.
- **Skinning:** muscle and fascia vertices follow their four nearest bones. That is a first
  pass: muscles stretch but don't bulge or slide.
- **Detail:** geometry reduced to 25% of the source triangle count.
- **Names:** each structure's transform and its mesh are both named `<id>__<side>`, e.g.
  `psoas_major__l`, `femur__r`. Structures outside the anatomy catalog are `za_<name>`.
  RealityKit merges the skinned meshes of a file into one model and keys each part by
  the mesh name, so the parts keep these names.

## Credits

- **Z-Anatomy** by Gauthier Kervyn and contributors, CC BY-SA 4.0:
  https://github.com/Z-Anatomy/Models-of-human-anatomy (`Z-Anatomy.zip`, `Z-Biomechanics.7z`).
- Z-Anatomy is built on **BodyParts3D**, © The Database Center for Life Science, licensed
  under CC Attribution 4.0 International: https://dbarchive.biosciencedbc.jp/en/bodyparts3d/
- **Changes made here:** meshes decimated to 25%, renamed to anatomy-catalog IDs, split by
  layer and body region, muscles and fascia skinned to the Z-Biomechanics rig, a squat
  animation baked from the rig's control bones, and exported to USDZ.

## Using these files

Under CC BY-SA 4.0 you may share and adapt these files, including commercially, if you
give credit (keep the credits above) and share your adaptations under the same licence.
