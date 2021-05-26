## Naba Expo Media
Synchronized video viewing with chat and other features.
Lightweight modern implementation and very easy way to run locally.

Default channel example: https://vidstreamgit.herokuapp.com/

### New features
- Reworked layout and theme
- Multi-Language support
- Hotkeys (`Alt-P` for global play/pause, etc)
- Mobile view with page fullscreen
- Way to play local videos for network users (without NAT loopback feature)
- Playback rate synchronization (with leader)
- `/30`, `/-21`, etc to rewind video playback in seconds
- Links mask: `foo.com/bar${1-4}.mp4` to add multiple items
- Override every front-end file you want (`user/res` folder)

### Supported players
- Youtube (videos, streams and playlists)
- Raw mp4 videos and m3u8 playlists (or any other media format supported in browser)
- Iframes (without sync)

### Setup
- Open `4200` port in your router settings (port is customizable)
- `npm install ws` in this project folder ([NodeJS](https://nodejs.org) required)
- Run `node build/server.js`
- Open showed "Local" link for yourself and send "Global" link to friends

### Setup (Docker)
- As alternative, you can install Docker and run:
- `docker build -t nabaexpovidstream .`
- `docker run --rm -it -p 4200:4200 -v ${PWD}/user:/usr/src/app/user nabaexpovidstream`
- (Docker container hides real local/global ips, so you need to checkout it manually)

### Configuration
It's just works, but you can also check [user/ folder](/user/README.md) for server settings and additional customization.

### How to use
- Login with any nickname
- Add your video url with "plus" button below (youtube or direct link to mp4 for example)
- Now it plays and syncs for all page users, well done
- You can click "leader" button to get access to global video controls (play/pause, time setting, playback speed)
- If you want to restrict permissions or add admins/emotes, see `Configuration` above

### Intergations
#### Heroku:
- Create app and commit repo to get build
- Remove `user/` folder from `.gitignore` and commit it to change default configuration
- Add `APP_URL` config var with `your-app-link.herokuapp.com` value to prevent sleeping when clients online

### Development
- Install [Haxe 4.1](https://haxe.org/download/), [VSCode](https://code.visualstudio.com) and [Haxe extension](https://marketplace.visualstudio.com/items?itemName=nadako.vshaxe)
- `haxelib install all` to install extern libs
- If you skipped `Setup` section before: `npm ci`
- Open project in VSCode and press `F5` for client+server build and run

