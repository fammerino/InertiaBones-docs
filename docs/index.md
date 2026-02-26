# InertiaBones

InertiaBones is a Unity Editor tool for VRChat avatars that allows you to create (mainly) rotational PhysBone jiggle on any bones and any avatars of your choosing.

It features:

- Deterministic PhysBone controller chain generation
- Safe SkinnedMeshRenderer weight rewriting
- Session (non-destructive) iteration mode
- Persistent mesh baking
- Influence loss protection
- Automatic baked mesh cleanup

It is designed to serve as a framework for current and future methods included in the tool, so that you can easily add PhysBone dynamics wherever you want.

---

## Important Notes

This tool does not do anything revolutionary by itself, you could manually do this to your avatar already, but considering the time it would take and the potential complexity of replacing weights on meshes directly in Unity can make it an arduous task.
By using InertiaBones you can bypass all of that by making complex setups in seconds, and iterate / tune everything in a safe environment before finalizing your setup and baking it into meshes so that your avatar is prefab-safe and can also be exported.

InertiaBones is built with numerous guardrails in place so that you can safely experiment with different setups.

The tool:

- Never overwrites mesh assets in place
- Always rebuilds from pristine backup
- Never mutates baked assets
- Protects against removing still-influencing controllers
- Ensures bindpose integrity

---

## Core Workflow Model

For each source bone, InertiaBones creates:

PBCTRL_<Source>
└── <Source>_Sim
└── <Source>_Jiggle

Mesh weights are redirected:

Source Bone → Jiggle Bone

All persistent output is generated from a hidden pristine backup stored under the avatar.