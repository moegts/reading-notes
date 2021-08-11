# CSS Transforms, Transitions, and Animations

## Transforms

### With CSS3 came new ways to position and alter elements. Now general layout techniques can be revisited with alternative ways to size, position, and change elements. All of these new techniques are made possible by the transform property.

#### The transform property comes in two different settings, two-dimensional and three-dimensional. Each of these come with their own individual properties and values.

#### Within this lesson we’ll take a look at both two-dimensional and three-dimensional transforms. Generally speaking, browser support for the transform property isn’t great, but it is getting better every day. For the best support vendor prefixes are encouraged, however you may need to download the nightly version of Chrome to see all of these transforms in action.

```bash
div {
  -webkit-transform: scale(1.5);
     -moz-transform: scale(1.5);
       -o-transform: scale(1.5);
          transform: scale(1.5);
}
```

### 2D Transforms

#### 2D Rotate

#### The transform property accepts a handful of different values. The rotate value provides the ability to rotate an element from 0 to 360 degrees. Using a positive value will rotate an element clockwise, and using a negative value will rotate the element counterclockwise. The default point of rotation is the center of the element, 50% 50%, both horizontally and vertically. Later we will discuss how you can change this default point of rotation.

```bash
//HTML
<figure class="box-1">Box 1</figure>
<figure class="box-2">Box 2</figure>

// CSS
.box-1 {
  transform: rotate(20deg);
}
.box-2 {
  transform: rotate(-55deg);
}
```

### Transitions#transitions

```bash

.box {
  background: #2db34a;
  transition-property: background;
  transition-duration: 1s;
  transition-timing-function: linear;
}
.box:hover {
  background: #ff7b29;
}

```

> transitions animations is very nice thing when i want to create any such thing i will practice it 😊

> I really do like the 404 animation

[404](https://codepen.io/kieranfivestars/pen/MYdQxX)

> this animation remind me that i am desinger xD

[Ball jumper](https://codepen.io/dp_lewis/pen/gCfBv)

> nice animation of buttons flying and stop when i hover over it

[buttons](https://codepen.io/retyui/pen/ByoaXV)

