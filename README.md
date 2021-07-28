# Shell Shockers aimbot
![螢幕擷取畫面 (274)](https://user-images.githubusercontent.com/62785735/127161083-303f3b47-44e6-472b-bcda-4837a93eac8b.png)
*This isn't an attempt to attack the game, but for education purposes only. If it ever gets too good, I'll take this down*

Thought it would be fun to write my own aimbot in this relatively simple first person shooter game. Since every enemy is an egg, and every egg is an enemy, I can detect enemies simpy by detecting egg shaped objects.
The steps are as follows

## Screenshots
For simplicity, a screenshot is taken only when the trigger key is pressed. It's then cropped out and blurred at unwanted items (i.e. my own gun).

## Color filter
Since there's only a few egg colors to choose from, I took samples of each egg colors, obtained their HSV values, and determined the margins of the HSV values that can be identified as each color 
![sample8](https://user-images.githubusercontent.com/62785735/127164032-238e26f1-0e99-4cb5-b6c6-6419078fd984.png)
![sample7](https://user-images.githubusercontent.com/62785735/127164060-5cc12c8d-5acb-4389-87a8-8ccd54ecf794.png) for this color, the HSV margin is somewhere around [10, 140, 60] and [20, 165, 250]

## Morphological transformation
After obtaining a mask for each egg color, I applied "opening" transformation with kernel size 3\*3 and 2 iterations, clearing up the false positive noises from the background. The mask for each egg colors are then unioned to get a mask for all enemy egg locations.
The cropped out screenshot![test_3](https://user-images.githubusercontent.com/62785735/127311441-44276454-9eb4-4f17-ab9e-72b51bc47846.png) 
Mask of all egg colors before mophological transformation![mask_0](https://user-images.githubusercontent.com/62785735/127311812-4cc917d7-a0f6-43fb-916b-0d523823af07.png) 
Mask of all egg colors after mophological transformation![mask_0](https://user-images.githubusercontent.com/62785735/127311992-173ead01-b131-4231-889a-2f1f7666e01a.png) 

## Hough circle detection
