# Known Issues & Limitations

## Known Issues

### Unpacking prefabs or modifying armatures after applying the tool

!!! warning
	Avoid unpacking prefabs or manually editing armatures on avatars that have already been processed with **Apply**, unless you understand how the backup system works.

Earlier versions exposed an edge case where unpacking prefabs (for example, outfit prefabs) could invalidate (partially break) stored backup references inside the hidden *__InertiaBonesEditorData* object. In certain situations, this prevented meshes from restoring correctly when running Remove.

This behavior has since been addressed. New safeguards ensure that backup entries remain consistent, and a repair button is available in the Debug / Maintenance foldout to rebuild backup data if necessary.

However, unpacking prefabs or manually restructuring the armature after applying the tool is not the intended workflow and may require manual review.

---

## Known Limitations

### PhysBone chains parented under converted source bones

The current version does **not** propagate InertiaBones jiggle motion to separate PhysBone chains that are parented under a converted source bone.

Example hierarchy:

```
Upperleg_R
├── Lowerleg_R
└── Belt_PB_R  <-- Has PhysBone
    └── Belt_PB_001_R
```

If `Belt_PB_R` has its own PhysBone component and is weighted accordingly, motion from the `Upperleg_R` InertiaBones controller will **not propagate** to that separate chain.

This limitation is planned for future improvement.

!!! info
	Until this is properly implemented, a workaround is to manually parent those PB-bonechains to the _Jiggle bone of their respective controller, but **Read the warning below first**.

!!! warning
	This is a manual workaround and is directly tied to the edge-case shown above (under **Known Issues**). Make sure to have a **backup** of your avatar or work on a **_Upload** copy if you are using this workaround, as it is not the intended workflow.

---

### Iterative editing in Persist (Bake) mode

When using **Bake converted meshes as assets**, iterative editing is not supported.

Example scenario:

1. Add 2 controllers and bake.
2. Later add 2 additional controllers and bake again.

Result:

- The avatar will have 4 controllers.
- Only the controllers included in the most recent bake will affect the baked meshes.

For iterative workflows, it is strongly recommended to:

- Use **Session-only mode**
- Finalize your setup
- Then perform a single Persist (Bake) operation