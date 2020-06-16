---
permalink:  /javascript/
title: "Introduction to JavaScript"
sidebar:
  nav: "docs"
---



### What is JavaScript?

JavaScript is a web programming language that is used to make web pages interactive.  Typically, JavaScript code is inserted 
into the HTML. Script tags are used to separate the JavaScript code from HTML.  In web map programming, we use JavaScript to 
interact with map libraries and with HTML objects.

 
<br>
 

#### A Simple JavaScript Program

This program below shows how a web page can be made interactive by including a JavaScript function in the HTML.  The function is named "MultiplyNumbers()" and, wehn called, will multiply two numbers that are passed to it.  The numbers are passed to the function via a HTML form  The results will be displayed to the screen in the form of a message box activated by the alert command.   

In the code below, you can see the JavaScript function in the head of the web page and and within the body of the web page, you an see the coe for the HTML form along with  button. The button is associated with an OnClick event which will make a call to the JavaScript function.   

    <HTML>
    <head>

    <script language="JavaScript">
      function MultiplyNumbers()
      {
        var number1,      // first number to add
         number2,        // second number to add
         product;         // sum of number1 and number2

       // convert numbers from strings to integers
        number1 = parseInt(document.frmMultiply.txtfirstNumber.value);
        number2 = parseInt(document.frmMultiply.txtsecondNumber.value);

        // Multiply the numbers
       product = number1 * number2;

       // display the results
        alert( "The product is " + product + " ");
        }
      </script>
      </head>

    <body>

    <H1> Welcome to My Web Page</H1>
    
    <br>

    <form name="frmMultiply">
    Enter first integer: <input type="text" name="txtfirstNumber" /><br />
    Enter second integer: <input type="text" name="txtsecondNumber" /><br>
    <input type="button" value="Multiply" onclick="MultiplyNumbers();">
    <p>
    </form>             
    </body>

    </html>


![image](https://user-images.githubusercontent.com/8826424/83361650-a772f580-a358-11ea-89d9-56b8879cbfab.png)

<br> 


#### Enhancing the Simple JavaScript program 

In the code below, the HTML form was adjusted so that the results appear in the form rather presented on a message box. 

![image](https://user-images.githubusercontent.com/8826424/83361162-a50e9c80-a354-11ea-8eb5-6ec6eefd251e.png)


    <html>
    <head>

    <script language="JavaScript">
    function MultiplyNumbers()
     {
     var number1, // first number to add
         number2,// second number to add
         product; // product of number1 and number2

     // convert numbers from strings to integers
        number1 = parseInt(document.frmMultiply.txtfirstNumber.value);
        number2 = parseInt(document.frmMultiply.txtsecondNumber.value);

      // Multiply the numbers
         product = number1 * number2;

      // display the results
         document.frmMultiply.results.value = product;
    }
     </script>

    </head>

      <body>
      <form method=post name="frmMultiply">
    <table border="1" cellpadding=5>
    <tr>
    <td align=center>Enter First Integer:</td>
    <td align=center><input type="text" name="txtfirstNumber" /></td>
    </tr>
    <tr>
    <td align=center>Enter Second Integer:</td>
    <td align=center><input type="text" name="txtsecondNumber" /></td>
    </tr>
    <tr>
    <td align=center><input type="button" value="Multiply" name="multiply" onclick="MultiplyNumbers();"></td>
    <td align=center><input type="text" name="results" value=""></td>
    </tr
    <tr>
     <td colspan="2" align="center"> <input value="Reset" type="reset"></td>
     </tr>

    </table>

    </form>   

    </body>

    </html>

 
<br>
 
#### W3Schools LightBulb Application 

Click on this [link](https://www.w3schools.com/js/js_intro.asp) to see the application.

Copy and paste the code below pr from the website into your web editor. Download the lightbulbs images and put them in the same folder as web page

 

    <!DOCTYPE html>
    <html>
    <body>

    <h1>What Can JavaScript Do?</h1>

    <p>JavaScript can change HTML attributes.</p>

    <p>In this case JavaScript changes the src (source) attribute of an image.</p>

    <button onclick="document.getElementById('myImage').src='pic_bulbon.gif'">Turn on the light</button>

    <img id="myImage" src="pic_bulboff.gif" style="width:100px">

    <button onclick="document.getElementById('myImage').src='pic_bulboff.gif'">Turn off the light</button>

    </body>
    </html>

 
 <br>
 
### Extend your JavaScript Knowlege
Now that you have a basic understanding of how JavaScript works, it is time to deepen your knowlege of JavaScript. Complete as  much JavaScript tutorials as you can and you will be well on your way to working with the language. Topics to study include:
 
 * Variables
 * Data types
 * Conditional Statements
 * Looping
 * Functions and Events
 * Arrays
 * Scope
 * Asynchronicy
 * Node.js
 * Error Handling
 * Classes, Objects, Methods
 * DOM Manipulation
 * JQuery
 
 <br>
 
### JavaScript Tutorial Links
* [W3Schools JavaScript Tutorials](https://www.w3schools.com/js/js_whereto.asp)
