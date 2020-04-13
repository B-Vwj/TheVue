+++
title = "Java Documentation"
menutitle = "Java"
description = "Java Documentation/Notes"
weight = 1
+++

Method Parameter

```
Public void growBy(int amount)
```

The method header above tells us that the method receives one parameter of type “int”.

No Return Value

Java method(s) may or may not return a value.
- The term “void” on the method header is used to indicate “no return value”.

Method Header Components

There are three components for Method Heads:
1. Method Return Type - means the method returns a value with the given return type (“int” in this case)
2. Method Name - the name of the method
3. Method Parameters - the method parameters that must be passes by the sender to this method.

Method Header

What is the Method Header?
- The method header is the first line of the method and gives information about the method

Purpose of the Method Header
- The purpose of the method header is to provide details to potential callers of the method. It would be very inefficient to require callers to dig through many lines of code to determine does. Instead, the method caller needs to only look at the method head.
- Another name for method header is _method signature_

Methods with Parameters

Methods are like Functions, check below for an example:

**Basic Function**:

```
Function computeArea(width, height)
	return width * height
```

**Corresponding Java Method**:

```
Public int computeArea(int width, int height) {
	return width * height;
}
```
Introducing Methods

## Introducing Methods
- So far, without methods, you’d probably just have some structure “[instance variables (ivars)]” into our classes.
- The Java method body uses the same braces _{ }_ as the **class body**.
- A method always consists of a Method Header, as well as maybe some other things like:
    - Ivars
    - “Return”


Example Below:

```
Public class Rectangle {
	private int width;
	private in height;
}
```

- So, let’s add _behavior_ to our object. Here’s an example simple method:

```
Public void setSmall() { 	// Set ivars to arbitrary small values
	width = 5;
	height = 1;
}
```

## Concepts of Messages
- Objects send messages to one another.
    - Without messages they do nothing.
    - A private object doesn’t allow us to see the insides.
    - Objects can receive messages through “access points”.
- A ***method*** is the code that will receive a message.
    - When a method is defined (coded) then we can send messages using that method name to object instances the given type.
    - A ***class** will generally have many methods***.
