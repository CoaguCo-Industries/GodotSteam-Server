# GodotSteam Server for GDNative
An open-source and fully functional Steamworks SDK / API server module and plug-in for the Godot Game Engine (version 3.x). For the Windows, Linux, and Mac platforms.

Additional flavors include:
- [Godot 2.x](https://github.com/CoaguCo-Industries/GodotSteam/tree/godot2)
- [Godot 3.x](https://github.com/CoaguCo-Industries/GodotSteam/tree/master)
- [Godot 4.x](https://github.com/CoaguCo-Industries/GodotSteam/tree/godot4)
- [GDExtension](https://github.com/CoaguCo-Industries/GodotSteam/tree/gdextension)
- [GDNative](https://github.com/CoaguCo-Industries/GodotSteam/tree/gdnative)
- [Server 3.x](https://github.com/CoaguCo-Industries/GodotSteam-Server/tree/godot3)
- [Server 4.x](https://github.com/CoaguCo-Industries/GodotSteam-Server/tree/godot4)
- [Server GDExtension](https://github.com/CoaguCo-Industries/GodotSteam-Server/tree/gdextension)

Documentation
----------
[Documentation is available here](https://godotsteam.com/).

Feel free to chat with us about GodotSteam on the [CoaguCo Discord server](https://discord.gg/SJRSq6K).

Current Build
----------
You can [download pre-compiled versions _(currently v3.0.1)_ of this repo here](https://github.com/CoaguCo-Industries/GodotSteam-Server/releases).

**Version 3.0.1 Changes**
- Changed: updated included Steam server script
- Changed: how initialization functions work, passing empty string now uses default IP (expected behavior)
- Fixed: incorrect verbal message from `serverInitEx`

**Version 3.0 Changes**
- Added: missing server functions from steam_gameserver.h
- Added: missing enums for server modes
- Added: in-editor documentation
- Changed: various improvements under-the-hood
- Changed: reorganized some constants
- Removed: unused enums, signals, functions
- Removed: unnecessary classes that are not part of the server build

[You can read more change-logs here](https://godotsteam.com/changelog/server_gdnative/).

Known Issues
----------
- The GDNative version does not allow for default arguments in functions, thus some functions may have odd behaviors.  If you are using this version of GodotSteam you are required to pass any argument that has a default in the module version. Also, there are no enums in the GDNative version due to how it is structured.
- The function `setRichPresence` when used on Windows will occasionally send the key as the value. This behavior does not happen on Linux nor OSX; it also doesn't exist in any versions of the module nor GDExtension.  In which case, please check your rich presence is set correctly by reading the rich presence back when using Windows and GDNative.
- **Using MinGW causes crashes.** I strong recommend you **do not use MinGW** to compile at this time.

Quick How-To
----------
For complete instructions on how to build the GDNative version of GodotSteam Server from scratch, [please refer to our documentation's 'How-To GDNative' section.](https://godotsteam.com/howto/gdnative/)  It will have the most up-to-date information.

Alternatively, you can just [download the pre-compiled versions in our Releases section](https://github.com/CoaguCo-Industries/GodotSteam-Server/releases) or [from the Godot Asset Library](https://godotengine.org/asset-library/asset/2222) and skip compiling it yourself!

Usage
----------
Do not use the GDNative version of GodotSteam with any of the module versions whether it be our pre-compiled versions or ones you compile.  They are not compatible with each other.

When exporting with the GDNative version, please use the normal Godot Engine templates instead of our GodotSteam templates or you will have a lot of issues.

Donate
-------------
Pull-requests are the best way to help the project out but you can also donate through [Github Sponsors](https://github.com/sponsors/Gramps), [Ko-Fi](https://ko-fi.com/grampsgarcia), or [Paypal](https://www.paypal.me/sithlordkyle)!

License
-------------
MIT license
