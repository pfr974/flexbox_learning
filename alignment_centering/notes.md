# About alignment and centering

Starting with our basic html and CSS files, we have the following:

![flexbox1](start.png)

Now, let's start to play with the CSS by adding a `justify-content` property to the `.container` class:

```css
.container {
  display: flex;
  justify-content: center;
  border: 10px solid goldenrod;
}
```

(I added a border to the container so we can see where it is)

What does `justify-content` do? It aligns the flex items along the main axis which is, by default, horizontally from left to right. Here with `justify-content: center;` we are telling the flex items to be centered along the main axis, giving us the following:

![flexbox2](justify_content_demo_center.png)

The other values that can be used for `justify-content` are: `flex-start`, `flex-end`, `space-between`, `space-around`, and `space-evenly`. The following link has a great visual demo of each of these values: https://css-tricks.com/snippets/css/a-guide-to-flexbox/#aa-justify-content.