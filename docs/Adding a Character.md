## Adding Funker Selector characters
Adding characters to the mod is relatively simple, it's not really that difficult. This is assuming you know how to add characters to Base Game, please refer to the [Official Modding Documentation](https://funkincrew.github.io/funkin-modding-docs/03-custom-characters/03-02-creating-a-character.html) for information on that!

#### Method 1: JSON

1. In your Mod, create a new folder within `data` called `funkerSelector/`.
2. Create a new JSON file named after your character's ID. Here is an example of what the JSON should look like:

    ```json
    {
      "version": "1.0.0",
      "characterID": "pico-playable",
      "characterType": "bf",
      "description": {
        "text": "It's Pico from the 1999 Flash Game: 'Pico's School'! featured as an opponent in Week 3, and as a playable character in WeekEnd 1."
      },
      "characterMenu": {
        "position": [150, 200],
        "scale": 1
      }
    }
    ```

3. For more details on the JSON format, refer to the documentation within the `docs/` folder of Funker Selector. Focus mainly on `characterID` and `characterType`!
   - `characterID` is self-explanatory.
   - Accepted values for `characterType` are: `bf`, `gf`, `dad`, `player`, and `opponent`.

The resulting file hierarchy should look like this:
```
|- My Funker Selector Mod
  |-data
    |-funkerSelector
      |-characterID.json
  |-_polymod_metadata.json
```

#### Method 2: charSelectList (v1.4.1 and under)

> [!CAUTION]  
> **Legacy character support was removed in v1.5.0. This will only work on Funker Selector v1.4.1 and under.**

1. In your Mod, create a new folder called `_append`.
2. Inside `_append`, create a new folder called `data`.
3. Within the `data` folder, create a new file called `charSelectList.txt`. Type your character's ID into this file.

The resulting file hierarchy should look like this:
```
|- My Funker Selector Mod
  |-_append
    |-data
      |-charSelectList.txt
  |-_polymod_metadata.json
```
