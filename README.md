# StyleCraft Documentation

## Table of Contents
- [Introduction](#introduction)
- [Getting Started](#getting-started)
- [Core Concepts](#core-concepts)
- [Text Formatting](#text-formatting)
- [Presets System](#presets-system)
- [Assets Management](#assets-management)
- [Blueprint Reference](#blueprint-reference)
- [Best Practices](#best-practices)
- [Troubleshooting](#troubleshooting)

## Introduction
StyleCraft is a text formatting and styling system for Unreal Engine that provides rich text formatting capabilities through a flexible and intuitive syntax. It acts as a translator between user-friendly markup and Unreal Engine's native rich text system.

### Core Features
- Intuitive text styling syntax
- Preset system for quick styling
- Custom fonts and materials support
- Color management system
- Full Blueprint integration

## Getting Started

### Installation
1. Add the plugin to your project
2. Enable it in the Plugins menu
3. Restart the editor
4. Configure basic settings in Project Settings > Plugins > StyleCraft

### Basic Usage
```
// Simple color formatting
{color="red"}This text will be red{/}

// Using presets
@title Main Title Text

// Multiple attributes
{color="blue" size="24"}Large blue text{/}
```

## Core Concepts

### How StyleCraft Works
StyleCraft processes your text through several stages:

```
Input: {color="red"}Hello{/}
↓
Processing: Converts to <b color="red">Hello</>
↓
Output: Rendered as red text
```

### Syntax Elements
- **Markers**: Default `{` and `}` for style blocks
- **Attributes**: `name="value"` format
- **Terminator**: Default `{/}` to end style blocks
- **Preset Prefix**: `@` for preset styles

## Text Formatting

### Available Attributes
| Attribute | Description | Example |
|-----------|-------------|---------|
| color | Text color (name or hex) | `color="red"` or `color="#FF0000"` |
| size | Font size | `size="24"` |
| font | Font family | `font="Arial"` |
| case | Text case transformation | `case="upper"` |
| opacity | Text transparency | `opacity="0.5"` |
| material | Material application | `material="MyMaterial"` |

### Color System
```
// Named colors
{color="red"}Red text{/}
{color="blue"}Blue text{/}

// Hex colors
{color="#FF0000"}Custom red{/}
```

### Text Transformations
```
// Uppercase
{case="upper"}This will be uppercase{/}

// Lowercase
{case="lower"}THIS WILL BE LOWERCASE{/}
```

## Presets System

### How Presets Work
```
You write: @title Hello World
↓
StyleCraft expands to: {color="blue" size="24"}Hello World{/}
↓
Processes to: <b color="blue" size="24">Hello World</>
```

### Configuring Presets
```cpp
// In project settings
Presets:
    "title": 
        Value: "{color=\"blue\" size=\"24\"}"
        Terminator: "{/}"
        bRequiresPrefix: true

    "warning":
        Value: "{color=\"red\" size=\"16\"}"
        Terminator: "{/}"
        bRequiresPrefix: true
```

## Assets Management

### Font Collections
1. Create a Font Collection asset
2. Add font entries with optional aliases
3. Reference in your styles using the font name or alias

### Material Collections
1. Create a Material Collection asset
2. Add materials with identifiers
3. Reference in your styles using the material name

## Best Practices

### Style Organization
1. Group related styles in presets
2. Use consistent naming conventions
3. Document custom styles

### Common Patterns
```
// Headers
@title Main Title
@subtitle Section Subtitle

// Messages
@warning Warning Message
@error Error Text
```

## Troubleshooting

### Common Issues
1. **Styles not applying**
   - Check syntax for proper quotes
   - Verify marker configuration
   - Validate preset definitions

2. **Fonts not loading**
   - Check font collection setup, ensure you use the correct name or alias
   - Verify font references
   - Ensure proper font asset setup

3. **Presets not working**
   - Verify prefix usage
   - Check preset configuration
   - Confirm terminator settings

### Debug Tips
1. Check the output log for formatting errors
2. Validate text format before processing
3. Test styles individually before combining

---

For more information or support:
- Review project settings
- Contact support channels
