# i3 Configuration for Chromebook

A highly customized i3 window manager configuration optimized for Chromebook usage on Fedora Linux. Features Numix color scheme, Chromebook-specific key bindings, and productivity enhancements.

## Features

- **Numix Color Theme**: Beautiful orange accent colors throughout the interface
- **Chromebook Optimized**: Custom key bindings for missing keys and hardware limitations
- **Multilingual Support**: Easy switching between English and Spanish keyboards
- **Productivity Workspaces**: Organized workspaces with auto-assignment for applications
- **Screen Rotation**: Support for tablet mode and presentation orientations
- **Visual Feedback**: Notifications for volume, brightness, and system changes

## Screenshots

Soon

The configuration provides a clean, (vanilla) modern interface with:
- Top-positioned status bar with workspace indicators
- Numix orange highlights for focused windows
- Borderless windows for maximum screen real estate
- Organized workspace names for easy navigation

## Installation

### Required Packages (Fedora)

```bash
sudo dnf install brightnessctl libnotify thunar pavucontrol
```

### Optional Packages

```bash
sudo dnf install alacritty blueman scrot picom rofi clipman dunst redshift blueman-applet
```

### Setup

1. Clone this repository:
   ```bash
   git clone https://github.com/LoboGuardian/i3.config.git
   cd i3.config
   ```

2. Backup your existing config:
   ```bash
   cp ~/.config/i3/config ~/.config/i3/config.backup
   ```

3. Install the new config:
   ```bash
   cp config ~/.config/i3/config
   ```

4. Reload i3:
   ```bash
   i3-msg reload
   ```

## Key Bindings

### Application Launchers
- `Super + Return`: Terminal
- `Super + b`: Firefox
- `Super + Shift + b`: Microsoft Edge
- `Super + c`: Zed editor
- `Super + Shift + f`: File manager (Thunar)
- `Super + d`: Application launcher (dmenu)

### Function Keys (Chromebook Specific)
- `Super + F1`: Terminal
- `Super + F2`: Firefox
- `Super + F3`: Microsoft Edge
- `Super + F4`: Zed editor
- `Super + F5`: File manager
- `Super + F6`: Audio control
- `Super + F7`: Application launcher
- `Super + F8/F9`: Lock screen
- `Super + F8/F9`: Switch to workspace 9
- `Super + F10`: Power menu
- `Super + F11`: None
- `Super + F12`: None

### Workspace Management
- `Super + 1-0`: Switch to workspace 1-10
- `Super + Shift + 1-0`: Move window to workspace 1-10
- `Super + Tab`: Switch to last workspace
- `Super + Ctrl + Left/Right`: Previous/Next workspace

### Window Management
- `Super + h/j/k/l`: Navigate windows (vim-style)
- `Super + Shift + h/j/k/l`: Move windows
- `Super + f`: Fullscreen toggle
- `Super + Shift + Space`: Toggle floating
- `Super + Space`: Focus floating/tiling

### Audio & Brightness
- `Super + =`: Volume up
- `Super + Shift + -`: Volume down
- `Super + Shift + =`: Mute toggle
- `Super + [`: Brightness down
- `Super + ]`: Brightness up

### Language Switching
- `Super + i`: Language selection mode
- `Super + Shift + i`: Quick toggle English/Spanish

### Screen Rotation
- `Super + Ctrl + o`: Rotation menu
- `Super + Ctrl + r`: Normal orientation
- `Super + Ctrl + Shift + r`: Rotate left

### System Controls
- `Super + Pause`: Power menu (lock, suspend, reboot, etc.)
- `Super + r`: Resize mode
- `Super + Shift + q`: Kill window
- `Super + Shift + r`: Restart i3

## Workspace Layout

1. **Terminal**: Command line work
2. **Firefox**: Primary web browser
3. **Edge**: Secondary browser
4. **Code**: Development with Zed editor
5. **Files**: File management
6. **Media**: Spotify, VLC, multimedia
7. **Chat**: Discord, Slack, Telegram
8. **Work**: General productivity applications
9. **Docs**: LibreOffice, document viewers
10. **Settings**: System configuration tools

## Customization

### Colors
The Numix color scheme can be modified by editing these variables in the config:
```bash
set $numix_orange #f9703e
set $numix_red #d64937
set $numix_dark_gray #2d2d2d
# ... etc
```

### Adding Applications
To auto-assign applications to workspaces, add lines like:
```bash
assign [class="ApplicationName"] $ws1
```

### Floating Windows
To make applications float by default:
```bash
for_window [class="ApplicationName"] floating enable
```

## Hardware Compatibility

### Tested Hardware
- Chromebook
- Fedora Linux

### Display Output
The configuration assumes the display is named `eDP-1`. If your display has a different name, update the rotation commands:
```bash
xrandr --listmonitors  # Check your display name
```

## Troubleshooting

### Volume/Brightness Not Working
Ensure the required packages are installed:
```bash
sudo dnf install brightnessctl pavucontrol
```

### Notifications Not Showing
Install the notification daemon:
```bash
sudo dnf install libnotify dunst
```

### Key Bindings Not Working
Check for conflicts with existing shortcuts and ensure your keyboard layout is correctly set.

## Contributing

Feel free to submit issues and enhancement requests. Pull requests are welcome for:
- Additional hardware compatibility
- New productivity features
- Bug fixes
- Documentation improvements

## License

This configuration is provided as-is under the MIT License. Feel free to modify and distribute.

## Acknowledgments

- i3 window manager community
- Numix theme developers
- Fedora Linux project

---

**Note**: This configuration is specifically optimized for Chromebook hardware limitations and may require adjustments for other devices.
