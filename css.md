# CSS

### Selectors

**Elements**
```css
img {
    /* all these styles apply to every <img> */
}
```

**Classes**
`.class-name{}`

**ID**
`#my-element{}`

**Rules**

```css
.my-wrapper .my-class{
    /*will apply only to "my-class" elements that are WITHIN "my-wrapper"*/
}

.class-one, .class-two {
    /*applies to both classes*/
}
```

### Pseudo selectors
```css
.my-class:hover{}
.my-class:focus{}

.my-class:first-child {
    /*only the first child WITHIN my-class*/
}

.my-class:nth-child(3) {
    /*only the 3 child in my-class*/
}

.class-one > .child {
    /*only direct children*/
}

.class-one.class-two {
    /*must have BOTH of these classes*/
}
```

### Units
- `px`
- `%`: percentage of the element's parent
- `vw`/`vh`: percentage viewHeight or viewWidth
- `rem`: ration of the root font-size

### Some basic CSS rules
```css
.class {
    color: blue; /*for text color*/
    background: red; /*background color*/
    width: 10px;
    max-width: 100vw; /*can't be bigger than 100% of width*/
    height: 10px;
    max-height: 100vh; /*can't be bigger than 100% of height*/
    margin: 20px; /*outside the element*/
    padding: 20px; /*inside the element*/
    font-size: 10px;
    font-family: "Avenir", Helvetica; /*Specific one, default if not found*/
}
```

### Position
- `relative`: default for all elements, will be arranged based on their siblings
- `absolute`: removes the element from the "flow" of sibling element. Instead, it becomes positioned based on its 
closest parents that has "relative" positioning. You can use `top`, `bottom`, `left`, `right` to move it around precisely
- Note: either "relative" or "absolute" positioning lets you use the `z-index`

### Display
- `block` (default)
- `inline-block` (stack horizontally)
- `none` (hide)
- `flex` (the King 👑)

### Flexbox
```css
.parent {
    display: flex;
    flex-direction: column; /*or row*/ 
    align-items: center; /*or flex-start, flex-end, space-between, space-around*/
    justify-content: center; 
    flex-wrap: wrap; /*allows children to wrap*/
    flex-flow: column wrap; 
}

.child {
    flex: 1; /*the ratio of how much space to take up*/
}
```
- `align-items`: aligns opposite the direction axis
- `justify-content`: aligns items along direction axis
- `flex-flow`: combines `flex-direction` and `flex-wrap` into one

### Responsive CSS

```css
html { /* MOBILE */
    font-size: 15px;
}

@media (min-width: 400px) {
  html { /* TABLET */
    font-size: 18px;
  }
}

@media (min-width: 768px) {
  html { /* DESKTOP */
    font-size: 21px;
  }
}
```

- you can use `rem` units to scale other elements on your page in relation to the `font-size` on your `<html>` element

### Animations
```css
.my-button {
    transition: all 0.2s; /*a "transition on your animation*/
}

.my-button:hover {
    transform: scale(1.2, 1.2) translate(100px, 50px);
}
```

Using "transform" or "opacity" for animations makes your application WAY more performant
and will not slow down the page, even with thousands of animations running

**Long Running Animations**
```css
.logo{
  animation: spinny infinite 20s linear;
}
@keyframes spinny {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}
```