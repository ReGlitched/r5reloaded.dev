# Getting Started

## Creating your first mod

Create a folder named anything you would like, in this case we will call it `ExampleMod`, inside this folder create another folder named `scripts` and a file named `mod.vdf` . `sh_ExampleMod.gnut`&#x20;

When you do that your file directory should be as follows:

```
ExampleMod/
├── mod.vdf
└── scripts/
```

Inside mod.vdf paste this. This defines your mods name, id, description, version, and your name.

```
"mod"
{
	"name" "Example Mod"
	"id" "examplemod"
	"description" "ModDescription"
	"version" "0.1"
	"author" "AuthorName"
}
```

Inside of the scripts folder create a folder named `vscripts`, inside of that create 2 files named `scripts.rson` and `sh_ExampleMod.gnut` \
your file directory should now be:

```
ExampleMod/
├── mod.vdf
└── scripts/
    └── vscripts/
        ├── scripts.rson
        └── sh_ExampleMod.gnut
```

Once you do that you can move on to the scripting portion here

{% content-ref url="main-scripts.md" %}
[main-scripts.md](main-scripts.md)
{% endcontent-ref %}
