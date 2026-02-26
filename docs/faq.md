# FAQ

## Does this modify my original mesh?

No.  
Persist Mode never overwrites existing mesh assets.

---

## Can I run Persist multiple times?

Yes.  
Each run creates a new deterministic baked asset.

Retention settings control cleanup.

---

## What happens if I remove controllers?

If removed controllers still influence vertex weights, a warning appears.

You can:
- Cancel
- Scan & Fill
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


Assets/Corner22/InertiaBonesData/GeneratedMeshes/


User data is separated from tool source.