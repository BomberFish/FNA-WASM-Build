# FNA-WASM-Build


[![WASM Build (FNA)](https://github.com/r58Playz/FNA-WASM-Build/actions/workflows/WASM.FNA.yml/badge.svg)](https://github.com/r58Playz/FNA-WASM-Build/actions/workflows/WASM.FNA.yml)

This repo is for automating the build of WebAssembly (WASM) native libraries for [FNA](https://fna-xna.github.io/), including:

* [FNA3D.a](https://github.com/FNA-XNA/FNA3D) - 3D graphics library for FNA.
* [FAudio.a](https://github.com/FNA-XNA/FAudio) - XAudio reimplementation for FNA.
* [SDL2.a](https://github.com/libsdl-org/SDL) - Simple DirectMedia Layer.
* ~[libtheorafile.a](https://github.com/FNA-XNA/Theorafile) - Ogg Theora videos decoder library.~ (not yet implemented)

There is currently just one workflow:

1.  **WASM Build (FNA)**.  

## Patches
This fork contains a few patches:
- `SDL2.patch` removes the calls to `EM_JS_DEPS` for `stringToUTF8` and `UTF8ToString` as those are runtime functions in Emscripten 3.1.34 which is what .NET 8 uses.
- `FNA3D.patch` adds `-pthread` to the `CFLAGS` so FNA3D is built with WASM threads support.

## Usage

Go to the Actions tab and download the .zip artifact from the latest workflow run.  
See for further details:  https://gist.github.com/TheSpydog/e94c8c23c01615a5a3b2cc1a0857415c
