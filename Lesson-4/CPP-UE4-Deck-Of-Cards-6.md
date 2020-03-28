---
layout: default
title:  "Functions Templates and Classes"
---

# UE4 Deck of Cards Page 6
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
4. [Show Back of Card](CPP-UE4-Deck-Of-Cards-4.show-back-of-card)

* Part III - Blueprint Deck Of Cards
1. [Deck of Cards](CPP-UE4-Deck-Of-Cards-4.deck-of-cards)
2. [Add Set Card Suit](CPP-UE4-Deck-Of-Cards-4.add-set-card-suit)
3. [Make Card Clickakble](CPP-UE4-Deck-Of-Cards-5.make-card-clickable)
4. [Create Two Piles](CPP-UE4-Deck-Of-Cards-5.create-two-piles)
5. [Finish Two Piles](CPP-UE4-Deck-Of-Cards-6.create-two-piles)

_____ 

## Finish Two Piles
Now we want to deal with getting cards back and forth between the two piles.  We will start by adding a variable to the **BP_Card_Actor** to hold what pile the card is in.

_____ 
{% assign num = 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Open up **BP_Card_Actor** and add a new **Integer** variabled called `OnPileNumber`. Press the **compile** button as we need access to this variable in another actor.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/OnPileNum.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now lets go back to **BP_Deck_Of_Cards** and pull from the **Return Value** pin from the **SpwanActor BP Card Actor** and add a **Set Pile Number** set to `0` to begin play. Be sure **not** to leave target empty (the same as putting **this**) as this variable does not exist in the deck.  
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SetOnPileNumberInBeginPlay.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now rename to the **Function** in the card deck blueprint to from `Pile1To2` to `Swap Piles` and open the function graph.  Double click on the blue line going into **Flip Card** and drag from it and select a **Get On Pile Number** node.  Pull off of it and select a **Integer \| Equal** node (same as **==** in c++).
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SwapPilesCheckPile.gif"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add a branch node and highjack the execution pin to go from **Flip Card** to **Branch** to **\-\-** execution pin. Take the output of the **==** pin and put it into the input of the **Branch** pin node.  Add a comment to the nodes here to indicate that this is for a card in the first pile.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SubractDeck1AddDeck2Conditin.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. We also need the card to go from the face up pile back on to the face down pile. For going from pile 2 back to pile 1 copy the nodes and comments box and paste another copy below changing the comment.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CopyPile1Nodes.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now we need to reverse which variables get decrimented and incremented.  We are decrimenting deck 2 and incrementing deck 1.  We don't need to delete the nodes we can change them by right clicking on **Card 1 Pile** and select **Replace variable Card1Pile** with **Card2Pile**. Repeat this for all **Card 2 Pile** and for both setters as well.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/FlipPile2To1.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. So your Card2Pile and Card1Pile nodes should all be reversed.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ReversePile1To2.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Connect the **\-\-** execution input node to the **False** execution pin from the **Branch** node. 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ConnectSecond.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now we need to change the variable that stores the pile the card is on so we need to pull from the card reference and select the **Set On Pile Number** node:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SetOnPileNumberTopNodes.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Change the variable to `1` to indicate the second pile.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SetOnPile1.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Copy and paste the **Set On Pile Number** and do the same to thee nodes below and change the value to `0`. Connect the **Target** pin back to the **Card Reference**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CopyPasteSetPileNum.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Pull from the **Card Reference** pin and add a **Set Actor Location** node so we can readjust the **Z** depth of the card so the order stays the same.  Right click the **Location** pin and and select **Split Struct Pin**.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SplitPinOnSetActor.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add a **Get Actor Location** node and make sure the target is the card.  Split the output pins and connect **X** and **Y** to the **Set Actor Location**.  Then for **Z** take the output of **Card2Pile** number for its depth in the new pile.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/GetSetActorFirstNodes.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Duplicate this entire process for going from pile 2 back to pile 1.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/DupliacateZSetting.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Make sure the **Target** is connected to the **Card**,
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/ConnectTargetToSetActorLoc.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Go back to the begining and we will set the card either in negative `120` or positive `120` depending on which pile it is on.  Mame some room before the **Set Actor Location** like so:
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/MakeRoomBetweenGetAndSet.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Now add a **Get On Pile Number** from the card target then check to see if it is equal to `0`.  Then go to a branch node.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/OnPileNumberCheck.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add a new private variable called `CardDisplacement` and set the default to `120`.  The set it to `-120` on the true branch path and to `120` on false branch.  Send the two outputs to **Set Actor Location**.  Then drag a **CardDisplacement** node and add it to its current **X** position and send it to the **New Location X** pin. 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/FinshUpCardDisplacement.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Compile and run the game and press the cards between the two piles.  Test it and make sure you can go through the entire deck from no discard to all cards discarded and back.  We will leave this here for now and end this walk through.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/FinalCardVideo.gif"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page">  
</div>
</div>

_____ 

<br><br>

[<- Previous](CCP-UE4-Deck-Of-Cards-4.html)&nbsp;&nbsp;&nbsp;[Home](../index.html)
<br />  
<br />  
<br />  

