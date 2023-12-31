# GodotSteam Server for Godot 3.x
An open-source and fully functional Steamworks SDK / API server module and plug-in for the Godot Game Engine (version 3.x). For the Windows, Linux, and Mac platforms. 

Additional flavors include:
- [Godot 2.x](https://github.com/CoaguCo-Industries/GodotSteam/tree/godot2)
- [Godot 3.x](https://github.com/CoaguCo-Industries/GodotSteam/tree/master)
- [Godot 4.x](https://github.com/CoaguCo-Industries/GodotSteam/tree/godot4)
- [GDExtension](https://github.com/CoaguCo-Industries/GodotSteam/tree/gdextension)
- [GDNative](https://github.com/CoaguCo-Industries/GodotSteam/tree/gdnative)
- [Server 4.x](https://github.com/CoaguCo-Industries/GodotSteam-Server/tree/godot4)
- [Server GDExtension](https://github.com/CoaguCo-Industries/GodotSteam-Server/tree/gdextension)
- [Server GDNative](https://github.com/CoaguCo-Industries/GodotSteam-Server/tree/gdnative)

Documentation
---
[Documentation is available here](https://godotsteam.com/). You can also check out the Search Help section inside Godot Engine after compiling it with GodotSteam Server.

Feel free to chat with us about GodotSteam on the [CoaguCo Discord server](https://discord.gg/SJRSq6K).

Current Build
---
You can [download pre-compiled versions _(currently v3.0)_ of this repo here](https://github.com/CoaguCo-Industries/GodotSteam-Server/releases).

**Version 3.0.1 Changes**
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

[You can read more change-logs here](https://godotsteam.com/changelog/server3/).

Known Issues
---
- **Using MinGW causes crashes.** I strong recommend you **do not use MinGW** to compile at this time.

"Quick" How-To
---
For complete instructions on how to build the Godot 3.x version of GodotSteam Server from scratch, [please refer to our documentation's 'How-To Servers' section.](https://godotsteam.com/howto/server/) It will have the most up-to-date information.

Alternatively, you can just [download the pre-compiled versions in our Releases section](https://github.com/CoaguCo-Industries/GodotSteam-Server/releases) and skip compiling it yourself!

Donate
---
Pull-requests are the best way to help the project out but you can also donate through [Github Sponsors](https://github.com/sponsors/Gramps), [Ko-Fi](https://ko-fi.com/grampsgarcia) or [Paypal](https://www.paypal.me/sithlordkyle)!

License
---
MIT license
