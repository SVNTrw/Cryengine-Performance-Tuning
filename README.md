# ArcheRage Performance Optimization Guide
This is a passion project focused on optimizing an outdated verison of Cryengine, specifically for the popular mmorpg ArcheAge!

## 📖 Why This Exists

ArcheRage and its relationship with **CryEngine** has been a decades-long struggle.

Stuttering.  
Crashing.  
Unstable FPS.

After spending years dealing with this, I decided to dig into *why* it happens—and more importantly, **how to fix/mitigate it** (Gameplay & Videos will feel/look noticably smoother even in 100+ player instances!)

This repository documents my optimization process, along with full credit to any sources used and a link to my discord support channel located at the bottom.

❗ **This Project is Appproved for use by the ArcheRage Private Server moderation team, likewise, there should be no issue using this on the Live servers or any other Private Server, no installation is required it's a simple cfg edit.**
##  What This Optimization Proccess Does
- **Significantly reduces stuttering**
- **Stabilizes FPS**, especially in crowded or high-load scenarios
- **Stabilizes FPS**

##  What It Doesn't Do
- Does **not** increase player/vehicle/mount view distance  
- Does **not** allow players to see ships, players, or objects from farther away than intended by the devs 
  *(No unfair advantage — this is purely performance-focused)*

## 💻 Requirements
- GPU
- CPU
- ArcheRage installed on an **SSD** *(strongly recommended)*

![Ingame Screenshot](https://i.imgur.com/U9kVJSo.png)

⭐Please note that the engine limits max fps to 150, this will not allow you to uncap fps, these are simple & uninvasive Cryengine commands that are just not utilized

## ⚙️ How to Install

1. **Backup your current `system.cfg` file**  
   - Location: `Documents > ArcheRage > system.cfg`  
   - Make a copy somewhere safe in case you need to revert.

2. **Change ingame settings as desirable, or you can follow my [Graphics Settings Guide](https://youtu.be/RE5O_nuJIvk)**
> ⚠️ 
> Do not set anything to Very High aside from Draw Distance.  
> Setting everything to Max and disabling anti-aliasing is okay.

  
3. **Edit `system.cfg`**  
   - Open `system.cfg` with **Notepad** or another text editor.

4. **Make a space under the already existing lines, then Copy & Paste the following lines under that**  
   - Replace or add the lines exactly as provided below. *(Click the cool box to copy the entire list!)*

```ini
r_UseShaderThread = 1
r_ShadersPrecache = 1
r_GeomInstancing = 1
gpu_ParticleBuffers = 1
e_Decals = 0
e_DetailMaterial = 0
e_Shadows = 1
e_ShadowsOnAlphaBlend = 0
e_ShadowsMaxTexRes = 512
e_ShadowsCastViewDistRatio = 0.2
e_ShadowsResScale = 0.5
e_ObjQuality = 1
e_LodRatio = 6
_UseHardwareOcclusionQueries = 1
r_UsePBuffers = 0
r_TexMaxAnisotropy = 16
r_UseParticlesHalfRes = 1
r_ParticleVerticeNum = 0 
gpu_ParticlePhysics = 0 
e_ParticlesQuality = 0
````

## Disclaimer!
Currently, changing any ingame settings will undo these lines, however they will reapply upon your next launch of the game.

## If you followed the steps above, you'll notice a **huge difference** right away:  
- FPS no longer drops to the 15s  
- Stuttering becomes much rarer  
- Overall gameplay feels smoother and more stable 


## 🛠 Extra Optimization Step (Not Neccecary, but applies to all games/programs & is quick to apply!)

   **Edit NVIDIA Shader Cache Size**  
   - Open **NVIDIA Control Panel → Manage 3D Settings → Shader Cache**  
   - Set it to **10 GB**  
   - Click Apply  
   - This helps reduce stuttering by caching shaders more effectively.





## **Congratulations!** You have now completed everything necessary to achieve increased performance.  

As stated at the beginning, I will now provide **credits** and a **direct Discord link** for any questions you may have :).


-SVNTrw






---


**[Discord Support Channel](https://discord.com/channels/417795371603853313/1333130730502492262)**













***Resource links/Credit;***

[Enviroment Graphics Overhaul Video by "The Bagel"](https://www.youtube.com/watch?v=ilk5SlYLv74) 
- Old but VERY signifigant video for this proccess, through this I was able to discover that you can add edits to the system.cfg , in this video they add lines that actually increase visual fidelity, you may still follow this guide at your own discresion.


[Cryengine Software Command List](https://web.archive.org/web/20230328190343/https://docs.cryengine.com/display/CRYAUTOGEN/CONSOLEPREFIXR)
- Using an internet archive, I was able to find the list of commands that work specifically for the cryengine version Archeage runs on, though many lines are redundant it is very educational
- Likely there are lines to discover that work for Archeage, for increasing visual fidelity or futher optimization




