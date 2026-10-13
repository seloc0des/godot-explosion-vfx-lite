# Quick start

Open the project and press Play, or open `res://demo/dragdrop_example.tscn` and hit F6.

Drag `addons/explosion_vfx_lite/scenes/expl_fireball.tscn` into your scene. It plays
and loops. It lands with its middle on the ground, so drag the green arrow up
until all of it shows. One-shot at a blast point:
```gdscript
var fx: FreeExplosionFx = preload("res://addons/explosion_vfx_lite/scenes/expl_fireball.tscn").instantiate()
fx.loop = false
fx.one_shot_free = true
fx.position = blast_position
add_child(fx)
```

Enable Glow in your `WorldEnvironment` (`glow_hdr_threshold ≈ 1.5`, ACES), Forward Plus.
Edit `presets/expl_fireball.tres`. Three HDR colours reskin it. Any white-on-black
texture works in a layer slot.

That preset is part of the pack: an edit changes every fireball you've placed, and a
pack update (new folder copied over the old) puts it back. To keep your own, right-click
the preset in FileSystem, choose **Duplicate...**, name the copy, drag it onto the
effect's **Preset** slot in the Inspector, then double-click the copy to edit it. An
update leaves it alone.
