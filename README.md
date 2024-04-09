Fork of the Scanner mod to provide OpenComputers access for the Terrain Scanner. Intended for use with Levitated 1.5.3 because I got tired of scanning chunks manually.
There's only 1 commit here, I don't intend on working on this further:

Libs:
- Added Hwyla and OC to the libs folder, couldn't get the old Hwyla gradle to work, didn't feel like doing it for OC.
- This was made for use with the modpack Levitated v1.5.3, so these versions are from that.

BaseTE:
- Changed BaseTE to extend TileEntityEnvironement from OC

TileEntityTerrainScanner:
- Added OC support for the Terrain Scanner: It connects directly via cable
	-accessible via components.scanner
	-added the following OC accessible functions:
		- isEnabled()
			Returns whether or not the scanner is currently running
		- getEnergyStored()
			Returns RF stored inside
		- setScannerPosition(x, y, z)
			Sets the current and start position of the scanner to the supplied coords. Returns true if successful, false if not. Will return false if the coordinates are outside of the max range specified in the config (does the same check as the scanner queue)
		- setScannerSpeed(newSpeed)
			Sets the scanner speed to the given speed. Returns the final speed. Will fail if <1 or higher than the max speedup set in the config.
		- activateScanning()
			Turns the scanner on.
		- deactivateScanning()
			Turns the scanner off.
		- isFinished()
			Should return true if and only if the scanner has run through it's current chunk to completion. Added a new private boolean for this to the TE that gets set to false whenever activated, and only goes true on the CurrentY > MaxY check.

Note: The scanner GUI might not update properly for players, but the information OC is getting (and the changes to the world) should happen client and serverside. I didn't intend on interacting with the scanner via anything but OC after I wrote this, so I didn't care enough to fix that.





Scanner Mod for Minecraft 1.12.2

Updated by IGCBOOM & Misterplus

Originally made by Eladkay.
