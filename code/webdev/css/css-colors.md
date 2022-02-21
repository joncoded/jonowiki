# 🚧 CSS colors

### Named colors

```css
.redFont {
    color: red;
}
```

* We could simply use English names of colors but
  * we limit ourselves in terms of shades
  * we can become prone to spelling mistakes :P

### Hexadecimal colors

```css
.hexFont {
    color: #6496C8;
}
```

* First pair of characters after # represents the amount of _red_
* Second pair, the amount of _green_
* Third pair, the amount of _blue_

### RGB colors

Each argument has a range from 0 (black) to 255 (white), creating around 16.7 million shades of color:

```css
.rgbFont {
    color: rgb(100, 150, 200);
}
```

* First number represents the amount of red
* Second, the amount of green
* Third, the amount of blue

However, instead of using a combination of digits and letters in each argument, we can use simpler integers from 0 to 255!

### HSL colors

* First number represents the degree value of the **hue** on the color wheel
  * 0/360 = red
  * 60 = yellow
  * 120 = green
  * 180 = cyan
  * 240 = blue
  * 300 = violet
* Second number represents the **saturation** (ranging from 0% to 100%)
  * 0% = less color (grayer look)
  * 100% = richer color (more vivid look)
* Third number represents the **luminosity** (ranging from 0% to 100%)
  * closer to 0% = increasingly darker to fully black
  * 50% = normal lighting
  * closer to 100% = increasingly brighter to fully white

### Alpha in RSB(A) and HSL(A)

The alpha, or opacity, represents the fourth argument in each of RGB and HSL:

```css
.RGBAClass {
    color: rgba(100, 150, 200, 0.2) /* 20% opacity */
}

.HSLAclass {
    color: hsla(240, 50%, 50%, 1.0) /* 100% opacity */
}
```

Recall that an opacity ranges from 0 to 1: 0 means no visibility and 1 means full visibility!
