+++
title = "CSS Fundamentals"
menutitle = "Terminologies"
description = "CSS Terminologies"
weight = 2
+++

## Terminology of CSS

Take this code as an example. This is called a ***declaration***. This declaration is made up of a ***property*** (color) and a ***value*** (black):

```
color: black;
```

Properties aren’t to be confused with ***attributes*** , which are part of the HTML syntax. For example, in the element `<a href=“#”></a>`, ***href*** is an attribute of the ***a*** tag.

A group of declarations inside curly braces is called a ***declaration block***. A declaration block is preceded by a ***selector*** (in this case, body):

```
Body {
	color: block;
	font-family: Helvetica, Sans-serif;
}
```

Together, the selector and declaration block are called a ***ruleset***. A ruleset is called a ***rule***, although, rule is rarely used so precisely and is usually used in the plural to refer to a broader set of styles.

Finally, ***at-rules*** are language constructs beginning with an “@“ (at) symbol. For examples:
- ***@Import*** rules
- ***@media*** queries
