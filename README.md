# CSS

We are finally jumping to the next step of learning CSS!

-Prefer em and rem over percentages, because me is meant for font so it's semantically cleaner
- Use rem to avoid compounding sizes

## Acknowledgement

This material is mainly derived from Professor Powell's CSE 134 lecture slides at UC San Diego.

For question that I came across, I also consulted my mentor *Camdyn Rasque*.

## Version of CSS and JavaScript:
These are usually to make sure that the browser gets a new version when the site gets updated with a new version, e.g. as part of our build process we'd have something like this:
```html
    <link rel="stylesheet" href="style.css?v=6">
```
Same for JavaScript:
```html
    <script src="script.js?v=5"></script>
```
## CSS Notes in my Portfolio Project 
I practice CSS syntaxes and logics by building my portfolio website!
The website is published **[HERE](https://stella-liyu-zhang.github.io/Portfolio/)**!

Here are some notes that I made in order to track what I learned throughout the whole dev process.
### The HTML Tree of my website:
- ```<head>``` part, where we 
    - link the style sheet and script APIs.
    - specify the metadata
    - Specify the title and the image/x-icon!
- ```<body>``` part, where we have 
    - navbar, including
        - logo ("stella zhang" home title)
        - menu (including all the 6 sections in ```<main>```).
    - ```<main>``` , where we have multiple sections, including 
        - About
            - column left
                - image
            - column right 
                - text-1: "Hello, I'm Stella!"
                - body:
                - LinkedIn and GitHub
        - Skills
        - SWE and PM Experiences
        - Academia Experience
        - Projects
            - Left: the demoing Google slides/picture
            - Right:
                - Time length
                - Description
                - View Project's project link.
        - Gallery
            - pictures/videos
        - Contact
- ```<footer>``` part
### "*" 
The * means "all elements" (a universal selector), so we are setting all elements to have zero margins, and zero padding, thus making them look the same in all browsers.

### Importing Google font API
How to: 
```css
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600;700&family=Ubuntu:wght@400;500;700&display=swap');

font-family: 'Poppins', sans-serif;
```
### grid-row and grid-column
Make "item1" start on row 1 and span 2 rows:
```css
.item1 {
  grid-row: 1 / span 2;
}
```
Make "item1" start on column 1 and span 2 columns:
```css
.item1 {
  grid-column: 1 / span 2;
}
```
### Don't forget the "rel="icon""!

The rel attribute defines the relationship between the current page and the linked resource. The rel="icon" value defines the web page icon or favicon which visually represents the website. The icon URL is specified in the href attribute.

```html
    <link rel="icon" type="image/x-icon" href="websiteimgs/anime.jfif">
```
### Scroll-behavior of html
```CSS

html{
    scroll-behavior: smooth;
}

/* Keyword values */
scroll-behavior: auto;
scroll-behavior: smooth;

/* Global values */
scroll-behavior: inherit;
scroll-behavior: initial;
scroll-behavior: revert;
scroll-behavior: revert-layer;
scroll-behavior: unset;
```

### Scroll bar 
- ::-webkit-scrollbar — the entire scrollbar.
- ::-webkit-scrollbar-button — the buttons on the scrollbar (arrows pointing upwards and downwards that scroll one line at a time).
- ::-webkit-scrollbar-thumb — the draggable scrolling handle.
- ::-webkit-scrollbar-track — the track (progress bar) of the scrollbar, where there is a gray bar on top of a white bar.
- ::-webkit-scrollbar-track-piece — the part of the track (progress bar) not covered by the handle.
- ::-webkit-scrollbar-corner — the bottom corner of the scrollbar, where both horizontal and vertical scrollbars meet. This is often the bottom-right corner of the browser window.
- ::-webkit-resizer — the draggable resizing handle that appears at the bottom corner of some elements.

### 
### Grid
To build a 2*3 grid, CSS would be
```CSS
.skills-wrapper{
    display:grid;
    grid-template-columns: 1fr 1fr 1fr;
    padding: 1em;
    grid-auto-rows:100px;
}
```
### Section
The padding-bottom CSS property sets the height of the padding area on the bottom of an element.



```CSS
section{
    padding-top: 50px;
    padding-bottom: 100px;
    padding-right: 0 px;
    padding-left: 0px;
}
```

### max-width

### .navbar.sticky .menu li a:hover

is when your mouse hover the area

### translateY() function
The translateY() CSS function repositions an element vertically on the 2D plane. Its result is a <transform-function> data type.

```css
@keyframes img-load {
    0% {
        transform: translateX(-100%);
    }
    100% {
        transform: translateX(0%);
    }
}
@keyframes button-load {
    0% {
        transform: translateX(300%);
    }
    100% {
        transform: translateX(0%);
    }
}
```
### z-index
## fas fa-angle-up

### display:flex
### padding-top, padding bottom

### font-weight
The font-weight CSS property sets the weight (or boldness) of the font. The weights available depend on the font-family that is currently set.

### linear-gradient
The linear-gradient() CSS function creates an image consisting of a progressive transition between two or more colors along a straight line. Its result is an object of the ```<gradient>``` data type, which is a special kind of ```<image>```.

## CSS BasicS


- Syntax
```CSS
h1 /* Selector */ 
{
  font-size/* Property Name */
  : /* Declaration */ xx-large /* Value */; /* Declaration Separation */
  color: red;
}
```
- Where should the style sheet be?
    - External style sheet
        - Pros: Can set styles for many pages in a site with one document
        - Cons: Extra download for style sheet
        - linked style sheets
            ```html
            <link rel="stylesheet" href="screenstyle.css" type="text/css">
            ```
             - with optional media attribute
             - can use JavaScript to target specific style sheet to toggle between them
    - Document wide style sheets
            - Pros: Control document style in one place. No additional download
            - Cons: Need to reapply style for subsequent pages
    - Inline style
        - Pros: Can control style to a single character, overrides other styles
        - Cons: Need to reapply for every document. Bound too closely to tages so as to be little more than a new tag
        - these properties will always beat out others, except when !important is applied
- Importing Style

```@import``` can be used to import other stylesheet into the current stylesheet

#### Selectors:
- Basics Selectors:
    - ```id``` Selectirs (#)
        - #example
        - should only appear once in each doc
    - ```class``` Selectors (.)
        - .example
        - to create a grouping or to associate like elements
    - ```Type``` Selectors 
        - h2
        - select all h2 element
- Grouping Selectors
    - ```,``` Selectors
        - h1, h2
        - Select all h1 and h2
- Combinators
    - (space) All Child Selector
        - ```body p```
        - select all ```p``` in ```body``` with nesting
    - ```> ``` Direct Child Selector
        - ``` body > p```
        - Select all ```p``` in ```body``` without nesting
    - ```+``` Adjacent sibling Selector
        - ```h1+p```
        - Select all ```p``` that follows ```h1```
- Attribute Selectors
    - General Syntax
        - element ```[attribute=value]```
        - ```[attr]``` 
            - Represents elements with an attribute name of attr
            - ```[href]```
            - target any element with attribute ```href```
        - ```[attr=value]```
            - Represents elements with an attribute name of attr whose value is exact value 
            - ```[href="hello.com"]```
            - target any element with attribute ```href="hello.com"```
        - ```[attr~=value]```
            - Represents elements with an attribute name of attr whose value is a whitespace-separated list of words, one of which is exactly value.
            - ```[href~="hello"]```
            - target any element with attribute ```href``` that contains ```hello```
        - ```[attr|=value]```
            - Represents elements with an attribute name of attr whose value can be exactly value or can begin with value immediately followed by a hyphen, - (U+002D). It is often used for language subcode matches.
            - ```[id |= "fig"]```
            - target any element with attribute id that start with fig follow by a ```-```
        - ```[attr^=value]```
            - Represents element with an attribute name of attr whose value is prefixed (preceded) by value.
            - ```[href^="https"]```
            - target any element with attribute ```href``` that starts with ```https```
        - ```[attr$=value]```
            - Represents elements with an attribute name of attr whose value is prefixed (preceded) by value.
            - ```[href^="https"]```
            - target any element with attribute ```href``` that starts with ```https```
        - ```[attr*=value]```
            - Represents elements with an attribute name of attr whose value contains at least one occurrence of value within the string.
            - ```[href*="hello]```
            - target any element with attribute ```href``` that contains the word ```hello```
        - ```[attr operator value i]```
            - Adding an i (or I) before the closing bracket causes the value to be compared case-insensitively (For characters within the ASCII range)
            - ```[href="hello.com" i]```
            - target any element with attribute ```href``` that is case insensitive
            - ```[href="hello.com" s]```
            - target any element with attribute ```href``` that is case sensitive

### Pseudo
Pseudo elements
- pseudo elements is a keyword added to a selector that lets you style a specific part of the selected element(s)
- can only use one pseudo element in a selector
- double colon should be used instead of single colon to distinguishes pseudo-classes with pseudo-elements

Pseudo Classes
- a pseudo class is added to a selector that specifies a special state of the selected element
- apply style to external factors like the history of the navigator or position of the mouse, or the status of its content

### Inheritance - Tree in Use
- Elements inherit the rules of their enclosing parents
- Note: Not every rule inherits
- Note: Defaults inherit too

### CSS Units
- pixels (px)
- points (pt)
- inches (in)
- metric centimeters (cm), millimeters (mm)
- picas (pc)
- em measurements (em, rem)
- ex measurements (ex)
- characters (ch)
- percentage values (%)
- view point dimensions (vh, vw)
- etc...
### font properties 
- ```font-family```
    - used to set to the font family used to render text
    - may be generic name or specific font type
    - all browser support
        - Serif
        - Sans-serif
        - Cursive
        - Fantasy
        - Monospace
- ```font-size```
    - Used to set the relative or physical size of the font
- ```font-style```
    - values: normal, italics, or oblique
- ```font-weight```
    - used to select the weight or darkness of the font 
    - values: range from 100 - 900 with keywords values 
- ```font-variant```
    - used to set a variation of the current font
    - values: small-caps and normal
- ```font-stretch```
    - used to stretch or condense fonts and text
    - values: ultra-condensed, condensed, expanded
- ```font-size-adjust```
    - used to scale fonts to make content take up similar space regardless of font availability 
- ```font```
    - short hand form and allows all font-properties to be specified
    - ```font: font-style font variant font-weight font-size/line-height font family```

### Text Properties 
- text-transform
    - can be used to effect the capitalization of the text
    - values: capitalize, uppercase, lowercase
- text-decoration
    - can be used to define an effect on text
    - values: line-through, overline, underline, and none
- word-spacing
    - specifies the amount of space between words
- letter-spacing
    - specifies the amount of space between letters
- text-align
    - determines how text in a block-level element is horizontally aligned
    - values: left, right, center, justify
- text-indent 
    - sets the indentation of text in the first line of a block-level element
- line-height
    - sets the height between lines in a block-level element
- white-space
    - controls how space, tabs, and newline characters are handled in an element
    - values:normal, pre, nowrap
- text-shadow
    - create drop shadows on text
### Vertical Alignment
- ```vertical-align```
        - controls the vertical positioning of text and images with respect to the baseline currently in effect.
- ```list-style-type```
    - set the type of the list numbering or bullet for ```<ol>``` and ```<ul>```
    - values: decimal, lower-roman, upper-roman, lower-alpha, upper-alpha, disc, circle, square, and none
- ```list-style-imge```
    - can be used to set the bullet to an image
- ```list-style-position```
    - can be used to set where the labels for the list are positioned relative to the box/block that makes up the list
    - values: inside and outside
- list-style
    - short hand for all above

### Background Properties
- ```background-color```
    - used to set an element's background color
    - values: transparent or color value
- ```background-image```
    - used to set a background image for any element
- ```background-repeat```
    - used to determine how a background image tiles when it is smaller than the region it is used in
    - values : repeat, repeat-x, repeat-y, no-repeat
- ```background-attackment```
    - can be set to limit of a background hsould be fixed or scroll.
    - values: fixed, scroll 
- ```background-position```
    - used to specified where a background image should be positioned
- ```background```
    - short hand property for all above

### Box Properties
- includes margin, border, padding
- ```box-sizing:```
    - ```content-box```: element size is defined by just the content size itself
    - ```border-box:``` element size is defined by adding the border, padding and the size of the content size

### Margins
- ```margin, margin-top, margin-right, margin-bottom, margin-left```
     - can set with negative units, but be careful about clipping
### Borders 
- ```border-style```
    - used to set type of border
    - values: dotted, dashed, double, groove
- ```border-width```
- ```border-color```
### Padding
- padding can be set to specify the space between the element's border and its contents
- ```padding, padding-top, padding-right, padding-bottom, padding-left```

### Float and Clear
- float
    - property that float block elements, which allows text to wrap around the block element
- clear 
    - act like a ```<br>``` to clear the floating madness

### Display
- none
    - not only invisible but also doesn't take up window space
- block 
    - can be used to turn an element into a block element
- inline
    - turn an element to an inline form
- list-item
    - turn an elment to an inline
- compact
- run-in
- marker
    - allows the automatic inclusion of flagged elements

## CSS Layout

### CSS Flexbox and Grid
- Flexbox lets us layout content in a 1-D contect where the items can flex to fill additional spaceor shrink to fit smaller places
- Grid lets us layout content in a 2-D context. This allows us to dynamically organize our content into rows and columns

Before starting this section, let's take a look at some terminology:
![terminologies of flexbox and grid](/imgs/terminologies%20of%20flexbox%20and%20grid.png)
> Note that a flex item can also be a flex container for items within itself.

### Container Peoperties: display and flex-direction
- display
    - Values: flex or inline-flex
    - Function: Establishes an element as a flexbox container. flex sets the elemnt as a block, inline-flex sets the element as inline.
- flex-direction
    - Values: row, row-reverse, column, column-reverse
    - Function: Specifies the direction that the items within the container flow.

### Container Property: flex-wrap
- Values: nowrap, wrap, wrap-reverse
- Function: Controls whether the flex container is single-line or multi-line, as well as the direction of the cross-axis
- Note: wrap and wrap-reverse will try to preserve item width ( in a fixed width container), nowrap will either squish items or let them overflow.

### Container Property: flex-flow
- flex-flow
    - Values: <>

## Container Property: justify-content 
- justify-content 
    -Values: flex-start, flex-end, center, space-between, space-around
    ![demo](/imgs/demo%20of%20justify-content.png)
## Flexbox

## CSS Units 
     
### CSS Values 

CSS values are values assigned to a property, including 
- keywords,
- integers/real numbers
- lengths
- percentages
- URL/URIs
- counters
- colors
- strings
- angles
- durations
- resolutions

CSS Values are sometimes refered to as data types- these terms are essentially interchangeable.

### Textual data types
1) Pre-defined keywords: 
    - values defined by the CSS spec that have inherent meanings (UNQUOTED). For example,
    ```css 
    text-decoration: underline
    ```
2) Author-defined Identifiers:
    - are simialr to keywords, but are defined by the author and thus have no ineherent meaning (UNQUOTED). For example,
    ```CSS
    grid-area: top-left;
    ```
3) Explicitly Author-defined Identifiers:
    - are author-defined identifiers that can be used in places that also take CSS-defined identifiers. They are all prefixed with double dashes.
    ```CSS
    .foo { --bg-color: blue; }
    ```
4) Quoted Strings:
    - are string values. Take either single or double quotes, and can be broken into multiple lines with \. For example,
    ```CSS
    background-color: "blue";
    content: "This is a long \ value for this property"; 
    ```
5) Resource Locators represnet a pointer to a Resource. They are usually written inside of url() or src() functional notations, and are usaually written inside quotation (recommended). For instance,
    ```CSS
    background: url(“https://a.com/img.jpg“)
    ```

### Numerical data types in CSS:
1) Integers. They can be preceded by a + or -. Example:
    ```CSS
    z-index: 5
    ```
2) Real Numbers. Example:
    ```CSS
    flex-grow: 2.5
    ```
3) Dimensions (including length, angle, time, and resolution types)
    ```CSS
    height: 50px
    ```
4) Percentages. 
    ```CSS
    width: 80%
    ```
5) Mixed percentages and Dimensions 
    ```CSS
    width: calc(100% - 40px)
    ```
6) Rtios are values that area ratio of 2 numeric values. Ex:
    ```CSS
    as-ect ratio: 16 / 9
    ```
## Lengths 
1) Absolute lengths are not sized relative to anythign else and are generally considered tob ethe smae size across devices.
2) Relative lengths are relative to another value, such as the parent element or size of the viewport. Relative units are useful for scaling and responsive design.

### Absolute Unit Comparison (https://codepen.io/dannyjuergens/pen/yLexmLy)
![absolute unit comparison](/imgs/absolute%20unit%20comparisons.png)
### ch and ex
- ch unit describes the character width of the number 0 in the given font.
- ex unit describes the height of a lowercase x in your given font. This can be useful when determining line-heights

### ems and rems
- em is relative to an element's parent font size. 
    - useful for components, where the root font of the component is using rem and the rest of the component just needs to scale based on that root.
- rem is relative to the root element's font size.

**Side note:**: It is recommended that you never manually set the root element font size. This takes away freedom from users such as those with limited vision who might have a larger browser font default. 


### Viewport-percentage Length Units

### Viewport 
- The viewport is the browser window
- On desktop the viewport does not include the top address/nav bar, but it does include the scrollbar.
- On mobile the viewport often includes the top address bar and any chin navigational bar.

### vw and vh
The vw and vh elements represent percentages of the viewport’s width and height respectively. 
> They are useful for creating elemnets and layouts that are based on the viewing window's size instead of hard pixel sizes.


### vmin 
will always retirn the smaller of the 2 screen dimensions, width or height.
> It's useful when we are making sure that something is always entirely visible on a screen.

### vmax
will always retirn the larger of the 2 screen dimensions, width or height.
> It's useful when we need to make sure that something (like a wallpaper) is always covering the entire background.

### Angle length units

| Unit      | Description       | Example     |
| :---        |    :----:        |          ---: |
| deg      | 360 degrees in a circle.     |  ``` {transform: rotate(27deg) }  ``` |
| grad   | 400 gradians in a circle        |   ```{transform: rotate(30grad) } ```   |
| rad    |  There are 2pi radians in a circle. | ```{transform: rotate(0.47rad)} ``` |
| turn    | 1 turn in a circle   |``` {transform: rotate(0.15 turn)}``` |

### Duration (Time) and Frequency Units 
- s: seconds ; ms : millisecond (1000 milliseconds in a second)
```CSS
 { transition-duration: 5s }
 { transition-duration: 50ms }
```

- Hz: Hertz (the number of occurrences per second); kHz: Kilohertz: (1000 Hertz)
```CSS
 { voice-pitch: 50Hz }
 { voice-pitch: 1kHz }
```

### Resolution units:
dpi (dots per inch), dpcm (dots per centimeter), dppx (dots per px unit)

### Percentages: 
calculate a relative value based on the parent's value
- width: 30% will set the width of the element to 30% of the parent's width.
- font-size: 110% will set the font size of the element to 110% of the parent's font size. 

> Note that with font sizing, % and em are pretty much the same thing

## Numbers
unit-less numerical value are allowed sometimes:
- Ex, opacity accepts a value between 0 (fully transparent) and 1 (fully opaque)
> Note that 0 is also unit-less.

### Zero
One value that can be left unit-less is 0. This is because 0px = 0pt = 0% = 0cm = 0mm ….. etc.

## Color - Keywords
1) Named colors: such as red or blue
2) CSS Keywords: there are only 2: currentcolor and transparent
3) System Colors: [Complete list](https://www.w3.org/TR/css-color-4/#typedef-system-color)


### Color-RGB 
A function rgb() has 3 required parameters:
- The first parameter is an integer value 0-255 for how much of the red channel channel is added to the color
- The second and third parameters are the exact same for the green and blue channels respectively
- There could be an optional fourth parameter, A, which can specify the opacity with a value between 0 and 1 (alternatively a percentage from 0% to 100%).
    - This is called the alpha value and is used with rgba()
    -  Red would be rgb(255, 0, 0) or rgba(255, 0, 0, 1)

### Color-Hex RGB
 Always prefixed with a #, can be a 3, 4, 6, or 8 digit hex code
- For 6 and 8 digit hexes, the values are #RRGGBB and #RRGGBBAA
- Each value (R, G, B) represents a color channel - red, green, and blue
- The last value (A) is optional, it’s for the alpha channel (transparency)
    - 00 is completely transparent, FF is completely opaque
    - Each color channel is a hexadecimal number between 00 and FF (0-255 in decimal, same as rgb())
    - The alpha channel is converted to a percentage out of 255
- When rendered, each digit is doubled, lengthening to ##RRGGBB and #RRGGBBAA respectively.

> Note that 4 and 8 digit hex values are supported in most browsers.

### Color - HSL(A)
a function hsl() that accepts 3 parameters for the hue, saturation, and lightness of a color. 
- The hue is a value (either a number or an angle) from 0-360, representing the angle of a color wheel. Here are some base points:

- The saturation is a percentage from 0% to 100% for how saturated the color is 
    - 0% represnets a fully-unsaturated gray, and 100% represenst a fully-saturated bright color.
- Finally, lightness is also a percentage from 0% - 100% for how "light" a clor is 
    - You start at 50% with the raw normal color. 
        - Anything higher think about it like you are adding white paint making it lighter until you have pure white at 100%
        - Anything lower than 50 think about it like you are adding black paint until you eventually have pure black at 0%. 

- hasla() also accepts an alpha value

### Color-Various New Color Functions
Currently support for these is fairly limited ourside of Safari beta, but they are on the horizon. All support alpha values
- hwb() 
    - Hue, Whiteness, and Blackness. Like HSL, this is aimed at having a more human friendly color space.
- lab()
    - Lightness, then a and b stand for the coordinates along the a and b axis of the lab color space.
    - Aimed at better replicating the human eye's perception of color
- lch() 
    - Lightness, Chroma, and Hue. Similar to lab, this color space is also aimed at replicating the human eye's perception of color.
- color()
    - The general color function allows a color to be set in a specified color space
    - There are several predefined color spaces such as strgb, display-p3. and rec2020.
- device-cmyk()
    - In the scenario that a given printer has not been calibrated but specific ink combinations are known through experimentation, this function lets you specify CMYK colors in a device-dependent way.


### Images
The image data type can be used wherever images are valid, usually background.
- It can be a url function (url()) to an actual image or it can be a gradient.
### Position
The position data type consists of a set of 2D coordinates used to position an item.
-It can contain keywords (top, left, bottom, right, and center) as well as lengths (400px, 4in, etc)
- The first value sets the horizontal position and the second value sets the vertical position.

 Ex.
```CSS
    background-position: right 100px
```

### Identifiers
They are not strings and as such should not be quoted.
Depending on the CSS property, different identifiers would be valid. For example, you should set 
```text-align:center```.

### Strings
There are scenarios in which we want to use a string literal in CSS. For instance, setting the content may require the use of a string.
To ensure proper differentiation from identifiers, all strings in CSS should be quoted.
### Functions
CSS has a number of built-in functions, including ones we have seen such as rgb(), hsl(), and url().
- THe functions look and behave similarly to those in other languages - it will consist of a function name and arguments contained in parentheses. 

Some useful CSS functions include:
- calc() - performs a calculation (using + - * /)
- min() - selects the smallest parameter (can use +-*/)
- max() - selects the largest parameter (can use +-*/)
- clamp() - clamps a value between an upper and lower bound (can use +-*/)
- attr() - retrieves the value of an attribute 

### Value combinations
- && separates two or more components, all of which must occur, in any order
- || (double bar) separates two or more options, one or more of which must occur, in any order
- | (single bar) separates two or more options, exactly one of which must occur
- [ ] can be used to group components 
## Conclusion
There are many data types (values) in CSS, and many different measurement units for each value.
There are many different unit types, most notably absolute and relative units.
There are enumerated identifiers in CSS that appear to be strings but are not quoted. Strings in CSS exist, and must be either single or double quoted.
CSS has a number of built in functions, include those for color and calculations.