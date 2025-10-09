# TheOne Localization Editor

**Comprehensive localization tools for Unity with OpenAI translation support**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Unity](https://img.shields.io/badge/Unity-2021.3%2B-blue.svg)](https://unity3d.com/get-unity/download)
[![UPM](https://img.shields.io/badge/UPM-Registry-green.svg)](https://upm.the1studio.org)

## Overview

This package provides powerful localization tools that integrate seamlessly with Unity's Localization package. Features include automatic TextMeshPro setup, key extraction from prefabs, AI-powered translation using OpenAI, and blueprint localization support.

## Features

- **Auto Localization Setup**: Automatically add LocalizeStringEvent components to TextMeshPro objects
- **Key Extraction**: Extract text from prefabs and scenes to create localization keys
- **AI Translation**: Translate keys to multiple languages using OpenAI API
- **Blueprint Localization**: Localize data-driven content from blueprint/scriptable objects
- **Batch Operations**: Process multiple prefabs and scenes at once
- **Build Processor**: Ensure localization is set up correctly before builds
- **Menu Integration**: Easy access via `TheOne → Localization` menu

## Requirements

- Unity 2021.3 or higher
- Addressables Package 1.19.0+
- Cysharp.UniTask 2.3.0+
- Unity Localization 1.3.0+
- TextMeshPro 3.0.0+
- TheOne Extensions 1.0.0+
- TheOne Tool Core 1.0.0+

## Installation

### Via UPM Registry (Recommended)

Add to your `Packages/manifest.json`:

```json
{
  "dependencies": {
    "com.theone.tool.localization": "1.0.0"
  },
  "scopedRegistries": [
    {
      "name": "TheOne Studio",
      "url": "https://upm.the1studio.org",
      "scopes": ["com.theone"]
    }
  ]
}
```

### Via Git URL

```json
{
  "dependencies": {
    "com.theone.tool.localization": "https://github.com/The1Studio/UITemplateLocalization.git"
  }
}
```

## Usage

### Auto Localization Setup

**Menu**: `TheOne → Localization → Auto Localization`

1. Select prefabs or scenes in Project window
2. Right-click → `TheOne → Auto Localization`
3. Tool automatically adds LocalizeStringEvent to all TextMeshPro components

### Extract Localization Keys

**Menu**: `TheOne → Localization → TMP Localization`

1. Open the TMP Localization window
2. Click "Extract Keys" to scan all prefabs and scenes
3. Keys are extracted and added to your string tables

### AI-Powered Translation

**Menu**: `TheOne → Localization → Auto Translation Tool`

1. Configure OpenAI API key in settings
2. Select source language and target languages
3. Click "Translate All" to auto-translate keys
4. Review and adjust translations as needed

### Blueprint Localization

Localize blueprint/scriptable object data:

```csharp
// Your blueprint class
[System.Serializable]
public class ItemBlueprint
{
    [LocalizeKey("ItemNames")]
    public string itemName;
    
    [LocalizeKey("ItemDescriptions")]
    public string description;
}
```

## Configuration

### AutoLocalizationConfig

Configure auto-localization behavior via `Assets/Create → TheOne → AutoLocalizationConfig`:

- Default string table
- Excluded prefab paths
- Auto-build validation
- Custom localization rules

### OpenAI Integration

Set up OpenAI API for translations:

1. Get API key from OpenAI
2. Store in `TheOne → Configuration And Tools → Localization`
3. Configure translation model and parameters

## API Reference

### AutoLocalizationManager

Main service for auto-localization operations:

```csharp
using TheOne.Tool.Localization;

// Setup localization on a GameObject
AutoLocalizationManager.SetupLocalization(gameObject);

// Extract keys from prefabs
AutoLocalizationManager.ExtractKeysFromPrefabs();
```

### TMPLocalization

Window for managing TextMeshPro localization.

### AutoTranslationTool

AI-powered translation using OpenAI API.

## Best Practices

1. **String Table Organization**: Use separate tables for different content types (UI, Items, Dialogue)
2. **Key Naming**: Use descriptive, hierarchical keys (e.g., `UI.Buttons.Start`, `Items.Weapons.Sword`)
3. **Review Translations**: Always review AI translations before shipping
4. **Blueprint Support**: Use LocalizeKey attribute for data-driven localization
5. **Build Validation**: Enable auto-check in build processor

## Workflow Example

```
1. Design UI with English text in TextMeshPro
2. Run Auto Localization to add LocalizeStringEvent
3. Extract keys using TMP Localization tool
4. Use Auto Translation to generate translations
5. Review and adjust translations
6. Test in different languages
7. Build with validation enabled
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## About The One Studio

**The One Studio** is a mobile game development company specializing in hypercasual and casual games.

- Website: [https://the1studio.com](https://the1studio.com)
- Email: contact@the1studio.com

## Related Packages

- [UITemplate](https://github.com/The1Studio/UITemplate) - Complete Unity UI framework
- [TheOne Template Editor](https://github.com/The1Studio/UITemplateEditorCore) - Core editor tools
- [Unity Optimization Tools](https://github.com/The1Studio/UnityOptimizationTools) - Project optimization
- [TheOne LocalData](https://github.com/The1Studio/UITemplateLocalData) - Local data management

## Support

- [GitHub Issues](https://github.com/The1Studio/UITemplateLocalization/issues)
- [Documentation](https://github.com/The1Studio/UITemplateLocalization#readme)

---

<div align="center">

Made with ❤️ by **The One Studio**

</div>
