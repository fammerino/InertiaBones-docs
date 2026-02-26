# FAQ

## Does this modify my original mesh?

No.  
Persist Mode never overwrites existing mesh assets.

---

## How can I remove everything from my avatar?

Simply change the mode to **Remove** and use **Scan & Fill Existing Controllers**, then **Run Remove**
This will remove all objects created by the tool, write weights back to the source bones and change mesh references back to their original.

---

## Can I run Persist (Bake) multiple times?

Yes.  
Each run creates a new baked asset.

Retention settings control cleanup.

---

## What happens if I remove controllers after using Bake?

If removed controllers still influence vertex weights, a warning appears.

You can:
- Cancel
- Scan & Fill existing controllers
- Run Anyway

---

## Can this corrupt my avatar?

Under normal usage, no.

The tool enforces strict invariants:
- No asset overwrite
- No bindpose shrink
- No bone index drift

---

## Where are baked meshes stored?

Inside:


Assets/Corner22/InertiaBonesData/GeneratedMeshes/Avatar-name/


User data is separated from tool source and is stored in its own folder (InertiaBonesData).
This folder should not be deleted if you are updating the tool to a newer version (Ensures you keep your presets and generated meshes).