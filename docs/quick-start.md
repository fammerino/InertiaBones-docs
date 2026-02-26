# Quick Start

## Basic Setup

1. Open your avatar in Unity.
2. Open InertiaBones from the Unity menu.
3. Click **Scan** to detect eligible bones.
4. Select bones you want to convert.
5. Choose **Session Mode** for testing.
6. Click **Apply**.
7. Tune PhysBone parameters.
8. When satisfied, switch to **Persist Mode**.
9. Click **Apply** to bake a mesh asset.

---

## Video Walkthrough

<iframe width="100%" height="500"
src="https://www.youtube.com/embed/YOUR_VIDEO_ID"
title="InertiaBones Quick Start"
frameborder="0"
allowfullscreen>
</iframe>

*(Replace with your video URL once uploaded.)*

---

## Recommended Workflow

**During tuning:**
- Use Session Mode
- Iterate freely
- Adjust settings without creating assets

**When finalized:**
- Switch to Persist Mode
- Apply once to bake
- Let retention cleanup manage older versions

---

## Important Early Notes

!!! warning
    Persist Mode creates new mesh assets. It never overwrites existing ones.

!!! tip
    Use Scan & Fill if you modify controllers manually outside the tool.

!!! info
    Removing controllers in Persist Mode will trigger a safety warning if vertex influence still exists.