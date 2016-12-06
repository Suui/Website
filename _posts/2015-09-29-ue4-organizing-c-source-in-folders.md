---
layout: post
title: "[UE4] Organizing C++ Source in Folders"
---

I always want to have my code nicely organized in a folder hierarchy. I am usually able to do it in Visual Studio by turning on "Show All Files" in the Solution Explorer. However, with Unreal Engine 4 it's way trickier. Let's remember that the VS Filters are non-existent in the Operating System, they are just a tool for organizing code in the IDE, not outside it.

The engine's source and your games' source are spread across multiple locations. I can't even see the "Show All Files" option. Plus, adding folders through the Add Code to Project options probably does some work on the back to get it ready for you, it also creates a VS Filter for it.

So, I tested out the effects of different ways to add / remove / rename and relocate folders and files in UE4, with the 4.7.6 version, and I'll leave here the procedures to accomplish those tasks as researched by myself. I would ***greatly appreciate any feedback on this***, there may be easier ways to get things done that I'm totally unaware off.

### Creating a Folder
* Should **always** be done through the Add Code to Project.
* This will generate a Folder in the OS and an equally named Filter in VS.
* You may find the folder name in the **UnrealHeaderTool.manifest** of your project, somewhere in the end (if it contains an inherited UE4 class).
* For the Content Browser to show the folder, it **must** inherit from a UE4 class (in other words, not inheriting from None).
* Not inheriting from a UE4 class is OK with folders, the only thing is it won't show in your Content Browser, but it's there.

### Renaming a Folder
* Renaming the filter in VS has **no** effect whatsoever.
* You **can't** rename it in the Content Browser.
* Your only way is to rename it in the OS.
* After renaming, **recompile** in UE4!
* You will see the changes in the Content Browser, recompilation may last longer than usual (quite longer for me).
* After renaming the folder, VS **won't** recognize the files that were inside.
* **Remove** the filter in VS and everything inside. This action **won't** delete your files (be sure to **remove**, not delete the files if asked by VS, although I believe in the UE4 solution it won't let you delete, a confirmation window will just ask you if you want to remove them or not).
* **Create** a new filter, named as the folder, and Add Existing Item to it, selecting the C++ files in the renamed folder.
* Everything should be correct, Intellisense working fine, files opened in VS fine, changes seen in the OS and the Content Browser.

### Deleting a Folder
* Delete the Folder in the OS and the corresponding filter in VS.
* Recompile in UE4. Beware of the possible compilation errors if you had dependencies.
* When it compiles, you may still see the classes in the Content Browser.
* Reload your project in UE4 and it should fix it.

### Creating a Class
* I always do it through the Add Code to Project, but the main reason for it has to do with the folder creation. I guess that creating classes with a template is perfectly fine.

### Renaming a Class
* This usually causes a problem with the Blueprints that derived from that class.
* You can prevent this, by opening every derived Blueprint **before** renaming the class and file.
* After renaming, compile from the editor, **don’t' close** the derived Blueprints!
* Once the compilation is successful, get to every Blueprint and reparent them.
* You may see both classes: The one before renaming, and the one after.
* Be sure to reparent to the newly named one!

**Problem:** Somehow you have a None derived Blueprint!
* You need to redirect the old class name to the new one in order to be able to open the Blueprint.
* Go to your project folder in the OS, you should find **DefaultEngine.ini** in the Config folder.
* Go ahead and edit it. No fears!
* Under **[/Script/Engine.Engine]** add the following:
* **+ActiveClassRedirects=(OldClassName=”MyOldClass”,NewClassName=”MyNewClass”)**
* Just change **"MyOldClass"** and **"MyNewClass"**, for example:
* *+ActiveClassRedirects=(OldClassName=**”NewCharacter”**,NewClassName=**”CustomCharacter”**)*
* ***You don't have to put the preceding letter (A for actor, F, etc...)***
* If you don't find the **[/Script/Engine.Engine]** block, just add it!
* Reload your project and you should be able to open your Blueprint now.
* Open it, reparent it, compile it, save it, close it. ^^
* Now that you've done that you can delete what you wrote in **DefaultEngine.ini** if you wish to.
* I guess deleting those lines is better than leaving them there, I'm not 100% sure but I haven't had any problems doing so.

### Deleting a C++ file
* Removing it in VS will have no effects in the OS nor in UE4.
* You can't delete it in the Content Browser.
* The only way is to delete it in the OS and then remove it in VS.
* Recompile! If you had dependencies, it won't compile. Fix the errors until it compiles just fine.
* You may still find the class in the Content Browser. Reload the project and it should be gone.

### Moving files between Folders
* Moving them in VS, has again no effect.
* As the Content Browser won't let you, you can only move them in the OS.
* After moving them, recompile in UE4. Compilation errors may raise if you had dependencies.
* Select the moved files in VS, right click and Exclude from Project. They will disappear from VS.
* Go to the Filter which is named as the Folder where you moved your files.
* Add existing files there, you may now fix the compilation errors and everything should work nicely.
