# Mycopunk-VersionsSpoofer
# Version Spoofer

A Mycopunk MelonLoader mod that allows you to spoof your game's build ID version number.

A MelonLoader mod that allows you to spoof your game's build ID version number.

## 🎯 Features

- **Configurable Build ID Spoofing**: Set any build ID number through MelonLoader preferences
- **Original Build Preservation**: Automatically captures and stores the real build ID for reference
- **Real-time Patching**: Uses Harmony to intercept build ID requests seamlessly
- **Comprehensive Logging**: Displays both original and spoofed build IDs in console
- **Easy Configuration**: Simple preference-based setup

## 📋 Requirements

- [MelonLoader](https://melonwiki.xyz/) (Latest version recommended)
- Game that supports MelonLoader with Il2Cpp
- .NET Framework compatible environment

## 🚀 Installation

1. **Install MelonLoader** on your target game
2. **Download** the latest release from the [Releases](../../releases) page
3. **Extract** the mod DLL to your game's `Mods` folder
4. **Launch** the game to generate configuration files
5. **Configure** your desired build ID (see Configuration section)

## ⚙️ Configuration

The mod creates a configuration category called `VersionSpoofer` with the following setting:

| Setting | Type | Default | Description |
|---------|------|---------|-------------|
| `FakeBuildId` | Integer | `0` | The build ID to report to the game |

### How to Configure:
1. Run the game once to generate the config file
2. Close the game
3. Open MelonLoader preferences (usually found in `UserData/MelonPreferences.cfg`)
4. Find the `[VersionSpoofer]` section
5. Set `FakeBuildId` to your desired build ID number
6. Save and restart the game

## 🔧 How It Works

The mod uses [HarmonyX](https://github.com/BepInEx/HarmonyX) to patch the `Il2Cpp.Online.GetBuildID()` method:

1. **Initialization**: Captures the original build ID before any modifications
2. **Patching**: Intercepts calls to `GetBuildID()` using Harmony prefix patch
3. **Spoofing**: Returns the configured fake build ID instead of the real one
4. **Logging**: Provides detailed console output for verification

## 📝 Example Output

```
[Version_Spoofer] Version Spoofer: OnInitializeMelon called!
[Version_Spoofer] Version Spoofer: Preferences created successfully
[Version_Spoofer] Version Spoofer: Original build ID retrieved successfully
[Version_Spoofer] === Version Spoofer Loaded ===
[Version_Spoofer] Original Game Build ID: 12345678
[Version_Spoofer] Spoofed Build ID: 87654321
[Version_Spoofer] ===============================
```

## 🛠️ Building from Source

### Prerequisites:
- Visual Studio 2019/2022 or JetBrains Rider
- .NET Framework 4.8 or later
- MelonLoader references
- Target game assemblies

### Build Steps:
1. Clone the repository
2. Open the solution in your IDE
3. Restore NuGet packages
4. Add references to your game's assemblies
5. Build the project
6. The compiled DLL will be in `bin/Debug` or `bin/Release`

## ⚠️ Important Notes

- **Use Responsibly**: This mod is for educational and testing purposes
- **Terms of Service**: Ensure compliance with your game's terms of service
- **Online Games**: Be cautious when using with online games that have anti-cheat systems
- **Backup**: Always backup your game saves before using any mods

## 🐛 Troubleshooting

**Mod doesn't load:**
- Ensure MelonLoader is properly installed
- Check that all dependencies are present
- Verify the mod DLL is in the correct `Mods` folder

**Build ID not changing:**
- Check the MelonLoader console for error messages
- Verify your configuration settings are correct
- Ensure the `FakeBuildId` value is set to something other than 0

**Game crashes:**
- Try setting `FakeBuildId` to a more reasonable value
- Check for conflicts with other mods
- Review the MelonLoader logs for error details

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📞 Support

If you encounter any issues or have questions:
- Open an [Issue](../../issues) on GitHub
- Check existing issues for similar problems
- Provide detailed information about your setup and the problem

---

**Author:** SeedOfAnarky  
**Version:** 1.0.0  
**Framework:** MelonLoader
