+++
title = "CSS Tips"
menutitle = "Sticky Footer"
description = "Keeping your footer stuck to the bottom of your website."
weight = 1
+++

## Sticky Footer for Your Website!

- Footer at the bottom of page: For your HTML use...

```
<body>
 <div id="page-container">
   <div id="content-wrap">
     <!-- all other page content -->
   </div>
   <footer id="footer"></footer>
 </div>
</body>
```

For CSS an example to use is...

```
#page-container {
  position: relative;
  min-height: 100vh;
}

#content-wrap {
  padding-bottom: 2.5rem;    /* Footer height */
}

#footer {
  position: absolute;
  bottom: 0;
  width: 100%;
  height: 2.5rem;            /* Footer height */
}
```

The `page-container` id tag covers the whole page (header, content, and footer), while the `content-wrap` id tag covers only the content (and possibly the header if you want to include it) while leaving the footer out so that you can position it in its `absolute position` to the bottom, hence: <br/>  `bottom: 0;`
