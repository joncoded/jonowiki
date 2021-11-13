---
description: adding non-alphanumeric text
---

# HTML special characters

These special characters come in three main types:

* **Entities** (characters which are especially not present on a standard keyboard)
  * things like "<" and ">" that should be converted to avoid confusion with their literal versions
  * obscure mathematical symbols
  * obscure foreign characters
  * most currency symbols
* **Emojis** (they are no longer pictures but now text-like characters!)

### Entities

There are two ways to encode entities:

```markup
&lt; <!-- "less than" - encoding by "name" -->
```

```markup
&#60; <!-- "less than" - encoding by "#number" -->
```

Common entities include:

| Appearance | Meaning              | By name | By number |
| ---------- | -------------------- | ------- | --------- |
|            | non-breaking space\* |         | \&#160;   |
| <          | less than            | <       | \&#60;    |
| >          | greater than         | >       | \&#62;    |
| &          | ampersand            | &       | \&#38;    |
| ¢          | cent                 | ¢       | \&#162;   |
| €          | euro                 | €       | \&#8364;  |
| ©          | copyright            | ©       | \&#169;   |
| ®          | registered trademark | ®       | \&#174;   |
| ™          | trademark            | ™       | \&#8482;  |

{% hint style="warning" %}
Remember that when HTML entities by name are _case sensitive!_
{% endhint %}

### Emoji

{% hint style="info" %}
Ensure that the `<head>` contains the following in order for emoji to work on the page:

```markup
...
<head>
    ...
    <meta charset="UTF-8">
    ...
</head>
...
```
{% endhint %}

Emoji are just symbols like $ or ¢ and we can simply input them using:

* an emoji keyboard (`control + command + space` on a Mac)
* HTML entity code (such as `&#128516` for 😄)

{% hint style="info" %}
Emoji is the plural of emoji!
{% endhint %}
