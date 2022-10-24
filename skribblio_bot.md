# Skribbl.io Automation Assisted Drawing Bot

**The Game:** Skribbl.io is a on online drawing game where a player is given three words to pick one from, and do their best to draw it. Players get points proportional to how quickly they guess, and the artist also gets more points if more people are able to guess. 

**How does it work?:** Built in Python, this bot utilizes custom google image search APIs as well as 2 siimple GUIs that are used to select the best of 3 words that are prompted to draw. It uses Selenium web automation library which controls an instance of Google Chrome. When it is the turn of the bot, the user controlling it types in the best of the words into the drawing prompt window that is open. After hitting enter, the user should then select the word that was just entered into the gui. After a few seconds, the 3 top image results of the prompt should open up, where the user can then select which one looks the best. The bot then begins to draw the image. 

**Image Analysis and Drawing:** This was the most difficult part. There is a limitation of 14 colors to draw in on Skribblio, so upon querying the Google images, it downloads the choice and converts the resolution to something that can be drawn more quickly. Each chunk of pixels is then put through a color rounding algorithm that picks the closest matching color that is available in Skribblio. When drawing, the bot skips white because often picture backgrounds are white and that is already the background of the drawing board. It starts with gray so that the image is usually outlined before starting to color in. It draws one color at a time to conserve time because there is a time limit to drawing. To help speed the bot up, there are a few efficiency tricks that I've used. When filling in a solid block of color, it recognizes the solid line and only fills in 30% of it. This usually isn't a problem as the resolution works best around 135px, and solids are obvious.

**Flaws and Potential Improvements:** The largest recurring problem seems to be finding the most accurate image that can be recognized. For example, if the word is movie. Searching movie might end up with results of movie posters, or something else that is trending at the time instead of just a camera. Part of this can be negated by adding "word art" to the beginning of the search to ensure that the pictures are very simple and recognizable. 


**How does it look? The prompt is papaya.**
<br>
<img src="images/drawing_prompt.png?raw=true"/>
<br>
Here's the window that opens up with the browser when the script starts. 
<br>
<br>
<img src="images/papaya_gui_selection.png?raw=true"/>
<br>
After hitting enter, it's time to pick that middle image because it looks the best.
<br>
<br>
<img src="images/papaya_start.png?raw=true"/>
<br>
It starts with the gray outline, it usually conveys a good beginning depiction of the object.
<br>
<br>
<img src="images/papaya_partial.png?raw=true"/>
<br>
As you can see it's started to fill in the colored parts, but not fully filled to keep things quick.
<br>
<br>
<img src="images/papaya_done.png?raw=true"/>
<br>
Here is the final drawing. Filled in and colored a little nicer than I could do by hand!
<br>
