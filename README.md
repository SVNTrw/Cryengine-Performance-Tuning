# Cryengine Performance Optimization Guide
This is a passion project focused on optimizing an outdated verison of Cryengine, specifically for the popular mmorpg ArcheAge!

## 📖 Why This Exists

ArcheAge’s relationship with CryEngine has been a decades long struggle for the community.

Stuttering.  
Crashing.  
Unstable FPS.

After months of testing/instancing, I've identified the commands that signifigantly reduce/remove these issues.

This repository consolidates my work into a simple CFG edit for end users.

❗ **This Project is Appproved for use by the ArcheRage Private Server moderation team, likewise, there should be no issue using this on the Live servers or any other Private Server, no installation is required it's a simple cfg edit.**
##  What This Optimization Proccess Does
- **Significantly reduces stuttering**
- **Stabilizes FPS**, especially in crowded or high-load scenarios
- **Stabilizes FPS**

##  What It Doesn't Do
- Does **not** increase player/vehicle/mount view distance  
- Does **not** allow players to see ships, players, or objects from farther away than intended by the devs 
  *(No unfair advantage — this is purely performance-focused)*

## 💻 Setup Requirements
- DirectX 11 enabled in-game
- Basic Text Editor (Notepad or Notepad++)
- ArcheRage installed on an **SSD** *(strongly recommended)*

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
;====================================================================
; CRYENGINE PERFORMANCE OPTIMIZATION
; Developed by: SVNTrw
; Targeted for ArcheAge / ArcheRage Performance & Stability
;====================================================================

;--- System & CPU Optimization ---
sys_job_system_enable = 1            ; Helps the engine share the workload across your processor
sys_job_system_max_worker = 4 ; Set this to your physical core count so the engine uses the whole CPU
r_UseShaderThread = 1                ; Keeps shader loading on its own track to prevent hitching
r_MultiThreaded = 1                  ; Tells the engine to use all available cores

;--- Memory & Asset Streaming ---
sys_budget_videomem = 4096 ; Total amount of VRAM your graphics card has in MB
sys_streaming_memory_size = 1024 ; How much room the engine has to pull assets from your drive
r_TexturesStreamPoolSize = 2048 ; The dedicated pool for textures usually half of your total VRAM
r_ShadersPrecache = 1                ; Handles the heavy lifting for shaders before you start playing
e_StreamPrediction = 1               ; Pre loads objects before they hit your screen to avoid pop in

;--- Geometry & Rendering ---
e_ObjQuality = 1                     ; Focuses on smooth performance instead of drawing distant objects
e_LodRatio = 6                       ; Controls how far away models stay in high detail
e_DetailMaterial = 0                 ; Cleans up surface materials to keep the GPU from overworking
r_GeomInstancing = 1                 ; Lets the GPU group similar objects together to save effort
_UseHardwareOcclusionQueries = 1     ; Prevents the card from rendering things you can't even see

;--- Lighting & Shadows ---
e_Shadows = 1                        ; Basic shadows for depth without the massive performance hit
e_ShadowsOnAlphaBlend = 0            ; Stops shadows from trying to render on grass or water
e_ShadowsMaxTexRes = 128 ; Keeps shadow quality at a level that won't tank your FPS
e_ShadowsResScale = 0.5              ; Cuts the overhead needed to calculate shadow size
e_ShadowsCastViewDistRatio = 0.2     ; Pulls the shadow distance in so you aren't wasting power on the horizon
r_UsePBuffers = 0                    ; Uses modern hardware methods instead of old legacy tech

;--- Particles & Visual Effects ---
r_UseParticlesHalfRes = 1            ; Massive help in large scale combat by optimizing spell effects
r_ParticleVerticeNum = 128 ; Puts a ceiling on particle complexity for smoother fights
gpu_ParticleBuffers = 1              ; Moves the particle workload from the CPU to the GPU
gpu_ParticlePhysics = 0              ; Turns off heavy physics for small effects you won't notice
e_ParticlesQuality = 0               ; Sets a solid performance baseline for all visual effects
q_ShaderPostProcess = 1              ; Lightens the load for things like bloom and motion blur
r_TexMaxAnisotropy = 16              ; Keeps your textures looking sharp at an angle

;--- Stability & Latency ---
r_FinishDoubleBuffered = 1           ; Helps with that "floaty" mouse feeling and cuts down stutter
````

***Note on Customization: The commands surrounded by stars above are optimized for a standard gaming PC (8-core CPU, 8GB GPU, 16GB RAM). While this is "Plug & Play" for most people, you can change the following values to match your specific hardware for even better results.***
- sys_job_system_max_worker = *4* ; Set this to your physical core count so the engine uses the whole CPU
- sys_budget_videomem = *4096* ; Total amount of VRAM your graphics card has in MB
- sys_streaming_memory_size = *1024* ; How much room the engine has to pull assets from your drive
- r_TexturesStreamPoolSize = *2048* ; The dedicated pool for textures, usually half of your total VRAM

## Disclaimer!
Currently, changing any ingame settings will undo these lines, however they will reapply upon your next launch of the game. I am currently working on an official addon that will apply the commands, and solve this issue in the future.

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




