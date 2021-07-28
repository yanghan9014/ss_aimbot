# Shell Shockers aimbot
![螢幕擷取畫面 (274)](https://user-images.githubusercontent.com/62785735/127161083-303f3b47-44e6-472b-bcda-4837a93eac8b.png)
*This isn't an attempt to attack the game, but for education purposes only. If it ever gets too good, I'll take this down*

Thought it would be fun to write my own aimbot in this relatively simple first person shooter game. It's a crude attempt expoiting the simplicity of the graphics of enemy eggs.
The steps are as follows

## Screenshots
For simplicity, a screenshot is taken only when the trigger key is pressed. It's then cropped out and blurred at unwanted items (i.e. my own gun).

## Color filter
Since there's only a few egg colors to choose from, I took samples of each egg colors, obtained their HSV values, and determined the margins of the HSV values that can be identified as each color 
![sample8](https://user-images.githubusercontent.com/62785735/127164032-238e26f1-0e99-4cb5-b6c6-6419078fd984.png)
![sample7](https://user-images.githubusercontent.com/62785735/127164060-5cc12c8d-5acb-4389-87a8-8ccd54ecf794.png) for this color, the HSV margin is somewhere around [10, 140, 60] and [20, 165, 250]

## 
