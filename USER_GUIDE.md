# 🎵 Khlang Music Bot - Complete User Guide

## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Queue Limit System](#queue-limit-system)
- [Commands Reference](#commands-reference)
  - [Music Commands](#music-commands)
  - [Playlist Commands](#playlist-commands)
  - [Filter Commands](#filter-commands)
  - [Config Commands](#config-commands)
  - [Information Commands](#information-commands)
  - [Premium Commands](#premium-commands)
  - [Owner Commands](#owner-commands)
- [Premium Features](#premium-features)
- [Multi-Bot System](#multi-bot-system)
- [Advanced Features](#advanced-features)
- [Support](#support)

---

## Overview

**Khlang Music Bot** is a powerful, feature-rich Discord music bot with advanced queue management, premium features, multi-bot coordination, and high-quality audio playback.

### Key Highlights
- 🎵 High-quality audio (up to 320kbps)
- 🔄 Advanced autoplay system
- 🎨 Customizable now-playing canvas
- 🌟 Premium tier system with queue limits
- 🤖 Multi-bot coordination support
- 📊 Adaptive quality settings
- 🎚️ 15-band equalizer
- 💾 Queue backup & restoration
- 🇰🇭 Full Khmer language support

---

## Features

### Core Features
| Feature | Description |
|---------|-------------|
| **High-Quality Audio** | Up to 320kbps bitrate for crystal-clear sound |
| **Multi-Source Support** | YouTube, Spotify, SoundCloud, and more |
| **Autoplay** | Automatically finds and plays similar songs when queue ends |
| **Queue Management** | Advanced queue with shuffle, reverse, move, and more |
| **24/7 Mode** | Bot stays in voice channel indefinitely |
| **Favorites** | Save and quickly play your favorite tracks |
| **Custom Playlists** | Create and manage personal playlists |
| **Voice Status** | Shows current track in voice channel status |
| **Canvas Display** | Beautiful now-playing images with customization |

### Advanced Features
| Feature | Description |
|---------|-------------|
| **Adaptive Quality** | Automatically adjusts quality based on queue size |
| **Session Owner** | Track who controls the music session |
| **Queue Backup** | Automatic backup and restoration after crashes |
| **Multi-Bot Coordination** | Multiple bot instances work together seamlessly |
| **Audio Filters** | 20+ audio filters (bassboost, nightcore, vaporwave, etc.) |
| **Cambodia Mode** | Special audio mode optimized for Cambodian music |
| **DJ Role** | Role-based music control permissions |

---

## Queue Limit System

### Tier Levels

| Tier | Queue Limit | Features | How to Get |
|------|-------------|----------|------------|
| 👤 **Regular User** | 100 tracks | Basic features | Default for all users |
| 🌟 **Premium User** | 500 tracks | All premium features + 5x queue | Subscribe to premium |
| 👑 **Bot Owner** | Unlimited | Full access to everything | Configured in bot settings |

### Queue Limit Commands
```
!queuelimit          - Check your queue limit and usage
!qlimit             - Alias for queuelimit
!queuemax           - Alias for queuelimit
```

### What Counts Toward Limit?
- ✅ Currently playing track
- ✅ All queued tracks
- ✅ Tracks added via playlists
- ✅ Autoplay tracks (uses session owner's limit)

### When Premium Expires

**What happens to your queue?**

If you have premium with 500 tracks and your subscription expires:

1. ✅ **Your existing queue is safe** - All tracks remain
2. ✅ **Music keeps playing** - Nothing is interrupted
3. ✅ **No tracks removed** - We don't delete anything
4. ❌ **Cannot add new tracks** - Blocked until queue drops below 100

**Grace Period System:**
```
Premium expires → Limit drops from 500 to 100
Current queue: 350 tracks

✅ You can:
  • Keep playing all 350 tracks
  • Use skip, pause, resume, etc.
  • Clear queue manually
  
❌ You cannot:
  • Add new tracks via !play
  • Load playlists
  • Add more than current limit
```

**To resume adding tracks:**
1. Wait for queue to drop below 100 naturally
2. Use `!remove <position>` to remove tracks
3. Use `!clearqueue` to clear entire queue
4. Renew premium to restore 500 track limit

**Commands during grace period:**
- `!queuelimit` - Shows how many tracks over limit
- `!queue` - View and manage current queue
- `!remove <pos>` - Remove specific tracks
- `!clearqueue` - Clear all tracks
- `!premium` - Renew subscription

### Upgrade Benefits
When you reach your queue limit, the bot will show:
- Your current tier
- Current queue usage
- How many tracks you're trying to add
- Available space remaining
- Information about upgrading to premium

---

## Commands Reference

### Music Commands

| Command | Aliases | Description | Usage |
|---------|---------|-------------|-------|
| `!play` | `p` | Play a song from URL or search | `!play <song name/URL>` |
| `!search` | - | Search and select from top 5 results | `!search <query>` |
| `!pause` | - | Pause the current track | `!pause` |
| `!resume` | - | Resume playback | `!resume` |
| `!stop` | - | Stop music and clear queue | `!stop` |
| `!skip` | `s` | Skip to next track | `!skip` |
| `!previous` | `prev` | Play previous track | `!previous` |
| `!queue` | `q` | Display the music queue | `!queue` |
| `!nowplaying` | `np` | Show currently playing track | `!nowplaying` |
| `!volume` | `vol` | Set volume (0-100) | `!volume <0-100>` |
| `!seek` | - | Seek to position in track | `!seek <time>` |
| `!loop` | `repeat` | Toggle loop mode | `!loop <off/track/queue>` |
| `!shuffle` | - | Shuffle the queue | `!shuffle` |
| `!autoplay` | - | Toggle autoplay mode | `!autoplay` |
| `!jump` | - | Jump to specific track in queue | `!jump <position>` |
| `!remove` | - | Remove track from queue | `!remove <position>` |
| `!move` | - | Move track to different position | `!move <from> <to>` |
| `!playtop` | - | Add track to top of queue | `!playtop <song>` |
| `!playskip` | - | Skip current and play new song | `!playskip <song>` |
| `!shuffleplay` | - | Play and shuffle immediately | `!shuffleplay <song>` |
| `!favorite` | `fav` | Manage favorite tracks | `!favorite` |
| `!playfav` | - | Play a favorite track | `!playfav <name>` |
| `!favorites` | `favs` | Play all favorites | `!favorites` |
| `!back` | - | Go back to previous track | `!back` |
| `!forward` | - | Skip forward in track | `!forward <seconds>` |
| `!rewind` | - | Rewind in track | `!rewind <seconds>` |
| `!grab` | - | Save current track to DMs | `!grab` |
| `!lyrics` | - | Get lyrics for current/specified song | `!lyrics [song]` |

### Advanced Queue Commands

| Command | Description | Usage |
|---------|-------------|-------|
| `!reverse` | Reverse the queue order | `!reverse` |
| `!shuffletop` | Shuffle only top X tracks | `!shuffletop <amount>` |
| `!shufflebottom` | Shuffle only bottom X tracks | `!shufflebottom <amount>` |
| `!removedupes` | Remove duplicate tracks | `!removedupes` |
| `!clearqueue` | Clear entire queue | `!clearqueue` |
| `!insert` | Insert track at specific position | `!insert <position> <song>` |
| `!bump` | Move track to top of queue | `!bump <position>` |

### Playlist Commands

| Command | Aliases | Description | Usage |
|---------|---------|-------------|-------|
| `!playlist create` | `pl create` | Create a new playlist | `!playlist create <name>` |
| `!playlist delete` | `pl delete` | Delete a playlist | `!playlist delete <name>` |
| `!playlist add` | `pl add` | Add current track to playlist | `!playlist add <name>` |
| `!playlist remove` | `pl remove` | Remove track from playlist | `!playlist remove <name> <position>` |
| `!playlist list` | `pl list` | List all your playlists | `!playlist list` |
| `!playlist view` | `pl view` | View playlist tracks | `!playlist view <name>` |
| `!playlist load` | `pl load` | Load playlist to queue | `!playlist load <name>` |
| `!playlist play` | `pl play` | Play a playlist | `!playlist play <name>` |

### Filter Commands

| Command | Description | Usage |
|---------|-------------|-------|
| `!bassboost` | Apply bass boost filter | `!bassboost <low/medium/high>` |
| `!nightcore` | Apply nightcore effect | `!nightcore` |
| `!vaporwave` | Apply vaporwave effect | `!vaporwave` |
| `!8d` | Apply 8D audio effect | `!8d` |
| `!karaoke` | Apply karaoke filter | `!karaoke` |
| `!tremolo` | Apply tremolo effect | `!tremolo` |
| `!vibrato` | Apply vibrato effect | `!vibrato` |
| `!distortion` | Apply distortion filter | `!distortion` |
| `!rotation` | Apply rotation (8D-like) effect | `!rotation` |
| `!echo` | Apply echo effect | `!echo` |
| `!speed` | Change playback speed | `!speed <0.5-2.0>` |
| `!pitch` | Change pitch | `!pitch <0.5-2.0>` |
| `!bass` | Adjust bass level | `!bass <-10 to 10>` |
| `!treble` | Adjust treble level | `!treble <-10 to 10>` |
| `!equalizer` | Custom 15-band equalizer | `!equalizer` |
| `!filters` | View active filters | `!filters` |
| `!clearfilters` | Remove all filters | `!clearfilters` |
| `!cambodiamode` | Optimized for Cambodian music | `!cambodiamode` |
| `!normalmode` | Reset to normal quality | `!normalmode` |
| `!stablemode` | Stable quality mode | `!stablemode` |

### Config Commands

| Command | Description | Usage |
|---------|-------------|-------|
| `!247` | Toggle 24/7 mode | `!247` |
| `!setprefix` | Change bot prefix | `!setprefix <new prefix>` |
| `!settings` | View server settings | `!settings` |
| `!setup` | Setup music channel | `!setup` |
| `!announce` | Toggle track announce | `!announce` |
| `!defaultvolume` | Set default volume | `!defaultvolume <0-100>` |
| `!adddj` | Add DJ role | `!adddj <role>` |
| `!removedj` | Remove DJ role | `!removedj <role>` |
| `!toggledj` | Toggle DJ mode | `!toggledj` |
| `!voicestatus` | Toggle voice channel status | `!voicestatus` |
| `!adaptivequality` | Toggle adaptive quality | `!adaptivequality` |
| `!claim` | Claim music session | `!claim` |
| `!unclaim` | Release music session | `!unclaim` |
| `!transfer` | Transfer session to another user | `!transfer <user>` |
| `!clearautoplay` | Clear autoplay history | `!clearautoplay` |
| `!resetsettings` | Reset all server settings | `!resetsettings` |

### Information Commands

| Command | Aliases | Description | Usage |
|---------|---------|-------------|-------|
| `!help` | `h` | Show help menu | `!help [command]` |
| `!ping` | - | Check bot latency | `!ping` |
| `!stats` | - | Bot statistics | `!stats` |
| `!botinfo` | `bi` | Bot information | `!botinfo` |
| `!servercount` | - | Server count | `!servercount` |
| `!uptime` | - | Bot uptime | `!uptime` |
| `!invite` | - | Get bot invite link | `!invite` |
| `!support` | - | Get support server link | `!support` |
| `!features` | - | List all features | `!features` |
| `!queuelimit` | `qlimit` | Check your queue limit | `!queuelimit` |
| `!musicstats` | - | Music statistics | `!musicstats` |
| `!mystats` | - | Your personal stats | `!mystats` |
| `!serverstats` | - | Server statistics | `!serverstats` |
| `!sessioninfo` | - | Current session info | `!sessioninfo` |
| `!instances` | - | Show bot instances | `!instances` |
| `!shardstatus` | - | Shard information | `!shardstatus` |
| `!health` | - | Bot health status | `!health` |
| `!node` | - | Lavalink node info | `!node` |
| `!system` | - | System information | `!system` |
| `!status` | - | Bot status | `!status` |
| `!whois` | - | User information | `!whois [user]` |
| `!changelog` | - | View recent changes | `!changelog` |

### Premium Commands

| Command | Description | Usage |
|---------|-------------|-------|
| `!premium` | View premium information | `!premium` |
| `!boost` | Boost a server with premium | `!boost` |
| `!unboost` | Remove server boost | `!unboost` |
| `!redeem` | Redeem premium code | `!redeem <code>` |

### Owner Commands

| Command | Description | Usage |
|---------|-------------|-------|
| `!eval` | Evaluate JavaScript code | `!eval <code>` |
| `!botconfig` | Configure bot settings | `!botconfig` |
| `!canvasbg` | Customize canvas background | `!canvasbg` |
| `!maintenancemode` | Toggle maintenance | `!maintenancemode` |
| `!blacklist` | Manage blacklist | `!blacklist` |
| `!whitelist` | Manage whitelist | `!whitelist` |

---

## Premium Features

### What's Included?

| Feature | Free | Premium |
|---------|------|---------|
| Queue Limit | 100 tracks | 500 tracks |
| 24/7 Mode | ✅ | ✅ |
| Autoplay | ✅ | ✅ |
| Audio Filters | ✅ | ✅ |
| Custom Playlists | ✅ | ✅ |
| Favorites | ✅ | ✅ |
| High Quality Audio | ✅ | ✅ |
| Premium Bots Access | ❌ | ✅ |
| Priority Support | ❌ | ✅ |
| No Ads | ❌ | ✅ |
| Custom Canvas | ❌ | ✅ |
| Advanced Stats | ❌ | ✅ |

### How to Get Premium?

1. Use `!premium` command to view options
2. Choose your subscription plan
3. Use `!redeem <code>` to activate
4. Boost servers with `!boost`

### Premium Benefits

- 🌟 **500 Track Queue Limit** - 5x more tracks than free users
- 🤖 **Premium Bot Access** - Access to additional bot instances (bots 5-10)
- 🎨 **Custom Canvas** - Fully customizable now-playing images
- 📊 **Advanced Statistics** - Detailed music analytics
- 💎 **Priority Support** - Faster response times
- ⚡ **No Ads** - Ad-free experience

---

## Multi-Bot System

### Bot Instances

| Instance | Type | Access | Description |
|----------|------|--------|-------------|
| Bot 1-4 | Free | Everyone | Available to all users |
| Bot 5-10 | Premium | Premium Users | Exclusive to premium subscribers |

### Features

- **Automatic Selection** - Bot automatically picks the best available instance
- **Load Balancing** - Distributes users across multiple bots
- **Seamless Switching** - Switch between bots without interruption
- **Coordination** - All bots work together in harmony
- **Voice Status** - Shared voice channel status updates

### Commands

- `!instances` - View all available bot instances
- Bot automatically coordinates which instance to use

---

## Advanced Features

### Autoplay System

**How it works:**
1. Queue finishes playing all tracks
2. Bot automatically searches for similar songs
3. Adds and plays the next track
4. Continues indefinitely until stopped

**Commands:**
- `!autoplay` - Toggle on/off
- `!clearautoplay` - Clear autoplay history

**Note:** Autoplay respects queue limits based on session owner's tier.

### Session Owner System

The session owner is the person who started the music session or claimed it.

**Benefits:**
- Control over music playback
- Autoplay uses their queue limit
- Can transfer ownership to others

**Commands:**
- `!claim` - Claim the session
- `!unclaim` - Release ownership
- `!transfer @user` - Transfer to another user
- `!sessioninfo` - View session details

### Voice Channel Status

Shows current track in the voice channel status (below channel name).

**Displays:**
- 🎵 Currently playing song
- ⏸️ Paused status
- 🔁 Loop mode
- 🔄 Autoplay status

**Command:** `!voicestatus` to toggle

### Adaptive Quality

Automatically adjusts audio quality based on queue size to optimize performance.

**Modes:**
- **Auto** - Adjusts based on queue size
- **High** - Always high quality (320kbps)
- **Medium** - Balanced quality
- **Low** - Lower quality for better performance

**Command:** `!adaptivequality`

### Queue Backup & Restoration

- ✅ Automatic backup every 5 minutes
- ✅ Restores queue after bot restart
- ✅ Saves currently playing track
- ✅ Preserves queue order
- ✅ Recovers volume settings

### Canvas Customization

Customize the now-playing image display.

**Customizable Elements:**
- Background image/gradient
- Colors (text, progress bar, border)
- Font sizes
- Thumbnail position
- Visual effects (shadows, glow, blur)

**Commands:**
- `!canvasbg` - View customization options
- `!canvasbg theme <name>` - Apply preset theme
- `!canvasbg preview` - Test current settings

**Available Themes:**
- Dark
- Light
- Neon
- Ocean
- Sunset
- Forest
- Purple
- Gold

### DJ Role System

Restrict music control to specific roles.

**Setup:**
1. `!adddj @DJ` - Add DJ role
2. `!toggledj` - Enable DJ mode
3. Only users with DJ role can control music

**Commands:**
- `!adddj <role>` - Add DJ role
- `!removedj <role>` - Remove DJ role
- `!toggledj` - Toggle DJ mode on/off

---

## Support

### Getting Help

| Method | Link/Command |
|--------|--------------|
| Support Server | Use `!support` command |
| Help Command | `!help [command]` |
| Bot Status | `!status` |
| Health Check | `!health` |

### Common Issues

#### Bot not joining voice channel?
- Check bot has `Connect` and `Speak` permissions
- Ensure you're in a voice channel
- Try `!stop` then `!play` again

#### Music not playing?
- Check volume with `!volume`
- Ensure track isn't paused (`!resume`)
- Verify Lavalink node is online (`!node`)

#### Queue limit reached?
- Check your limit: `!queuelimit`
- Upgrade to premium for 500 track limit
- Clear some tracks from queue

#### Commands not working?
- Check bot has required permissions
- Verify prefix with `!help`
- Ensure DJ mode isn't restricting access

### Report Bugs

If you find a bug:
1. Use `!support` to join support server
2. Provide detailed information:
   - Command used
   - Error message
   - Steps to reproduce
3. Include `!botinfo` output

---

## Configuration Examples

### Basic Server Setup
```
1. !setup                    # Setup music channel
2. !setprefix !              # Set your prefix
3. !defaultvolume 80         # Set default volume
4. !announce                 # Enable track announcements
5. !voicestatus              # Enable voice status
```

### DJ Mode Setup
```
1. Create a role called "DJ"
2. !adddj @DJ               # Add the role
3. !toggledj                # Enable DJ mode
```

### Quality Settings
```
!adaptivequality            # Enable adaptive quality
!normalmode                 # Or use normal mode
!cambodiamode               # For Cambodian music
```

---

## Tips & Tricks

### Queue Management
- Use `!shuffletop 10` to shuffle only next 10 songs
- `!bump 5` to move track #5 to play next
- `!removedupes` to clean up duplicate entries

### Audio Quality
- `!cambodiamode` for Cambodian songs
- `!bassboost high` for extra bass
- `!equalizer` for precise audio control

### Playlist Management
- Create themed playlists for different moods
- Use `!playlist add` while songs play to build playlists
- Load entire playlists with `!playlist load`

### Premium Usage
- Boost servers you manage most
- Create large playlists (up to 500 tracks)
- Use premium bots during peak hours

---

## Version Information

**Current Version:** 4.0  
**Last Updated:** January 2026  
**Lavalink Version:** v4  
**Node.js Version:** 18+

### Recent Updates
- ✅ Queue limit system implementation
- ✅ Enhanced autoplay engine
- ✅ Multi-bot coordination
- ✅ Canvas customization
- ✅ Session owner system
- ✅ Adaptive quality settings
- ✅ Premium tier system

---

## Credits

**Developed by:** Sophan Developer  
**Repository:** Khlangbot  
**License:** MIT

### Special Thanks
- Discord.js team
- Erela.js developers
- Lavalink team
- All contributors and testers

---

## Legal

### Terms of Service
- Bot provided as-is
- No warranty or guarantees
- Service may change without notice
- Premium subscriptions are non-refundable

### Privacy Policy
- Bot stores minimal user data
- Music history stored temporarily
- Premium status tracked
- No personal data sold

### Data Collected
- Server IDs and settings
- User music preferences
- Queue and playlist data
- Premium subscription status

---

*For the latest updates and announcements, join our support server using `!support` command.*

**Enjoy your music! 🎵**
