# Textures

### TXTR Assets

This asset type is being used to add .dds type textures into the rpak, it's not being required to add if texture path is correct in the material json.

We strongly recommend using mipmapped textures for better performance and better look.

```
{
    "_type": "txtr",
    "_path": "texture/(texture path).rpak"
}
```

Required .DDS Types:

\_col (albedo): BC7 sRGB\
\_nml (normal): BC5U / R8G8\
\_gls (gloss): BC4U\
\_spc (specular): BC7 sRGB\
\_ilm (emissive): BC7 sRGB\
\_ao (ambient occlusion): BC4U\
\_cav (cavity): BC4U\
\_opa (opacity): BC4U

UI Assets:\
BC7 sRGB

Loadscreens:\
BC1 sRGB (Low Quality)\
BC7 sRGB

Minimap:\
BC1 sRGB
