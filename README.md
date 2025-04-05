# Development Commentary Template

How does the design of video game space affect the actions and experiences of players? Consider how different game spaces have been categorised in the literature and concepts of space and place discussed in the lecture.  

## Project Outline (Suggested Word Count 500) 
We aim to create a horror puzzle-platformer inspired by Supermassive Games' Little Nightmares 2. The game will feature one enviroment/room in which the player will have to solve puzzles to escape. It's concept will be closely tied to Little Nightmares 2 themes and will draw from a scrapped idea of 'The Barber'. The player will play as an imprisoned child who tries to escape their captivity in the barber shop. In order to prioritise quality and functionality, I will keep the mechanisms and puzzles simple. There will be four puzzles and two types of mechanisms (store and carry). The main anticipated challenges I may face are: ensuring a bug-free, smoothly-working game on an engine I am unfamiliar with; and working efficiently and productively with a team I have not met before. To help aid my development despite these challenges I will begin work early to ensure I have enough time to tackle any problems that arise and give my team the sufficient time needed for the to produce work also. 

## Research (Suggested Word Count 1,100) 

### Methodology  
To create an effective game that meets the criteria given, I will use Little Nightmares 2 as my main game source. I will collate aesthetic sources with my team to ensure an accurate atmosphere and art that aligns with the original aesthetic of the game; we will use a Figma board to display this research. I will do reseach into the mechanics used within the game and will recreate them using Unreal's blueprints system. I aim to create simple carry, drop and store mechanisms using help from online tutorials when needed. I also aim to create the sound and, as we do not have an animator, I aim to complete animations also. To organise our tasks and effectively monitor our progress will we use Trello. 

### Game Sources  
When researching Litle Nightmares 2, it became apparent that its horror-fueled tension relied on foul/disturbing atmospheres and spaces rather than sudden jumpscares and typical horror tactics. Therefore we decided to create a space that alligned with this idea. We've utalised grotesque and scary assets (e.g blood splatter, body parts, sharp utensils) and intense music/sound to mimic the atmosphere created in Little Nightmares 2. During research, I found the keybindings used within the game and decided to keep these similar to my game also. Through game testing it became apparent that the 'E' key was the most intuitive choice for 'interact', therefore I have kept this key as interact and also added the 'Q' key which was also used within the keybindings. Little Nightmares 2 uses a platformer-type camera system that has a 'handheld' movement. I have attempted to recreate this within the game.
*What Remains of Edith Finch* 

### Academic Sources  
Through research into game space it became apparent that keeping some areas hidden until the player explores them can increase suspense (Murray, 2020), therefore we have separated the room with curtains to keep areas unknown until entered. This allows the player to have autonomy over their progress within the space and allows them to feel a sense of self exploration as they uncover more of the enviroment. Video game space can also be used for 'enviromental storytelling'. This is a way for the player to unravel more of the narrative through the enviroment. (Fernandez-Vara, 2011). We have created an enviroment which slowly reveals more of the narrative context as the player plays. 
When tackling team work and organisation, the book *Agile Game Development* by Clinton Keith (Keith, 2021) addresses the importance of not prioritising personal goals above team goals. When creating our game we ensured that we worked with synergy and communicated often to achieve a shared outcome. 


### Documentation Sources  
I used multiple relevant video tutorials to aid my programming of different mechanisms. 
- Investigate relevant documentation, tutorials, or instructional videos that provide technical insights into your tasks. Summarise the content and its relevance to your project.  
- Explain how this technical knowledge supports your project work and guides your decision-making process.

## Implementation (Suggested Word Count 1,100)  

### Process
- Provide a step-by-step breakdown of your development process, including key milestones and decisions made throughout the project.  
- Highlight any tools, frameworks, or techniques used, and explain how they contributed to the implementation.  
- Include screenshots, diagrams, or code snippets where relevant to showcase your progress.

### New Approaches  
When developing the carry mechanism, I followed an online tutorial for guidance. It provided substancial help for creating the mechanism however I found that the objects carried would frequently collide with the player and cause movement issues. Additionally, the suggested skeletal socket for the objects to bind to was not optimal and resulted in many issues; the object would also change size and shape when carried. Therefore I created a new carry socket and turned physics and collisions off for the object. This then solved the collisions issue and I realised that the initial socket had been scaled up and this was affecting the size of the object. I also encountered a problem when developing the 'store' mechanism: I was unable to use the same carry socket for both mechanisms 


- Detail any innovative or new approaches you explored during the project.  
- Explain why these approaches were chosen and how they differ from standard practices.  
- Evaluate the success of these approaches, including any challenges faced and lessons learned.

### Testing
We performed blind and guided user testing during our eighth week of production where we would monitor and note any observations as the game was tested. We also provided a form for testers to complete post-testing to collate more in-depth, anonymous feedback. Positively, we found that 100% of testers found the game synonymous with the Little Nightmares 2 aesthetic and gameplay. We also found that 70% of testers understood and enjoyed the 'book' puzzle. However, testers were confused by the controls and struggled to understand them. We noticed most players intuitively used the 'E' key. Therefore, I added user interface widgets to indicate which controls to press and decided to place interactions on the 'E' key as this was the most intuitive. Game testing also highlighted various small bugs and issues that could arise during gamplay, therefore using breakpointing I was able to locate the issues within my code. Some testers noted that they struggled to understand where to progress through the game, however this was most likely due to the lack of assets within the game during the time of testing. Once the assets were inputted, I believe this problem is less apparent. 

*graph images here :)


### Technical Difficulties
- Identify any technical difficulties encountered during the implementation phase.  
- Provide details on how these issues were diagnosed and resolved.  
- If any difficulties remain unresolved, explain the impact on the project and any mitigation strategies used to minimise their effect.  
- Reflect on what you would do differently in future projects to avoid similar issues.

## Outcomes (Suggested Word Count 300) 

### Source Code/Project Files
- Provide a link to your complete source code or project files.  
- Ensure the link is publicly accessible or shared with the appropriate permissions.  
- Include a brief description of the files provided, highlighting key components or any instructions required to run the project.

### Build Link
- Share a link to a playable or executable build of your project.  
- Ensure the build is accessible across relevant platforms and is publicly accessible.  
- Include any necessary instructions for running the build, such as system requirements or installation steps.

### Video Demonstration
- Embed a video or provide a link to a recorded demonstration of your project in action.  
- The video should showcase key features, functionality, and any unique elements of your project.  
- Include a brief commentary or text overlay in the video to explain the different aspects of your project as they are shown.

## Reflection (Suggested Word Count 500) 

### Research Effectiveness  
- Assess the usefulness of the research conducted during the project.  
- Highlight which sources (games, academic, documentation) had the most significant impact on your work and explain why.  
- Identify any research gaps or areas where additional information could have improved your project outcomes.

### Positive Analysis 
On positive reflection, the game suitably fits the brief given and aligns well with the themes and aesthetics from Little Nightmares 2. The game succesfully features similar mechanisms and movement and the animations chosen work well within the enviroment. I was able to tackle difficult issues, such as create my own solutions to fix unefficient blueprints found online. I was also able implement sounds and animations without an animator. The decision to keep the project simple was successful as it enabled us to achieve everything we wanted and left room for additional implementations.

### Negative Analysis  
On negative analysis, the game still has small bugs and doesn't work as smoothly as I'd hoped. If given more time I would eliminate these bugs. Due to recieving the player asset later than anicipated, I had to rush the animations and footstep sounds which lead to them being not as polished. To eliminate this problem, I would ensure in pre-production deadlines for specific assets. The game also lacks fun which may have been improved by implementing a timer system or an enemy AI. However with the time given 

### Next Time
If I were to undertake a similar project I would ensure in pre-production that stricter team deadlines are set to avoid work being left until the latter weeks. This would prevent work from becoming stacked. I would also increase my workload in the first two weeks as those weeks were purely dedicated to pre-production and I could have utalised that time to develop. In pre-production, I would focus more on the game's enjoyability/entertainment value and explore programming enemy AIs and more ways to 'lose'/die.


## Bibliography  

**Academic Sources**

**Videos**
https://youtu.be/P-wbqMKFClk?si=XomIBOsRSP8s7Yd1
https://youtu.be/kB1_qxNUi9Q?si=IwZCXieHzy26Qq7q
https://youtu.be/m1sOZumo1M4?si=sGvccZp0fb57qRZb
https://youtu.be/m1sOZumo1M4?si=mVFv7AdQTmtOBrBC
https://youtu.be/qbgDaRo312k?si=M_C_cM5iYg3cR4od



**Games**




- Compile a complete list of all sources referenced throughout your project. This may include articles, journals, videos, games, software, documentation, or any other materials.  
- Ensure all references are formatted according to the [university's citation method](https://mylibrary.uca.ac.uk/referencing).  
- Organise your references in alphabetical order. Alternatively, you may separate them by type (e.g., academic sources, games, videos), but consistency is key.
