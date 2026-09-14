```markdown
# Default Apps

View and change your XDG default applications from Noctalia: web browser, email, calendar, file manager, music/video players, image viewer, text editor, PDF viewer, archive manager, word processor, and BitTorrent client. Changes are written through `xdg-mime`, so they apply desktop-wide, the same as changing defaults in a full desktop environment.

| | |
|---|---|
| **Plugin** | `Thaer99ob/default-apps` |
| **Panel** | `Thaer99ob/default-apps:manager` |
| **Bar widget** | `Thaer99ob/default-apps:current` |
| **Launcher** | `/apps` |

## Requirements

- `xdg-utils` (provides `xdg-mime`)

## Usage

### Panel

Open the manager panel from the bar widget, via the Noctalia launcher by typing `/apps`, or with:

```bash
noctalia msg panel-toggle Thaer99ob/default-apps:manager
```

Each row shows a category, its current default, and a dropdown of installed applications that declare the relevant MIME type(s). Select your preferred applications from the dropdowns and click the **Apply** button to save all changes at once. Closing the panel without clicking Apply discards your picks.

### Bar widget

Add the **Default Apps** widget to a bar from the widget picker. It shows a clean shortcut icon on your bar. Hovering over the widget displays your current default web browser in a tooltip, and clicking it opens the manager panel.

### Launcher

Open the Noctalia global search or provider menu and type `/apps`. Selecting the provider immediately opens the configuration panel.

## Settings

This plugin declares no settings; panel placement is configured under **Settings → Plugins** like any other panel.

## Notes

- Defaults are stored by `xdg-mime` in `~/.config/mimeapps.list`; the plugin keeps no state of its own.
- Candidate apps come from desktop entries in `~/.local/share/applications`, `/usr/local/share/applications`, `/usr/share/applications`, and Flatpak exports. Apps whose desktop file does not declare the relevant MIME type (or Category, where used) do not appear for that category.
