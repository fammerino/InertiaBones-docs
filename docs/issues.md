# Known Issues & Limitations

## Known Issues

## Known Limitations

- Current version will not propagate PhysBone jiggle down to other PhysBone chains parented to source-bones that have been converted to controllers.

Example hierarchy structure:

Upperleg_R
	Lowerleg_R
	Belt_PB_R <---- If this has a PhysBone component and it is weighted to that, then motion from the Upperleg_R InertiaBones controller will not propagate down.
		Belt_PB_001_R (etc...)

We are aiming to fix this in the future, but be aware of it for now.

- Current version does not allow for iterative editing **when** using **Bake converted meshes as assets**.

What is meant by this is the following -> Adding 2 controllers to an avatar, then adding 2 different controllers to the same avatar.
If the persist (Bake) option is on, then the resulting behaviour will be a total of 4 controllers on the avatar, but only 2 of them actually affect the meshes you baked.

That is why it is recommended to use **Session-only mode** when doing this sort of iterative editing. Then bake when you have finalized your setup / preset.

