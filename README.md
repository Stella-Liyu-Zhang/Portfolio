# CSS

We are finally jumping to the next step of learning CSS!

-Prefer em and rem over percentages, because me is meant for font so it's semantically cleaner
- Use rem to avoid compounding sizes

## Acknowledgement

This material is mainly derived from Professor Powell's CSE 134 lecture slides at UC San Diego.

For question that I came across, I also consulted my mentor *Cam

## Version of CSS
These are usually to make sure that the browser gets a new version when the site gets updated with a new version, e.g. as part of our build process we'd have something like this:
```CSS
    <link rel="stylesheet" href="style.css?v=6">
```
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
## CSS Notes in my Portfolio Project 
I practice CSS syntaxes and logics by building my portfolio websites!
Here are some notes that I made in order to track what I learned throughout the whole dev progress.

### "*" 
The * means "all elements" (a universal selector), so we are setting all elements to have zero margins, and zero padding, thus making them look the same in all browsers.

### Importing Google font API
How to: 
```css
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600;700&family=Ubuntu:wght@400;500;700&display=swap');

font-family: 'Poppins', sans-serif;
```

### Don't forget the "rel="icon""!

The rel attribute defines the relationship between the current page and the linked resource. The rel="icon" value defines the web page icon or favicon which visually represents the website. The icon URL is specified in the href attribute.

```html
    <link rel="icon" type="image/x-icon" href="websiteimgs/anime.jfif">
```
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

### 
```css
@keyframes img-load {
    0% {
        transform: translateX(-100%);
    }
    100% {
        transform: translateX(0%);
    }
}
```

### font-weight
The font-weight CSS property sets the weight (or boldness) of the font. The weights available depend on the font-family that is currently set.

### linear-gradient
The linear-gradient() CSS function creates an image consisting of a progressive transition between two or more colors along a straight line. Its result is an object of the ```<gradient>``` data type, which is a special kind of ```<image>```.



## Conclusion
There are many data types (values) in CSS, and many different measurement units for each value.
There are many different unit types, most notably absolute and relative units.
There are enumerated identifiers in CSS that appear to be strings but are not quoted. Strings in CSS exist, and must be either single or double quoted.
CSS has a number of built in functions, include those for color and calculations.