## Rating

> ⭐️⭐️⭐️⭐️
>
> Note: This is a personal rating based on my own experience and understanding of the library, the downside is the plugin that are chargeable for more complex animation

## What is GSAP

GSAP is a library that allow you to turn SVG into powerful animation, NPM package has 350k download weekly, very active activity (last week update on their repo started 11 years ago) almost 17k ⭐️ on [Github](https://github.com/greensock/GSAP)

Video introduction in 90sec

https://www.youtube.com/watch?v=RYuau0NeR1U

## How SVG work

SVG can be created using the `path d=""` element (for the most complex one which is what pick our interest, see the path similar to CNC language machine where each coordinate is executed to move the SVG in the direction wanted

- Move command is represented by the letter `M` let say we want to move a line into the X/Y coordinate, we would call the path element with `M 10 10`
- `L` would allow us to draw a line and can be represented using _absolute_/_coordinate_ like this
  ```
  L x y
    or
  l dx dy
  ```
- `H` or `V` would allow us to drawns Horizontal (`H`) or Vertial (`V`) line
  `<path d="M 10 10 H 90 V 90 H 10 L 10 10"/>`
- We can shorten the above path for example using the "Close Path" reprensted with `Z`
  `<path d="M 10 10 H 90 V 90 H 10 L 10 10"/>` become `<path d="M 10 10 H 90 V 90 H 10 Z"/>`

- A Tween is an animation which add feature like `repeat()` `repeatDelay()` `yoyo()` ...

  > syntax : TweenMax.method(element, duration, vars)

## Tips

- Using the GSDevTools.create({}) (for codepen as an example) can help drasticaly for complex animation [Link of the CDN for CodePen](https://s3-us-west-2.amazonaws.com/s.cdpn.io/16327/GSDevTools3.min.js)

## Reusable items example

The below code is a resuable function that would apply specific animation base on the CSS class

```js
const bars = (iten) => {
  let tl = new TimelineMax();
  tl.staggerTo(item, 4, {
    scaleY: 0,
    transformOrigina: "bottom 0%",
    yoyo: true,
    repeat: -1,
    ease: Power0.easeNone,
    stagger: {
      amount: 1.5,
    },
  });
  return tl;
};
```

All commands came in two variantes, an Uppercase letter would mean _absolute_ coordinate on the page, while _lowercase_ would mean relative coordinate.

## MorphSVGPlugin

Really powerful and allow to morph SVG into specific shape, but also allow to have animation using the property `MorphSVGPlugin.pathData.ToBezier` which would allow you to align the initial SVG to some shape you would have draw in your editor and set to invisible for example

> [Docs](https://greensock.com/docs/v3/Plugins/MorphSVGPlugin)

[[info | Info]]
| **Plugins** in general / MorphSVG is part of the paid plugin from GSAP

## Resources

- [OMG SVG](https://svgomg.net/) Allowing you to pretify your SVG you created yourself or found online
- [Affinity Designer](https://affinity.serif.com/en-us/) Allow you to create your own SVG (similar to Illustrator but cheaper, free alternative -> Inkscape)
- [CodePen animation example](https://codepen.io/nexty5870/pen/mdQBjdL)
