# 🚧 CSS colors

### Named colors

### Hexadecimal colors

### RGB colors

### HSL colors

* First number represents the degree value of the **hue** on the color wheel
  * 0/360 = red
  * 60 = yellow
  * 120 = green
  * 180 = cyan
  * 240 = blue
  * 300 = violet
* Second number represents the **saturation**
  * 100% = richer color
  * 0% = grayer tone
* Third number represents the **luminosity**
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
