The old version uses `<h1 align="center">` for the centered title — that's intentional GitHub markdown style, it's valid and renders nicely. Here's the updated version keeping that pattern:

```markdown
## Send to Unreal, Blender 5.1 / UE 5.6
<h1 align="center">Send to Unreal 5.6, Blender 5.1</h1>

A patched fork for pushing assets from Blender 5.1 to Unreal Engine 5.6 on Linux.

Thank you to **Epic Games** for creating this amazing addon, and the fork author **joshequake** for the upkeep of the tools.

|Blender Build|Supported Version|
|-------------|-----------------|
| 5.1+        | UE5.6           |

## Why This Fork Exists — The Python 3.13 Docstring Bug

Python 3.13 changed how `__doc__` strings are normalized, which broke the docstring removal logic in `rpc/factory.py` when serializing functions to send to Unreal. This fork replaces the broken `str.replace()` call with a regex that handles indentation correctly. Without this fix you will see `SyntaxError: expected 'else' after 'if' expression`.

## Setup

Clone the repository.

Compress the contents to make a single `send2ue.zip`
(Important: naming the zip anything other than `send2ue.zip` caused an error.)

If you download a zip of the repo, there may be an extra parent folder. You may need to unzip, enter the folder, then change the second folder name to `send2ue` and zip that — that is your addon.

In Blender: Edit → Preferences → Extensions → Install from Disk... `send2ue.zip`

In each Unreal Engine project:

Edit → Plugins → Search "Python" → Check "Enabled" on Python Script Plugin

Restart the editor.

Edit → Project Settings → Plugins → Python → Remote Execution

Set the following values:

Enable Remote Execution → Checked
Multicast Group Endpoint → 239.0.0.1:6766
Multicast Bind Address → 0.0.0.0

> Multicast TTL of 1 is recommended to keep traffic on your local network segment.

In Blender: Edit → Preferences → Add-ons → send2ue

Set the following values:

Multicast Group Endpoint → 239.0.0.1:6766
Command Endpoint → 0.0.0.0:6776

If Blender's console prompts you to disable the Interchange FBX importer, run the command it provides in the Unreal Output Log console.

## Tested On

- Pop OS Linux
- Blender 5.1 (Python 3.13)
- Unreal Engine 5.6.1
```
