# Animations

### RRIG Assets (Animation Rigs)

Animation Rigs (rrig) define how models animate by specifying the bone structure and animation layers. These rigs are used by .rmdl models to apply various animations, such as walking, running, aiming, etc. When an animation seq is referenced in a rig, the associated animation sequences are automatically loaded by the RPak, so you don't need to explicitly reference them separately.

These assets define the skeleton and animation layers for a model. Each animation rig can have multiple animation sequences that are applied to a model based on the rig's bone structure.\
Sequences: Animation sequences are included by the RPak tool when the animation rig is loaded. They don't need to be explicitly listed unless additional customization is needed.

This is an example of how an animation rig (.rrig) is referenced in the main RPak JSON file. It also includes a list of animation sequences that belong to this rig.

```
{
    "_type": "arig",
    "_path": "animrig/robots/drone_air_attack/drone_air_attack_plasma.rrig",
    "$sequences": [
        "animseq/robots/drone_air_attack/drone_air_attack_plasma/aim_layer.rseq",
        "animseq/robots/drone_air_attack/drone_air_attack_plasma/aim_run.rseq",
        "animseq/robots/drone_air_attack/drone_air_attack_plasma/aim_walk.rseq",
        "animseq/robots/drone_air_attack/drone_air_attack_plasma/alert.rseq",
        "animseq/robots/drone_air_attack/drone_air_attack_plasma/attack.rseq",
        "animseq/robots/drone_air_attack/drone_air_attack_plasma/idle.rseq",
        "animseq/robots/drone_air_attack/drone_air_attack_plasma/reload.rseq"
    ]
}
```

Key Fields in RRIG Asset JSON:

\_type: "arig" specifies that this is an animation rig asset.\
\_path: "animrig/filepath.rrig" The path to the .rrig file that defines the animation rig.\
$sequences: A list of animation sequences associated with the rig. These are applied based on the animation rig's configuration, so they are automatically loaded by the RPak tool.

Bone Structure: The .rrig file defines the skeleton, so it must be compatible with the model (.rmdl) that references it. This ensures the animations are applied correctly to the model's bones.\
Sequences and Animations: If the animation sequences (e.g., idle, attack) have been defined in the rig, they are automatically linked to the model. However, any additional animation sequence that isn't part of the original rig cannot be added into the rig. Otherwise this will cause a crash.

### RSEQ Assets

Animation Sequences (rseq) are animation files that define the movement or behavior of a model, such as idle animations, attack animations, etc. These sequences are often associated with Animation Rigs (.rrig) and Models (.rmdl). However, if they are not part of a rig or model, they must be explicitly included in the main RPak JSON.

It is essential to not rename the .rseq files. Renaming these files will cause a breakage in the GUIDs (Global Unique Identifiers) of the animations, resulting in missing references and crashes.

```
{
    "_type": "rseq",
    "_path": "animseq/props/testanimfolder/close_idle.rseq"
}
```

In most cases we don't need this asset type, only use for this would be replacing an animation sequence from R5Reloaded build.
