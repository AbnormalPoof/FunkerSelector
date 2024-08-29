## The JSON Format

As of v1.2.0, a new JSON format has been introduced in Funker Selector. This deprecates the old charSelectList.txt method
and allows for a bit more flexibility when adding characters!
The mod queries `data/funkerSelector/` at runtime and parses the JSON files in there, then takes the variables and passes it through the `CharacterSelectSubState` SubState to set up the Character.

### Example

```json
{
  "version": "1.0.0",
  "characterID": "bf",
  "characterType": "bf",
  "description": {
    "text": "The main protagonist of Friday Night Funkin', sporting his iconic blue hair and red-blue cap. Girlfriend loves him, her parents on the other hand...",
    "size": 35,
    "offsets": [0, 0]
  },
  "characterMenu":
  {
    "position": [150, 250],
    "scale": 1,
    "isPixel": false,
    "flipX": false,
    "selectedAnim": "hey"
  }
}
```

Now, you don't have to include ***every*** variable in here. In fact, here are only the essential ones you need:

```json
{
  "version": "1.0.0",
  "characterID": "bf",
  "characterType": "bf"
}
```

It won't look very pretty in the Character Selection screen, though...

### Variables

---

```json
"version": "1.0.0"
```
This is the version of the JSON Format, self explanatory.

---

```json
"characterID": "bf"
```
The Character ID to use, this is ***needed*** or else the character will not show up in the menu!

---

```json
"characterType": "bf"
```
The character type, accepted values are: `bf`, `gf`, `dad`, `player`, and `opponent`.
(`player` and `opponent` are just aliases for `bf` and `dad` respectively.)

---

***(These will be grouped together since they serve basically the same functionality.)***

```json
"gameOverMusicSuffix": ""
```
The music suffix used in the Game Over screen.

```json
"blueBallSuffix": ""
```
The blue ball suffix used in the Game Over screen.

```json
"pauseMusicSuffix": ""
```
The music suffix used in the Pause Menu.

You can use pretty much any suffix for these three as long as it's valid (exists in the files, either through a mod or the game's assets).
For example, Boyfriend (Pixel) uses `-pixel`, while Pico (Playable) uses `-pico`!

---

#### Description data

```json
"description": {
  "text": "The main protagonist of Friday Night Funkin', sporting his iconic blue hair and red-blue cap. Girlfriend loves him, her parents on the other hand...",
  "size": 35,
  "offsets": [0, 0]
}
```
This is a short description of the character, with a few properties:

```json
"text": "The main protagonist of Friday Night Funkin', sporting his iconic blue hair and red-blue cap. Girlfriend loves him, her parents on the other hand..."
``` 
The text itself.

```json
"size": 35
```
The font size.

```json
"offsets": [0, 0]
```
The offsets for the description. These are ***not*** the actual X and Y coordinates of the text, this is mainly for adjustment.

---

#### Character Sprite data

This is responsible for character appearance in the menu!

```json
"characterMenu":
{
  "position": [150, 250],
  "scale": 1,
  "isPixel": false,
  "flipX": false,
  "selectedAnim": "hey"
}
```

```json
"position": [150, 250]
```
The X and Y coordinates of the character.

```json
"scale": 1
```
The scale / size of the character.

```json
"isPixel": false
```
Multiplies the scale by 6 and disables anti-aliasing.

```json
"selectedAnim": "hey"
```
The animation to use when the character is selected.
The default animation is "hey"!

---

#### Character Variation data

`characterVariations` is an array that can contain character variations for specific songs.

```json
"characterVariations": [
  {
    "songID": "senpai",
    "characterID": "bf-pixel"
  },
  {
    "songID": "eggnog",
    "characterID": "bf-christmas"
  }
]
```

```json
"songID": "senpai"
```
The song ID we are targeting.

```json
"characterID": "bf-pixel"
```
The character ID we want to use.

Funker Selector will prioritize character variations over the base character ID. If no variations exist, the base character ID you set will be used instead.

## Conclusion
That's pretty much it! Adding a JSON Character should be relatively simple.
