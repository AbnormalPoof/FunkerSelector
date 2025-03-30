## Adding Funker Selector characters
Adding Funker Selector character in your mod involves creating a JSON file in your mod's `data/funkerSelector/` folder. This is assuming you know how to add characters to Base Game, please refer to the [Official Modding Documentation](https://funkincrew.github.io/funkin-modding-docs/03-custom-characters/03-02-creating-a-character.html) for information on that!

Below is an example of Pico (Playable)'s JSON file, from `data/funkerSelector/pico-playable.json`

```json
{
  "version": "1.0.0",
  "characterID": "pico-playable",
  "characterType": "bf",
  "mustUnlock": true,
  "unlockMethod": {
    "type": "playableCharacter"
  },
  "description": {
    "text": "It's Pico from the 1999 Flash Game: 'Pico's School'! featured as an opponent in Week 3, and as a playable character in WeekEnd 1.",
    "unlockCondition": "Beat WeekEnd 1 on any difficulty."
  },
  "characterMenu": {
    "position": [150, 200],
    "scale": 1
  },
  "characterVariations": [
    {
      "songID": ["spookeez", "south"],
      "characterID": "pico-dark",
      "songVariation": "erect"
    }
  ]
}
```

The available JSON fields are:

  - `version`: The version of the JSON file. Keep this at `1.0.0`.
  - `characterID` **[REQUIRED]**: The character ID the character uses.
  - `characterType`: The character type of this character, accepted values are: `bf`, `gf`, `dad`, `player`, `speaker`, and `opponent`.
  - `mustUnlock`: Whether or not you need to unlock the character first in order for them to be playable, used with `unlockMethod`. Optional, defaults to `false`.
  - `voiceID`: The ID to use for vocal replacement. Optional, defaults to the character ID.
  - `introSwapFrame`: The frame where the turntable stops moving and the character appears in the Freeplay DJ's intro animation, used for DJ swapping for a smooth transition. Optional, defaults to `3`.

Character description data (`description`) is structured like so:

  - `text`: The description text itself.
  - `unlockCondition`: The unlock condition of the character shown if the character is locked.

Character unlock data (`unlockMethod`) is structured like so:

  - `type`: The method of unlocking to use, accepted values are:
    - `playableCharacter`: The character's associated playable character has to be unlocked. (ex. You have to unlock Pico by beating WeekEnd 1 before unlocking him in Funker Selector)
    - `song`: A song has to be completed to be unlocked. This has 3 additional properties:
      - `songID`: The song's ID.
      - `difficultyList`: The available difficulties the song can be completed on. Optional, defaults to `["easy", "normal", "hard"]`
      - `minimumRequiredRank`: The minimum rank that's required to consider the character unlocked. Accepted values are `SHIT`, `GOOD`, `GREAT`, `EXCELLENT`, `PERFECT`, and `PERFECT_GOLD`.
    - `storyWeek`: A week in story mode has to be completed. This has 2 additional properties.
      - `levelID`: The ID of the week.
      - `difficultyList`: The available difficulties the song can be completed on. Optional, defaults to `["easy", "normal", "hard"]`

Character suffix data (`suffixes`) is structured like so:

  - `gameOverMusic`: The suffix used for the game over music. Optional, defaults to `""`.
  - `blueBall`: The suffix used for the blue ball SFX in the game over screen. Optional, defaults to `""`.
  - `pauseMusic`: The suffix used for the pause menu music. Optional, defaults to `""`.

Character sprite data (`characterMenu`) is structured like so:

  - `position`: The absolute position of the character.
  - `scale`: The scale of the character.
  - `flipX`: Whether or not to flip the character horizontally.
  - `selectedAnim`: The animation that plays when you select the character. Optional, defaults to `"hey"`.
  - `useCustomSprites`: Whether or not the character will use custom sprites instead of their character sprite. You'll need to specify custom sprite data.
  - `customSpriteData`: The custom sprite data, this follows the same animation data format the base game uses for its characters and props.

Character variation data (`characterVariations`) is structured like so:

  - `songID`: The song ID to target. Can either be an array of multiple IDs or a single string.
  - `characterID`: The character ID of the variation.
  - `songVariation`: The song variation to target. Optional, defaults to `"default"`.

## Vocal Replacement
> [!NOTE]
> This has only been tested with split vocals; it’s very likely it might not work properly for songs with single vocal tracks.

You can add character specific vocals for existing songs.

1. In your mod, create a new folder named `songs`.
2. Inside the `songs` folder, create another folder named after the song's ID you want to replace vocals for (e.g., `satin-panties`).
3. Inside this folder, drop your vocal file in `.ogg` format.
   - The naming scheme should follow this format: `Voices-characterID-variation.ogg`. Only add `-variation` if the vocals are for a song variation like Erect.
     - If you set a `voiceID` in the JSON data, use that instead of the character ID!

The file hierarchy should look like this:
```
|- My Funker Selector Mod
  |-songs
    |-tutorial
      |-Voices-characterID.ogg
  |-_polymod_metadata.json
```
