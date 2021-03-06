# audica-hook

This is a significantly stripped down version of the [beatsaber-hook](https://github.com/sc2ad/beatsaber-hook) library for Audica on the Quest.

## Acknowledgements

This wouldn't have been possible without a few people who have helped immensely.

- [emulamer](https://github.com/emulamer/): Provided support, tested, and in general just a great person to talk to. This wouldn't exist at all if not for him motivating me to keep working.
- [jakibaki](https://github.com/jakibaki/): Created the library that actually supports all of the mod loading, as well as a lot of support when developing (and bearing with my annoying questions).

Right now this loads mods (`.so` files) from `/sdcard/Android/data/com.harmonixmusic.kata/files/mods/`

Uses [Android Inline Hook](https://github.com/ele7enxxh/Android-Inline-Hook) + some macros for magic

Copy-paste `libmain.so` and `libmodloader.so` built from `QuestLoader` to the same directory as `libil2cpp.so`, which should be: `/data/app/com.harmonixmusic.kata/lib/arm64-v8a/`

Alternatively, check the releases page for the Audica `songloader` mod, and the `libmain.so` and `libmodloader.so` files.

Follow [Frida Without Root](https://koz.io/using-frida-on-android-without-root/) to learn how to inject the modloader-library into the apk (with the so built from this instead of frida)

The function offsets (as well as infos about the structs) can be obtained with [Il2CppDumper](https://github.com/sc2ad/Il2CppDumper)

```ndk
ndk-build NDK_PROJECT_PATH=. APP_BUILD_SCRIPT=./Android.mk NDK_APPLICATION_MK=./Application.mk
```
