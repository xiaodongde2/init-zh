# init - Claude Code Chinese Initialization Plugin

Chinese version of `/init` command, generates CLAUDE.md in Chinese.

## Features

- Analyze codebase structure, identify project type
- Generate Chinese CLAUDE.md with build commands, architecture, etc.
- Support custom path: `/init:zh /path/to/project`

## Installation

```
npx skills add xiaodongde2/init-zh `
  --skill init-zh `
  --agent claude-code `
  --global `
  --yes
```

### One-click Install (Windows PowerShell)

```powershell
# Add marketplace to settings.json
$settingsFile = "$env:USERPROFILE\.claude\settings.json"
$settings = Get-Content $settingsFile -Raw | ConvertFrom-Json
$settings.extraKnownMarketplaces | Add-Member -Name "init-zh-github" -Value @{
    source = @{ source = "github"; repo = "xiaodongde2/init-zh" }
} -Force
$settings.enabledPlugins | Add-Member -Name "init@init-zh-github" -Value $true -Force
$settings | ConvertTo-Json -Depth 10 | Set-Content $settingsFile -Encoding UTF8
```

### Manual Configuration

Add to `~/.claude/settings.json`:

```json
{
  "extraKnownMarketplaces": {
    "init-zh-github": {
      "source": {
        "source": "github",
        "repo": "xiaodongde2/init-zh"
      }
    }
  },
  "enabledPlugins": {
    "init@init-zh-github": true
  }
}
```

## Usage

After installation, restart Claude Code and use:

```
/init:zh
/init:zh /path/to/project
```

## Command Format

Plugin command format: `/plugin-name:skill-name`

| Component   | Source                              | Value    |
| ----------- | ----------------------------------- | -------- |
| plugin-name | marketplace.json `plugins[].name` | `init` |
| skill-name  | commands/*.md filename              | `zh`   |

## Version History

| Version | Description                                  |
| ------- | -------------------------------------------- |
| 1.0.0   | Initial version                              |
| 1.0.1   | Command name changed to `init:zh`          |
| 1.0.2   | Complete installer with auto cleanup         |
| 1.0.3   | Embed plugin content to fix JSON parse error |
| 1.0.5   | Sync version with Gitee release             |

## Author

xiaodongde (xiaodongde2008@gmail.com)
