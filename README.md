# Dino Bars
This is a mod for ARK: Survival Evolved. It adds health, torpor and stamina bars to dinosaurs.

### Steam Workshop link
https://steamcommunity.com/sharedfiles/filedetails/?id=1618319057

## Edit the mod in ARK Editor
To edit the mod you need the ARK Editor from the Epic Games launcher.
After installing it, put the files from this repository into the folder Projects\ShooterGame\Content\Mods\DinoBars (create the DinoBars sub folder first).

- Open the ARK Editor and wait until it has discovered all assets (there is a popup in the bottom left corner with a progress bar and title "Discovering Assets", this can take a while).
- Navigate to the Maps folder within ARK Editor and double click on the TestMap to open it.
- In the world settings on the right, scroll down to the "Primal Game Data Override" drop down and select "PrimalGameData_BP_DinoBars" (this is only available after all assets have been discovered. If it is still not available, select the PrimalGameData_BP_DinoBars within the Mods\DinoBars folder and click on the arrow icon next to the drop down).
- Navigate to the PrimalEarth\Dinos\Dodo folder and drag and drop the Dodo_Character_BP into the map (again, this may take a while and ARK Editor may freeze for a bit).
- Drag and drop more/other dinos into the map if you wish.
- Save the map and click on play (both buttons are on the top of the screen, above the map).
- If you are close to a dino you should now see the mod working (a health bar should appear above the dino).
- All files in the folder Mods\DinoBars belong to the mod and can be edited however you want.
- The core logic is in the Blueprints\HUD\DinoBars_HUD. Switch to the graph view to edit the code via visual scripting.
- The design/layout is in the Blueprints\UI\DinoBarsUI and DinoBarsSimpleUI. Those also contain a big part of the code.

The reason why this mod does not have to be the first loaded mod for the HUD to work is because of the way the HUD is registered in PrimalGameData_BP_DinoBars (LoadedWorld event). The HUDClass of the GameMode is overwritten at runtime. This only works because other mods don't do this yet. However, if other mods start to use this technique as well, then the loading order will matter again because there can only be one HUD class. Possibly the better approach would be for mods to just create widgets and attach them to the existing HUD, if any. Only if no HUD class exists, one would have to be created. However, the main code for this mod is in the HUD class and would need to be moved elsewhere.

## Keyboard shortcuts
- [Alt] + [F5] or just [F5]: Displays the settings window. (F5 can be changed)
- [Alt] + [F6]: Toggle bars for wild dinos.
- [Alt] + [F7]: Toggle bars for tamed dinos.
- [Alt] + [F8]: Toggle minimalistic mode.
- [Alt] + [Numpad -]: Decrease the size of all bars by 10% to a minimum of 30%.
- [Alt] + [Numpad +]: Increase the size of all bars by 10% to a maximum of 300%.
- [Alt] + [Numpad /]: Decrease the display distance by 1000 to a minimum of 1000.
- [Alt] + [Numpad *]: Increase the display distance by 1000 to a maximum of 10,000.
- [Alt] + [Numpad 0]: Toggle filtering
- [Alt] + [Numpad 1-9]: Toggle filter group 1-9

## Credits
Rice, meat and fish icon:
Icon made by Adib Sulthon (https://www.flaticon.com/authors/adib-sulthon) from https://www.flaticon.com

Sea and dove icon:
Icon made by Freepik (https://www.freepik.com) from https://www.flaticon.com
