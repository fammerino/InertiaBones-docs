# Quick Start

##Recommended First-Time Usage

If you are new to InertiaBones, it is recommended to:

- Duplicate your avatar before first use, **or**
- Enable the **Create Upload Copy** option in the tool UI when applying.

This is simply good workflow practice when introducing any new automation tool into an existing avatar setup.

While InertiaBones is designed to be deterministic and crash-safe, creating a backup during your first use ensures you can freely experiment and become familiar with its behavior without concern.

Once you are comfortable with the workflow, this precaution is typically unnecessary.

---

## Video Walkthrough

<iframe width="100%" height="500" src="https://www.youtube.com/embed/ysLpTjRzJb8?si=pwyRCc--5lvRZMwd" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

---

## Basic Setup

1. Open your Unity avatar project.
2. Open InertiaBones from the Tools menu.
3. Select the avatar you want to convert on by dragging it into **Avatar Root**.
4. Select bones on your avatar you want to convert by dragging them into **Source Bone**.
5. Choose a Built In preset or make your own.
6. Click **Apply** and use play-mode to see the results.
6. Redo the steps above until you are satisfied with the setup.
7. When satisfied, make sure to use **Scan & Fill** to target all controllers, then switch on **Bake converted meshes as assets**.
8. Click **Apply** to bake the affected meshes into assets that are prefab safe and survives reopening projects and similar.
9. Done!

!!! info
    InertiaBones is meant to be used as a **final** pass on your avatar before uploading. If you use any other tools that make changes to mesh / armature or similar, make sure to use them before applying InertiaBones.

---

## Recommended Workflow

**During tuning:**
- Use Session Mode
- Iterate freely
- Adjust settings without creating assets

**When finalized:**
- Switch to Bake Mode
- Apply once to bake
- Let retention cleanup manage older versions

---

## Important Early Notes

!!! warning
    Persist Mode creates new mesh assets. It never overwrites existing ones.

!!! info
    Omitting controllers in Bake Mode will trigger a safety warning if vertex influence still exists.