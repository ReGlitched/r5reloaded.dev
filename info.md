# Info

Each mod has its own folder inside the `mods` directory. Inside a typical mod folder, you'll find:

* **Pak Files**: For custom assets and content.
* **Resource Folder**: For localization (translations) and UI assets.
* **Scripts Folder**: For any custom logic or gameplay changes.
* **mod.vdf**: A configuration file describing the mod.

## What you can customize in a mod

* **Basic Information**\
  Set your mod's name, unique ID, description, version number, and author.
* **Localization**\
  Attach your own translation files to support multiple languages.\
  Example: `resource/mymod_%language%.txt`
* **ConVars (Console Variables)**\
  Define custom settings that players can tweak via the in-game console.\
  You can set default values, min/max ranges, and helpful descriptions.
* **Custom Audio**\
  Include your own sounds, music, or voice lines through your mod’s pak files.\
  Custom audio is currently not possible, but when it does. Mod system is already ready for it.
* **Custom Scripts**\
  Add or override game behavior using your own scripts to create new features, modify movement, weapons, UI, or even create brand-new game modes.
* Custom Assets\
  Add custom models, animations, materials, etc.
