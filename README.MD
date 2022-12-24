# Windows 7 & 8.1 compatibility patch for The Skywalker Saga.

Libraries used in patch:
- dxvk async 1.10.1
- xaudio2_8.dll replaced by FAudio 22.04 (based on idea from CWTesseract/win7fix)

On Windows 8.1 only dxvk is needed to make game work but with additional d3d10 dlls, so for each os is seperate zip archive.

xaudio2_8.dll replacement solution with FAudio may also work for other games, which requires this library to work. Feel free to try.
(Files: FAudio.dll, SDL.dll, xaudio2_8.dll)

Note: CWTesseract win7fix was created using FAudio 19.10, I have compiled the newest version, because when going in-game, game was crashing.

# Usage
1. Go to [releases](https://github.com/4meters/skywalkersaga-win7-8.1patch/releases) page and download the latest zip file, check for OS version.
2. Extract the `.dll` files to main directory of The Skywalker Saga, next to `LEGOSTARWARSSKYWALKERSAGA_DX11.exe`.

# How it works?
`xaudio2_8.dll` file is replaced by linking library dll which points various functions to `FAudio.dll` library.

You can read more about it here: https://github.com/CWTesseract/win7fix#readme

So the first error of missing xaudio2_8.dll on Win7 is fixed. But still even if game launch it immediately closes after splash window.

The problem is that The Skywalker Saga uses DirectX11 Api Calls which are supported only by Windows 10+.

The solution is to use dxvk - DirectX to Vulkan translator. It's mainly used in WINE project, for playing games on Linux.
But it's also useful in case if somehow the game uses DirectX Api Calls which are supported only by Windows 10 or newer.

It works like this:

`Game -> DirectX calls -> dxvk -> Vulkan -> graphics-card`

Best performance is on dxvk async version. So this version is used in patch.

With combination of these two solutions game work without any issue.
Sometimes there maybe lags, espacially on first run, which may even cause game to crash, its due to building dxvk cache.

# Sources
- https://github.com/Sporif/dxvk-async (`d3d11.dll`, `d3d10.dll`, `d3d10core.dll`, `d3d10_1.dll`, `dxgi.dll`)
- https://github.com/FNA-XNA/FAudio (`FAudio.dll`, `xaudio2_8.dll` built by me, at version 22.04)
- https://github.com/libsdl-org/SDL (`SDL.dll` - version 2.0.20, needed for FAudio)
