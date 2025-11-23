## Send to Unreal, Blender 5.1 Alpha

<h1 align="center">Send to Unreal 5.6, Blender 5.1 Alpha</h1>

A simple solution for pushing assets from Blender 5.1 to Unreal Engine 5.6.

Thank you to **Epic Games** for creating this amazing addon, and the fork author **joshequake** for the upkeep of the tools.

|Blender Build|Supported Version|
|-------------|-----------------|
| 5.1+       | UE5.6    |
| 4.0+       | Not specified    |
| 3.6        | Not specified    |


## Setup
Download or clone the repository.
Compress the contents to make a single send2ue5.zip

In Blender Edit → Preferences → Extensions → Install from Disk... send2ue5.zip

In an Unreal Engine Project (each project)
Edit → Plugins → Search “Python” → Check “Enabled” on Python Script Plugin → Restart Editor
Edit → Project Settings → Plugins → Python Script Plugin → Remote Execution
Set the following values:
Enable Remote Execution → Checked
Multicast Group Endpoint → 239.0.0.1:6766
Multicast Bind Address → 0.0.0.0

## Help Contribute
Contributions are encouraged! Find out how you can contribute to this repo in one of the following ways:

* Development
* Documentation
* Testing



