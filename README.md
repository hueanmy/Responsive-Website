# :raised_hand: Responsive-Website :raised_hand:

Introduce some principles when designing responsive website.

## :point_right: Grid View

## :point_right: Media Queries

*Note: Media Queries cannot work with IE8 and lower versions. Some support libraries that will provide Javascript processing include Respond.js and CSS3-MediaQueries.js.

### What? 
Media Queries is a CSS technique introduced in CSS3. We use the @media syntax to include a block of CSS properties only if a certain condition is true
```
@media only screen and (max-width: 600px) {
    body {
        background-color: blue;
    }
}
```

### Break point

```
/* For desktop: */
.col-1 {width: 8.33%;}
.col-2 {width: 16.66%;}
.col-3 {width: 25%;}
.col-4 {width: 33.33%;}
.col-5 {width: 41.66%;}
.col-6 {width: 50%;}
.col-7 {width: 58.33%;}
.col-8 {width: 66.66%;}
.col-9 {width: 75%;}
.col-10 {width: 83.33%;}
.col-11 {width: 91.66%;}
.col-12 {width: 100%;}

@media only screen and (max-width: 768px) {
    /* For mobile phones: */
    [class*="col-"] {
        width: 100%;
    }
}
```

### Example
```
/* For mobile phones: */
[class*="col-"] {
    width: 100%;
}
@media only screen and (min-width: 600px) {
    /* For tablets: */
    .col-s-1 {width: 8.33%;}
    .col-s-2 {width: 16.66%;}
    .col-s-3 {width: 25%;}
    .col-s-4 {width: 33.33%;}
    .col-s-5 {width: 41.66%;}
    .col-s-6 {width: 50%;}
    .col-s-7 {width: 58.33%;}
    .col-s-8 {width: 66.66%;}
    .col-s-9 {width: 75%;}
    .col-s-10 {width: 83.33%;}
    .col-s-11 {width: 91.66%;}
    .col-s-12 {width: 100%;}
}
@media only screen and (min-width: 768px) {
    /* For desktop: */
    .col-1 {width: 8.33%;}
    .col-2 {width: 16.66%;}
    .col-3 {width: 25%;}
    .col-4 {width: 33.33%;}
    .col-5 {width: 41.66%;}
    .col-6 {width: 50%;}
    .col-7 {width: 58.33%;}
    .col-8 {width: 66.66%;}
    .col-9 {width: 75%;}
    .col-10 {width: 83.33%;}
    .col-11 {width: 91.66%;}
    .col-12 {width: 100%;}
}
```
## :point_right: Use relative values instead of absolute values (avoid using traditional units like pixels or inches).

Absolute values cannot be resized horizontally / horizontally by devices.

Some values can using: %, rem, vh, vw, ch, ex, vmax, vmin

### %

```
@media only screen and (min-width: 992px) {
    .image {
        width: 100%;
    }
}
```

### rem

#### Why using rem?

```
<body>
    <div class="test">Test</div>
</body>
```

```
body {
    font-size: 14px;
}
div {
    font-size: 1.2em; // calculated at 14px * 1.2, or 16.8px
}
```

```
<body>
    <div>
        Test <!-- 14 * 1.2 = 16.8px -->
        <div>
            Test <!-- 16.8 * 1.2 = 20.16px -->
            <div>
                Test <!-- 20.16 * 1.2 = 24.192px -->
            </div>
        </div>
    </div>
</body
```
There are too many font-size dependencies in a large website, to avoid this it is best to base it on a single font size value. That's why "rem" was born, "R" in rem stands for "root"; this is equal to the font set at the root; in most cases it is an html element.

```
html {
    font-size: 14px;
}
div {
    font-size: 1.2rem;
}
```

Rem can using for grid

You can rely on an entire grid system or UI style library on the original font of HTML by using rem and its widespread use in specific places. This predicts for font sizing and scaling

```
.container {
    width: 70rem; // 70 * 14px = 980px
}
```

### vh & ch

Reactive web design techniques depend heavily on percentage rules. However, CSS ratios are not always the best solution for every problem. The width of the CSS relative to the closest parent element.

The vh element is 1/100 the height of the viewport. For example, if the height of the browser is 900px, 1vh will evaluate to 9px. Similarly, if the viewport width is 750px, 1vw will evaluate to 7.5px.

```
.slide {
    height: 100vh;
}
```

### vmin and vmax

```
.box {
    height: 100vmin;
    width: 100vmin;
}
```

### ex and ch

Note: Can using calc:

```
.nav-left {
    height: calc(100% - 64px);
}
```

## :point_right: Use SVG icons instead of regular image icons (JPG, PNG, ...)

SVG icons and images will not be blurred when zoomed in any size

## :point_right: Display flow type content
This principle means that content should only be displayed in one line from top to bottom, absolutely avoid having users swipe horizontally to be able to see the content, they will leave your site immediately.


