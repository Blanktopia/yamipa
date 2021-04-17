# Yet Another Minecraft Image Placing Addon
[![Tests](https://github.com/josemmo/yamipa/workflows/Tests/badge.svg)](https://github.com/josemmo/yamipa/actions)
[![Latest Version](https://img.shields.io/github/v/release/josemmo/yamipa)](https://github.com/josemmo/yamipa/releases/latest)
![Minecraft Version](https://img.shields.io/badge/minecraft-%3E%3D1.16-blueviolet)
[![bStats Players](https://img.shields.io/bstats/players/10243)](https://bstats.org/plugin/bukkit/Yamipa/10243)
[![License](https://img.shields.io/github/license/josemmo/yamipa)](LICENSE)

Yamipa is an Spigot plugin that allows you to place images on any surface in your Minecraft server.
It is designed with performance and compatibility in mind, so even the most low-specs servers should be able to run it.

<p align="center">
    <a href="https://i.imgur.com/9rzeKFS.mp4"><img alt="Placing and removing image" src="screenshots/demo.gif" width="250"></a>
    <a href="screenshots/sample-1.jpg"><img alt="Sample Screenshot" src="screenshots/sample-1.jpg" width="250"></a>
    <a href="screenshots/sample-2.jpg"><img alt="Sample Screenshot" src="screenshots/sample-2.jpg" width="250"></a>
</p>
<h3 align="center">· · ·</h3>

## Installation
Download the JAR file for the [latest release](https://github.com/josemmo/yamipa/releases/latest) and copy it to the
"plugins" directory of your Minecraft server as you'll do with any other plugin. That's it!

### Requirements
Before installing Yamipa make sure you meet the following requirements:

- CraftBukkit, Spigot or PaperMC v1.16.x
- [ProtocolLib v4.x.x](https://www.spigotmc.org/resources/protocollib.1997/)

---

## Configuration
Yamipa is ready-to-go right out of the box. By default, it creates the following files and directories under the
`plugins/YamipaPlugin` directory:

- `cache`: A directory containing cached images to speed up the rendering process. You shouldn't modify its contents.
- `images`: **This is the directory where you put the image files** you want to place in your Minecraft world.
- `images.dat`: A file holding the list and properties (e.g. coordinates) of all placed images in your server. You
shouldn't modify its contents.

You can change the default path of these files by creating a `config.yml` file in the plugin configuration directory:
```yaml
verbose: false         # Set to "true" to enable more verbose logging
images-path: images    # Path to images directory
cache-path: cache      # Path to cache directory
data-path: images.dat  # Path to placed images database file
```

This library uses bStats to anonymously report the number of installs. If you don't like this, feel free to
disable it at any time by adding `enabled: false` to the
[bStats configuration file](https://bstats.org/getting-started#:~:text=Disabling%20bStats) (it's ok, no hard feelings).

---

## Usage
This plugin adds the following commands:

- `/image describe`: Show detailed information about a placed image.
- `/image download <url> <filename>`: Download an image from a URL and place it in the images directory.
- `/image list [<page>]`: List all available files in the images directory.
- `/image place <filename> <width> [<height>]`: Place an image of size `width`x`height` blocks.
- `/image remove`: Remove a placed image from the world without deleting the image file.
- `/image remove <radius> [<placed-by>]`: Remove all placed images in a radius of `radius` blocks around the player.

---

## Permissions
If you want more granular control over the players who can use a particular set of commands, permissions are the way to go!

Yamipa defines the following permissions, each one corresponding to the command with the same name:

- `yamipa.describe`
- `yamipa.download`
- `yamipa.list`
- `yamipa.place`
- `yamipa.remove`
- `yamipa.remove.radius`

By default, only server OPs have all permissions granted. You can change this by using a permission plugin,
such as [LuckPerms](https://luckperms.net/) or [GroupManager](https://elgarl.github.io/GroupManager/).

Both these plugins have been tested to work with Yamipa, although any similar one should work just fine.

---

## License
Yamipa is licensed under the [MIT License](LICENSE) and includes third-party software licensed under
the MIT License and the [GPLv3 License](https://www.gnu.org/licenses/gpl-3.0.html).
