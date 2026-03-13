# Changelog

## How to update:

Delete the following folder before importing new version *\Assets\Corner22\InertiaBones*

Alternatively just drop in the new .unitypackage and make sure that the import window detects changed & new files.

### InertiaBones updates

#### 27.02.2026 InertiaBones V1.0.0 is released to the public.
#### 13.03.2026 InertiaBones v1.1.0 released.

	
##### Bug fixes:

- Fixed [**"*Mesh* has no bones assigned"**](https://fammerino.github.io/InertiaBones-docs/faq/#meshname-has-no-bones-assigned-when-attempting-to-run-apply) issue. (Dialog box for listing and skipping added)
- Fixed [**"MA Scale Adjuster reverting after apply"**](https://fammerino.github.io/InertiaBones-docs/faq/#why-does-ma-scale-adjuster-revert-scaling-after-applying) issue.
- Fixed missed bone detection for alternative naming ("Left" / "Right") resulting in improperly mirrored endpoints.
- Hardened reference to root avatar object to make **Create Upload Copy** more robust.
- Made presets backwards compatible when overwriting existing ones with new features. (Preset version from 2 -> 4)
	
##### Additions:

- Added [**Bone List Preset**](https://fammerino.github.io/InertiaBones-docs/configuration/#avatar-root-bones-section) dropdown for faster application and example bone setups.
- Added toggle for [**Move MA Scale Adjusters**](https://fammerino.github.io/InertiaBones-docs/configuration/#move-ma-scale-adjusters) automatically back and forth.
- Added [**Vertical Thigh Jiggle**](https://fammerino.github.io/InertiaBones-docs/configuration/#enable-experimental-features) rig setup as experimental feature.
- Added toggle and foldout for [**Exclude knee area from weight transfer**](https://fammerino.github.io/InertiaBones-docs/configuration/#exclude-knee-area-from-weight-transfer).
- Added **Built In** sample preset for new features - *Rotational Standard Jiggle (V1.1.0 feature sample)*
- Added heatmap preview for *Vertical Thigh Jiggle* and *Knee Exclusion*
- Added scene refresh upon changing settings for better previewing experience
