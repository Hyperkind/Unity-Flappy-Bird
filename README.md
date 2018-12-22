Assets: http://bit.ly/flappybirdstyle

Getting Started
1. Create new 2D project
2. Name it (name)FlappyBird
3. Import assets downloaded
    1. Can just drag and drop into assets folder
4. In sprites folder select BirdHero
5. Change sprite mode to multiple
6. Open Sprite Editor
7. Click slice
8. Click Apply
9. When you expand bird hero, there should be 3 separate sprites
    1. Will be used for bird animation
10. Move BirdHero_0 to hierarchy
11. Reset birdhero to origin
12. Move grass sprite to hierarchy
13. Rename to Ground
14. Position ground field at bottom
    1. -2.5 should be good
15. Rename to Sky
16. Move sky sprite and add as child to ground
    1. 3.5 should be good
17. Select Sky sprite in hierarchy
18. On sorting layer, select add sorting layer
19. Create 3 new layers
    1. Background
    2. Midground
    3. Foreground
20. Select SkyTemplate and add sorting layer background
21. Select Ground and add sorting layer foreground
22. Sky should now be behind the ground
23. Select Bird set sorting layer foreground
24. Save scene & project
25. Add rigidbody 2D to bird
26. Add polygon collider 2D to bird
27. Add box collider 2D to ground
    1. Edit collider and adjust size of y to match the ground
28. Test
    1. Bird should now fall and land on ground
29. Save scene & project

Bird Scripting
1. Click bird and add script component
2. Name script Bird
3. In project folder create new folder called scripts
4. Move bird script into scripts folder
5. Open Bird Script
6. Live Code Bird Script part 1
7. Save & test
    1. Students should now be able to have bird flap with mouse button
8. Save scene & project

Bird death on ground touch
1. Return to Bird Script
2. Live Code Bird Script part 2
    1. Command + ‘ when selecting OnCollisionEnter2D
    2. This runs when Game Object this is attached to collides with another collider
3. Save & test
    1. Bird should not be able to fly after touching ground
4. Save project & scene

Animating the bird
1. In project folder, create new folder called Animation
2. Select Bird game object
3. Open window > animation > animation
4. Dock animation on scene view window to save space
5. Click Create button
6. On save window, make sure that it is saving to project
7. Name the first animation Idle
8. Save to Animation folder
    1. In animation folder, students will see two new files created
    2. In Inspector for bird, there will be a new Animator component
9. With bird selected, click add property
10. Navigate to Sprite Renderer > sprite
11. Click + button next to sprite
12. Delete 2nd keyframe (diamond) in animation window
13. Drag select the 1st keyframe of the bird animation and copy it (diamond will be blue)
    1. Edit > Copy
14. Create a new animation
    1. Click on Idle > Create New Clip
15. Name new animation Flap
16. Save to animation folder
17. Click in the empty animation window and paste
    1. Edit > Paste
18. Check if record button in animation window is selected
    1. Sprite box in sprite renderer will also be highlighted red
19. Expand BirdHero in project folder
20. Drag and drop BirdHero_1 onto red sprite box to apply sprite
21. Repeat steps 14 - 20 and name new animation Die
    1. Use BirdHero_2 for new Die sprite
22. Add Animator window if it did not get added when adding Animation frame
    1. Window > Animation > Animator
    2. Move Animator window next to Animation window
    3. Students will see Idle, Die and Flap animations listed
    4. Entry will already be linked to Idle
23. On left side of Animator window click the Parameters tab
24. Add a new Trigger Parameter called Flap
25. Add a 2nd Trigger Parameter called Die
26. Right click on Idle, select Make Transition and click on Die
27. Click on new line that appears
28. Uncheck Has Exit Time
    1. This will prevent Die animation from displaying automatically
29. Add a new condition
30. Change the dropdown to Die
31. Right click Idle > Make Transition and link to Flap
32. Select line linking to flap
33. Uncheck Has Exit Time
34. Add new condition Flap
35. Right Click Flap > Make Transition and link back to Idle
    1. Leave Has Exit Time Checked
36. Test
    1. With animator window open click the button on Flap
        1. Bird will flap wings and go back to idle animation with the keyframes set up
    2. Click the Die button and die animation will set
        1. Unable to get back to idle since there is no transition back to idle from Die
37. Save scene & project
38. Open Bird Script
39. Live code Part 3
40. Save & Test
    1. Flap animation and die animation should play
41. Save Scene & Project

Score & GameOver UI Setup
1. Close Animation & Animator tab
2. On scene tab, zoom out to see outside of the game view
3. Add UI Text game object
4. With text selected mouse over Scene and press F to focus on the UI game object
    1. Students will see that it is much larger than game. Do not worry about this
5. Set Text to “Score: 0"
6. Set Font Size to 32
7. Set Font using imported font
8. Set Horizontal and Vertical Overflow to Overflow
9. Using anchor presets hold Alt key and click the bottom alignment
10. Set Rect Transform Y for text to 50
11. Add new shadow component to text
12. Set Effect Distance x 1.8 Y -1.68
13. Rename To ScoreText
14. Duplicate the Text Game Object and rename to GameOverText
15. Update Text to Game Over
16. Using Anchor Presets position at center top
17. Set Rect Transform Pos Y to -50
18. Duplicate Score Text again and move it to be a child of GameOverText
19. Rename to RestartText
20. Using Anchor Presets, Hold Alt & Set to Middle top
21. Use Rect Transform Pos Y and adjust to be lower than GameOverText
22. Click on GameOverText and disable the UI component for now with the checkbox next to the name
23. Save Scene & Project

Adding Game Controller
1. Create new Empty Game Object
2. Rename to GameController
3. Add new script to GameController game object called GameController
4. Move script to scripts folder
5. Open up GameController script
6. Live code GameController script
7. Live code Bird script part 4
8. Test
    1. Let bird die, GameOverText and RestartText will appear on death
9. Save scene & project
10. Return to GameController script
11. Live code Part 2
12. Text
    1. When bird dies, able to flap and it will reset again
13. Save scene & project

Scrolling Repeating Background
1. Select Ground
2. Add Rigidbody 2D component to Ground
3. Set Body Type to Kinematic
    1. Does not get affected by Gravity
4. Create new script and name it ScrollingObject
5. Move ScrollingObject script to Scripts folder
6. Open ScrollingObject script
7. Open GameController script
8. Live code ScrollingObject script
9. Live code GameController part 3 script
10. Save scripts & test
    1. Bird will fly and background will stop on death
    2. Background will not repeat for now
11. Save scene & project
12. Click Ground
13. Duplicate Ground and rename to Grass 2
14. Create new empty game object
15. Reset Scenery to origin
16. Rename to Scenery
17. Move Grass & Grass 2 into Scenery
18. Select Grass 2
19. Copy Size X from Box Collider 2D
    1. Should be 20.48
20. Paste into Transform Position X on Grass 2
    1. It will now extend the background
21. Select Grass & Grass 2
22. Add new script
23. Name script RepeatingBackground
24. Move RepeatingBackground to scripts folder and open
25. Live code Bird script part 5
26. Save & Test
    1. When playing, ground & background will now reposition to end of next game object to simulate endless background
    2. When player dies, both ground game objects stop
    3. Bird should not slide on ground
27. Save scene & project

Adding Columns