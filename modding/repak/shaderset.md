# ShaderSet

### SHDS Assets

ShaderSets are used to define the set of shaders for materials, which control how objects are rendered, including effects like lighting, shadowing, and texture mapping. These assets must be exported with the RSX tool and are stored with the .msw extension.

```
{
    "_type": "shds",
    "_path": "shaderset/shader.rpak"
}
```

Key Fields:\
\_type: This specifies the asset type. For ShaderSets.\
\_path: The file path to the ShaderSet asset (e.g., "shaderset/shader.rpak"). This path points to the .msw file that contains the compiled ShaderSet, which is used by materials in the game.

Additional Considerations:\
Exporting with RSX: ShaderSets need to be exported using the RSX tool to ensure that the .msw file is correctly compiled.\
If the ShaderSet doesn't already exist in the R5Reloaded build, it needs to be explicitly referenced and included in the main RPak JSON.

### SHDR Assets

SHDR (Shader) assets are individual shaders used in rendering pipelines. They contain the code and data that determine how objects or materials are drawn in the 3D environment. SHDR assets are typically referenced by ShaderSets (SHDS), but they can also be used on their own for overwriting already exist shaders in the r5reloaded build.

```
{
    "_type": "shdr",
    "_path": "shader/shader.rpak"
}
```
