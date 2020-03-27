+++
title = "Javascript Fundamentals"
menutitle = "Javascript Constructors"
description = "Constructors in JavaScript"
weight = 4
+++

## Constructors in JS!

Callback Functions
- Functions that we pass into functions that will call them later.

(Function)Constructors

Var Person = function(name, yearOfBirth, Job) {
	this.name;
	this.yearOfBirth;
	this.job
}

Inheritance
- Add all methods and properties into the constructor’s prototype property.

Constructor: Person

We’re adding the method:

```
this.calcAge = func() {
	console.log(2020 - this.yearOfBirth)
}
```

To the person constructor, and now, it is inherited by all objects.
Example:

```
var John = new Person(‘John’, 1990, ‘teacher’);
```

The func above will inherit `calcAge` method because we defined the variable as a ***new*** object that also has `Person()`, in which we also pass the parameters:
`’John’, 1990, ‘teacher’`.

So now when we create new objects like…
`var Jane = new Person(‘Jane’, 1969, ‘designer’);`
It works the same!
