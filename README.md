# Starship Prompt Configuration

This is a customized configuration for the [Starship](https://starship.rs/) cross-shell prompt. It provides a rich, informative command prompt with various indicators for development tools, system status, and git information.

## Features

### Global Settings

- No blank line between prompts (`add_newline = false`)
- Extended command timeout of 1000ms to prevent warnings
- Custom prompt symbol: `\uf40d` → 󰆍 in red (#FF0000)

### Prompt Layout

The prompt is organized in a single line with the following components:

```text
username @ hostname directory git_info [fill] k8s terraform docker node package memory battery time shell cmd_duration
```

### Development Tools

- **Node.js**: Shows version with icon `\ue718` → 󰎙
- **Package**: Displays version with icon `\uf487` → 󰏗
- **Git Information**:
  - Branch icon: `\uf418` → 󰘬
  - Status (shows modified/staged/etc.)
  - Metrics (added/deleted lines)

### Cloud & Infrastructure

- **Terraform**: Shows version with icon `\uf1c2` → 󱁢
- **Kubernetes**: Displays context and namespace with icon `\uf43e` → 󱃾
- **Docker**: Shows context with icon `\uf308` → 󰡨

### System Information

- **Memory Usage**: RAM usage with icon `\uf85a` → 󰍛
- **Battery Status**:
  - Multiple thresholds (100%, 50%, 20%)
  - Different icons for various states:
    - Full: 🔋
    - Charging: ⚡️
    - Discharging: 💀
    - Unknown: ⌛
    - Empty: !
  - Color-coded (green → yellow → red)

### Time & Performance

- **Time**: Shows current time in HH:MM format
- **Command Duration**: Shows execution time for commands taking >500ms

### Directory

- Shows current directory path
- Truncates to 4 folders
- Read-only indicator: `\uf43e` → 󰌾
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
  - Recommended: [FiraCode Nerd Font](https://github.com/ryanoasis/nerd-fonts/tree/master/patched-fonts/FiraCode)

## Nerd Font Icons Quick Reference

| Icon Purpose | Unicode    | Display |
|-------------|------------|---------|
| Prompt      | `\uf40d`   | 󰆍      |
| Node.js     | `\ue718`   | 󰎙      |
| Package     | `\uf487`   | 󰏗      |
| Git Branch  | `\uf418`   | 󰘬      |
| Terraform   | `\uf1c2`   | 󱁢      |
| Kubernetes  | `\uf43e`   | 󱃾      |
| Docker      | `\uf308`   | 󰡨      |
| Memory      | `\uf85a`   | 󰍛      |
| Read-only   | `\uf43e`   | 󰌾      |

## Installation

1. Install Starship: `curl -sS https://starship.rs/install.sh | sh`
2. Install FiraCode Nerd Font:

   ```bash
   # macOS with Homebrew
   brew tap homebrew/cask-fonts
   brew install --cask font-fira-code-nerd-font
   ```

   For other systems, download from [Nerd Fonts releases](https://github.com/ryanoasis/nerd-fonts/releases)
3. Place this configuration at `~/.config/starship.toml`
4. Add the following to your shell's RC file (e.g., `.zshrc`, `.bashrc`):

   ```bash
   eval "$(starship init bash)"  # or zsh/fish depending on your shell
   ```

5. Configure your terminal to use FiraCode Nerd Font

## Notes

- Some icons require a Nerd Font to display correctly
- The prompt is optimized for performance with a 1000ms command timeout
- Git metrics are enabled by default
- Memory usage monitoring is always active
- If icons aren't displaying correctly:
  1. Verify FiraCode Nerd Font is installed
  2. Ensure your terminal is configured to use the font
  3. Try restarting your terminal application
