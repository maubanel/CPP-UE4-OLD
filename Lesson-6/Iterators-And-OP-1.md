---
layout: default
title:  "Cards II"
---

# Iterators & Object Pointers 1
_____ 



* Part I - Iterators
1. [Template Iterators](CPP-Cards-II-1.html#orstemplate-iterat)


_____ 

## Template Iterators
Most containers are created with iterators to access members of that data structure safely. It is an object (sometimes a pointer) that has the ability to iterate through the elements in range.  Each coorntainer has different iterator options that can include forward, backward, begin, end and random access to name a few. These iterators normally have a mutable (non-const) version and a const version that doesn't allow you to change the item in the container.  Lets take a look.

_____ 

{% assign num = 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Open up **Visual Studio** and start a new project.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/StartNewProject.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page">  
</div>
</div>

_____ 

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Select a **Console App** then press the **Next** button.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/SelectConsoleApp.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Call the new Project `IteratorsAndObjectPointers` and select a convenient location.  Press the **Create** button to build the template for this project.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/CreateNewProjectName.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Add a **Vector** and **String** header and to make the code more legible allow us to directly access **string**, **vector** and **cout** without having to prepend `std::`.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/AddHeaders.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-6 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Rather thaorn using subscripts (Vector[0]) which dereference the item, we can get an iterator which allows us to access this item through its interface like a pointer.  This uses less memory and is more performant.  A few things:<br>`*` dereferences iterator like a pointer to see the element<br>`++` incremenst one element in the container<br>`--` decrements one element in the container<br>`!=` or `==` checks for equality of iterators.<br><br> Now lets create a vector and use the **Vector's** function of **begin()** and **end()** to get the begining and the end of a vector  Please note that end is one element **PAST** the last element.  So this returns the end of the memory location and is out of bounds of the container (one past the end). So lets print out the first element and the last element (end() -1).
</div>
</div>
<div class="col-12 col-lg-6">
<img src="images/PrintFirstAndLast.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. Compile and run the project to see the first and last item in the container.
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/RunFirstLast.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>

{% assign num = num | plus: 1 %}
<div class = "row">
<div class="col-12 col-lg-4 col align-self-center">
<div markdown = "1">
{:start="{{ num }}"}
{{ num }}. 
</div>
</div>
<div class="col-12 col-lg-8">
<img src="images/.jpg"  class= "img-fluid"  alt="Screenshot of Microsoft's Visual Studio Community website page demonstrating community version that is needed download">  
</div>
</div>
_____ 


<br><br>

[Home](../index.html)&nbsp;&nbsp;&nbsp; [Continue ->](CPP-Cards-II-2.html)
<br />  
<br />  
<br />  

