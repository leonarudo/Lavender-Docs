# StorageCategory

<br>

# StoragePrefab.json
The StorageCategory defines the size, refrigeration and sounds of an storage.<br>

<br>

## Example
```json
[
    {
		"id": 1,
		"Name": "Chest",
		"Panels": 24,
		"Refigerated": 0.0,
		"OpenSoundPath": "Sounds/object/chest_001_open",
		"OpenSoundVolume": 1,
		"OpenSoundPitch": 1,
		"OpenSoundDistance": 20,
		"CloseSoundPath": "Sounds/object/chest_001_close",
		"CloseSoundVolume": 1,
		"CloseSoundPitch": 1,
		"CloseSoundDistance": 20,
		"LockedSoundPath": "Sounds/object/chest_001_locked",
		"LockedSoundVolume": 1,
		"LockedSoundPitch": 1,
		"LockedSoundDistance": 20,
		"UnlockSoundPath": "Sounds/door/door_unlock_keys_001",
		"UnlockSoundVolume": 1,
		"UnlockSoundPitch": 1,
		"UnlockSoundDistance": 20,
		"LockpickSoundPath": "Sounds/door/door_unlock_001",
		"LockpickSoundVolume": 1,
		"LockpickSoundPitch": 1,
		"LockpickSoundDistance": 20
	},
]
```
<br>

## Keys
- The ``Name`` key is used to identify a StorageCategory in the Database.
- The ``Panels`` key determines the storage size. (max value 88)
- The ``Refigerated`` key determines the refrigeration factor. (Refrigerator 0 - 1. Freezer 1 or more)