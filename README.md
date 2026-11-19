# GBA Player

A static page that runs GBA games in the browser with EmulatorJS 4.2.3 (mGBA core).
It hosts no game files. Works on GitHub Pages.

## Saves next to the ROM (Chrome / Edge)

Click **Choose game folder** and pick the folder that holds your `.gba`. The page
loads `<rom name>.sav` from that folder and, whenever the game saves, writes it
back there (within a few seconds; the previous save is kept as `.sav.bak`).
The browser remembers the folder, so later visits are just **Play** (plus a
one-click access prompt). Put the folder on a USB stick or in OneDrive / Google
Drive to play the same save on any computer. The `.sav` also works in desktop mGBA.

**Autosave backups (the pokefirered mod):** the mod's ROM saves in the background
every 5 minutes, into the game's spare save slot, so the game itself still loads your
last manual save. The page spots those writes and puts them in
`backup_<rom name>.sav` instead, leaving `<rom name>.sav` as your manual save. To
go back to an autosave, rename the backup to `<rom name>.sav`. In desktop mGBA
there's no separate backup file: autosaves stay in the spare slot inside the `.sav`.

## Other browsers

Firefox and Safari can't write to a folder: there you choose the ROM each time
and saves stay in that browser (player menu: Export / Import Save File).

Local testing: serve this folder and open `index.html`; `local/` and all ROM/save
files are git-ignored.
