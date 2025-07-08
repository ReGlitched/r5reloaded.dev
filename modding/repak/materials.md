# Materials

### MATL Assets

Material assets (matl) are a core part of how objects are rendered in the game, as they define properties like shaders, textures, blend states, and surface properties. Materials are packaged in .rpak files but internally reference a JSON file that holds the actual material data.

Overview of MATL Assets:\
Material JSON: The material data contains information about the shader used, textures applied, blend states, depth/stencil settings, surface properties, and more.\
Reference in Main RPak JSON: MATL asset refers to the material file by pointing to an .rpak file, which is responsible for loading the material data JSON.\
Ported Materials: If a material was ported from another Apex build, or if it uses special materials like depth or colpass materials, these must be explicitly included in the RPak.

This is an example of how a material asset is referenced in the main RPak JSON.

```
{
    "_type": "matl",
    "_path": "material/models/Weapons_R2/epg/epg_mag_sknp.rpak"
}
```

The "\_type": "matl",\
The "\_path" "material/jsonpath.rpak" specifies the path to the .json file that contains the material data.

Material Data JSON Example:\
This is an example of the material data JSON that would be loaded when the material .json file is referenced. It contains the properties of the material, including its textures, shader, blend states, and other properties.

```
{
	"name": "models/Weapons_R2/epg/epg_mag",
	"width": 512,
	"height": 512,
	"depth": 0,
	"glueFlags": "0x56000122",
	"glueFlags2": "0x100000",
	"blendStates": [
		"0xF0138286",
		"0xF0138286",
		"0xF0008286",
		"0x0",
		"0xF0138286",
		"0x0",
		"0x80500002",
		"0x0"
	],
	"blendStateMask": "0x5",
	"depthStencilFlags": "0x7",
	"rasterizerFlags": "0x6",
	"uberBufferFlags": "0x0",
	"features": "0x1F5A92BD",
	"samplers": "0x1D0300",
	"surfaceProp": "plastic",
	"surfaceProp2": "",
	"shaderType": "sknp",
	"shaderSet": "0x15797A5751148156",
	"$textures": {
		"0": "texture/models/Weapons_R2/epg/epg_mag_albedoTexture.rpak",
		"1": "texture/models/Weapons_R2/epg/epg_mag_normalTexture.rpak",
		"2": "texture/models/Weapons_R2/epg/epg_mag_glossTexture.rpak",
		"3": "texture/models/Weapons_R2/epg/epg_mag_specTexture.rpak",
		"5": "texture/models/Weapons_R2/epg/epg_mag_aoTexture.rpak",
		"6": "texture/models/Weapons_R2/epg/epg_mag_cavityTexture.rpak",
		"7": "texture/models/Weapons_R2/epg/epg_mag_opacityMultiplyTexture.rpak"
	},
	"$depthShadowMaterial": "0x0",
	"$depthPrepassMaterial": "0x0",
	"$depthVSMMaterial": "0x0",
	"$depthShadowTightMaterial": "0x0",
	"$colpassMaterial": "0x0"
}
```

Key Fields in Material Data JSON:

name: The name of the material (used for reference).\
width and height: Texture dimensions (used for material setup).\
glueFlags and glueFlags2: Various flags related to material behavior.\
blendStates: Blend states that define how materials blend with others.\
depthStencilFlags, rasterizerFlags, uberBufferFlags: Various rendering flags.\
features: Additional features or settings that modify how the material behaves.\
samplers: Defines how textures are sampled by the GPU.\
surfaceProp: Defines the surface property (e.g., plastic).\
shaderType: The shader type used (in this case, sknp).\
shaderSet: A reference to the ShaderSet associated with this material.\
$textures: A dictionary of textures applied to the material, where keys represent the texture slots (e.g., albedo, normal, spec, etc.) and the values are paths to the texture .rpak files.\
$depthShadowMaterial, $depthPrepassMaterial, etc.: Optional fields that point to specific depth or colpass materials. These should be included if the material uses them.

If the material uses special depth or colpass materials ($depthShadowMaterial, $depthPrepassMaterial, etc.), these materials must also be ported and included in the RPak. These materials are used in advanced rendering techniques like shadow mapping or post-processing effects.

Custom materials may require special handling for compatibility. Check below for the texture slot types.

slot0: \_col\
slot1: \_nml\
slot2: \_gls/\_exp\
slot3: \_spc\
slot4: \_ilm\
slot5: \_ao\
slot6: \_cav/cvt\
slot7: \_opa\
slot8: detail/camo\
slot9: \_dm\_nml/\_nml (detail normal map)\
slot10: \_msk (detail texture mask)\
Blend Materials (used for maps):\
slot16: \_bm (blendmap)\
slot22: \_col\
slot23: \_nml\
slot24: \_gls/\_exp\
slot25: \_spc
