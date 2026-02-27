# InertiaBones

InertiaBones is a Unity Editor tool for VRChat avatars that allows you to create (mainly) rotational PhysBone jiggle on any bones and any avatars of your choosing.

It features:

- Deterministic PhysBone controller chain generation
- Safe SkinnedMeshRenderer weight rewriting
- Session (non-destructive) iteration mode
- Persistent mesh baking
- Influence loss protection
- Automatic baked mesh cleanup

The tool is designed to serve as a framework for current and future methods included in the tool, so that you can easily add PhysBone dynamics wherever you want.

[Get started →](quick-start.md){ .md-button .md-button--primary }
[Configuration →](configuration.md){ .md-button }

---

## Important Notes

While the underlying techniques used by InertiaBones are technically achievable manually, performing them correctly inside Unity is time-consuming, error-prone, and difficult to iterate safely — especially when modifying mesh weights directly.

InertiaBones streamlines this entire workflow.

It allows you to generate complex controller setups in seconds, iterate and tune them in a non-destructive environment, and only finalize your configuration once you are satisfied. When ready, you can bake the result into clean mesh assets so your avatar remains prefab-safe and export-ready.

The tool is built with multiple guardrails to ensure deterministic behavior and safe experimentation, allowing you to explore advanced setups without risking mesh corruption or structural instability.

The tool:

- Never overwrites mesh assets in place
- Always rebuilds from pristine backup
- Never mutates baked assets
- Protects against removing still-influencing controllers
- Ensures bindpose integrity

---

## Core Workflow Model

For each source bone, InertiaBones creates:

```
PBCTRL_SourceBone
└── SourceBone_Sim
    └── SourceBone_Jiggle
```

Mesh weights are redirected:

Source Bone → Jiggle Bone

All persistent output is generated from a hidden pristine backup stored under the avatar.