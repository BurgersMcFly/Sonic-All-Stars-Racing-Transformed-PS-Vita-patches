# Sonic-All-Stars-Racing-Transformed-PS-Vita-patches
VitaGrafix resolution and FPS patches for Sonic &amp; All-Stars Racing Transformed on the PS Vita.

For PCSE00056, game version 1.01.

## Usage

Add these lines in patchlist.txt:
```
# Sonic & All-Stars Racing Transformed
[PCSE00056, eboot.bin, 0xD6A8133B] # [US 1.01]
@IB
0:0x0485d0 t2_mov(1, 0, ib_w)
0:0x0485d6 t2_mov(1, 0, ib_h)
@FPS
0:0x147e8e t1_mov(0, vblank)
```

Add these lines in config.txt:
```
[PCSE00056]
ENABLED=1
OSD=1
IB=OFF
FPS=OFF
```

## Getting ID and NID for your game
Taken from [Make Your Own Patch for VitaGrafix](https://wp.yuki.pet/make-your-own-patch-for-vitagrafix/).

1. Launch your game. Give it a few seconds to boot up properly and then exit the game. 

1. Open VitaShell on your PSVita and enable transfer mode, either USB or FTP.

1. Navigate to /ux0:/data/VitaGrafix and open log.txt. It should look like this:

```
VitaGrafix v5.0.2
=======================================
[MAIN] Title ID: PCSE00056
[MAIN] SELF: ux0:/patch/PCSE00056/eboot.bin
[MAIN] NID: 0xD6A8133B
=======================================
[IO] Parsing ux0:data/VitaGrafix/patchlist.txt
[PATCH] Patching seg000 : 000485D0 to 5F F4 70 70, size=4
[PATCH] Patching seg000 : 000485D6 to 5F F4 08 74, size=4
[PATCH] Patching seg000 : 00147E8E to 01 20, size=2
[PATCH] Patched 10 bytes in 3 patches and it took 71ms
[PATCH] 288 total game patches found in patch list
```

Your title ID is [MAIN] Title ID: **PCSE00056**.
Your NID is [MAIN] NID: **0xD6A8133B**.

Replace PCSE00056 and 0xD6A8133B with yours.

## Credits

1.[VitaGrafix Documentation](https://github.com/Electry/VitaGrafix/wiki/The-VG-Language%E2%84%A2) 
2.[Make Your Own Patch for VitaGrafix](https://wp.yuki.pet/make-your-own-patch-for-vitagrafix/) 
3.[Getting resolution addresses for vitaRescale](https://wololo.net/talk/viewtopic.php?t=48713) 
4.[Elecry Explanation](https://github.com/Electry/VitaGrafix/issues/112) 
5.[VGi plugin](https://github.com/Electry/VGi) 
