+++
title = "Vue.JS Notes"
menutitle = "VueJS Notes"
description = "Notes/Documentation for the VueJS framework"
weight = 4
+++

## VueJS 
What is Vue.js?
- Vue.js is a Javascript framework that helps to compartmentalize and organize web page source codes
- Based on Node.js and similar to React frameworks
- Provides an approachable, versatile, and performant experience

### Why Vue.js?
- Super easy to use
- Very similar to React
- Data updates in real time in all the appropriate places
- Can build logic right into HTML elements
- Highly scalable

### Who is this tutorial for?
- Those looking for an easy to use JS framework
- Those who want to write easily maintainable JS
- Those who like the idea of compartmentalized pages
- Those familiar with basic HTML, CSS, JS, and npm

### What will we Cover?
- Installing Vue.js and starting a project
- Creating and using Vue instances
- Passing data into Vue instances and using it
- Vue instances variables and functions
- Using conditionals in Vue
- Handling user interactions and inputs
- Vue components
- Final project

—

Vue Instances

What is a Vue Instance?
- Provides a way to attach Vue functionality to an HTML element
- Allows for fine control over specific parts of a page
- Idea stems from MVVM design pattern
- Attach HTML element, pass in data, functions, lifecycle events, etc

How do we use Data in Vue?
- Pass data as a dictionary or JS object into the Vue
- Define variables names as keys and values as values
- Can then call upon variable names in HTML elements with {{}}} and . Syntax

Instance Members
- Instance members are variables and functions that exist for every instance of a Vue
- Often take special values such as functions or objects

How do we use If Statements and Loops?
- Use a v-attribute in an HTML element
- Can use `v-if`, `v-else-if`, and `v-else` attributes
- Can use `v-for` and iterate through an array

How do we respond to button presses?
- Add a function in the “methods” attribute of a view object
- Implement the function and assign the name to a key
- Use the `v-on:clock` attribute in an HTML element
- This triggers the assigned function when user clicks on the element

How do we respond to text input?
- Create an input on the HTML side
- Create a variable in the Vue side to hold the temporary input
- Assign a v-model attribute that changes upon input from user

What are Components?
- Components are custom HTML elements
- Can provide custom attributes to use via “props” along template
- Can add components to Vue instances

Summary
- Installing Vue.js and starting a project
- Creating and using Vue instances
- Passing data into Vue instances and using it
- Vue instance variables and functions
- Using conditionals in Vue
- Handling user interactions and inputs
- Vue components
- Final Blog project

Where do we go from here?
- Improve upon our basic project
- Build more projects with Vue.js
