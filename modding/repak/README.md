# RePak

## Overview

**Asset Types**

dtbl: Datatables, Comma-separated values (CSV). Custom or manually ported from Apex Seasons.\
shds: Material shadersets, Multi Shader Wrapper (MSW). Connects two different shaders into one set. Only supported by the latest RSX version.\
shdr: Material shaders, Multi Shader Wrapper (MSW). txtr: Texture assets, DirectDraw Surface Images (DDS). Ensure you check the texture types in the txtr section.\
matl: Materials, JavaScript Object Notation File (JSON). Exported with RSX or custom-made. Contains all material data.\
aseq: Animation sequences, Respawn Sequences (RSEQ). Animation data for Respawn Models, Can’t be custom-made, needs to be exported using RSX.\
arig: Animation rigs. Respawn Rigger Design File (RRIG). Model rig for Respawn Models, Can’t be custom-made, needs to be exported using RSX.\
rmdl: Models, Respawn Model (RMDL)\
uimg: Atlas, This is used for ui images, minimaps and loadscreens. See atlas section.

**Asset Order in Main RPak JSON**\
stlt > stgs > txan > dtbl > shdr > shds > txtr > matl > aseq > arig > rmdl > uimg
