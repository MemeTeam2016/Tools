# GBA Player

A static page that runs GBA games in the browser with EmulatorJS 4.2.3 (mGBA core).
It hosts no game files: you pick a ROM from your own computer, and the browser
keeps it in its local storage. Works on GitHub Pages.

## Cloud saves

Saves can live in a separate private repo (`SAVES_REPO` in `index.html`), so the
same save plays on any computer:

- A fine-grained GitHub token with access to only that repo (Contents: read and
  write) is encrypted in the browser with your password (PBKDF2-SHA256, 600k
  iterations, AES-GCM). Only that encrypted copy, `vault.json`, is published here.
- On any computer: enter the password, pick a save (or make a new one), play.
  The page checks the game's save every 5 seconds and uploads it once it has
  stopped changing. Each upload is a commit, so old saves stay in the history.
- Play on one computer at a time: the last upload wins.
- Use a long passphrase: `vault.json` is public, so a weak password could be guessed.

Setup: open the page, use "Set up cloud saves", and publish the `vault.json` it
downloads next to `index.html`. To change the password or token, do it again.

## Other

- "Play offline" keeps saves in that browser only (player menu: Export / Import Save File).
- Fast-forward, save states and key bindings are in the player menu.
- Local testing: serve this folder and open `index.html?rom=local/<file>.gba`
  (`local/` and all ROM/save files are git-ignored).
