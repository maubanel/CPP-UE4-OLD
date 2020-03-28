---
layout: default
title:  "Functions Templates and Classes"
---

# CPP Cards II  Page 5
_____ 

## Index
_____ 

* Part I - Refactor Basic Class
1. [Refactor Basic Class](CPP-Cards-II-1.html#refactor-basic-class)
2. [Add a Namespace](CPP-Cards-II-1.html#add-a-namespace)
3. [Structs and Classes](CPP-Cards-II-1.html#structs-and-classes)
4. [Static Members of a Class](CPP-Cards-II-1.html#static-members-of-a-class)
5. [Equal & Not Equal Operators](CPP-Cards-II-1.html#equal--not-equal-operators)

* Part II - Creation and Destruction
1. [Detructor](CPP-Cards-II-2.html#detructor)
2. [Stack and Heap](CPP-Cards-II-2.html#stack-and-heap)
3. [More on Pointers](CPP-Cards-II-2.html#more-on-pointers)

* Part III - More on Type
1. [More Const](CPP-Cards-II-3.html#more-const)
2. [Auto](CPP-Cards-II-3.html#auto)
3. [Decltype](CPP-Cards-II-4.html#decltype)

* Part IV - Applying to UE4
1. [Setting up Project and New Level](CPP-Cards-II-5.html#setting-up-project-and-new-level)
2. [Namespaces](CPP-Cards-II-5.html#namespaces)
3. [Equality in UE4 Card Class](CPP-Cards-II-5.html#equality-in-ue4-card-class)
4. [UStructs](CPP-Cards-II-6.html#ustructs)
5. [Static Members](CPP-Cards-II-7.html#static-members)
6. [Destructor](CPP-Cards-II-7.html#destructor)

_____ 

## Setting up Project and New Level
Lets copy over our last CPP Card Game exercise and set up a new level.
_____ 
{% assign num = 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Create a new folder to copy the old project into somewhere convenient. Call it `UE Cards II`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CreateNewFolder.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Go to the folder with the old **DeckOfCards** uproject and copy all the files.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CopyOldProject.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Paste it all into the new folder you created:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CopyOldProject2.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Delete the VS solution as the linker might have a different directory set up.  We will generate a new one.  Rename the project to `DeckOfCards2.uproject`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DeleteVSRenameProj.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now there are project generated files for the old location.  Just to be safe lets delete the **Binaries**, **Intermediate** and **Saved** folders.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DeleteBinariesIntermediateSave.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now right click on the **.uproject** file and select **Generate Visual Studio project files**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CreateNewVSSolution.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. This will take a while so be patient.  Notice it regenerates a new **Intermediate** and **Saved** folder.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/WaitABit.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Double click on the **.uproject** file and it will most likely as if you want to recompile and probably state that the version has changed.  Just answer yes and proceed to load the game.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/OpenCopiedProject.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Make a new level and call it `L_Card_Same_Diff` to test the **== operator** for our card class.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/NewLCardDiffLevel.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Open project settings and set the **L_Card_Same_Diff** level as the **Editor Startup Map**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SetNewStartupProject.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Drag two copies onto the play area of **BP_Card_Actor**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DragTwoCopiesBPCard.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. We don't have our camera so save the level and open **L_Card_Table** and right click in the **World Outliner** on the camera and select **copy**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CopyCamera.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now reload the **L_Card_Same_Diff** level and paste the camera into this level.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/PasteIntoLevel.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Run the game and you will notice that it is not using this new camera.  Open **L_Card_Table** and select **Open Level Blueprint**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/OpenOldLBP.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Select the three nodes (not the Begin Play event) and copy (cntrl-c) the blueprint nodes.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/Copy3Nodes.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now reload the **L_Card_Same_Diff** level and open the **Level Blueprint**.  Paste the content of the old level blueprint into it.  Notice the camera reference is unknown as it doesn't know the location of the camera in this room.  We will fix that.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/PosteNodesInNewLevel.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Connect the execution pin from **Event BeginPlay** to **Set View Target with Blend** nodes.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ConnectExecutionPins.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Select the camera actor in the level.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SelectCameraActorInLevel.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Go back to the **Level Blueprint** and right click on the empty graph and select **Create a Reference to CameraActor**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RightClickOnGraphAndCreateReferenceForCam.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Delete the **Unknown** node and attach the new **CameraActor** pin to the **New View Target** pin in the **Set View Target with Blend** node.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ReconnectCamActor.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Compile and run the game and look to see if the cards are lined up correctly.  In my case one card is off screen.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RunGameCardLayoutWrong.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Select the camera actor and move the cards so they are centered side by side.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ClickOnActorAndCenter.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. I adjusted it a few times until I was happy with the layout.  I leave room on top to have text that will say whether the cards are the same or not.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/HappyWithLayout.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

_____ 


{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Press the **Call Flip Card** bool to turn over both cards.  They should default to the **Ace of Spades**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/FlipBothCardsOver.jpg"  class= "img-fluid"  alt="Screenshot">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Run the project and you the cards should now be face up.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RunGameCardsTurnedOver.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>
_____

## Namespaces
If you are writing a non UE4 class you can use namespaces as you would normally do in a native C++ class.  Be careful Unreal code does not wrap in a global namespace so be careful to avoid collisions.

Namespaces are not currently supported in the Unreal Header Tool so they should NOT be sued when defining UCLASS, USTRUCT, UACTOR etc...

[Unreal Manual - Coding Standards](https://docs.unrealengine.com/en-US/Programming/Development/CodingStandard/index.html#namespaces)


_____

## Equality in UE4 Card Class
Lets make sure we can compare two cards to find out if they are the same number and suit. 

_____
{% assign num = 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Let add a new blueprint to hold the text to indicate sameness of the two cards.  Press the **Add New** button and select a **Actor Blueprint Class** and add it to the **Blueprints** folder. Call this new blueprint `BP_Same_Message`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddNewBPActorClass.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Open the **BP_Same_Message** blueprint and add a **TextRender** component.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddTextRenderComponent.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add `The two cards are` to the **Text** box.  Pick a bright color.  **Center** the **Horizontal Alignment**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AdjustText.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Click on the Material for the Text Render and we need to change it as this will not work in an unlit room.  Click on the **View Options** eyeball and select **Show Engine Content**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ShowEngineContentForMat.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstratalling community version that is needed download">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Search and select **Unlit Text** node that comes with the engine.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/Unlit Text.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Drag a reference to BP_Same_Message and rotate it so that it is in the correct direction and is facing the camera.  It should look something like this.  On the next page we will move into C++ and add the operator override.  
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddBPSameMessage.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>


_____ 
<br><br>

[<- Previous](CPP-Cards-II-4.html)&nbsp;&nbsp;&nbsp;[Home](../index.html)&nbsp;&nbsp;&nbsp; [Continue ->](CPP-Cards-II-6.html)
<br />  
<br />  
<br />  

