+++
title = "Javascript Dice Game Project"
menutitle = "Dice Game Project"
description = "Dice Game built with Javascript"
weight = 50
+++

***NOTE:*** HTML and CSS were already configured when we did worked on the Javascript. Make your own version :).

Dice Game — What we learned from this:

- How to create our fundamental game variables;
- How to generate a random number;
    - “Math.random()”
    - “Math.floor(Math.random() * 6) + 1”
        - To get a random number between 1 - 6.
- How to manipulate the DOM;
    - We can do DOM manipulations is the ‘document’ object.
    - Method: ‘querySelector’
         - Manipulate and change values and elements of our webpage.
    - ‘document.querySelector()’
        - Lets us select stuff exactly like CSS
        - Only selects the first thing it finds that matches its parameters.
- How to read from the DOM;
    - ‘document.querySelector().textcontent’
- How to change CSS Styles;
     - Manipulate CSS elements: ‘document.querySelector(.dice).style.display ‘
- How to set-up an event handler;
    - ‘document.querySelector(***insert-button***).addEventListener(‘click’, function{})’
- What a callback function is;
    - Function that is called by another function. In other words, a function that we pass into another function as an argument. And the function receiving it will call it.
    - ‘Document.querySelector(***Insert Button***).addEventListener(‘click’, function{})’
- What an anonymous function is;
    - A function without a name.
    - ‘function() {}’
- Another way to select elements by ID;
    - ‘Document.getElementById()’
- How to change the image in an <img> element;
    - In the dice game example, we had the function roll the dice and generate a random number.
    - Conveniently, the dices were named “dice-1”, “dice-2”, “dice-3”, and so forth. So we can set the generated number, which is set to dice variable, and it turns out like:
    - “Documemt.querySelector().src = ‘dice-‘ + dice + ‘.png’”
- What’s the Ternary Operator?
    - Conditional Statement ? True : False
- How to add, remove, and toggle HTML classes?
- Add Classes
    - document.querySelector('.player-0-panel').classList.remove('active');
- Remove Classes
    - document.querySelector('.player-1-panel').classList.add('active');
- Toggle Classes (adds and removes automatically)
    - document.querySelector('.player-0-panel').classList.toggle('active');
- How to use functions to correctly apply the DRY principle;
    - DRY = Don’t Repeat Yourself
    - Create a function containing how the players are switched, then call that function when you need to switch player turns.
- How to think about the game logic like a programmer;
- What a ‘state’ variable is, and how to use it and why;
