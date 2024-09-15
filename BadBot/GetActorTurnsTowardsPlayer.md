This code is for looping for each actor class (that we specified). The main objective I created this function was to find our mainPawn/DefaultPawn.

![Screenshot 2024-09-14 224320](https://github.com/user-attachments/assets/5db73f10-93dc-4c1e-b2e0-20a4094da4ca)


This blueprint is for an actor(Self Blueprint) to turn/face the player. The blueprint works by searching for our pawn object, by looping through all pawn in the level. And by getting its index and creating a variable with it, we can get our default pawn (player/TargetPawn). Then in event tick we use "Find Look at Rotation" function and set our actor rotation with it so that the actor can turns towards the player.

![image](https://github.com/user-attachments/assets/1399c04c-c2d3-45a4-84a5-d29843696caa) 

This is the enhanced version of above. We add 2 seconds delay for the drone so that the drone has two seconds before turns to player. But adding delay to begin play will have a problem, that the event tick function won't retrieve the TargetPawn(default pawn) address. So there will be an error. To solve that. We added a validated get from the TargetPawn (activate it with right click the variable), so the process won't run until TargetPawn is valid. Then add interpolation to give the drone a smooth rotation when turns to us.

![image](https://github.com/user-attachments/assets/d041a491-a6b8-4bc4-acf6-76c4e0008572)

