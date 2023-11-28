---
description: adding non-alphanumeric text
---

# 💱 HTML special characters

At least two kinds of special characters exist in HTML:

* **Entities**
  * characters which do not appear on all keyboards; or
  * characters that would interfere with HTML code such as `<` and `>`
* **Emoji**
  * icons that no longer consist of image files but text-like characters 😁

### Entities

There are two ways to encode entities:

```markup
&lt; <!-- "less than" - encoding by "name" -->
```

```markup
&#60; <!-- "less than" - encoding by "#number" -->
```

Common entities include:

| Appearance | Meaning              | By name   | By number |
| ---------- | -------------------- | --------- | --------- |
|            | non-breaking space\* | `&nbsp;`  | `&#160;`  |
| <          | less than            | `&lt;`    | `&#60;`   |
| >          | greater than         | `&gt;`    | `&#62;`   |
| &          | ampersand            | `&amp;`   | `&#38;`   |
| ¢          | cent                 | `&cent;`  | `&#162;`  |
| €          | euro                 | `&euro;`  | `&#8364;` |
| £          | pound                | `&pound;` | `&#163;`  |
| ©          | copyright            | `&copy;`  | `&#169;`  |
| ®          | registered trademark | `&reg;`   | `&#174;`  |
| ™          | trademark            | `&trade;` | `&#8482;` |

{% hint style="warning" %}
Remember that when HTML entities by name are _case sensitive!_

i.e. `&euro;` will work but not `&Euro;`
{% endhint %}

### Emoji

Emoji are just symbols like $ or ¢ and we can simply input them using:

* an emoji keyboard (`control + command + space` on a Mac)
* HTML entity code (such as `&#128516` for 😄)

We also need to ensure that the `<head>` contains this line of code for emoji to appear on the page:&#x20;

```markup
...
<head>
    ...
    <meta charset="UTF-8">
    ...
</head>
...
```

{% hint style="info" %}
**Fun fact:** Emoji is the plural of emoji!

**Another fun fact:** The resemblance of the word "emoji" to "emotion" is a [complete coincidence](https://en.m.wiktionary.org/wiki/emoji)!
{% endhint %}
