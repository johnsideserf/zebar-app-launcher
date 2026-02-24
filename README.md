# App Launcher for Zebar

A configurable app launcher widget for [Zebar](https://github.com/glzr-io/zebar). Adds a waffle-menu button that opens a dropdown to launch your favorite apps.

![Embedded mode — docked in bar](./preview-docked.png)

## Features

- **Two layout modes** — embed flush in your bar or float standalone
- **Configurable apps** — add any app with a name, Nerd Font icon, and command
- **Themeable** — all colors customizable via `config.json`
- **Click-outside & Escape to close** — dropdown dismisses naturally
- **Dynamic window resizing** — embedded mode keeps a tiny footprint when closed, expands on click

## Installation

1. Copy the `app-launcher` folder to `~/.glzr/zebar/`
2. Add a startup config to `~/.glzr/zebar/settings.json`:

```json
{
  "startupConfigs": [
    {
      "pack": "app-launcher",
      "widget": "app-launcher",
      "preset": "floating"
    }
  ]
}
```

3. Restart Zebar

## Presets

| Preset | Description |
|--------|-------------|
| `floating` | Standalone button below the bar (default) |
| `embedded` | Flush with the bar's top-left corner |

Change the `"preset"` value in `settings.json` to switch modes.

When using `embedded`, also set `"mode": "embedded"` in `config.json` so the widget styles and window resizing adjust accordingly.

## Configuration

All settings live in a single `config.json` file:

```json
{
  "mode": "floating",
  "theme": {
    "background": "rgba(13 14 22 / 92%)",
    "foreground": "#a9b1d6",
    "accent": "#7aa2f7",
    "hover": "rgba(122 162 247 / 18%)",
    "active": "rgba(122 162 247 / 28%)",
    "border": "rgba(122 162 247 / 15%)"
  },
  "apps": [
    { "name": "Terminal", "icon": "nf nf-md-console", "command": "wt.exe" },
    { "name": "Browser", "icon": "nf nf-md-web", "command": "msedge.exe" },
    { "name": "Explorer", "icon": "nf nf-md-folder", "command": "explorer.exe" },
    { "name": "Notepad", "icon": "nf nf-md-note_text", "command": "notepad.exe" }
  ]
}
```

### Mode

- `"floating"` — standalone button with rounded corners and border
- `"embedded"` — flush button that blends into the bar (use with the `embedded` preset)

### Theme

All CSS color values. Applied at runtime, with sensible defaults as fallback.

| Key | Controls |
|-----|----------|
| `background` | Dropdown and button background |
| `foreground` | Text color |
| `accent` | Icon color and active borders |
| `hover` | Hover highlight |
| `active` | Active/pressed highlight |
| `border` | Button and dropdown border |

### Apps

Each entry in the `apps` array:

| Field | Description |
|-------|-------------|
| `name` | Display label in the dropdown |
| `icon` | [Nerd Font](https://www.nerdfonts.com/cheat-sheet) class (e.g. `nf nf-md-console`) |
| `command` | Executable name or path. Names in `PATH` work directly (e.g. `wt.exe`). For apps not in PATH, use the full path |

## Screenshots

| Floating (closed) | Floating (open) |
|---|---|
| ![](./preview-floating-unclicked.png) | ![](./preview-floating-clicked.png) |

| Embedded (closed) | Embedded (open) |
|---|---|
| ![](./preview-unclicked.png) | ![](./preview-docked.png) |

## Requirements

- [Zebar](https://github.com/glzr-io/zebar) v3.0+
- Windows 10/11

## License

MIT
