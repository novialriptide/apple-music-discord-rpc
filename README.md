# apple-music-discord-rpc

**[Deno](https://deno.com) + JavaScript for Automation (JXA) Discord Rich Presence Client for the macOS Apple Music app (Catalina and later) and legacy iTunes.**

Works with local tracks and Apple Music streaming service.

<img width="350" alt="Screenshot 2024-08-29 at 20 05 10" src="./images/preview.png">

## Features

- Seamless background startup on login, with no status bar clutter
- Minimal codebase
- Discord presence updates only while a track is actively playing
- Quick-access button to view the current song directly on the Apple Music website ([#5](https://github.com/NextFire/apple-music-discord-rpc/pull/5))
- MusicBrainz fallback for album artwork if Apple Music assets are unavailable ([#66](https://github.com/NextFire/apple-music-discord-rpc/pull/66))
- Dynamic progress bar within Discord, showing “Listening to x” with real-time playback progress ([#107](https://github.com/NextFire/apple-music-discord-rpc/pull/107))

## Getting Started

Follow one of the two sections below to download the script and enable the macOS launch agent that will start it at login.

### Homebrew (Recommended)

#### Install

After installing [Homebrew](https://brew.sh), execute the following commands:

```
brew tap nextfire/tap
brew install apple-music-discord-rpc
brew services restart apple-music-discord-rpc
```

These commands

- add [this tap](https://github.com/NextFire/homebrew-tap) to Homebrew,
- install its `apple-music-discord-rpc` formula (and Deno),
- enable the launch agent and start it immediately.

The `music-rpc.ts` executable is now also in `PATH`.

#### Uninstall

```
brew services stop apple-music-discord-rpc
brew remove apple-music-discord-rpc
brew untap nextfire/tap
```

### Shell Scripts

#### Install

Install [Deno](https://deno.com) (v2+), clone the repository and execute [`install.sh`](/scripts/install.sh):

```
git clone https://github.com/NextFire/apple-music-discord-rpc.git
cd apple-music-discord-rpc/
./scripts/install.sh
```

It will copy the [launch agent](/scripts/moe.yuru.music-rpc.plist) into `~/Library/LaunchAgents/` and edit it accordingly.

#### Uninstall

```
cd apple-music-discord-rpc/
./scripts/uninstall.sh
cd ../
rm -rf apple-music-discord-rpc/
```
