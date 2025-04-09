# Development Commentary 

**Chosen question:** How does the design of video game space affect the actions and experiences of players? Consider how different game spaces have been categorised in the literature and concepts of space and place discussed in the lecture.  

## Project Outline 
We aim to create a horror puzzle-platformer inspired by Supermassive Games' Little Nightmares 2 *(Little Nightmares 2, 2021)*. The game will feature one environment/room in which the player will have to solve puzzles to escape. It's concept will be closely tied to Little Nightmares 2 themes and will draw from a scrapped idea of 'The Barber'. The player will play as an imprisoned child who tries to escape their captivity in the barber shop. In order to prioritise quality and functionality, I will keep the mechanisms and puzzles simple. There will be four puzzles and two types of mechanisms (store and carry). The main anticipated challenges I may face are: ensuring a bug-free, smoothly-working game on an engine I am unfamiliar with; and working efficiently and productively with a team I have not met before. To help aid my development despite these challenges I will begin work early to ensure I have enough time to tackle any problems that arise and give my team the sufficient time needed for the to produce work also. 

## Research  

### Methodology  
To create an effective game that meets the criteria given, I will use Little Nightmares 2 as my main game source. I will collate aesthetic sources with my team to ensure an accurate atmosphere and art that aligns with the original aesthetic of the game; we will use a Figma board to display this research. I will do research into the mechanics used within the game and will recreate them using Unreal's blueprints system. I aim to create simple carry, drop and store mechanisms using help from online tutorials when needed. I also aim to create the sound and, as we do not have an animator, I aim to complete animations also. To organise our tasks and effectively monitor our progress will we use Trello. 

### Game Sources  
When researching Little Nightmares 2, it became apparent that its horror-fuelled tension relied on foul/disturbing atmospheres and spaces rather than sudden jump scares and typical horror tactics. Therefore we will create a space that aligned with this idea. We will utilise grotesque and scary assets (e.g. blood splatter, body parts, sharp utensils) and intense music/sound to mimic the atmosphere created in Little Nightmares 2. During research, I found the key bindings used within the game and will keep these similar when assigning key bindings in my game.  Little Nightmares 2 uses a platformer-type camera system that has a 'handheld' movement, I will attempt to recreate this within the game.

![Screenshot 2025-04-09 154017](https://github.com/user-attachments/assets/2fdefd3a-494b-4a1a-8703-62d45058e1a8)

Figure 1. Figma board showing shared game research.


### Academic Sources  
Through research into game space it became apparent that keeping some areas hidden until the player explores them can increase suspense (Murray, 2020), therefore we will separate the room with curtains to keep areas unknown until entered. This will allow the player to have autonomy over their progress within the space and allow them to feel a sense of self exploration as they uncover more of the environment. Video game space can also be used for 'environmental storytelling'. This is a way for the player to unravel more of the narrative through the environment. (Fernandez-Vara, 2011). We will create an environment which slowly reveals more of the narrative context as the player plays. 
When tackling team work and organisation, the book *Agile Game Development* by Clinton Keith (Keith, 2021) addresses the importance of not prioritizing personal goals above team goals. When creating our game we will ensure that we work with synergy and communicate often to achieve a shared outcome. 


### Documentation Sources  
Throughout my development process I used multiple online video tutorials to aid me. To create the desired camera I used (How to Make A (Organizer) Puzzle in Unreal Engine 5, 2022). This source was quick, efficient and helpful. To help create my main carry mechanism I used (How to Carry Physical Objects in Unreal Engine 5 (2023)), this source provided helpful insight however I encountered many issues which I then had to solve myself; further detail of how I solved the issues is found in [New Approaches](###-New-Approaches). The source which helped me create the 'book' puzzle was the most helpful source I used during development (How to Make A (Organizer) Puzzle in Unreal Engine 5 (2022)). This source showed me a simple way to create a sorting puzzle using colour variables. More detail can be found in [Process](###-Process). To help me with animations I used (How To Make An Animation Blueprint In Unreal Engine 5.1 | How To Animate A Character - UE5 Tutorial (2023)). This source aided me in creating blend spaces that smoothly transitioned animations depending on the players speed and then showed me how to incorporate these into an animation blueprint. I then learnt to use a state machine to help program when the game should transition between animations (e.g. when the player is falling, play falling idle).



## Implementation 

### Process
I began by replicating the platformer-type camera seen in Little Nightmares 2 and adjusting the controls to suit. I then decreased player speed and jump velocity to be more reflective of Little Nightmares 2. Next I implemented a crouch mechanism. My next priority was to program the mechanisms needed. Originally I had chosen to use a push-pull system, similar to the original game, however this presented technical difficulties and did not work optimally with the size and shape of the objects needed to be moved. Therefore, I created a carry and drop mechanism for the player to move objects. This works by attaching the object to the carry socket on the player's skeletal mesh when the player holds left click and when they release, it unbinds the object and places it in front of the player. I used the tag 'carriable' on all objects that could be carried to ensure only those objects could be picked up. I also used a boolean of IsCarrying to ensure the player could not carry two objects at once. I then realised I would need a type of storing system to store objects which needed to be held by the player at the same time they carried another. I created a similar system in which the object with the correct tag would be attached to the store socket on the skeletal mesh using the E key.

<iframe src="https://blueprintue.com/render/qbe2c_4f/" scrolling="no" allowfullscreen></iframe>

Figure 2. [BlueprintUe](https://blueprintue.com/render/qbe2c_4f/) Carry mechanism

After these mechanisms, I began the 'book' puzzle in which the player must place each utensil in the correct position to unlock the drawer. To do this, I followed a tutorial in which I learnt to use correlating colour variables. Each object and placement area was given a hex code and if those codes matched, the correct variable would be true. Once every placement area had matched to an object the drawer would open and set a new location for the key and hammer also. I then began programming the climb and escape. Once storing the hammer and overlapping the escape area, the player can press Q to escape. Using time line, the player's Z position changes over 4 seconds to simulate the climbing of the wall. I developed a similar program for the lock and key. The door swings open when the player is storing the key and presses E. I used time line for this with a different graph shape to create a more accurate movement for the door. 

<iframe src="https://blueprintue.com/render/fj-s93a3/" scrolling="no" allowfullscreen></iframe>

Figure 3. [BlueprintUE](https://blueprintue.com/render/fj-s93a3/) Colour matching system 


After game testing, I implemented UI widgets to indicate which controls to press and highlight the interactables. The widgets appear when the player is near the object and disappear when the overlap ends. However, I was unable to solve an issue in which the widget shows on the item as it is carried. I also implemented 'need key' and 'need hammer' widgets when the player attempts to interact without the hammer or key. This will help reduce confusion we observed in play testing surrounding the key and hammer's functions.  

<iframe src="https://blueprintue.com/render/cywzqb4v/" scrolling="no" allowfullscreen></iframe>

Figure 4. [BlueprintUE](https://blueprintue.com/render/cywzqb4v/) Widget system

Post game testing, I inherited the scales puzzle from my designer and used time line once again to change the rotation of the scales when the platform overlaps the jar. This puzzle is temperamental and, if given more time, I would've improved it by having the scales affected by all objects including the player.

Upon receiving the rigged player asset, I used Mixamo (Mixamo, s.d.) to create animations and followed tutorials on how to implement these in game. I created multiple blend spaces to smoothly transition animations based on the player's speed, then used an animation blueprint to program these into the game play.  


https://github.com/user-attachments/assets/630b1971-fc4e-4ff2-89a6-cf3e043e1e65


Figure 5. Animations in game


I then created an ambient score for the main level and implemented 3D sound effects throughout using sound attenuation. 

Throughout the process I was also imputing assets and materials as I received them.

<iframe src="https://blueprintue.com/render/2ji4f5nu/" scrolling="no" allowfullscreen></iframe>

Figure 6. [BlueprintUE](https://blueprintue.com/render/2ji4f5nu/) Material creation using 3 images from artists.

### New Approaches  
When developing the carry mechanism, I followed an online tutorial for guidance (How to Carry Physical Objects in Unreal Engine 5, 2023). It provided substantial help for creating the mechanism however I found that the objects carried would frequently collide with the player and cause movement issues. Additionally, the suggested skeletal socket for the objects to bind to was not optimal and resulted in many issues; the object would also change size and shape when carried. Therefore I created a new carry socket and turned physics and collisions off for the object. This then solved the collisions issue and I realised that the initial socket had been scaled up and this was affecting the size of the object. I also encountered a problem when developing the 'store' mechanism: I was unable to use the same carry socket for both mechanisms and after discussing with my peers I decided to create a new socket on the player's back to store objects. I then adjusted this mechanism slightly to recognise which object the player was storing so that when opening the door or escaping the room, those events would only occur if storing the correct object. 


### Testing
We performed blind and guided user testing during our eighth week of production where we would monitor and note any observations as the game was tested. We also provided a form for testers to complete post-testing to collate more in-depth, anonymous feedback. Positively, we found that 100% of testers found the game synonymous with the Little Nightmares 2 aesthetic and game play. We also found that 70% of testers understood and enjoyed the 'book' puzzle. However, testers were confused by the controls and struggled to understand them. We noticed most players intuitively used the 'E' key. Therefore, I added user interface widgets to indicate which controls to press and decided to place interactions on the 'E' key as this was the most intuitive. Game testing also highlighted various small bugs and issues that could arise during game play, therefore using break pointing I was able to locate the issues within my code. Some testers noted that they struggled to understand where to progress through the game, however this was most likely due to the lack of assets within the game during the time of testing. Once the assets were inputted, I believe this problem is less apparent. 

 ![AestheticData](https://github.com/user-attachments/assets/5846c8f7-4033-440e-bd70-3f8930f99112) 
 
 Figure 3. Graph showing 100% positive feedback data.


 ![ControlsData](https://github.com/user-attachments/assets/99abe8c8-05a2-43f7-94cc-11e7883345ce) 
 
 Figure 4. Graph showing multiple opinions and confusion on controls. 
 

### Technical Difficulties
When beginning my project in Unreal, I encountered an issue with file management and organisation. I had duplicated each folder which lead to me and my designers saving work in different and unorganised places. I solved the issue by deleting copies with the least references. To prevent this issue in the future, I will organise my folders into static and dynamic before beginning my development process. 

Due to my lack of packaging throughout my development, I encountered many problems when trying to package before the deadline. I found disabling unneeded plugins and using IsValid nodes helped solve the errors.Breakpointing and using development only strings allowed me to highlight which nodes were causing errors and issues. I will package my project frequently next time I complete a similar assignment to avoid this occurring with little time to spare near the deadline. 


## Outcomes

### Source Code/Project Files
[GitRepository](https://github.com/zefst/ClientBrief) Project found in main branch under ClientBrief.uproject.


### Build Link
[GameBuild](https://zefst.itch.io/littlebarbers)
Accessable for Windows.

### Video Demonstration
[VideoDemo](https://youtu.be/BTN0nVBivxA) Video walkthrough of game demonstrating puzzles and general game play.

## Reflection 

### Research Effectiveness  
The research into Little Nightmares 2 was very useful; it provided aesthetic and game play references which eased our production process. It also aided me in choosing appropriate animations, mechanisms and key bindings. The video tutorials also had signifigant impact on my creation of different mechanisms. Although not copied exactly, they served as a template and inspiration for my own blueprints. Through my video research I was able to learn multiple ways of programming a mechanism and could combine them for the best outcome. However, some tutorials proved to be unhelpful and consumed my time as I tried to fix them. In the future, I will try to program mechanisms myself to ensure the exact mechanism wanted is created and time isn't wasted. I originally attempted a push and pull mechanism using an online tutorial (Push and Pull Objects System on UE5 - Tutorial, 2023) however I found this source was ineffective for the specifics of my game. My objects needed to be moved were too small and did not work with the method shown in this source. 


### Positive Analysis 
On positive reflection, the game suitably fits the brief given and aligns well with the themes and aesthetics from Little Nightmares 2. The game successfully features similar mechanisms and movement and the animations chosen work well within the environment. I was able to tackle difficult issues, such as create my own solutions to fix inefficient blueprints found online. I was also able implement sounds and animations without an animator. The decision to keep the project simple was successful as it enabled us to achieve everything we wanted and left room for additional implementations. Working with my peers was successful; I communicated often and met deadlines set to ensure work would be done on time.

### Negative Analysis  
On negative analysis, the game still has small bugs and doesn't work as smoothly as I'd hoped. If given more time I would eliminate these bugs. The scales puzzle works temperamentally and the widgets do not display perfectly. Due to receiving the player asset later than anticipated, I had to rush the animations and footstep sounds which lead to them being not as polished. To eliminate this problem, I would ensure in pre-production deadlines for specific assets. The game also lacks fun which may have been improved by implementing a timer system or an enemy AI. 

### Next Time
If I were to undertake a similar project I would ensure in pre-production that stricter team deadlines are set to avoid work being left until the latter weeks. This would prevent work from becoming stacked. I would also increase my workload in the first two weeks as those weeks were purely dedicated to pre-production and I could have utilised that time to develop. In pre-production, I would focus more on the game's enjoyability/entertainment value and explore programming enemy AIs and more ways to 'lose'/die. Additionally, I would increase the game testing as the feedback we gained was very valuable and record the sessions for more in depth analysis. I would've also added more SFX to increase the realism of the game and used sound related mechanisms.

## Bibliography  


#### Academic Sources
Fernandez-Vara, C. (2011) 'Game Spaces Speak Volumes: Indexical Storytelling' In: MIT web domain At: https://dspace.mit.edu/handle/1721.1/100274.

Murray, S. (2020) 'Horizons Already Here: Video Games and Landscape' In: Art Journal 79 (2) pp.42–49.

#### Audio
Metal 3.wav by chevyskulls (s.d.) At: https://freesound.org/people/chevyskulls/sounds/505640/ ​#

fluorescent light hum buzz1.flac by kyles (s.d.) At: https://freesound.org/people/kyles/sounds/637541/ ​

FX_metalic_clang_contact_04designedAtmos by NapierFreesound (s.d.) At: https://freesound.org/people/NapierFreesound/sounds/710855/ ​

Footsteps on tile by ChloePieterse (s.d.) At: https://freesound.org/people/ChloePieterse/sounds/764530/ 

grandfather clock tick in case 1.wav by urbaneguerilla (s.d.) At: https://freesound.org/people/urbaneguerilla/sounds/161443/ (Accessed  08/04/2025).


#### Games
Little Nightmares 2. (2021). PC [Game]. Minato City, Bandai Namco Entertainment.  

#### Other Sources

Mixamo (s.d.) At: https://www.mixamo.com/#/ .

#### Videos

How to Carry Physical Objects in Unreal Engine 5 (2023) At: https://www.youtube.com/watch?v=bCAlowYEYEI 

How To Create Footsteps In Unreal Engine 5 (Tutorial) (2022) At: https://www.youtube.com/watch?v=P-wbqMKFClk

How To Make An Animation Blueprint In Unreal Engine 5.1 | How To Animate A Character - UE5 Tutorial (2023) At: https://www.youtube.com/watch?v=qbgDaRo312k 

How to Make A (Organizer) Puzzle in Unreal Engine 5 (2022) At: https://www.youtube.com/watch?v=m1sOZumo1M4 

How to Make a 3D Sound in Unreal Engine 5 (2022) At: https://www.youtube.com/watch?v=dttUv6--1nA 

How To Make A 3D Interaction Prompt In Unreal Engine 5 (Tutorial) (2023) At: https://www.youtube.com/watch?v=kB1_qxNUi9Q 

Push and Pull Objects System on UE5 - Tutorial (2023) At: https://www.youtube.com/watch?v=v3JXpF4wl_o (Accessed  09/04/2025)

Unreal Engine - Side Scroller Camera Tutorial (2023) At: https://www.youtube.com/watch?v=659FjVeibv0 

Unreal Engine 5 Tutorial - How to Crouch (2022) At: https://www.youtube.com/watch?v=0DQJkzLqCLk 
