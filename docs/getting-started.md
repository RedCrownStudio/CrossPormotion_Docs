# Getting Started

## Setup

1. Drag the Prefab `Canvas_CrossPromotion_*` in your scene
2. Make sure you have a EventSystem in your scene when not add one
3. Open the Settings in the menu bar `Red Crown > Cross Promotion`
   - Json Raw URL: the url where your JSON is hosted on
   - Percentage: Is the Percentage how often the newest game should be displayed
   - Game ID: is the id from the JSON from the actual game so it get not displayed in the own game

### Use Callback (Wait for finish)

This package use the Unity start function, but you can change it to get the finished callback.

1. Open the `CrossPromotion.cs`
2. Delete this

   ```csharp
   private void Start()
   {
       StartCoroutine(LoadCrossPromotion());
   }
   ```

3. Call the `LoadCrossPromotion()` Coroutine in you script

   - Load the `Canvas_CrossPromotion_*` Object in your script (e.g. `GameObject.Find("Canvas_CrossPromotion_*")`)

4. Wait for `CrossPromotion_Finished` to get `true`

## JSON

You can create your JSON file from the example.

### Attributes

- name: The name of the game
- image: the url for the game image
- playStoreID: the id to link to the play store
- appStoreID: the id to link to the app store
- hexColor: here you can add a color for the frame
- price: here you can add a text with the price like “FREE” or “3.99$”
- id: the id of the game to ignore this in own game

### Add a new Game

1. Copy the `newGame` element from your JSON

   ```JSON
   "newGame": {
       "name": "Example 3",
       "image": "https://drive.google.com/uc?export=download&id=1mgOfUdIOI_v1z21WQegjWFgJpJeq5eer",
       "playStoreID": "de.redcrown.example3",
       "appStoreID": "3",
       "hexColor": "FDFDFDFF",
       "price": "NEW",
       "id": "2"
   }
   ```

2. Paste it under the newGame element

   ```JSON
   {
    "newGame": {
        "name": "Example 3",
        "image": "https://drive.google.com/uc?export=download&id=1mgOfUdIOI_v1z21WQegjWFgJpJeq5eer",
        "playStoreID": "de.redcrown.example3",
        "appStoreID": "3",
        "hexColor": "FDFDFDFF",
        "price": "NEW",
        "id": "2"
    },
    "newGame": {
        "name": "Example 3",
        "image": "https://drive.google.com/uc?export=download&id=1mgOfUdIOI_v1z21WQegjWFgJpJeq5eer",
        "playStoreID": "de.redcrown.example3",
        "appStoreID": "3",
        "hexColor": "FDFDFDFF",
        "price": "NEW",
        "id": "2"
    },
    "game1": {
        "name": "Example 2",
        "image": "https://drive.google.com/uc?export=download&id=17yujfPsHdt38HpwWQ8LVoOqqjtPa5Ay7",
        "playStoreID": "de.redcrown.example2",
        "appStoreID": "2",
        "hexColor": "E2E7ECFF",
        "price": "FREE",
        "id": "1"
    },
    "game0": {
        "name": "Example 1",
        "image": "https://drive.google.com/uc?export=download&id=1DtkbFlyNk0gx-CKHnP_6c-TLYk1RssOb",
        "playStoreID": "com.rc.example1",
        "appStoreID": "1",
        "hexColor": "333333FF",
        "price": "FREE",
        "id": "0"
    }
   }
   ```

3. change the key to “game” + next number

   ```JSON
   {
    "newGame": {
        "name": "Example 3",
        "image": "https://drive.google.com/uc?export=download&id=1mgOfUdIOI_v1z21WQegjWFgJpJeq5eer",
        "playStoreID": "de.redcrown.example3",
        "appStoreID": "3",
        "hexColor": "FDFDFDFF",
        "price": "NEW",
        "id": "2"
    },
    "game2": {
        "name": "Example 3",
        "image": "https://drive.google.com/uc?export=download&id=1mgOfUdIOI_v1z21WQegjWFgJpJeq5eer",
        "playStoreID": "de.redcrown.example3",
        "appStoreID": "3",
        "hexColor": "FDFDFDFF",
        "price": "NEW",
        "id": "2"
    },
    "game1": {
        "name": "Example 2",
        "image": "https://drive.google.com/uc?export=download&id=17yujfPsHdt38HpwWQ8LVoOqqjtPa5Ay7",
        "playStoreID": "de.redcrown.example2",
        "appStoreID": "2",
        "hexColor": "E2E7ECFF",
        "price": "FREE",
        "id": "1"
    },
    "game0": {
        "name": "Example 1",
        "image": "https://drive.google.com/uc?export=download&id=1DtkbFlyNk0gx-CKHnP_6c-TLYk1RssOb",
        "playStoreID": "com.rc.example1",
        "appStoreID": "1",
        "hexColor": "333333FF",
        "price": "FREE",
        "id": "0"
    }
   }
   ```

4. Update the variables for the new game and the price from the old game from “NEW” to something like “FREE”

   ```JSON
   {
    "newGame": {
        "name": "Example 4",
        "image": "https://drive.google.com/uc?export=download&id=1mgOfUdIOI_v1z21WQegjWFgJpJeq5eer",
        "playStoreID": "de.redcrown.example4",
        "appStoreID": "4",
        "hexColor": "3D3D3D",
        "price": "NEW",
        "id": "3"
    },
    "game2": {
        "name": "Example 3",
        "image": "https://drive.google.com/uc?export=download&id=1mgOfUdIOI_v1z21WQegjWFgJpJeq5eer",
        "playStoreID": "de.redcrown.example3",
        "appStoreID": "3",
        "hexColor": "FDFDFDFF",
        "price": "FREE",
        "id": "2"
    },
    "game1": {
        "name": "Example 2",
        "image": "https://drive.google.com/uc?export=download&id=17yujfPsHdt38HpwWQ8LVoOqqjtPa5Ay7",
        "playStoreID": "de.redcrown.example2",
        "appStoreID": "2",
        "hexColor": "E2E7ECFF",
        "price": "FREE",
        "id": "1"
    },
    "game0": {
        "name": "Example 1",
        "image": "https://drive.google.com/uc?export=download&id=1DtkbFlyNk0gx-CKHnP_6c-TLYk1RssOb",
        "playStoreID": "com.rc.example1",
        "appStoreID": "1",
        "hexColor": "333333FF",
        "price": "FREE",
        "id": "0"
    }
   }
   ```
