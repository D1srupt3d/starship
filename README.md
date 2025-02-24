# Starship Prompt Configuration

This is a customized configuration for the [Starship](https://starship.rs/) cross-shell prompt. It provides a rich, informative command prompt with various indicators for development tools, system status, and git information.

## Features

### Global Settings
- No blank line between prompts (`add_newline = false`)
- Extended command timeout of 1000ms to prevent warnings
- Custom prompt symbol: "󰆍" in red (#FF0000)

### Prompt Layout
The prompt is organized in a single line with the following components:
```
username @ hostname directory git_info [fill] k8s terraform docker node package memory battery time shell cmd_duration
```

### Development Tools
- **Node.js**: Shows version with 󰎙 icon
- **Package**: Displays version with 󰏗 icon
- **Git Information**:
  - Branch (󰘬 icon)
  - Status (shows modified/staged/etc.)
  - Metrics (added/deleted lines)

### Cloud & Infrastructure
- **Terraform**: Shows version with 󱁢 icon
- **Kubernetes**: Displays context and namespace with 󱃾 icon
- **Docker**: Shows context with 󰡨 icon

### System Information
- **Memory Usage**: RAM usage with 󰍛 icon
- **Battery Status**: 
  - Multiple thresholds (100%, 50%, 20%)
  - Different icons for various states (🔋, ⚡️, 💀, ⌛, !)
  - Color-coded (green → yellow → red)

### Time & Performance
- **Time**: Shows current time in HH:MM format
- **Command Duration**: Shows execution time for commands taking >500ms

### Directory
- Shows current directory path
- Truncates to 4 folders
- Read-only indicator (󰌾)
- Does not truncate to git repo root

### Shell Indicator
- Fish: 🐟
- PowerShell: ⚡
- Unknown: ❓

## Style Customizations
- Username: Bold blue
- Hostname: Bold red
- Directory: Bold cyan
- Git branch: Bold purple
- Git status: Bold red
- Time: Custom purple (#A575F4)
- Fill characters: Bold black "─"

## Dependencies
- Requires [Starship](https://starship.rs/) to be installed
- Requires a [Nerd Font](https://www.nerdfonts.com/) for the custom icons

## Installation
1. Install Starship: `curl -sS https://starship.rs/install.sh | sh`
2. Place this configuration at `~/.config/starship.toml`
3. Add the following to your shell's RC file (e.g., `.zshrc`, `.bashrc`):
   ```bash
   eval "$(starship init bash)"  # or zsh/fish depending on your shell
   ```

## Notes
- Some icons require a Nerd Font to display correctly
- The prompt is optimized for performance with a 1000ms command timeout
- Git metrics are enabled by default
- Memory usage monitoring is always active
