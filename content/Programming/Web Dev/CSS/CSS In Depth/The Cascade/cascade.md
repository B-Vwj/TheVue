+++
title = "CSS Fundamentals"
menutitle = "The Cascade"
description = "What is the Cascade?"
weight = 2
+++

## The Cascade

Fundamentally, CSS is about declaring rules: _Under various conditions, we want certain things to happen._

When declarations conflict, the cascade considers three things to resolve the difference:
1. _Stylesheet Origin_ - Where the styles come from. Your styles are applied in conjunction with the browser’s default styles.
2. _Selector Specificity_ - Which selectors take precedence over which.
3. _Source Order_ - Order in which styles are declared in the stylesheet.

**“Flowchart”**
Conflicting Declarations =>
Different **origin** or importance?
- Yes: Use declaration with higher-priority origin
- No: Move onto the next step =>

Is one an inline style? (Scope)
- Yes: Use inline declaration.
- No: Move onto next step =>

Do Selectors have different **specificity**?
- Yes: Use declaration with higher specificity.
- No: Move onto next step =>

Use declaration that comes later in the **source-order**.
