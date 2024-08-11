# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.2.1] - 2024-08-11
### Added
- Added a small hotkey menu in the Character Menu, accessible by pressing D.
- J will now jump to the currently selected character.
### Changed
- Optimized a few spots in the `charSelect` and `CharacterMenu` modules.
- Refactored vocal replacement. `PlayState.instance.voices` is now replaced properly instead of the hacky way of setting `PlayState.instance.currentChart.characters.player` and basically running with it.
- Use a more memory-efficient method for "Preload Sprites".
### Fixed 
- Fixed "Preload Sprites" doing the opposite of what it was supposed to do.
  - In addition, disabling the option will now remove the sprites from memory.
- Fixed a random Null Object Reference from occuring when "Default" was selected.

## [1.2.0] - 2024-08-03
### Added
- A new JSON System for adding Funker Selector characters! Loaded from `data/funkerSelector/` in the mod folder.
  - This should allow for more flexibility when adding characters.
  - For documentation on this, please see `docs/Funker Selector JSON Character Format.md`.
- You can now change the Opponent and Girlfriend by pressing either Q or E! This will change the current page.
- Added a count to the UI which shows the current character, and the total amount of characters for the current page.
### Changed
- Gave the entire UI a fresh coat of paint. If the current character is a JSON Character, they will have their sprites displayed, along with a neat little description about them!
  - The UI now uses PhantomMuff by Cracsthor! Allows for text resizing, making the UI less cluttered in general. 
  - With this UI overhaul comes some new options related to it:
    - Simplify UI: Simplifies the UI if it's too much.
    - Preload Sprites: Wether to preload the character sprites or not.
- Changed the way saving works. It now uses `Save.instance.modOptions` instead of accessing `FlxSave` directly.
  - Your currently selected character will transfer over.
- Some minor optimizations here and there, mainly for the Character Selection screen.
### Deprecated
- With the introduction of the new JSON System, `charSelectList.txt` is now deprecated! This method of loading characters will still be supported for the time being, but I recommend moving your characters to JSON if possible.

## [1.1.1] - 2024-07-23
### Fixed
- Fixed vocal replacement for Default variation songs.

### Changed
- "Default" ID now uses the Face icon.

## [1.1.0] - 2024-07-22
### Added
- Added the Boyfriend variants and Pico to the default character list.

## [1.0.0] - 2024-07-21
### Added
- Pretty much everything.