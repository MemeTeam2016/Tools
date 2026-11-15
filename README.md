# GBA Player

A static page that runs GBA games in the browser with EmulatorJS (mGBA core).
It hosts no game files: you pick a ROM from your own computer, and the browser
keeps it (and your saves) in its local storage. Works on GitHub Pages.

- Saves stay in the browser that made them. Move them between computers with
  the player menu's Export Save File / Import Save File.
- Fast-forward, save states and key bindings are in the player menu.
- Local testing: serve this folder and open `index.html?rom=local/<file>.gba`
  (`local/` and all ROM/save files are git-ignored).
