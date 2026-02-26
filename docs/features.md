# Features

## Controller Generation

For each source bone:


PBCTRL_<Source>
└── <Source>_Sim
└── <Source>_Jiggle


- Deterministic naming
- Idempotent rebuild
- Existing controllers detectable via scan

---

## Session Mode

- Instantiates working mesh
- No asset creation
- Fully reversible
- Safe for rapid iteration

Recommended for parameter tuning.

---

## Persist Mode (Bake)

- Always rebuilds from pristine backup
- Creates brand-new mesh asset
- Never overwrites existing mesh
- Uses timestamped deterministic naming
- Wrapped in StartAssetEditing
- Safe delayed cleanup

Persist is immutable output generation.

---

## Backup System

A hidden object under the avatar stores:

- Original mesh
- Original bones
- Original root bone
- Relative SMR path

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

- Groups baked meshes by SMR hash
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

Persist always derives from backup, ensuring:

- No cumulative corruption
- Stable bindpose integrity
- No bone index drift