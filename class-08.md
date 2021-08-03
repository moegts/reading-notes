# CSS Layouts

## using floats

floats are used to view elements side by side

A lot of layouts place boxes
next to each other. The float
property is commonly used to
achieve this

The float property can have one of the following values:

- left - The element floats to the left of its container
- right - The element floats to the right of its container
- none - The element does not float (will be displayed just where - it occurs in the text). This is default
- inherit - The element inherits the float value of its parent

![float](https://i0.wp.com/css-tricks.com/wp-content/uploads/2021/03/web-text-wrap.png?w=540&ssl=1)

## clear

The clear property allows you
to say that no element (within
the same containing element)
should touch the left or right hand sides of a box. It can take
the following values

left
The left-hand side of the box
should not touch any other
elements appearing in the same
containing element.
right
The right-hand side of the
box will not touch elements
appearing in the same containing
element.
both
Neither the left nor right-hand
sides of the box will touch
elements appearing in the same
containing element.
none
Elements can touch either side.

![no clear](https://i0.wp.com/css-tricks.com/wp-content/uploads/2020/12/unclearedfooter.png?w=540&ssl=1)

by using the clear property

```bash
#footer {
   clear: both;
}
```

![clear](https://i0.wp.com/css-tricks.com/wp-content/uploads/2020/12/clearedfooter.png?w=540&ssl=1)

## Screen Sizes

Different users of your site will have screens that various 
sizes you should make your site compatible with every screen
regadless of size

## Screen Resolution

Resolution refers to the number of dots a screen shows per inch. Some 
devices have a higher resolution than desktop computers and most 
operating systems allow users to adjust the resolution of their screens.

## Fixed Width Layouts

in this layout increases or decreases doesnt change the components of the web pages site

### Advantages

- Pixel values are accurate
at controlling size and
positioning of elements.
- The designer has far greater
control over the appearance
and position of items on the
page than with liquid layouts.
- You can control the lengths
of lines of text regardless of
the size of the user's window.
- The size of an image will
always remain the same
relative to the rest of the
page.

### Disadvantages

- You can end up with big gaps
around the edge of a page.
- If the user's screen is a much
higher resolution than the
designer's screen, the page
can look smaller and text can
be harder to read.
- If a user increases font sizes,
text might not fit into the
allotted spaces.
- The design works best on
devices that have a site or
resolution similar to that of
desktop or laptop computers.
- The page will often take up
more vertical space than a
liquid layout with the same
content

## Liquid Layout

in this layout increases or decreases does change the components of the web pages site , it uses percentages to cahnge size

## A Fixed Width Layout

A Fixed Width  layouts that start with a specific size as stipulated by the web designer. They remain that width, regardless of the size of the browser window viewing the page. Fixed-width layouts allow a designer more direct control over how the page will look in most situations.

## Layout Grids

it is used by designers and web designers to help them position items on the web page

[learn more about Grid layouts](https://visme.co/blog/layout-design/)

## CSS Frameworks

CSS frameworks aim to make your life easier by providing the code for
common tasks, such as creating layout grids, styling forms, creating
printer-friendly versions of pages and so on. You can include the CSS
framework code in your projects rather than writing the CSS from scratch