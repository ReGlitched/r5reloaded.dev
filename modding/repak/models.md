# Models

### MDL Assets

This asset type is used to define 3D models (RMDL) within the RPak. These models can be static or dynamic, and they may include animations and physics files. Models are typically loaded into the game by their file paths and can be used as props, characters, or other interactive elements.

```
{
    "_type": "mdl_",
    "_path": "mdl/props/kralstest/thisisa_testprop.rmdl",
    "$animrigs": [
        "animrig/props/prowler_hatch_tt/prowler_hatch_tt.rrig"
    ],
    "$sequences": [
        "animseq/props/prowler_hatch_tt/close.rseq",
        "animseq/props/prowler_hatch_tt/close_idle.rseq",
        "animseq/props/prowler_hatch_tt/open.rseq",
        "animseq/props/prowler_hatch_tt/open_idle.rseq",
        "animseq/props/prowler_hatch_tt/prowler_hatch_tt/prop_bloodhoundTT_hatch_spawn.rseq"
    ]
}
```

Key Fields:

_type: Asset type, always set to "mdl_" for model assets.\
\_path: Path to the model file within the game assets (e.g., mdl/props/kralstest/thisisa\_testprop.rmdl).\
$animrigs: An array of paths to the animation rigs associated with the model. These rigs define how the model will animate (e.g., animrig/props/prowler\_hatch\_tt/prowler\_hatch\_tt.rrig).\
$sequences: Optional array of paths to animation sequences for the model. If a model doesn’t have an animation rig but still requires animations, these sequences can be applied directly to the model. Sequences included within the model doesn't require to be added seperately aka RePak will auto add them.

Important Notes:\
Materials: Every material used by the model must be included in the main rpak json. Missing materials may result in GUID errors.\
Physics Files: If the model is interactive or needs physics behavior, make sure to include the associated .phy file.

//=========================================================\
// Surface Types //\
//=========================================================

// -----------------------------\
// Surface Materials\
// -----------------------------

default metal\_titan solidmetal / NOTE: Almost nothing is solid metal - so "metal" is sheet metal metal / NOTE: Only flag a few things as "solidmetal" (I-Beams, anvils, etc) metal\_box / Smaller metal box (< 2' width/height/depth) metalpanel / Thick solid steel panel - used for solid wall, floor, machine construction metalgrate metalvent dirt tile xo\_shield wood / NOTE: materials should use wood\_box, wood\_crate, wood\_plank, wood\_panel etc wood\_solid water concrete glass glass\_breakable flesh armorflesh / NOTE: Flesh for physics, metal for bullet fx sand mud grass brokenglass gravel bloodyflesh

// -----------------------------\
// Non Surface Materials\
// -----------------------------

shellcasing\_small shellcasing\_large weapon / NOTE: Weapon models - sounds for when weapons drop computer canister / NOTE: Large oxygen tank, propane tank, welding tank metal\_barrel / NOTE: Larger metal barrel, metal oil drum glassbottle / NOTE: Glass soda bottle, cup, plate, jar pottery / NOTE: Ceramic jug, mug grenade / NOTE: Solid hand grenade grenade\_triple\_threat bouncygrenade

// -----------------------------\
// world materials\
// -----------------------------

metal\_bouncy slipperymetal / Note: Airboat pontoons have very low friction slipperyslime wood\_lowdensity wood\_box / Note: Small crate wood\_crate / Note: Large crate, large wood furniture (bookcases, tables) wood\_plank / Note: wood board, floorboard, plank wood\_furniture / Note: small wood furniture - chairs, small tables wood\_panel / Note: wood panel - plywood panel, wood door panel slime quicksand rock / Note: Solid rock (small sounds) lava\_rock lava\_rock\_hot / Note: Lava rock that shows a glows when shot lava\_flow / Note: scrolling uv lava, like water. porcelain / Note: tubs, urinals, sinks boulder / Note: Large solid rock (large sounds) asphalt brick concrete\_block / Note: 9x12 prefabricated concrete cinder blocks chainlink / Note: chainlink fencing material chain / Note: metal chain alienflesh watermelon snow ice carpet plaster / Note: drywall, office wall material, sheetrock cardboard / Note: carboard box plastic\_barrel / Note: larger plastic barrel, hollow, soft plastic plastic\_box / Note: small - medium plastic box, hard plastic plastic / Note: smaller generic hard plastic item / Note: small med kit, smaller tech items, battery floatingstandable rubber rubbertire jeeptire slidingrubbertire brakingrubbertire slidingrubbertire\_front slidingrubbertire\_rear

// -----------------------------\
// objects\
// -----------------------------

floating\_metal\_barrel plastic\_barrel\_buoyant roller popcan paintcan paper papercup ceiling\_tile default\_silent player player\_control\_clip foliage Underground\_Cube Turret\_Gib metal\_spectre arc\_grenade upholstery flyerflesh ammo\_box Helmet Large\_Backpack Small\_Backpack Large\_Medkit Small\_Medkit Att\_Scope Att\_Sup Wpn\_AR Wpn\_Snipe Wpn\_SMG Wpn\_Pistol Wpn\_Shotgun Vest Mags Cyn\_Medkit Frag ArcBlade BatteryShield reflective WeightedCube\_Bounce PaintBomb sphere2
