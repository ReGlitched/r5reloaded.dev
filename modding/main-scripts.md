---
description: how to register and run custom scripts with the mod system
---

# Main Scripts

### Creating Custom Script Mods <a href="#f0-9f-93-9c-creating-custom-scripts" id="f0-9f-93-9c-creating-custom-scripts"></a>

#### Setting up `scripts.rson` <a href="#id-1-ef-b8-8f-e2-83-a3-create-a-scriptsrson-file" id="id-1-ef-b8-8f-e2-83-a3-create-a-scriptsrson-file"></a>

This file defines what scripts should be loaded when the game starts.

Example `scripts.rson`:

```
When: "SERVER || CLIENT || UI"
Scripts:
[
    sh_ExampleMod.gnut
]
```

* **When**: Specifies which environments should load the script: `SERVER`, `CLIENT`, `UI`, or combinations.
* **Scripts**: Lists all `.gnut` files to be loaded.

#### Setting up `sh_ExampleMod.gnut` <a href="#id-2-ef-b8-8f-e2-83-a3-set-up-the-main-script-with-callbacks" id="id-2-ef-b8-8f-e2-83-a3-set-up-the-main-script-with-callbacks"></a>

Inside your main script (e.g., `sh_ExampleMod.gnut`), define the following **standard callbacks**:

```
#if SERVER
global function CodeCallback_examplemod_ModInit()
#endif

#if CLIENT
global function ClientCodeCallback_examplemod_ModInit()
#endif

#if UI
global function UICodeCallback_examplemod_ModInit()
#endif

#if SERVER
void function CodeCallback_examplemod_ModInit()
{

}
#endif

#if CLIENT
void function ClientCodeCallback_examplemod_ModInit()
{

}
#endif

#if UI
void function UICodeCallback_examplemod_ModInit()
{

}
#endif
```

**Important:**

* Each callback must exist depending on what the script is registered for.
* If a script is loaded for `SERVER`, it must have `CodeCallback_*_ModInit()`.
* If a script is loaded for `CLIENT`, it must have `ClientCodeCallback_*_ModInit()`.
* If a script is loaded for `UI`, it must have `UICodeCallback_*_ModInit()`.

### &#x20;Important Notes for Mod Developers <a href="#e2-9a-a0-ef-b8-8f-notes-for-mod-developers" id="e2-9a-a0-ef-b8-8f-notes-for-mod-developers"></a>

* Always **globalize** your callback functions at the top.
* The script codecallback name is determined from the 'id' field in mod.vdf. Make sure it's renamed correctly.
* Use conditional compilation (`#if UI`, `#if SERVER`, `#if CLIENT`) to separate logic properly.
