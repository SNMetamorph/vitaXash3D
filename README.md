# vitaXash3D
A port of Xash3D-FWGS to the PSVita.

## Warning
This is currently very broken and not user-friendly at all. Expect severe graphics glitches, crashes and gameplay oddities.

HLSDK is statically linked into the engine executable, so you can only use this with Half-Life right now.

Any other GoldSrc mod/game that has custom DLLs would require some modifications to be able to hardlink in the same way, I'll write a guide on that later.

The port supports mods that don't have their own DLLs (e. g. USS Darkstar).

## Requirements
- VitaSDK (in PATH and with VITASDK set);
- [vitaGL](https://github.com/Rinnegatamante/vitaGL).

## Building
Run `make` in this directory. This should produce a VPK.

## Running
1. Copy the `valve` directory from your Half-Life installation (preferably the Steam version) to `ux0:/data/xash3d/` on your Vita. If you don't have access to a Half-Life installation,
you can use the [data files](https://github.com/fgsfdsfgs/vitaXash3D/releases/download/v1/uplink.zip) from the free demo version of HL, Half-Life Uplink.
2. Copy the `build/data` directory to `ux0:/` on your Vita. Replace everything if asked.
3. Delete everything from `valve/cl_dlls` and `valve/dlls`.
4. Install the VPK obtained after building the port.
5. Run it.

Selecting the "Dev Mode" icon enables advanced logging and debug features, so use that for debugging. The log will be saved to `ux0:/data/xash3d/engine.log`.

Keep in mind that the game can hang for a long time when saving or autosaving (see issue [#7](https://github.com/fgsfdsfgs/vitaXash3D/issues/7)),
so don't kill it if it suddenly hangs when you enter a map or cross a checkpoint. You can disable autosaves in the "Game options" menu or with `sv_autosave 0`.

The mod launcher detects all directories you have inside `ux0:/data/xash3d/`, including `valve`, except directories that have names starting with a dot.

Installing mods works the same as with PC Half-Life: you just have to copy the mod directory (e. g. `darkstar`) into `ux0:/data/xash3d/`. Keep in mind
that if the mod has custom game DLLs (e. g. They Hunger, Counter-Strike, Opposing Force...), it most likely won't work correctly.

## Credits
- Uncle Mike & co for Xash3D and FWGS team for Xash3D-FWGS;
- Vita SDK Team for the Vita SDK;
- Rinnegatamante for vitaGL, vitaQuake/vitaQuakeII and general advice;
- ArkSource for the Live Area stuff;
- everyone on the #henkaku and #vitasdk IRC channels for help and/or testing.
