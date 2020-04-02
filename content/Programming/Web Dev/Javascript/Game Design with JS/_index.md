+++
title = "Javascript Game Design Documentation"
menutitle = "Javascript Game Design"
description = "Javascript Game Design Documentation/Notes"
weight = 3
+++

### What is a Canvas?
- Platform we draw on
- Packaged in HTML `<canvas>` tags
- Add a width and height
- Access the canvas and canvas context inside `<script>` tag

### How do we Draw on a Canvas?
- Supply a drawing context and function
- Add a rectangle with specified dimensions
- Draw rectangle on Canvas context
- Call draw function from a step function

### How do we add Movement?
- Create update function
- Update positions of items in the game
- Call update function in step function
- Can update multiple items with an array and for loops

### How do we add Controls?
- Add event listeners
- Listen for events such as mouse clicks or key presses
- Call functions to update position accordingly
- Call update functions

### How do we detect Collisions?
- Check ‘x’ and ‘y’ positions
- Determine if there’s overlap by comparison
- Do this for all objects
- End game or perform other collision logic

### What is a Sprite?
- Entity in game with an image and properties such as a x and y position and width and height
- Can represent player, enemies, or even background and other objects
- Load in images
- Draw sprite images instead of rectangles

### What did we Learn? (In the JS game section lol)
- Coding basics with JS syntax
- Game development basics with JS
- Two separate parts:
    - JS language basics
    - Game development basics with the final game

### In Summary
```
- Game Development
    - Canvas
    - Drawing on a Canvas
    - Adding movement to objects
    - Updating multiple items
    - Adding player controls
    - Collision detection and objectives
    - Sprites
````
