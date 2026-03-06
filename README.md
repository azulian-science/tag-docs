## Tags

### `Robot`

Apply to a character `Model`. The model will wander around on its own using pathfinding.

No attributes required. The model must have a `Humanoid` and `HumanoidRootPart`.

---

### `Followbot`

Apply to a character `Model`. The model will follow a target and fall back to wandering if the target dies or leaves.

Requires: a child `ObjectValue` named `Leader` pointing at the target to follow (can be a player character or a `BasePart`).

No other attributes needed.

---

### `SpriteNPC`

Apply to a `Model` with a `BasePart` as its primary part. The model displays an animated sprite sheet and moves around.

The primary part should have `SurfaceGui` children named `Front` and/or `Back`, each containing an `ImageLabel`.

#### Attributes

- `SpriteSheetID` _(string, required)_ - Asset ID for the front-facing sprite sheet (e.g. `rbxassetid://...`)
- `SpriteSheetIDBack` _(string, optional)_ - Asset ID for the back-facing sprite sheet. Defaults to `SpriteSheetID` if not set.
- `FrameRate` _(number, optional)_ - Animation speed in frames per second. Default: `24`
- `WalkDistance` _(number, optional)_ - How far the NPC paces back and forth in studs. Default: `20`
- `WalkSpeed` _(number, optional)_ - Movement speed in studs per second. Default: `8`
- `CircleRadius` _(number, optional)_ - If set, the NPC orbits in a circle instead of pacing. Value is the orbit radius in studs.
- `CircleSpeed` _(number, optional)_ - Orbit speed in radians per second. Only used when `CircleRadius` is set. Defaults to `WalkSpeed ÷ CircleRadius`.
- `CircleCenter` _(Vector3, optional)_ - Center point of the orbit. Only used when `CircleRadius` is set. Defaults to the NPC's spawn position.

---

### `TeleportClicker`

Apply to a `ClickDetector`. When a player clicks it, they are animated and teleported into the currently loaded dream.

#### Attributes

- `Hub` _(boolean, required)_ - Must be `true` for the clicker to work.

---

### `Draggable`

Apply to a `BasePart` or `Model`. Players can click and drag the object around.

---

### `Antigravity`

Apply to a `BasePart` or `Model`. The object will partially or fully counteract gravity, making it float.

#### Attributes

- `Floatiness` _(number, optional)_ - How strongly gravity is counteracted. `1` = fully floats in place. Values above `1` push upward, below `1` still fall but slower. Default: `1`

---

### `Ejector`

Apply to a `BasePart` or `Model`. When a player touches it (or any descendant `BasePart`), they are flung back to the dream's spawn point. Only affects players who are currently inside a dream.

No attributes required.

---

### `PlaySoundOnClick`

Apply to a `BasePart` or `Model`. A click detector is added and plays a sound when clicked.

**Attributes:**

- `SoundID` _(string, required)_ - Asset ID of the sound to play (e.g. `rbxassetid://...`)
- `Volume` _(number, optional)_ - Playback volume from `0` to `1`. Default: `1`

---

## Prop Attributes

These attributes are set directly on any **BasePart** or **Model** you want players to scan with the **PropTool**.

- `IsProp` _(boolean, required)_ - Marks this object as a scannable prop. Must be `true`.
- `DisplayName` _(string, required)_ - The name shown in the scan UI.
- `Description` _(string, required)_ - A short description shown in the scan UI.
- `DownloadedIn` _(string, required)_ - The dream or location the prop is downloaded in, shown in the scan UI.

All four are required for the prop scan to display correctly
****
