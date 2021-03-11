# HTML special characters

These special characters come in three main types:

* **Entities** \(characters which are especially not present on a standard keyboard\)
  * things like "&lt;" and "&gt;" that should be converted to avoid confusion with their literal versions
  * obscure mathematical symbols
  * obscure foreign characters
  * most currency symbols
* **Emojis** \(they are no longer pictures but now text-like characters!\)

### Entities

There are two ways to encode entities:

```markup
&lt; <!-- "less than" - encoding by "name" -->
```

```markup
&#60; <!-- "less than" - encoding by "#number" -->
```

Common entities include:

| Appearance | Meaning | By name | By number |
| :--- | :--- | :--- | :--- |
|  | non-breaking space\* | &nbsp; | &\#160; |
| &lt; | less than | &lt; | &\#60; |
| &gt; | greater than | &gt; | &\#62; |
| & | ampersand | &amp; | &\#38; |
| ¢ | cent | &cent; | &\#162; |
| € | euro | &euro; | &\#8364; |
| © | copyright | &copy; | &\#169; |
| ® | registered trademark | &reg; | &\#174; |
| ™ | trademark | &trade; | &\#8482; |

{% hint style="warning" %}
Remember that when HTML entities by name are _case sensitive!_
{% endhint %}

### Emojis

{% hint style="info" %}
Ensure that the `<head>` contains the following in order for emojis to work on the page:

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

Emojis are just symbols like $ or ¢ and we can simply input them using:

* an emoji keyboard \(`control + command + space` on a Mac\)
* HTML entity code \(such as `&#128516` for 😄\)

