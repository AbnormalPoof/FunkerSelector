## Vocal Replacement

> [!NOTE]  
> I've only tested this with split vocals; it’s very likely it might not work properly for songs with single vocal tracks.

1. In your mod, create a new folder named `songs`.
2. Inside the `songs` folder, create another folder named after the song's ID you want to replace vocals for (e.g., `satin-panties`).
3. Inside this folder, drop your vocal file in `.ogg` format. The naming scheme should follow this format: `Voices-characterID-variation.ogg` (Only add `-variation` if the vocals are for a song variation like Erect.)

The file heirarchy should look like this:
```
|- My Funker Selector Mod
  |-songs
    |-tutorial
      |-Voices-characterID.ogg
  |-_polymod_metadata.json
```