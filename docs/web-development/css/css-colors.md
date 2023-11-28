---
description: working with font hues and other light attributes
---

# 🎨 CSS colors

**Colors** have at least four different notations in CSS but we normally use just one or two:

* Names
* Hexadecimal
* RGB
* HSL

### Named colors

```css
.redFont {
    color: red;
}
```

* We could simply use English names of colors but we
  * limit ourselves in terms of shades
  * can become prone to spelling mistakes

### Hexadecimal colors

With hexadecimal (base-16) numbers, each "digit":

* can be anything from 0 to 15, with A representing 10, B for 11, all the way up to F for 15
* when combined with another "digit", a two-digit hex code pair can have up to 256 possible combinations
* three pairs of hexadecimal digits can therefore represent 16,777,216 possible combinations of colors

```css
.hexFont {
    color: #6496C8;
}
```

In the above snippet, we look at each pair of digits after the `#` as such:

* First pair (`#64`): amount of red \[(16 x 6) + 4 = **100**]
* Second pair (`#96`): amount of green \[(16 x 9) + 6 = **150**]
* Third pair (`#C8`): amount of blue \[(16 x 12) + 8 = **200**]

### RGB colors

This follows the same principle as hexadecimal but using a different notation...

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

Unlike hexadecimal and RGB notation, this **HSL (hue-saturation-luminolosity)** notation has to do with two additional properties of color:

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

### Adding "alpha" or opacity

The **alpha**, or **opacity (fadedness)**, represents the fourth argument in each of RGB and HSL:

```css
.RGBAClass {
    color: rgba(100, 150, 200, 0.2) /* 20% opacity */
}

.HSLAclass {
    color: hsla(240, 50%, 50%, 1.0) /* 100% opacity */
}
```

Recall that an opacity ranges from 0 to 1:&#x20;

* 0 means no visibility
* 1 means full visibility
