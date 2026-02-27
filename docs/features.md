# Tool System Features

## Compatibility

Initial compatibility testing with *Marshmallow PB* suggests strong compatibility. Other tools like Motchiri Shader and BPP / BPPP should also work fine, although it has not yet been fully tested.

!!! info
	Regarding compatibility, the bottom line is to make sure you utilize any tools doing operations on mesh/armature **before** using InertiaBones.


## Controller Generation

For each source bone in list when applying:

```
PBCTRL_SourceBone (Holds the Constraint setup)
└── SourceBone_Sim (Holds the PB component)
    └── SourceBone_Jiggle (Holds the rewritten weight)
```

- Deterministic naming
- Idempotent rebuild
- Existing controllers detectable via scan

---

## Session Mode

- Instantiates working mesh (In-memory)
- No asset creation
- Fully reversible
- Safe for rapid iteration

Recommended for parameter tuning.

---

## Persist Mode (Bake)

- Always rebuilds from pristine backup
- Creates brand-new mesh asset
- Never overwrites existing mesh
- Meshes use timestamped naming to support cleanup.
- Safe delayed cleanup (Configurable in **Options**)

Persist is immutable output generation.

---

## Backup System

A hidden object under the avatar stores:

- Original mesh
- Original bones
- Original root bone
- Relative SkinnedMeshRenderer path

Used for:

- Deterministic rebuild
- Influence detection
- Restore
- Corruption prevention

---

## Persist Guardrail

When removing controllers in Persist Mode:

- Existing controllers are scanned
- Omitted controllers are detected
- Influence is checked via pristine backup
- Warning modal appears if risk detected

Options:

- Cancel
- Scan & Fill
- Run Anyway

Prevents silent vertex data loss.

---

## Rolling Cleanup

Retention options:

- Disabled
- Keep 1
- Keep 2
- Keep 5

Cleanup:

- Groups baked meshes by SkinnedMeshRenderer hash
- Sorts by timestamp
- Deletes oldest beyond retention
- Never deletes referenced meshes

---

## Advanced Usage

### Presets

- Save configuration presets
- Load across avatars
- Share within projects

### Deterministic Rebuild

Persist (Bake) always derives from backup, ensuring:

- No cumulative corruption
- Stable bindpose integrity
- No bone index drift