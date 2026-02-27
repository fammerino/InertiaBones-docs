# Known Issues & Limitations

## Known Issues

!!! warning
	Beware of unpacking prefabs on converted avatars after you run **Apply**

We previously saw an issue regarding **unpack prefab** on outfits or similar, that would cause the *Backup entries* in the hidden _InertiaBonesData object to lose their backup path and or bone list, which in turn caused problems like meshes not returning to normal when running **Remove** 

This issue should be resolved, but considering that this workflow is non-standard and **not** the intended order of use for the tool, I am noting it down here. 
(new methods ensure that a clean set of backup entires exist, and a button in the **Debug / Maintenance** foldout has been added that has proven very efficient at repairing this issue if it happens)

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
	Until this is properly implemented, a workaround is to manually parent those PB-bonechains to the _Jiggle bone of their respective controller.
	Do be warned that this is a manual workaround and will likely break the outfit if you **Run Remove** without manually undoing the workaround first.

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