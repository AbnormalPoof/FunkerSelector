## Proposal: New JSON format.

One of the things in the TODO is to replace charSelectList.txt with a fresh JSON format system.
This JSON can define a lot of things, like the gameover music suffix, pause menu music suffix, Freeplay Menu assets, etc etc.
This can go in `[Mod Folder Name]/data/funkerSelect/`

### EXAMPLE

Additional behavior to animations can be added through HScript.

```json
{
  "version": "1.0.0",
  "characterID": "bf",
  "description": "This blue-hair kid will not hesitate to rap\nbattle anyone who dares stand\nbetween him and his Girlfriend!",
  "pauseSuffix": "",
  "gameoverSuffix": "",
  "assets": [
    {
      "freeplayBF": [
        {
          "assetPath": "freeplay/freeplay-boyfriend",
          "renderType": "animateatlas",
          "offsets": [0, 0],
          "animationData": [
            {
              "name": "intro",
              "prefix": "boyfriend dj intro",
              "offsets": [0, 0]
            },
            {
              "name": "idle",
              "prefix": "Boyfriend DJ",
              "offsets": [0, 0]
            },
            {
              "name": "confirm",
              "prefix": "Boyfriend DJ confirm",
              "offsets": [0, 0]
            },
            {
              "name": "pumpIntro",
              "prefix": "Boyfriend DJ fist pump",
              "frameIndices": [1, 2, 3, 4,],
              "offsets": [0, 0]
            },
            {
              "name": "fistPump",
              "prefix": "Boyfriend DJ fist pump",
              "frameIndices": [5, 6, 7, 8, 9, 10, 11, 12, 13],
              "offsets": [0, 0]
            },
            {
              "name": "spook",
              "prefix": "bf dj afk",
              "offsets": [0, 0]
            },
            {
              "name": "tv",
              "prefix": "Boyfriend DJ watchin tv OG",
              "offsets": [0, 0]
            }
          ]
        }
      ],
      "resultsSHIT": [
        {
          "assetPath": "shared:resultScreen/results-bf/resultsSHIT",
          "renderType": "animateatlas",
          "offsets": [0, 0],
          "animationData": [
            // If additional animations are needed, you can specify them here and then implement them using HScript.
          ]
        }
      ],
      "resultsGOOD": [
        {
          "assetPath": "shared:resultScreen/results-bf/resultsGOOD",
          "renderType": "sparrow",
          "offsets": [0, 0],
          "animationData": [
            {
              "name": "fall",
              "prefix": "fall",
              "offsets": [0, 0]
            },
            {
              "name": "loop",
              "prefix": "Boyfriend Good Anim0",
              "offsets": [0, 0]
            }
          ]
        }
      ],
      "resultsGREAT": [
        {
          "assetPath": "shared:resultScreen/results-bf/resultsGREAT",
          "renderType": "animateatlas",
          "offsets": [0, 0],
          "animationData": [
            // If additional animations are needed, you can specify them here and then implement them using HScript.
          ]
        }
      ],
      "resultsEXCELLENT": [
        {
          "assetPath": "shared:resultScreen/results-bf/resultsEXCELLENT",
          "renderType": "animateatlas",
          "offsets": [0, 0],
          "animationData": [
            // If additional animations are needed, you can specify them here and then implement them using HScript.
          ]
        }
      ],
      "resultsPERFECT": [
        {
          "assetPath": "shared:resultScreen/results-bf/resultsPERFECT",
          "renderType": "animateatlas",
          "offsets": [0, 0],
          "enableHearts": true, // Wether to enable the Hearts which appear in the original animation.
          "animationData": [
            // If additional animations are needed, you can specify them here and then implement them using HScript.
          ]
        }
      ]
    }
  ]
}
```
