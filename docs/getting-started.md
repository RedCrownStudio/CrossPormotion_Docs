# Getting Started

## Setup

1. Drag the Prefab `Canvas_CrossPromotion_*` in your scene
2. Make sure you have a EventSystem in your scene when not add one
3. Open the Settings in the menu bar `Red Crown > Cross Promotion`
   - Json Raw URL: the url where your JSON is hosted on
   - Percentage: Is the Percentage how often the newest game should be displayed
   - Game ID: is the id from the JSON from the actual game so it get not displayed in the own game

### Use Callback

This package use the Unity start function, but you can change it to get the finished callback.

1. Open the `CrossPromotion.cs`
2. Delete this

   ```csharp
   private void Start()
   {
       StartCoroutine(LoadCrossPromotion());
   }
   ```

3. Call the `LoadCrossPromotion()` Coroutine in your script

   - Load the `Canvas_CrossPromotion_*` Object in your script (e.g. `GameObject.Find ("Canvas_CrossPromotion_*")`)

4. Wait for bool `CrossPromotion_Finished` to get `true`

## JSON

You can create your JSON file from the [example](/example_json).

### Attributes

- id: the id of the game
- name: The name of the game
- playStoreID: the id to link to the play store
- appStoreID: the id to link to the app store
- price: here you can add a text with the price like “FREE” or “3.99$”
- images: an array for all your images of the game
  - url: the url where you image is
  - frameColor: ere you can add a color for the frame in hex format

### Add a new Game

1. Copy the last game from the array like this:

   ```JSON
   {
      "id": 2,
      "name": "Example 2",
      "playStoreID": "de.redcrown.example2",
      "appStoreID": "2222",
      "price": "FREE",
      "images": [
        {
          "url": "https://drive.google.com/uc?export=download&id=1DtkbFlyNk0gx-CKHnP_6c-TLYk1RssOb",
          "frameColor": "#5841f4"
        }
      ]
    }
   ```

2. Paste it to the end of the array like this:

   ```JSON
   {
    "games": [
        {
            "id": 1,
            "name": "Example 1",
            "playStoreID": "de.redcrown.example1",
            "appStoreID": "1111",
            "price": "FREE",
            "images": [
                {
                    "url": "https://drive.google.com/uc?export=download&id=1mgOfUdIOI_v1z21WQegjWFgJpJeq5eer",
                    "frameColor": "#f44242"
                },
                {
                    "url": "https://drive.google.com/uc?export=download&id=17yujfPsHdt38HpwWQ8LVoOqqjtPa5Ay7",
                    "frameColor": "#41f456"
                }
                ]
            },
            {
                "id": 2,
                "name": "Example 2",
                "playStoreID": "de.redcrown.example2",
                "appStoreID": "2222",
                "price": "FREE",
                "images": [
                    {
                        "url": "https://drive.google.com/uc?export=download&id=1DtkbFlyNk0gx-CKHnP_6c-TLYk1RssOb",
                        "frameColor": "#5841f4"
                    }
                ]
            },
            {
                "id": 2,
                "name": "Example 2",
                "playStoreID": "de.redcrown.example2",
                "appStoreID": "2222",
                "price": "FREE",
                "images": [
                    {
                        "url": "https://drive.google.com/uc?export=download&id=1DtkbFlyNk0gx-CKHnP_6c-TLYk1RssOb",
                        "frameColor": "#5841f4"
                    }
                ]
            }
        ]
    }
   ```

3. Update the variables for the new game like this:

   ```JSON
   {
    "games": [
        {
            "id": 1,
            "name": "Example 1",
            "playStoreID": "de.redcrown.example1",
            "appStoreID": "1111",
            "price": "FREE",
            "images": [
                {
                    "url": "https://drive.google.com/uc?export=download&id=1mgOfUdIOI_v1z21WQegjWFgJpJeq5eer",
                    "frameColor": "#f44242"
                },
                {
                    "url": "https://drive.google.com/uc?export=download&id=17yujfPsHdt38HpwWQ8LVoOqqjtPa5Ay7",
                    "frameColor": "#41f456"
                }
                ]
            },
            {
                "id": 2,
                "name": "Example 2",
                "playStoreID": "de.redcrown.example2",
                "appStoreID": "2222",
                "price": "FREE",
                "images": [
                    {
                        "url": "https://drive.google.com/uc?export=download&id=1DtkbFlyNk0gx-CKHnP_6c-TLYk1RssOb",
                        "frameColor": "#5841f4"
                    }
                ]
            },
            {
                "id": 3,
                "name": "Example 3",
                "playStoreID": "de.redcrown.example3",
                "appStoreID": "3333",
                "price": "3.99$",
                "images": [
                    {
                        "url": "https://drive.google.com/uc?export=download&id=1DtkbFlyNk0gx-CKHnP_6c-TLYk1RssOb",
                        "frameColor": "#5841f4"
                    }
                ]
            }
        ]
    }
   ```
