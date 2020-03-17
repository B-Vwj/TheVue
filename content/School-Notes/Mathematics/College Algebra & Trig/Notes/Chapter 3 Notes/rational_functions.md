+++
title = "Rational Functions"
menutitle = "3.6 - Rational Functions"
description = "3.6 Notes"
weight = 7
+++

## _Notes:_

### Terms

***Rational Function*** is a function of the form: <br/>
`R(x) = n(x)/d(x)` <br/> where **n(x) and d(x)** are polynomials.

***Domain:*** Input 'range' of x.

***Range:*** Output 'range' of y.

***Y-axis:*** "Vertical Asymptote"

  - Vertical Asymptote: <br/>
  A Vertical Asymptote for a rational function is a line `x=k`; <br/>
  Where 'k' is a zero of the denominator of the function.

Example:

```
f(x) = (2x+5)/(x-2)
```

When x is close to 2, x-2 is close to 0, so dividing by a very small number, which gives us large numbers.

"(1 - 2), (1.5 - 2), (1.75 - 2), (1.9 - 2), (1.999999 - 2)"

***X-axis:*** "Horizontal Asymptote"

  - Horizontal Asymptote: <br/>
  A Horizontal line 'y=k' such that as x gets larger, R(x) gets closer to 'k'. <br/> In other works... **"As x -> ∞; R(x) -> k"**

***Diagonal Asymptote:***

Example: <br/> Given function...
***f(x) = (x<sup>2</sup> + 2x - 8)/(x-1)*** <br/> We can divide simplify the expression by completing the division; Which will give us the equation (with a remainder):
`(x + 3) - (5)/(x-1)`.

The Diagonal Asymptote is then defined by the equation: `y = x + 3`


### Summary of Vertical and Horizontal asymptotes:

Vertical asymptotes are lines 'x=k'; Where k is a zero of **d(x) but not of n(x)**.

- Vertical asymptotes ***correspond*** to zeros of the denominator!

***Extra rules:***
```
If (n(x) has a smaller degree than d(x)) {
  then 'y = 0' (the x-axis) is a Horizontal Asymptote;
}
Else if (n(x) and d(x) have the same degree) {
  then 'y = (a/b)' is the Horizontal Asymptote {
    Where 'a' and 'b' are the leading coefficients of n(x) and d(x);
  }
}
Else if (n(x) has a higher degree than d(x)) {
  then the Horizontal Asymptote is actually a DIAGONAL Asymptote;
}
```
