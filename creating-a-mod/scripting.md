# Scripting

For this example we will be setting up a new weapon mod.\
Inside of your `sh_ExampleMod.gnut` file under `CodeCallback_examplemod_ModInit` add this:\
`PrecacheWeapon( $"mp_weapon_WeaponName" )` \
\
It should look like this:

```
#if SERVER
void function CodeCallback_examplemod_ModInit()
{
    PrecacheWeapon( $"mp_weapon_WeaponName" )
}
#endif
```

Now go back into your `scripts` directory, inside that folder create another folder named `weapons` \
Inside the weapons folder create a txt named `mp_weapon_WeaponName.txt` \
Your file directory should now look like this

```
ExampleMod/
├── mod.vdf
└── scripts/
    ├── weapons/
    │   └── mp_weapon_WeaponName.txt
    └── vscripts/
        ├── scripts.rson
        └── sh_ExampleMod.gnut
```

Inside that txt you can define weapon settings and variables any way you would like. In this case we will create a silenced pistol. \
For now you can use this file, copy and paste the contents of this into your weapon script:

{% file src="../.gitbook/assets/mp_weapon_WeaponName.txt" %}

After this is done you should be able to boot up the game and load into a map. \
Type `give mp_weapon_WeaponName` into the console and you will have your weapon.
