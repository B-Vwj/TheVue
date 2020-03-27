+++
title = "CSS in Depth"
menutitle = "CSS in Depth"
description = "Notes/Documentation for CSS"
weight = 1
+++

## Introduction to CSS

“CSS is not a programming language, strictly speaking, but it does require abstract thoughts.”

Most Fundamental Principles:
- The Cascade
- The Box Model
- Wide array of unit types available

The HTML code we’ll be basing the CSS code about is:

```
<!DOCTYPE HTML>
<head>
	<link href=“styles.css” rel=“stylesheet” type=“text/css” />
</head>
<body> 	<header class=“page-header”>
		<h1 id=“page-title” class=“title”>Wombat Coffee Roasters</h1>
		<nav>
			<ul>
				<li><a href=“/“>Home</a></li>
				<li><a href=“/coffees”>Coffees</a></li>
				<li><a href=“/brewers”>Brewers</a></li>
				<li><a href=“/specials” class=“featured”>Specials</a></li>
			</ul>
		</nav>
	</header> </body>
```
