# Flexbox, creating a flexbox navigation bar

## Introduction 

We start with the following HTML:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>FlexBox Nav</title>
  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/font-awesome/4.3.0/css/font-awesome.min.css">
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <div class="wrapper">

    <nav class="flex-nav">
      <ul>
        <li><a href="#">Item 01</a></li>
        <li><a href="#">Item 02</a></li>
        <li><a href="#">Item 03</a></li>
        <li><a href="#">Item 04</a></li>
        <li><a href="#">Item 05</a></li>
        <li><a href="#">Item 06</a></li>
        <li class="social">
          <a href="http://twitter.com/wesbos"><i class="fa fa-twitter"></i></a>
        </li>
        <li class="social">
          <a href="http://facebook.com/wesbos.developer"><i class="fa fa-facebook"></i></a>
        </li>
        <li class="social">
          <a href="http://github.com/wesbos"><i class="fa fa-github"></i></a>
        </li>
        <li class="social">
          <a href="http://instagram.com/wesbos"><i class="fa fa-instagram"></i></a>
        </li>
      </ul>
    </nav>

  </div>

</body>
</html>
```

and the following CSS:

```css
/* Some CSS Setup - nothing to do with flexbox */
html {
  box-sizing: border-box;
}

*, *:before, *:after {
  box-sizing: inherit;
}

body {
  font-family: sans-serif;
  margin: 0;
  background-image: linear-gradient(260deg, #2376ae 0%, #c16ecf 100%);
}

a {
  color:white;
  font-weight: 100;
  letter-spacing: 2px;
  text-decoration: none;
  background:rgba(0,0,0,0.2);
  padding:20px 5px;
  display: inline-block;
  width: 100%;
  text-align: center;
  transition:all 0.5s;
}

a:hover {
  background:rgba(0,0,0,0.3);
}

.wrapper {
  max-width: 1000px;
  margin: 0 auto;
  padding:50px;
}

/* Flex Container */
.flex-nav ul {
  border:1px solid black;
  list-style: none;
  margin: 0;
  padding: 0;
  
}

@media all and (max-width:1000px) {
}

@media all and (max-width:500px) {
}
```
Please note that our focus in the CSS file is on the `.flex-nav ul` selector. Everything is mostly about having the page looking good.

Our page initially looks like this:

![Initial state](initial_state_flexnav.png)

## Working on the flex container

Let's start simple and have the following lines in our CSS:

```css
/* Flex Container */
.flex-nav ul {
  border:1px solid black;
  list-style: none;
  margin: 0;
  padding: 0;
  display: flex;
}

.flex-nav li {
  flex: 3;
}

.flex-nav .social {
  flex: 1;
}
```

which gives us:

![First modification, full window](first_modif_flexnav.png)

Here, `ul` is the flex container and the `li`'s are the flex items. By having `flex: 3;` for them and `flex: 1;` for `.social`, we make sure that the social icons are not taking as miuch space as the other items. Please note that initially, `.flex-nav li` sets up all the items the same but `.flex-nav .social` will override it for the `.social` class items.

Another interesting thing to note at this stage is that if we reduce the window size, we still get something relatively nice:

![First modification, smaller window](first_modif_flexnav_small_window.png)

**This simplicity is what I have been enjoying about flexboxes in my learning.**