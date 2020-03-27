+++
title = "CSS Fundamentals"
menutitle = "Stylesheet Origins"
description = "CSS Origin"
weight = 3
+++

## Understanding Stylesheet Origin

The Stylesheets you add to your web page aren’t the only ones the browser applies. There are different types, or origins, of stylesheets. Yours are called _authors_ stylesheets; There are also _user agent_ styles, which are the browser’s default styles.
- Use agent styles have lower priority, so your styles override them.
    - Some browsers let users define a user stylesheet. User stylesheets are rarely used and beyond your control, so I’ve left them out for simplicity.

There is an exception to the style origin rules: declarations that are marked as ***important***. A declaration can be marked important by adding `!important` to the end of the declaration, before the semicolon:

```
Color: red !important;
```

Declarations marked `!important` are treated as a higher-priority origin, so the order of preference, in decreasing order, is this:
1. Author important
2. Author
3. User Agent

- Note: The cascade independently resolves conflicts for every property of every element on the page.
    - The concept of style origin will come into play when we get to transitions and animations because they introduce more origins to this list.
