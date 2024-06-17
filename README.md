[![GitHub Release](https://img.shields.io/github/v/release/IanE-Official/rehash-sfse-asi-loader)](https://github.com/IanE-Official/rehash-sfse-asi-loader/releases)
[![Main/Release Build](https://github.com/IanE-Official/rehash-sfse-asi-loader/actions/workflows/build-push.yml/badge.svg)](https://github.com/IanE-Official/rehash-sfse-asi-loader/actions/workflows/build-push.yml)

# 📑 SFSE ASI Loader

SFSE plugin which safely preloads ASI mods with logging forked from Doodlez by Ian E.

## To install / use this mod as an end-user:

1. For the mod to work correctly, Install Starfield (Steam Edition), [Starfield Script Extender (SFSE)](https://www.nexusmods.com/starfield/mods/106), and [Address Library for SFSE Plugins](https://www.nexusmods.com/starfield/mods/3256).
2. Download latest compiled version from [NexusMods](https://www.nexusmods.com/starfield/mods/8055?tab=files) or my [Github Releases](https://github.com/IanE-Official/rehash-sfse-asi-loader/releases)
3. **_To use just place expand in your Starfield data directory or just copy the DLL to `{StarfieldDirectory}/Data/SFSE/Plugins/` and run the game_**

## Get started from source

### ⚙ Requirements

- [CMake](https://cmake.org/)
  - Add this to your `PATH`
- [DKUtil](https://github.com/gottyduke/DKUtil)
  - Used for logging primarily; Init & update with git submodule
- [SFSE](https://github.com/ianpatt/sfse)
  - Init & update with git submodule
- [PowerShell](https://github.com/PowerShell/PowerShell/releases/latest)
  - Runs scripts which automate building
- [Vcpkg](https://github.com/microsoft/vcpkg)
  - Handles non-submodule dependency packages
- [Visual Studio Community 2022](https://visualstudio.microsoft.com/)
  - Desktop development with C++. **Note that VSCode will not build properly at this time.**
- [Starfield Steam Distribution](#-deployment)
  - Add the environment variable `SFPath` with the value as the path to the game installation

### 💻 Register Visual Studio Community 2022 as a Generator

- Open `x64 Native Tools Command Prompt`
- Run `cmake`
- Close the cmd window

### 🔨 Building

To build from source (unrecommended):

```
git clone https://github.com/IanE-Official/rehash-sfse-asi-loader.git sfse-asi-loader
cd sfse-asi-loader
git submodule init
git submodule update
cd extern/vcpkg
./bootstrap-vcpkg.bat
vcpkg integrate install
cd ..
cd ..
.\build-release.ps1
```

> If you are building for a Starfield **_other than the latest_**, use `git clone https://github.com/IanE-Official/rehash-sfse-asi-loader.git --branch {version} sfse-asi-loader`
> where {version} is set to the newest version of starfield you are trying to build for (currently 1.12.32).

### 📦 Deployment

Automated steps in Build-release.ps1 will automatically handle deployment.

### ➕ DKUtil addon

This project bundles [DKUtil](https://github.com/gottyduke/DKUtil).

## 📖 License

[MIT LICENSE with requirment of credit and restrictions on packaging DLLs directly with Mods.](LICENSE)

## Security

See [SECURITY.md](SECURITY.md)

## ❓ Credits

- [Doodlez's original Mod](https://www.nexusmods.com/starfield/mods/857) which this was forked from.
- [Ryan for his commonLibSSE code](https://github.com/Ryan-rsm-McKenzie/CommonLibSSE) which was referenced in DKUtil.
- [ianpatt's starfield script extender](https://github.com/ianpatt/sfse).
- [Original plugin template](https://github.com/gottyduke/PluginTemplate)
