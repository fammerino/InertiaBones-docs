## Compatibility

!!! warning
	 We have seen issues occur when used alongside some tools and optimizers that target mesh / armature on run-time & upload.

I have been made aware of some users struggling with warped / distorted meshes after applying the tool, sometimes;

 - Instantaneously
 - Explicitly in play-mode & after uploading
 - After using toggles on the avatar in-game.

In every attempt to reproduce the issues myself, I have not been able to see the same behaviour, which points to something project-specific like certain tools/gimmicks, or a combination of them to be the root-cause.
Due to the vast amount of different tools, gimmicks, and prefabs (non-outfit prefabs) that is used, I sadly cannot test the compatibility with each and every one of them.

### Compatibility test

If you struggle with issues similar to; or listed above, please do the following:

1. Attempt to apply the tool on an unedited prefab-version of the avatar in question (without any tools or gimmicks attached)
	- If this works fine, then you are likely running into a compatibility issue.
2. Add the different tools & gimmicks that were present on the avatar where you had issues, one by one and redo step one (clean apply with x tool/gimmick attached)
	- Do this until you run into the specific tool/gimmick; or combination of them, that ends up causing issues.
3. (Optional but preferred): Send me a **Bug Report** formatted like the one you can find under **Contact**, so I can verify why it is happening and hopefully implement a solution for future versions.

!!! info
	Regarding compatibility, the bottom line is most often to make sure you utilize any tools doing operations on mesh/armature **before** using InertiaBones.
