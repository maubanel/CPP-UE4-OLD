---
layout: default
title:  "Functions Templates and Classes"
---

# UE4 Deck of Cards Page 3
_____ 

## Index
_____ 

* Part I - Test in Blueprints
1. [Getting Set-Up](CPP-UE4-Deck-Of-Cards-1.html#getting-set-up)
2. [Add Test Blueprint](CPP-UE4-Deck-Of-Cards-1.html#add-test-blueprint)
3. [Configure Project](CPP-UE4-Deck-Of-Cards-1.html#configure-project)
4. [Make Camera Default](CPP-UE4-Deck-Of-Cards-1.html#make-camera-default)
5. [Mimic Our Final C++ Class](CPP-UE4-Deck-Of-Cards-2.html#mimic-our-final-c++-class)

* Part II - C++ Card Class
1. [Basic Card C++ Class](CPP-UE4-Deck-Of-Cards-2.html#basic-card-c++-class)
2. [Dynamic Materia](CPP-UE4-Deck-Of-Cards-3.html#dynamic-material)
3. [User Selected Card Suit](CPP-UE4-Deck-Of-Cards-3.html#user-selected-card-suit)

_____ 

## Dynamic Material
A UE4 material in its default state can't be changed at runtime.  To be able to change a material, we need to add a dynamic material and attach it to the existing material on the object.

_____ 
{% assign num = 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. We cannot create a dynamic material in the C++ class constructor.  We need to do this in the C++ equivalent of the blueprint constructor, which is called `OnConstruction`.  Add this to the `.h` file:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/OnConstructionDotH.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. You can click on the link above for the method and read the description of this function.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CreateDefinition.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page">  
</div>
</div>

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Lets define it in the `.cpp` file and call the parent classes implementation that we can add to (with the **Super::** directive)
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/OnConstructionCPP.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Go back to the `.h` and lets add a pointer to a [UMaterialInstanceDynamic](https://api.unrealengine.com/INT/API/Runtime/Engine/Materials/UMaterialInstanceDynamic/index.html).
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DynamicMaterialDotH.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Include the appropriate header file that we linked to above.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DynamicMaterialDotHHeader.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. We need to run **Create** and we need to pass it the pointer to the dynamic material as well as a pointer to ones parent class **UObject**. We get to this by passing a reference to the instance we are calling from using the `this` keyword.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CreateDynamicMaterial.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. So lets call the **Create** function. Compile.  There is a problem, Material is local to the constructor.  We need to move the pointer declaration to the `.h` file.  Lets do that.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DynamicMaterialPassParameters.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Remove the type identifyer in front of **Material** in the `.cpp`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RemoveTypeFromMaterial.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Lets make this pointer available to the entire class.  Add this variable to the class `.h` file:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddMaterialDeclarationToClassHeader.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>
_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Go back to the CPP and add a call to set the current material to the dynamic one we just created.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CreateDynamicMaterialInOnConstruction.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. We need to create a new class method to alter the card.  We want the user to switch cards in the editor and have it updated in game.  Lets start by creating a `void` method `SetCard()` that updates the card to a desired number and suit.  Create a declaration in the `.h` file.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CreateFunctionToSetCard.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. There is a shortcut to creating a defintion in the `.cpp` file.  Hover over `SetCard` and you will see a hint button that you can click on.  Select `Create definition of SetCard in Card_Actor.cpp`.  Select this option.  It will then open a window under.  You can close it then go to the `.cpp` file.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ShortCutCreateDefinition.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now in the `.cpp` file you will see that it automatically created an empty definition file that we can work with!
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CreatedDefinition.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. If we look at our **Material** blueprint we will want to update the **Texture Parameter** that we named `Card Texture`.  Now we need to add a `UTexture2D` to the `.h` file:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AlterTexture.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Include the `.h` for the texture to the `.h` file. Now remember to always leave the `.generated.h` as the last include.  Now look up in google the `UTexture2D` and find the location of the header and add it to the your header.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/IncludeText2D.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now declare the texture pointer:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DeclareTexturePointer.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Get reference for another card to test our work to date.  I am getting the reference location for the 10 of hearts.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GetReferenceForCard.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. I load the texture the same way we loaded the mesh and material.  I pasted the entire location.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/LoadTexture.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. I remove what is outside the single quotes and get rid of the extension so it should end up looking like:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/FinalLocationForTexture.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now we call a method in the **Dynamic Instance Material** called `SetTextureParameterValue` that changes the parameter with the name we used in the editor and pass it the texture of 10 of hearts we just loaded.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SetDynamicMaterial.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now call this method we just created in the `OnConstruction` event.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CallCardInOnConstruction.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Compile and Run the game and notice it now loads up to the ten of hearts.  Our dynamic material change worked!
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RunGame10Hearts.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

_____ 

## User Selected Card Suit
Now we want the user to be able to choose which card and suit to pick in the editor.  We want the varibales to be exposed and editable in the editor.  We will start by storing the suit and card numbers in special UE4 Enumerators.

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Lets create two more enumerator classes to store both the card number and the suit.  We could use a plain c++ enumerator class but we will not be able to edit it in blueprints or the editor.  There is a [UENUM](https://api.unrealengine.com/INT/API/Runtime/CoreUObject/UObject/UEnum/index.html) that inherits from a **UObject** which makes it accessible in the editor.<br><br>There is one large limitation which it is only available with a uint8 font which allows for 256 different enumerators per class.  More than enough for a deck of cards but could cause issues with larger structures where another solution might have to be implemented.<br><br>It is a UE4 standard to name an enumerator with a capital **E**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/NumberAndSuitEnum.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>
_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now lets add two new variables with a special indicationn that we want to edit the variables even though they are in a private class.  We create a number and suit enumerator reference. We use the enumerator types we created above.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddingCardAndSuitVars.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>


_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add a new function that will select the correct texture for the card.  Now they are named CONSISTENTLY so that we can use a loop to construt their full name without having to retype the entire path every time.  Open the `.h` file and add a new functiono called `void SetCard()`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddSetCardFunction.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. We are going to have to construct an entire directory name that we will destroy after the function is called named `TextureLocation`.  We will have two **FString** variables to store the number `Num` and suit `St`.  Then we switch the the suit enumerators to attach the correct string.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SwitchThroughSuitNames.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. We do the same thing with the card number.  
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SetSuitFilelname.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
<div class="col-12">
<img src="images/FiveToTenEnum.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Finish off the rest of the numbers from Jack to King.  We assemble the name to match the location of the card textures.  To pass the **FName** to **StaticLoadObject** we can just dereference the **Fstring** and it will load the textures.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/FinishEnumNumAndAssignName.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}.  Now we could call this function in **BeginPlay** but you will have to play the game after you set the card to see if it works.  By placing it in the **OnConstruction** event we will run this script anytime anything changes in the editor.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/InConstructionSetCard.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Drag a copy of thee new CPP class into the game screen if it is not already there.  Compile and Run the game and look click on the card number and suit in the World Outliner.  Notice that you can change the card and it changes in the game at the exact same time!
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ChangeCardInMenu.gif"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

_____ 
{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Next up we will flip the card from front to back. This way we can have a stacked deck face down and another pile face up.
</div>
</div>
</div>


_____ 

<br><br>

[<- Previous](CCP-UE4-Deck-Of-Cards-2.html)&nbsp;&nbsp;&nbsp;[Home](../index.html)&nbsp;&nbsp;&nbsp; [Continue ->](CPP-UE4-Deck-Of-Cards-4.html)
<br />  
<br />  
<br />  

