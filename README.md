java c
31263 / 32004 Game Development
Lab Week 6
Getting Started
1. Download the corresponding week’s zip file from this week’s module on Canvas.
2. Unzip the project folder and open it in Unity. If there are any warnings about difference in versions, just continue. If this causes any red errors in the console once the project opens, notify the tutor.
3. Within the weekly folders there are image and executable files starting with “Status…”. These files give you a preview of what is expected for each point percentage below.
a. If you are on Mac and the Status-100Percent App file won’t run, hold control and click (right click) then select Open, if there is a security warning, acknowledge it an press open again.
i. If you still have trouble, you may need to change the permissions of the file with the following command in a Terminal window: chmod -R +x Status-100Percent-Mac.app/Contents/MacOS
b. If you are running the Windows executable on the lab computers, you need to copy the entire executable folder into Windows(C:)/Users//AppLockerExceptions.
From there you can double run the .exe file.
Tasks
Points                                                               Requirements
40%
• Open the project folder in Unity. Open Week6Scene if it is not already open.
• Create an empty GameObject called “Managers”.
• Open the TimeManager script. in the Scripts folder
• For every 1 second that passes, TimeManager should print the time since start of game as an integer seconds value.
o Tip: use a private member variable such as “int lastTime” to store the time value that was last printed. Then use Time.time in Update() to check if a full second has passed.
o Make sure that TimeManager starts printing from 0 (e.g. 0, 1, 2… etc).
▪ Tip: Consider an initial value of lastTime that would be overridden for Time.time = 0 in the first Update call.
• Attach TimeManager to the Managers gameobject.
There is no ProgressEvaluator for this week because it would give away the solutions to the activity. It is better for you to learn from a good challenge and check your own progress this week. Make sure you are looking at the Status-xPercent image files or ask your tutor to check your game is running as expected.
50% (P)
• In TimeManager, use Input.GetKeyDown(KeyCode) to detect when the Spacebar is pressed, which should do the following:
o Pause and unpause (tip: see Time.timeScale)
o Print to the console “Spacebar pressed”
o Note: Update() is still called but Time.time is no longer updated
60% (P)
• Instead of Time.time, change the code to use Time.deltaTime and a private variable called “timer”. Keep track of time by adding deltaTime to the timer (e.g. timer += Time.deltaTime;)
o The printing to console should still start from 0.
• On pressing the Enter (Return) key, the seconds timer should be reset to 0.
o The reset should take place in a new private method called ResetTime() to make this functionality easily re-usable. It should be called when the game starts and then whenever the Return key is pressed.
o ResetTime() should also reset all time related variables to their default values.
Reminder: Complete the COMPLETE-BEFORE-SUBMISSION.txt file before you submit. Otherwise, you will receive a mark of 0 .
70% (C)
• From the Prefab folder in the Project Window:
o Drag a RedPrefab into the Hierarchy Window, make sure the rotation is zeroed and set the position to (2,1,0)
o Drag a BluePrefab into the Hierarchy Window, make sure the rotation is zeroed and set the position to (-2,-1,0)
• In TimeManager:
o Create a serialized private Transform. array called transformArray. Select the Managers gameobject in the Hierarchy Window and change the size of the transformArray in the Inspector Window to 2. Drag the RedPrefab and BluePrefab instances from the Hierarchy Window into the array.
o Create a c# “constant” float member variable called “moveWait” and set it to 2.0f.
• From the Start() method of the TimeManager
o Change the camera view from “perspective” to “orthographic” (tip: see Camera.main and Camera.orthographic).
o Set the orthographic size of the main camera to 2.5f.
80% (D)
• In TimeManager, create a new private method called MoveObjects()
o Once every  seconds on the timer, move the colored objects in a synchronized square clockwise manner (e.g. when the timer prints out as 2 the RedPrefab should pop to (2,-1,0) and the BlueP代 写31263 / 32004 Game Development Lab Week 6
代做程序编程语言refab to (-2,1,0), then move again at 4 seconds).
o Challenge: Can you make it so that this movement can account for any starting positions of the two objects but assuming that there are only two objects to move and that they start with different x and y values? (not required, only for a fun and useful challenge)
▪ Rotation in this case is not around (0,0), but such that the red and blue gameobjects will be in each other’s initial positions after two MoveObject calls.
90% (HD)
• Create another const float called “scaleWait” and set it to 4.0f.
• Create the private method “ScaleObjects()” which should do the following to the transformArray elements:
o If an object’s local x scale value is greater than 1.5 then divide all scale values by 1.2.
o Otherwise, multiply all scale values by 1.2.
o Tip: see Transform.localScale
• In ResetTime(), use InvokeRepeating(…) to call ScaleObjects() once every  seconds.
• This behavior. should obey the Pausing and Reset functionality (tip: see CancelInvoke(…))
100% (HD)
• When the “Escape” key is pressed, TimeManager should generate a random value between (0.5, 1.0) and start the following coroutine (tip: see StartCoroutine()).
o “IEnumerator RotateObjects(float randomDelay){…}”
• This coroutine should wait for  seconds, then rotate the two game objects by positive 90 degrees around the z axis, then repeat 3 more times (e.g. wait-rotate-wait-rotate and so on. The objects turn a full 360 degrees before exiting the method) (tip: see WaitForSeconds(…))
• This should obey the Pausing functionality but not the Reset functionality (i.e. the objects should finish their full rotation).
• Try the Status-100% executables
o Press Escape to start the rotation
o Press Spacebar to pause the movement, scaling, and rotation
o Press Spacebar to un-pause everything
▪ If you do this a few times and your objects are rapidly changing size (i.e. not at 4 second intervals) then you are stacking Invoke calls (multiple scale invokes are running at the same time) and you need to go back and check the 90% section.
o Press Escape again and then Enter to reset the timer for movement and scaling but the rotation should continue
▪ If you press Escape multiple times and your objects are no longer rotating at even intervals or are popping back a forth between rotations then you are stacking coroutine calls – only one rotation coroutine at a time should be running.
• CLEAN, EFFICIENT, ELEGANT CODE!
Bonus
Submit your work on Canvas before continuing. Follow the instructions on the last page.
This part is optional. If you completed the above activity very quickly, try this. It is not graded, but it will enhance your skill.
• Merge you Week 5 solution into your Week 6 solution (or use the provided Week 5 Solution on Canvas instead)
• Remove the Update() methods from all of the Week 5 and 6 scripts
o Replace them instead with Coroutines that are started in Awake or Start.
o See if you can change the content of these so that they do the same thing as the old Update methods but in a different way.
• Note: This is definitely not a recommended thing to do!
o Do not re-invent the wheel – Unity already has a game cycle, you don’t need to make your own (a mistake a lot of people make when they first master Coroutines)
o However, this is a good exercise to show you the power of Coroutines and how all Unity Update() methods are essentially just Coroutines.
Submission
When you complete the activity to the grade threshold that you want, you then need to:
1. Evaluate your progress:
a. Make sure that you have run the “ProgressEvaluator” at the final band you achieved.
b. Not doing so is an indication that you are not evaluating and tracking your own learning.
2. Complete the plagiarism declaration:
a. Complete the “COMPLETE-BEFORE-SUBMISSION.txt” file in the highest level of the project folder.
3. Reduce file size:
a. Remove all files and folders starting with the “Status-…” prefix
b. Remove the “Library” folder
4. Preparing your zip file:
a. Zip the entire project folder.
b. Re-name the zip file to “[student ID]-LabWeek[week number].zip”.
5. Submit the zip file to Canvas for the associated link for this week in the Lab before Monday 9am of the following week.
6. Failure to follow any of these could result in a 0% mark for that week.









         
加QQ：99515681  WX：codinghelp
