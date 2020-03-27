+++
title = "CSS Fundamentals"
menutitle = "Specificity in CSS"
description = "Specificity"
weight = 2
+++

## Understand Specificity

Understanding Specificity is essential. You can go a long way without an understanding of stylesheet origin because 99% of the styles on your website come from the same origin. But if you don’t understand specificity, it’ll come back to bite you.

### Inline Styles

If you use an HTML `style` attribute to apply styles, the declarations are applied only to that element.
- These are, in effect, “scoped” declarations, which override any declarations applied from your stylesheet or a `<style>` tag. Inline styles have no selectors because they are applied directly to the element they target.
- To override inline declarations in your stylesheet, you’ll need to add an `!important` to the declaration, shifting it into a higher-priority origin. If the Inline styles are marked important, then nothing can override them.

### Selector Specificity

An ID selector (I.E. #nav) has a higher specificity than a class selector.
In fact, a _single_ ID has a higher specificity than a selector with any number of classes.Similarly, a class selector has a higher specificity than a tag selector (also called a ***type selector***).

The exact rules of specificity are:
1. If a selector has more IDs, it wins (that is, it’s more specific)
2. If that results in a tie, the selector with the most classes wins.
3. If that results in a tie, the selector with the most tag names wins.

Consider the example below:

```
/* 1)  Four tags */
Html body header h1 {
	color: blue;
}

/* 2) Three tags and one class */
Body header .page-header h1 {
	color: orange;
}

/* 3) Two classes */
.page-header .title {
	color: green;
}

/* 4) One ID */
#page-title {
	color: red;
}
```

The most specific selector here is 4, with one ID, so its color declaration of red is applied to the title. The next specific is 3, with two class names. This would be applied if the ID selector (4) was absent. Selector 3 has a higher specificity than selector (2), despite its length: two classes are more specific than one class. Finally, 1 is the least specific, with four element types (that is, tag names) but no IDs nor Classes.
- Pseudo-class Selectors (for example, _:hover_) and attribute selectors (for example, _[type=‘input’]_) each have the same specificity as a class selector. The universal selector (\*) and combinators (>, +, ~) have no effect on specificity.

Specificity is a simple concept, however, if you don’t understand specificity, you can drive yourself mad trying to figure out why one rule works and another doesn’t.

### Notation for Specificity

A common way to indicate specificity is in a number form, often with between each number. For example, _”1,2,2”_ (ID, Class, Tag) indicates a specificity of one ID, two Classes, and two Tags. IDs having the highest priority are listed first, followed by classes, then tags.

<small>**Note:** _If you happen to use VS Code like I do, you can hover over the selector in your CSS stylesheet to see the specificity._
<br/><small>- _The writer of this site._ </small> 
</small>

Occasionally, people use a four-number notation with a 0 or 1 in the most significant digit to represent whether a declaration is applied via **inline styles**. In this case, it would be _”1, 0, 0, 0”_ (Inline, ID, Class, Tag). This would override styles applied via selectors.

### Specificity Considerations

Consider the three different fixes we can apply:

#### _Fix One: Adding the `!important` annotation_  

```
/* Possible Fix One */

#main-nav a {

	color: white;
	background-color: #13a4a4;
	padding: 5px;
	border-radius: 2px;
	text-decoration: none;

}

.featured {

	background-color: orange !important; /* Now a higher-priority origin */

}
```

Using `!important` is easy for quick fixes. However, it’s a naive fix. It can cause you problems down the road. If you start adding !important to multiple declarations, what happens when you need to trump something already set to important?

When you give several declarations an `!important`, then the origins match and the regular specificity rules apply. This ultimately will leave you back where you started; once you introduce an `!important`, more are likely to follow.

#### _Fix Two: Increasing the specificity to override the one overriding (lol)._

```
/* Possible Fix Two */

/* Specificity remains 1,0,1 */
#main-nav a {

	color: white;
	background-color: #13a4a4;
	padding: 5px;
	border-radius: 2px;
	text-decoration: none;

}

/* Specificity increase to 1,1,0 */
#main-nav .featured {

	background-color: orange; /* !important annotation is no longer necessary */

}
```

This fix also works. Now, your selector has one ID and one Class, giving it a specificity of “1,1,0”, which is higher than the `#main-nav a` selector (a specificity of “1,0,1”), so the background color orange is applied to the element.

We can still do better, though. Instead of _raising_ the specificity of the second selector, let’s see if we can _lower_ the specificity of the first. The element has a class as well (here’s a refresher: `<ul id=“main-nav” class=“nav”`), so you can change your CSS to target the elements by its class name rather than its ID.

#### _Fix Three: Lowering the specificity of the Overriding selector._

```
/* Changing “#main-nav” to “.nav” throughout stylesheet. */
.nav {

	margin-top: 10px;
	list-style: none;
	padding-left: 0;

}

.nav li {

	display: inline-block;

}

/* Lowers the first specificity (1,0,1) => (0,1,1) */
.nav a {

	color: white;
	background-color: #13a4a4;
	padding: 5px;
	border-radius: 2px;
	text-decoration: none;

}

/* Increases the second specificity (0,1,0) => (0,2,0) */
.nav .featured {

background-color: orange;

}
```

We’ve brought the specificity of the selectors down. The orange background is high enough now to override the teal.

As you can see from these examples, specificity tends to become a sort of arms race. This is particularly the case with large projects. It’s generally best to keep specificity low when you can, so when you need to override something, your options are open.

## Understanding Source Order

The third and final step to resolving the cascade is source order. If the origin and the specificity are the same, then the declaration that appears later in the stylesheet - or appears in a stylesheet included later in the page - takes precedence.

This means you can manipulate the source order to style you featured link. If you make the two conflicting selectors equal in specificity, then whichever appears last wins.

Consider the fourth option shown:

```
/* Specificity: (0,1,1) */
.nav a {

color: white;
background-color: #13a4a4;
padding: 5px;
border-radius: 2px;
text-decoration: none;

}

/* Specificity: (0,1,1) */
a.featured {

background-color: orange;

}
```

Again, we’ve set both selectors to a specificity of _“1,1,0”_. Source order determines which declaration is applied to your link, resulting in an orange featured button.

This addresses the problem we were facing but, potentially, also introduces a new one: although a featured button inside the `nav` looks correct, what happens if you want to use the featured class on another link elsewhere on the page, outside of your nav? You’ll get an odd blend of styles: the orange background, but not the text color, padding, or border radius of the nav links.


### Link Styles and Source Order

You may already know that your selectors for styling links should go in a certain order. That’s because source order affects the cascade.

The code below shows styles for links on a page in the “correct” order:

```
a:link {

color: blue;
text-decoration: none;

}

a:visited {

color: purple;

}

a:hover {

text-decoration: underline;

}

a:active {

color: red;

}
```

The cascade is the reason this order matters: given the same specificity, later styles override earlier styles. If two or more of these states are three of one element at the same time, the last one can override the others. If the user hovers over a visited link, the hover styles take precedence. If the user activates the link (that is, clicks it) while hovering over it, the active styles take precedence.

A helpful mnemonic to remember this order is ***LoVe/HAte***:
- Link
- Visited
- Hover
- Activate

### Cascaded Values

A declaration that “wins” the cascade is called a ***cascaded value***. There’s at most one cascaded value per property per element.

- _Cascaded Value_: A value for a particular property applied to an element as a result of the cascade.

If a property is never specified for an element it has no cascaded value for that property.

### Two Rules of Thumb

1. _Don’t use IDs in your selector_. Even one ID ratchets up the specificity a lot. When you need to override the selector, you often don’t have another meaning full ID you can use, so you can wind up having to copy the original selector and add another class to distinguish it from the one you are trying to override.
2. _Don’t use `!important`_. This is even more difficult to override than an ID, and once you use it, you’ll need to add it every time you want to override the original declaration - and then you’ll still have to deal with the specificity.

These two rules can be good advice, but don’t cling to them forever. There are exceptions where they can be okay, but never use them in a knee-jerk reaction to win a specificity battle.

“An important note about importance If you’re creating a JavaScript module for distribution (such as an NPM package),

I strongly urge you not to apply styles inline via JavaScript if it can be avoided. If you do, you’re forcing developers using your package to either accept your styles exactly or use !important for every property they want to change.

Instead, include a stylesheet in your package. If your component needs to make style changes dynamically, it’s almost always preferable to use JavaScript to add and remove classes to the elements. Then users can use your stylesheet, and they have the option to edit it however they like without battling specificity.”
