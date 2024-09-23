java c
31263 / 32004 Game Development
Lab Week 4
Getting Started
1. Download the corresponding week’s zip file from this week’s module on Canvas.
2. Unzip the project folder and open it in Unity. If there are any warnings about difference in versions, just continue. If this causes any red errors in the console once the project opens, notify the tutor.
3. Within the weekly folders there are image and executable files starting with “Status…”. These files give you a preview of what is expected for each point percentage below.
a. If you are on Mac and the Status-100Percent App file won’t run, hold control and click (right click) then select Open, if there is a security warning, acknowledge it and press open again.
i. If you still have trouble, you may need to change the permissions of the file with the following command in a Terminal window: chmod -R +x Status-100Percent-Mac.app/Contents/MacOS
b. If you are running the Windows executable on the lab computers, you need to copy the entire executable folder into Windows(C:)/Users//AppLockerExceptions.   From there you can double run the .exe file.
Tasks
Points                                                                                   Requirements
40%
Setting your Default Script. Editor
• Create a new C# script. called Test.
o In the Start method, start typing “Deb”
o You should have an auto-complete that says “Debug”. Select this, then start typing “.Lo” and select the Debug.Log() method.
 If this is not the case, follow the instructions in the Week 5 Module on Canvas to synch the Visual Studio IntelliSense Autocomplete with Unity.
o Finish this to be Debug.Log(“Test”);
• Attach this script. as a component of the MainCamera by dragging it onto the Camera.
50% (P)
Initializing a repository
• See this week’s lecture for hints on how to complete the following through Git Bash or explore it through the use of Sourcetree or GitHub (installed in the lab room).
o For ease of instruction and consistency, the below instruction are for Git Bash (or using Git in the Terminal if you are on Mac)
• Create a new repository on GitHub.com (or your git host of choice, such as BitBucket, GitLab, etc.)
• Initialize a local repository in the Unity Activity folder for this week (hint: see “git init”)
o This should be at the same folder level as the folders “Assets”, “Project Settings”, etc.
o This will create a hidden folder named “.git”. See next instruction on how to reveal hidden directories in your operating system.
• In the same directory as your “.git” folder, create a file called “.gitignore”
o The .git folder may be hidden in your file browser, and because .gitignore has a “.” at the start, it may also be hidden on Macs.
 In Windows, use the following instructions to show hidden files: https://support.microsoft.com/en-au/help/4028316/windows-view-hidden-files-and-folders-in-windows-10
 In Mac, in the terminal use “ls -a” (that is a lower case “L”) to show list hidden files.
o In the .gitignore file, paste the code from the following: https://github.com/github/gitignore/blob/master/Unity.gitignore
o This will ensure that certain unnecessary files will not be committed to your online repository, freeing up space and speeding up your commit process
• Add your GitHub repository as a remote of the local repository (hint: see “git remote”)
• Add all the files in the activity folder to the repository (hint: see “git add”)
• Commit all changes to the local repository (hint: see “git commit”)
• Push all the changes to the remote GitHub repository (hint: see “git push”)
o If you are using GitBash (the terminal) with a GitHub.com repository, you may get an error when you try to put in your login details. If so, you should follow the instructions in the following link to create a personal login token OR use GitHub Desktop instead (it will handle authentication for you) - https://docs.github.com/en/github/authenticating-to-github/keeping-your-account-and-data-secure/creating-a-personal-access-token
Set the ProgressEvaluator to band that you just completed (see left grey column) and press Play to test your progress for known errors.
60% (P)
Set the ProgressEvaluator’s “Band Reached” variable to “Deactivate” and continue with the lab.
Setting up prefabs and referencing them in scripts
• Create a new branch of your repository called “dev” by using “git checkout -b dev”.
• In Unity, open this week’s scene to begin developing.
• create a red material and a blue material and set their albedo accordingly
o Create two spheres in the scene, one with the red material, the other with the blue material.
o Now create two prefabs from these called RedPrefab and BluePrefab
o Delete the two sphere gameobjects from the scene.
• Right click in the Project Window and create a new C# script. called “LoadAssets”
• Open up the LoadAssets script.
• Create a public GameObject member variable called redObj of the LoadAssets class (i.e. outside of any method).
• Save the script. and return to the Unity window to auto-compile it.
• In the Hierarchy panel, create a new empty GameObject, rename it to “LoadManager”, set all position and rotation values to 0, set all scale values to 1, and add the LoadAssets script. as a component of this game object
• Assign the RedPrefab prefab to the redObj variable of the LoadAssets component of the LoadManager game object.
• Save your Unity scene (ctrl+s or cmd+s), then in your repository
o Add all the changes to your local repository (git add -A)
o Commit the changes to this branch (git commit -m “60 percent complete”)
o Push the changes (git push origin dev)
Set the ProgressEvaluator to band that you just completed (see left grey column) and press Play to test your progress for known errors.
• Open the ProgressEvaluator.cs file and uncomment (i.e. remove the // symbol) the line at the top that says #define Pass60
70% (C)
Set the ProgressEvaluator’s “Band Reached” variable to “Deactivate” and continue with the lab.
Instantiating Prefabs as GameObjects through code
• Create a private GameObject member variable called blueObj of the LoadAssets class but make it available to the Inspector View (tip: search SerializeField in Unity Docs).
• Open the LoadAssets script. again. When the game starts, the LoadAssets component should create a redObj at (2,0,0) and a rotation of zero and a blueObj at (-2,0,0) and a rotation of zero (tip: search Instantiate, Vector3, and Quaternion.identity in Unity Docs).
• Save the script, assign BluePrefab to blueObj on the LoadManager game object, and press play in Unity to see the results.
Setting a consistent frame-rate
• When the LoadAssets component is first run, use the method in the following documentation to limit the framerate to 60 frames per second.
o https://docs.unity3d.com/ScriptReference/Application-targetFrameRate.html
o If you have a reasonable powerful computer, this will slow down the game to help with seeing the output of the rest of the code in this activity.
• With your repository – add, commit, push
Set the ProgressEvalua代 写31263 / 32004 Game Development Lab Week 4R
代做程序编程语言tor to band that you just completed (see left grey column) and press Play to test your progress for known errors.
80% (D)
Set the ProgressEvaluator’s “Band Reached” variable to “Deactivate” and continue with the lab.
Printing GameObject properties
• Create and checkout a new branch in your local repository called “feature-print”
• In Unity, create a new script. called “ConsolePrint”
• Edit the RedPrefab and BluePrefab prefabs to have a ConsolePrint component.
• For every frame, the ConsolePrint script. should print the following “GameObject’s name:i”
o “GameObject’s name” is the name of the game object that the component is attached to.
o “i” is an integer that is set to 3 at the start of the game and increments by 1 at the start of every frame. (i.e. the first Debug.Log statement should say 4 on it).
o There should be no white-spaces in this string
• Press play in Unity and observe what happens.
• In your repository – add, commit, push
Set the ProgressEvaluator to band that you just completed (see left grey column) and press Play to test your progress for known errors.
90% (HD)
Set the ProgressEvaluator’s “Band Reached” variable to “Deactivate” and continue with the lab.
Renaming files, referencing components, and using tags
• Change the name of ConsolePrint in the Project Window to “PrintAndHide” and fix any errors that arise.
• In PrintAndHide make the member variable “public Renderer rend”.
o Select RedPrefab in the Project Window, then drag it onto its own PrintAndHide.Rend reference.
o Repeat the above for BluePrefab.
• Create a new Tag called “Red” and change the RedPrefab tag to this.
• Create a new Tag called “Blue” and change the BluePrefab’s tag to this.
• In your repository
o Add, commit, push the “feature-print” branch
o Checkout the “dev”
o Merge “feature-print” into “dev” (hint: see “git merge”)
o Push the “dev” branch
Set the ProgressEvaluator to band that you just completed (see left grey column) and press Play to test your progress for known errors.
• Open the ProgressEvaluator.cs file and uncomment (i.e. remove the // symbol) the line at the top that says #define HD90
• The Console Window is going to get spammed (and this is needed for the ProgressEvaluator)
o Make sure you are looking at the top right of the Console window to see if there are any red exclamation marks (errors).
o Click the white exclamation mark (normal log output) to hide the output coming from your PrintAndHide script. if needed to see the ProgressEvaluator yellow and red messages easier.
100% (HD)
Set the ProgressEvaluator’s “Band Reached” variable to “Deactivate” and continue with the lab.
Deactivating GameObjects and Disabling Components
• Create and checkout a new repository branch called “feature-hide”
• In the PrintAndHide script.
o If the Tag of the game object is “Red” and i = 100, deactivate the game object.
o If the Tag of the game object is “Blue” and i = a random integer between 150 and 250 (inclusive of the numbers 150 and 250) which is generated when the game starts, disable the Renderer component of this object.
• Press play in Unity and observe what happens, especially in the console.
• In your repository
o Add, commit, push the “feature-hide” branch
o Checkout the “dev” branch a merge “feature-hide” into it
o Push the dev branch
o Merge the “dev” branch into the “master” branch and push the master branch
• View your git commit tree (in git bash, you can use gitk or see the GitHub online project page under “Commits” to see the tree)
o Compare it with the one on the next page
o You will not be marked down in this activity if does not look like this, but if it doesn’t, try to analyze where and why it went wrong.
CLEAN, EFFICIENT, ELEGANT CODE!
Set the ProgressEvaluator to band that you just completed (see left grey column) and press Play to test your progress for known errors.
• Make sure to wait until you see the message “PROGRESS EVALUATOR: HD100 Band: No common mistakes found”.
• This should occur sometime before frame. 300.
Bonus
Submit your work on Canvas before continuing. Follow the instructions on the last page.
This part is optional. If you completed the above activity very quickly, try this. It is not graded, but it will enhance your skill.
Assemblies
• While your code is likely compiling quite fast at the moment, this will become much slower as you add more scripts.
o Every time you change one script, Unity re-compiles everything! Imagine how bad this gets when you have ten’s of thousands lines of code spread across dozens of script. files.
o If you’ve been using Unity for a few years, you’ll also notice that a new dialog box pops up during compilation saying “Reloading script. assemblies”
• So what are “Assemblies” and how can they speed up your compile speed?
o In short, they are C# code packages (also know as Dynamic Linked Libraries or DLL’s). They allow logically linked code to be packaged/assembled together and left untouched during compilation unless any of the code in that assembly has changed.
o Look into assemblies more at
https://docs.unity3d.com/Manual/ScriptCompilationAssemblyDefinitionFiles.html and find tutorials such as https://youtu.be/eovjb5xn8y0
o Add a few extra dummy C# scripts to your project (you can pull some from past week’s lab activities)
o Then begin to organize them into assemblies
o Depending on your computer hardware and the number of lines of code you have in your project, you may or may not notice a speed difference.
o Regardless, keep this technique in mind when you are working on your Assessment 3 and 4 or on projects in 31262/32003 Introduction to Computer Game Design, 31102 Game Design Studio 1, or the Playmakers Dev Team extracurricular project.
Git Repo Tree
Each circle is a commit. Circles with a percent show when they should have been committed. Circles with a “M” are when a merge occurred and an auto-commit was made. If your Git Tree looks more flat (like a single line) that is fine, just make sure that the tag for each branch stops at its highest commit or merge point.

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
