# FAQ

## Does this modify my original mesh?

No.  
Persist Mode never overwrites existing mesh assets.

---

## Can I use this if I already have thigh / belly / butt PhysBones?

Yes.

InertiaBones adds controller chains only to the bones you explicitly select and does not remove or overwrite existing PhysBone setups. Existing PhysBone components, constraints, and child chains remain intact.

The tool has been tested on complex multi-bone/multi-child thigh, belly, and butt rigs and integrates cleanly, often enhancing overall motion when tuned properly.

Only the bones you choose to convert are affected.

!!! note
	This behavior assumes your existing PhysBone setups are located directly under the avatar’s root armature at the time of applying. Unusual hierarchy structures may require manual review. 

## How can I remove everything from my avatar?

Simply change the mode to **Remove** and use **Scan & Fill Existing Controllers**, then run **Remove**.
This will remove all objects created by the tool, write weights back to the source bones and change mesh references back to their original.

---

## Can I run Persist (Bake) multiple times?

Yes.  
Each run creates a new baked asset.

Retention settings control cleanup.

---

## What happens if I unselect existing controllers (removing them from the Bones list) after baking and try to bake again?

If you previously baked with certain controllers enabled, and then deselect one or more of them before baking again, a warning will appear.

This happens because those controllers may still influence vertex weights in the mesh. Deselecting them without proper handling could unintentionally remove their influence.

You will be given three options:

- Cancel – Stop and review your selection.
- Scan & Fill – Resync the UI with the existing controllers. (Optionally add more if that was your intention)
- Run Anyway – Continue intentionally and remove their influence during the new bake.

This safeguard prevents accidental weight changes when modifying an already baked setup.

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