# Contributing

## Table of Contents

- [Finding Card Lists](#finding-card-lists)
- [Downloading Card Images](#downloading-card-images)
- [Find Alternative Artwork Numbering](#find-alternative-artwork-numbering)
- [Updating the Plugin Version](#updating-the-plugin-version)
- [LackeyCCG Plugin Guide](#lackeyccg-plugin-guide)

## Finding Card Lists

- Use the [Yu-Gi-Oh! Card Guide](https://www.yugiohcardguide.com/) to find what cards are in all decks and packs. These are listed by release date.

## Downloading Card Images

Resolutions used:
- New cards added to our modern plugin = 407 x 593
- Original plugin = 300 x 443

Downloading card images:
- Use [YGOPRODeck](https://ygoprodeck.com/) to "Search" for the card name.
- Select "Image (.jpg)" to open the full card image.
- Right-click to download it.
- The resolution of all cards is 813 x 1185. This is too large for LackeyCCG. Resize it half of the resolution (407 x 593).
    - Linux and macOS: `$ magick ~/Downloads/<DOWNLOADED_FILE_NAME>.jpg -resize 50% ~/Downloads/<CARD_NAME>.jpg`
- Move the image to the plugin images folder at  `sets/setimages/general/`.

## Find Alternative Artwork Numbering

- Use the [Yu-Gi-Oh! Wiki on Fandom](https://yugioh.fandom.com/wiki/Yu-Gi-Oh!_Wiki) to "Search" for the card name.
    - Example: [Blue-Eyes White Dragon main page](https://yugioh.fandom.com/wiki/Blue-Eyes_White_Dragon).
- Find the "Other card information" section and select the link for "Artworks".
    - Example: [Blue-Eyes White Dragon card artwork page](https://yugioh.fandom.com/wiki/Card_Artworks:Blue-Eyes_White_Dragon).
- Look for the TCG (not OCG) release order. Use this to help name the card in this plugin.
    - Example:
        - Blue-Eyes White Dragon "1st OCG/2nd TCG" would be called "Blue-Eyes White Dragon (Alt Art 1)" in this plugin.
        - Blue-Eyes White Dragon "2nd OCG/1st TCG" would be called "Blue-Eyes White Dragon" in this plugin.
        - Blue-Eyes White Dragon "3rd OCG/TCG" would be called "Blue-Eyes White Dragon (Alt Art 2)" in this plugin.

## Updating the Plugin Version

The plugin version is in a date format.

Automatically (recommended):
- Load the plugin using the ["Offline" installation guide](README.md).
- In LackeyCCG, run the command `/mkupdate plugins/yugioh/updatelist.txt`. This updates the version date and checksums.
- On Linux or macOS, run these commands to copy the `updatelist.txt` (the environment variable `LACKEYCCG_DIR` must be defined first).
    ```
    $ rm updatelist.txt
    $ mv "${LACKEYCCG_DIR}"/plugins/yugioh/updatelistNEW.txt ./updatelist.txt
    ```
- Update the date in the `version.txt` file in the format of `YYMMDD`.

Manually (not recommended):
- Update the date in these two files:
    - `updatelist.txt` = Update the version in the format of `MM-DD-YY`.
    - `version.txt` = Update the version in the format of `YYMMDD` but this file appears to be unused.

## LackeyCCG Plugin Guide

For additional tips, refer to the [official LackeyCCG Plugin Creation Tutorial](https://lackeyccg.com/tutorialplugin.html).
