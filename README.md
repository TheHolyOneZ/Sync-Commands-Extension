# Sync-Commands-Extension
The Sync Commands extension for Discord is a bot module that allows server administrators and bot owners to synchronize application commands efficiently. Unlike slash commands, this extension uses a custom prefix (e.g., !sync), allowing for flexible command execution.
> 💡 **Built for the Zygnal Ecosystem — to download and use this extension, you must be part of the Zygnal Ecosystem.**  
> This extension (cog) is part of the **Zygnal Ecosystem** and is only available through its supported platforms.  
> You can use it with:  
> - The **[Discord Bot Framework](https://github.com/TheHolyOneZ/discord-bot-framework)** — ideal for developers who want full control and flexibility *(includes an integrated extension marketplace)*, or  
> - The **[ZygnalBot](https://zygnalbot.de)** — a prebuilt, plug-and-play Discord bot *(also includes an integrated extension marketplace)*.  
>
> Browse and install extensions at [zygnalbot.com/extension](https://zygnalbot.com/extension).  
> For help or community discussions, join us on Discord: [discord.gg/sgZnXca5ts](https://discord.gg/sgZnXca5ts)
# Discord Bot Sync Commands Documentation

## Overview

The Sync Commands Extension provides a comprehensive set of tools for managing Discord application commands (slash commands). This extension allows bot administrators and owners to sync, clear, copy, and debug application commands both globally and for specific guilds.

## Commands

### Help Command

| Command | Description | Permissions |
|---------|-------------|------------|
| `!help_sync` | Displays help information for all sync commands | Anyone |

### Administrator Commands

| Command | Description | Permissions |
|---------|-------------|------------|
| `!sync_guild` | Syncs commands to the current guild only | Server Administrator |
| `!sync_status` | Checks the status of commands in the current guild and globally | Server Administrator |

### Bot Owner Commands

| Command | Description | Permissions |
|---------|-------------|------------|
| `!sync_global` | Syncs commands globally to all guilds | Bot Owner |
| `!sync_force [guild_id]` | Force syncs commands to a specific guild or globally | Bot Owner |
| `!clear_commands [guild_id]` | Removes all commands from a guild or globally | Bot Owner |
| `!sync_copy <source_guild_id> [target_guild_id]` | Copies commands from one guild to another or globally | Bot Owner |
| `!reload_and_sync [guild_id]` | Reloads all extensions and syncs commands | Bot Owner |
| `!sync_debug [guild_id]` | Gets detailed debug information about commands | Bot Owner |

## Command Details

### !help_sync

Displays a comprehensive help message showing all available sync commands, their descriptions, and when to use them.

**Usage:**
```
!help_sync
```

### !sync_guild

Syncs application commands to the current guild only. This is useful when you want to update commands for a specific server without affecting others.

**Usage:**
```
!sync_guild
```

**Permissions Required:** Server Administrator

### !sync_global

Syncs application commands globally to all guilds where the bot is present. Use this when you want to update commands across all servers.

**Usage:**
```
!sync_global
```

**Permissions Required:** Bot Owner

### !sync_force

Force syncs commands to a specific guild or globally. This is useful when normal sync isn't working properly.

**Usage:**
```
!sync_force [guild_id]
```

**Parameters:**
- `guild_id` (Optional): The ID of the guild to force sync commands to. If not provided, commands will be force synced globally.

**Permissions Required:** Bot Owner

### !clear_commands

Removes all application commands from a specific guild or globally. This command requires confirmation before execution.

**Usage:**
```
!clear_commands [guild_id]
```

**Parameters:**
- `guild_id` (Optional): The ID of the guild to clear commands from. If not provided, global commands will be cleared.

**Permissions Required:** Bot Owner

### !sync_status

Checks the current status of application commands in both the current guild and globally. Shows the number of commands registered locally and on the API, as well as lists all command names.

**Usage:**
```
!sync_status
```

**Permissions Required:** Server Administrator

### !sync_copy

Copies application commands from one guild to another or globally. This command requires confirmation before execution.

**Usage:**
```
!sync_copy <source_guild_id> [target_guild_id]
```

**Parameters:**
- `source_guild_id` (Required): The ID of the guild to copy commands from.
- `target_guild_id` (Optional): The ID of the guild to copy commands to. If not provided, commands will be copied to global commands.

**Permissions Required:** Bot Owner

### !reload_and_sync

Reloads all bot extensions and syncs application commands to a specific guild or globally. This is useful after making code changes to ensure all commands are up to date.

**Usage:**
```
!reload_and_sync [guild_id]
```

**Parameters:**
- `guild_id` (Optional): The ID of the guild to sync commands to after reloading extensions. If not provided, commands will be synced globally.

**Permissions Required:** Bot Owner

### !sync_debug

Gets detailed debug information about application commands, including local and API command counts, command names, and sync results. This is useful for troubleshooting sync issues.

**Usage:**
```
!sync_debug [guild_id]
```

**Parameters:**
- `guild_id` (Optional): The ID of the guild to get debug information for. If not provided, debug information will be shown for the current guild (if in a guild) and globally.

**Permissions Required:** Bot Owner

## Use Cases

### When to Use Guild Sync vs Global Sync

- **Guild Sync (`!sync_guild`)**: Use when testing new commands or when you want to have different commands in different servers.
- **Global Sync (`!sync_global`)**: Use when you want all servers to have the same commands or when you've finalized your command set.

### Troubleshooting Command Issues

1. Start with `!sync_status` to see the current state of commands
2. If commands aren't appearing, try `!sync_force` to force a sync
3. For detailed debugging, use `!sync_debug` to get comprehensive information
4. If all else fails, you can use `!clear_commands` followed by a sync to start fresh

### After Making Code Changes

Always use `!reload_and_sync` after making changes to your bot's code to ensure all extensions are reloaded and commands are properly synced.

## Notes and Warnings

- **Clearing Commands**: The `!clear_commands` operation is destructive and will remove all commands from the specified scope. Use with caution.
- **Global Operations**: Global operations affect all servers where your bot is present. Make sure you're ready to deploy changes everywhere before using global commands.
- **Rate Limits**: Discord has rate limits on API operations. Avoid running sync commands too frequently to prevent hitting these limits.
- **Confirmation Required**: Destructive operations like clearing or copying commands require confirmation to prevent accidental execution.

## Credits

Made By TheZ
