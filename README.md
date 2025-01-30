# startship

# Get editor completions based on the config schema
"$schema" = 'https://starship.rs/config-schema.json'

# Removes the blank line between shell prompts
add_newline = false

# Replace the "❯" symbol in the prompt with "➜"
[character]
success_symbol = "[󰁔](bold green)"
error_symbol = "[󰁔](bold red)"

# Cloud/Infrastructure tools
[terraform]
symbol = "󱁢 "
format = "via [$symbol$version]($style) "
style = "bold 105"

[kubernetes]
symbol = "󱃾 "
format = '[$symbol$context( \($namespace\))]($style) '
style = "bold blue"
disabled = false

[docker_context]
symbol = "󰡨 "
format = "via [$symbol$context]($style) "
style = "blue bold"

# Development tools
[nodejs]
symbol = "󰎙 "
format = "via [$symbol$version](bold green) "

[package]
symbol = "󰏗 "
format = "[$symbol$version]($style) "
style = "208"

# Git information
[git_branch]
symbol = "󰘬 "
format = "[$symbol$branch]($style) "
style = "bold purple"

[git_status]
format = '([\[$all_status$ahead_behind\]]($style) )'
style = "bold red"

# System info
[username]
style_user = "bold blue"
format = "[$user]($style) "
show_always = true

[hostname]
ssh_only = false
format = "[@$hostname](bold red) "
disabled = false

[directory]
style = "bold cyan"
read_only = "󰌾 "
truncation_length = 4
truncate_to_repo = false

# Command duration
[cmd_duration]
min_time = 500
format = "took [$duration](bold yellow) "

# Time
[time]
disabled = false
format = '[\[ $time \]](bold white) '
time_format = "%R"

# Shell indicator
[shell]
fish_indicator = "🐟 "
powershell_indicator = "⚡ "
unknown_indicator = "❓ "
style = "cyan bold"
disabled = false

# Memory usage module
[memory_usage]
disabled = false
threshold = -1
symbol = "🧠 "
style = "bold dimmed green"

# Battery module
[battery]
full_symbol = "🔋 "
charging_symbol = "⚡️ "
discharging_symbol = "💀 "
unknown_symbol = "❓ "
empty_symbol = "! "

[[battery.display]]
threshold = 100
style = "bold green"

[[battery.display]]
threshold = 50
style = "bold yellow"

[[battery.display]]
threshold = 20
style = "bold red"

# CPU usage
[custom.cpu]
command = "top -bn1 | grep 'Cpu(s)' | awk '{print $2}'"
when = "true"
format = "CPU: [$output]($style)"
style = "bold red"


