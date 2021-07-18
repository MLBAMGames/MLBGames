[![image](https://raw.githubusercontent.com/MLBAMGames/MLBGames/master/mlbgames.png)](http://mlbamgames.github.io/MLBGames/)

[![GitHub release (latest by date)](https://img.shields.io/github/v/release/mlbamgames/mlbgames?style=flat-square)](https://www.github.com/MLBAMGames/MLBGames/releases/latest)
[![GitHub all releases](https://img.shields.io/github/downloads/MLBAMGames/MLBGames/total?style=flat-square)](https://www.github.com/MLBAMGames/MLBGames/releases/latest)
[![Windows](https://img.shields.io/badge/plateform-windows-inactive?style=flat-square)](https://www.github.com/MLBAMGames/MLBGames/releases/latest)
[![Subreddit subscribers](https://img.shields.io/reddit/subreddit-subscribers/mlb_games?style=flat-square)](https://www.reddit.com/r/mlb_games)
[![Status](https://mlb-games-status.herokuapp.com/us/badge)](https://mlbamgames.github.io/mlb-games-status/)

Tool to watch MLB games streams in High Definition

Choose a date.  
Choose a game.  
Choose a stream.  
Enjoy!

![image](https://raw.githubusercontent.com/MLBAMGames/MLBGames/master/ui.png)

# _Index_

- [First use](#first-use)
  - [Requirements](#requirements)
  - [Is this app safe?](#is-this-app-safe)
- [Documentation](#documentation)
  - [Games](#games)
    - [Navigation bar](#navigation-bar)
    - [Game panel](#game-panel)
  - [Standings](#standings)
  - [Settings](#settings)
    - [Customize game panels](#customize-game-panels)
    - [Stream Quality](#stream-quality)
    - [Rewind and Replay](#rewind-and-replay)
    - [Content Delivery Network (CDN)](#content-delivery-network-cdn)
    - [Server's Hostname](#servers-hostname)
    - [Proxy Port](#proxy-port)
    - [Players](#players)
    - [Streamer](#streamer)
    - [Language](#language)
    - [Dark Theme](#dark-theme)
    - [Arguments](#arguments)
    - [Ad Detection](#ad-detection)
  - [Console](#console)
- [Wiki and Support](#wiki-and-support)
- [Contribute](#contribute)
- [Donation](#donation)
- [Download](#download)

---

# _First use_

## _Requirements_

MLBGames is an app built on .NET Framework 4.5. It's only available on Windows (Windows XP, Vista are not supported). Any CPU architecture is supported (x86/x64).

If you run MLBGames on Windows 7 you will probably need to install:

- [.NET Framework 4.5](https://www.microsoft.com/en-ca/download/details.aspx?id=30653)

In the release page, [download](#download) the complete version includes:

- Our proxy [mlbam-proxy](https://github.com/MLBAMGames/go-mlbam-proxy)
- Our Windows-Hosts-File editor [mlbam-host](https://github.com/MLBAMGames/go-mlbam-hosts) (if you have issues with our proxy)
- Our app upater
- Media player MPV
- Streamer Streamlink

If you choose the simplified version instead of the complete version, you'll need:

- A supported [media player](#players)
- A supported [streamer](#streamer)

## _Is this app safe?_

Yes, it is. The server only responds in plain text and won't harm your PC. You can verify yourself by inspecting the code.

# _Documentation_

Everytime you launch MLBGames it will search for today's games.

## _Games_

### _Navigation bar_

If you want to watch past games, use the calendar or use the arrows to navigate through the days.

![image](https://raw.githubusercontent.com/MLBAMGames/MLBGames/master/navigation-bar.png)

Use the refresh button (right side) to refresh the current day's games.

### _Game panel_

Game panels will have a different frame color based on their game status (scheduled, pregame, live, ended).

Games broadcasting will be shown with a red border:

![image](https://raw.githubusercontent.com/MLBAMGames/MLBGames/master/game-live-panel.png)

Other games (ended or scheduled) are grey:

![image](https://raw.githubusercontent.com/MLBAMGames/MLBGames/master/game-old-panel-spoiler.png)
![image](https://raw.githubusercontent.com/MLBAMGames/MLBGames/master/game-old-panel.png)

Features on the panel:

- Watch recap by clicking on the play icon on the top-right corner (when available)
- Watch a stream by clicking on a network logo or a camera (hover on it to get some more info)
- Rewind a live stream: see [_Rewind and Replay_](#rewind-and-replay) section.

Game panels can be customized to show or hide information. It can be changed in the settings menu.

## _Settings_

### _Customize Game panels_

MLBGames gives you options to change how a game panel will appear.

| Option                    | Required game statuses to work | Default value |
| :------------------------ | :----------------------------- | :-----------: |
| Order by live games first | Today's games                  |     `ON`      |
| Live innings state        | Live games                     |     `ON`      |
| Live scores               | Live games                     |     `OFF`     |
| Series record             | Live and past series games     |     `ON`      |
| Teams city abbreviation   | Upcoming, live and past games  |     `OFF`     |
| Final scores              | Past games                     |     `OFF`     |

### _Stream Quality_

The selected value will define which video quality will be sent to your media player, from the worst to the best quality. Selecting the highest quality also means larger files to download :

| Name      | Resolution              | Data usage  |
| :-------- | :---------------------- | :---------: |
| Excellent | 720p at 60fps (or best) | ~ 2.5 Gb/hr |
| Superb    | 720p                    | ~ 1.8 Gb/hr |
| Great     | 540p                    | ~ 1.3 Gb/hr |
| Normal    | 360p                    | ~ 0.7 Gb/hr |
| Low       | 228p                    | ~ 0.5 Gb/hr |
| Mobile    | 224p (or worst)         | ~ 0.3 Gb/hr |

### _Rewind and Replay_

The Rewind/Replay feature is only available for **Live games only** and it's good way to **prevent a live stream from lagging** because you set the stream _X_ minutes behind so the delay gives you a nice buffer.

If you see a red game panel with a ![image](https://raw.githubusercontent.com/MLBAMGames/MLBGames/master/live-button.png) icon in the left corner that means you will have access to the Replay or Rewind feature. To use the feature, you have click on the icon (top-left corner of the game panel), and click on a stream to start watching.

- ![image](https://raw.githubusercontent.com/MLBAMGames/MLBGames/master/rewind-button.png)  Rewind: click it once.
- ![image](https://raw.githubusercontent.com/MLBAMGames/MLBGames/master/replay-button.png)  Replay: click it twice.
- ![image](https://raw.githubusercontent.com/MLBAMGames/MLBGames/master/live-button.png)  Live (default): Click it three times to set it back to Live.

![image](https://raw.githubusercontent.com/MLBAMGames/MLBGames/master/game-live-panel-actions.gif)

If you use the rewind or replay feature and you want to change the default behaviour, you can set your preferences here.

#### Live Replay

If Replay is selected, it will start the stream from the selected value

- When the game starts (play ball) - _7:10PM for a game scheduled at 7PM_
- When the event starts (game time) - _7:00PM for a game scheduled at 7PM_
- At the beginning of the stream - _Around 6:30PM (pregame) for a game starting at 7PM_

#### Live Rewind

If Rewind is selected, it will use the slider value to set the stream behind the live stream.

![image](https://raw.githubusercontent.com/MLBAMGames/MLBGames/master/track-bar-live-rewind.png)

> _NOTE: If you use the rewind slider in settings, but you set it before game time and the stream has no data at this time, it might start from live._

### _Content Delivery Network (CDN)_

MLBGames uses by default Akamai CDN, but Level 3 can be activated by turn on the alternate network in settings.

Default: Akamai

> Akamai is one of the oldest CDNs and is generally considered to be the largest global CDN. They have 'servers everywhere' and a wide range of products and services. The company is actively involved in Let's Encrypt and is pushing HTTP/2 adoption.

Alternate: Level 3

> Level 3 owns and operates a global Tier-1 network and their CDN runs on top of it. It has POPs on all continents and their product focus is on video and large object delivery. Level 3 CDN is part of the Google Cloud CDN Interconnect.

### _Server's Hostname_

This drop down list shows all MLBGames server hostnames. If you can't play games, try another hostname.

### _Proxy Port_

Use the slider to change the proxy port when starting MLBGames.

Remember that if you close MLBGames while watching a stream, it will close the proxy as well and it will kill the stream. Just minimize MLBGames instead while playing.

### _Players_

MLBGames supports 3 media players:

- [MPV](https://mpv.io/installation/) : a simple and powerful cross-platform media player
- [VLC](https://www.videolan.org/vlc/index.html) : a strong and popular cross-platform multimedia player
- [MPC](https://mpc-hc.org/downloads/) : a light-weight media player

If you don't have or want VLC/MPC players, use the default media player to watch games. Make sure you select MPV as the default player.

If you had previously installed VLC or MPC, MLBGames should find it automatically if you installed it in Program Files. Otherwise you will have to browse ![image](https://raw.githubusercontent.com/MLBAMGames/MLBGames/master/dotdot.png) your computer and get the path to the .EXE file.

If you don't have one of these players installed, use the links on the right to download it.

### _Streamer_

A streamer is not a media player. It's an application that MLBGames uses to get the stream from the Internet and parse it to your media player. The default streamer that MLBGames provided can be found in the **Complete** zip. The **Simplified** .zip file does not have any. If you use the Complete package, don't move the provided streamer and media player out of the MLBGames folder. Otherwise, you will have to speciy another streamer to be able to stream a game.

- [StreamLink](https://streamlink.github.io/install.html) : recommanded command-line tool that extracts and pipes streams into a media player
- [Livestreamer](https://docs.livestreamer.io/install.html) : old and deprecated tiny command-line tool that extracts and pipes streams into a media player. It may takes 60 secs to open a stream.

Follow the link above, download the installer and set the path in MLBGames settings.

### _Dark Theme_

Renders MLBGames with dark tones. An application restarts is needed for changes to take effect.

### _Language_

MLBGames supports two languages: English and French.
More can be added, but we are waiting for contributions.

Contribute:

> If you want to contribute. Translate the file `MLBAMGames/MLBGames/English.resx`. It can be modified in Visual Studio, remove any lines tagged as Console lines (these are not translated), rename the file and open a Pull Request.

### _Arguments_

If you wish to customise the way your player or the streamer opens, turn on one of these options and add your arguments:

- Player args : If you want to add more arguments (commands) to be sent to your media player with the default args that MLBGames send.
- Streamer args : If you want to add more arguments (commands) to be sent to streamlink with the default args that MLBGames send.

### _Ad Detection_

MLBGames doesn't use any Ad Detection by default, but you can activate it and select the app you want to use during commercials. If you don't use any, it's better if you keep the Ad Detection disabled.

Ad detection supports these applications:

- Media player: If you want to play music/video during ads from another media player.
  - Always play next media: It won't pause your media player when the ad ends, but it will skip to the media (song/video).
  - Bind to Spotify: If you want to use Spotify app, but Windows use another one instead, enabled this feature to use Spotify hotkeys.
  - Force to start: It will open Spotify when you start MLBGames, or enable the media app detector.
  - Media control delay: By default 100ms, but can be increased if your media player doesn't play or pause at the right time, 1000ms = 1 second btw.
- OBS Scene Changer : If you want to switch between windows when an ad hits.
  - Ad ending hotkey: Set the same hotkey that the one in OBS to display the window that the game is on.
  - Ad starting hotkey: Set the same hotkey that you use in OBS to display the window when a commercial plays.

## _Console_

Go to this tab to see everything that MLBGames logs. Any error or warning will show up here. Click on `Copy to clipboard` if you get an issue and want to report it on Github. Paste the log text when opening an issue.

# _Wiki and Support_

Having an issue with MLBGames? Go to our Wiki to find a fix. Look at the side bar, on the right, to navigate between known issues. If you can't find it, feel free to open an [issue](https://github.com/MLBAMGames/MLBGames/issues) :

> #### [Wiki and Support](https://github.com/MLBAMGames/MLBGames/wiki)


If you think that the app does not work or is down, please check if our services are up :

> #### [Server Status](https://mlbamgames.github.io/mlb-games-status/)


Support by the reddit community :

> #### [Subreddit](https://www.reddit.com/r/mlb_games)  

# _Contribute_

MLBGames is coded in VB.NET using Visual Studio and .Net Framework 4.5. If you want to contribute : [Follow the guidelines](https://github.com/MLBAMGames/MLBAMGames/CONTRIBUTING.md)

Thanks to our [contributors](https://github.com/MLBAMGames/MLBAMGames/graphs/contributors)

# _Donation_

[Donate via Paypal](https://streamlabs.com/stevensnjd4/tip): Make sure to mention MLBGames in the message box so we know which project you're supporting!  
Donate via Bitcoin: `17uSfctCE4n5uLAHqZQEozqEiLafSaUgQL`

# _Download_

In the _assets_ section of the release, download the `.zip` archive:
- **Complete**: If you never downloaded MLBGames before, or you want to start fresh.
- **Simplified**: If you already have MPV latest version and StreamLink apps on your PC.

> Simplified version is x10 lighter than the Complete one.

### Windows: [Lastest release](https://github.com/MLBAMGames/MLBGames/releases/latest)
