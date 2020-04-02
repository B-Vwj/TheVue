+++
title = "CSS Inheritance"
menutitle = "Inheritance"
description = "CSS Inheritance"
weight = 4
+++

There’s one last way that an element can receive styles - _inheritance_. The cascade is frequently conflated with the concept on inheritance. Although the two topics are related, you should understand each individually.

If an element has no cascaded value for a given property, it may inherit one from an ancestor element. It’s common to apply a `font-family` to the `<body>` element. All the ancestor elements within will then inherit this font; you don’t have to apply it explicitly to each element on the page.

Inheritance (order of props being passed down)
= = = = = = = = = = = = = = = = = = = = >
```
										       = = = > <li>
										      /
							      = = = > <ul> = = = > <li>
							     /			\
				 = = = > <header> 			 = = = > <li>
				/			     \
<html> = = = > <body> 			 = = = > <h1>
				\
				  = = = > <main>
```

Not all properties are inherited, however. By default, only certain ones are. In general, these are the properties you’ll _want_ to be inherited. They’re primarily properties pertaining to text:
- color
- font
- Font-family
- Font-size
- Font-weight
- Font-variation
- Font-style
- Line-height
- Letter-spacing
- text-align
- text-indent
- text-transform
- white-space **and**
- word-spacing

A few others inherit as well, such as the:

_list properties:_
- List-style
- List-style-type
- List-style-position **and**
- List-style-image

_table border properties:_
- Border-collapse
- Border-spacing

## Special Values

There are two special values that you can apply to any property to help manipulate the cascade: ***inherit*** and ***initial***. Let’s take a look at these.

### Using the _inherit_ keyword

Sometimes, you’ll want inheritance to take place when a cascaded value is preventing it. To do this, you can use the keyword inherit. You can override another value with this, and it’ll cause the element to inherit that value from its parents.

For example:

```
/* Global link color for the page */
a:link {
	color: blue;
}

…

/* Footer text color set to Gray */
.footer {
	color: #666;
	background-color: #ccc;
	padding: 15px 0;
	text-align: center;
	font-size: 14px;
}

/* Footer link color inherits font color from footer */
.footer a {
	color: inherit;
	text-decoration: underline;
}
```

The third ruleset here overrides the blue link color, giving the link in the footer a cascaded value of inherit. Thus it inherits the color from its parent, `<footer>`.

### Using the _initial_ keyword

Sometimes you’ll find you have styles applied to an element that you want to undo. You can do this by specifying the keyword initial. Every CSS property has an initial, or default, value.

The benefit of initial, is that you don’t have to think about it as much. You may be in the habit of using the value **auto** to do this sort of reset. In fact, you can use `width: auto` to achieve the same result. This is because the default value of `width` is `auto`.

It’s important to note, however, that auto isn’t the default value for all properties. It’s not even valid for many properties; for example, `border-width: auto` and `padding: auto` are invalid and therefore have no effect. You could take the time to dig up the initial value for these, but it’s often easier to use `initial`.

- Declaring `display: initial` is equivalent to `display: inline`. It won’t evaluate to `display: block` regardless of what type of element you apply it to. That’s because initial resets to the initial value for the property, not the element; inline is the default value for display property.

## Shorthand properties

**Shorthand properties** are properties that let you set the values of several other properties at one time. For example, `font` is a shorthand property that lets you set several font properties. This declaration specifies `font-style`, `font-weight`, `font-size`, `line-height`, and `font-family`.

For example:

```
font: italic bold 18px/1.2 "Helvetica", "Arial", sans-serif;
```

Similarly, 
- `background` is a shorthand property for multiple background properties: `background-color`, `background-image`, `background-size`, `background-repeat`, `background-position`, `background-origin`, `background-chip`, and `background-attachment`.
- `border` is a shorthand for `border-width`, `border-style`, and `border-color`, which are in turn shorthand properties as well.
- `border-width` is shorthand for the top, right, bottom, and left border widths.

Shorthand properties are useful for keeping your code succinct and clear, but a few quirks about them aren’t readily apparent.

### Beware shorthands silently overriding other styles

Most shorthand props let you omit certain values and only specify the bits you’re concerned with. It’s important to know, however, that doing this still sets the omitted values; they’ll be set implicitly to their initial value. This can silently override styles you specify elsewhere.

### Understanding the order of shorthand values

Shorthand properties try to be lenient when It comes to the order of the values you specify.

#### Top, Right, Bottom, Left

Shorthand property order particularly trips up devs when it comes to properties like _margin_ and _padding_, or some of the border properties that specify values for each of the four sides of an element. For these props, the values are in clockwise order, beginning at the top (“It’s HIGH NOON”).

A good mnemonic to remember this is **TRouBLe**.

#### Horizontal, Vertical

The TRouBLe mnemonic only applies to properties that apply individually to all four sides of the box. Other properties only support up to two values. These include props like `background-position`, `box-shadow`, and `text-shadow` (although these aren’t shorthand propers, strictly speaking).

For example:

```
background-position: 25% 75%
```

The first value specifies the horizontal right/left values, followed by the vertical top/bottom values. Think of it like coordinates on a graph. (X, Y).
