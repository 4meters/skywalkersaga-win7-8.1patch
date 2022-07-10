# Windows 7 & 8.1 compatibility patch for The Skywalker Saga.

Libraries used in patch:
- dxvk async 1.10.1
- xaudio2_8.dll replaced by faudio 22.04 (based on idea from CWTesseract/win7fix)

On Windows 8.1 only dxvk is needed to make game work but with additional d3d10 dlls, so for each os is seperate zip archive.

xaudio2_8.dll replacement solution with FAudio may also work for other games, which requires this library to work. Feel free to try.
(Files: FAudio.dll, SDL.dll, xaudio2_8.dll)

Note: CWTesseract win7fix was created using FAudio 19.10, I have compiled the newest version, because when going in-game game was crashing.

# Usage
1. Go to [releases](https://github.com/4meters/skywalkersaga-win7-8.1patch/releases) page and download the latest zip file, check for OS version.
2. Extract the `.dll` files to main directory of The Skywalker Saga, next to `LEGOSTARWARSSKYWALKERSAGA_DX11.exe`.

# Sources
- https://github.com/Sporif/dxvk-async (`d3d11.dll`, `d3d10.dll`, `d3d10core.dll`, `d3d10_1.dll`, `dxgi.dll`)
- https://github.com/FNA-XNA/FAudio (`FAudio.dll`, `xaudio2_8.dll` built by me, at version 22.04)
- https://github.com/libsdl-org/SDL (`SDL.dll` - version 2.0.20, needed for FAudio)
