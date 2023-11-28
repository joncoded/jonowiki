---
description: organizing similar records of data together on a webpage
---

# 🍽 HTML \<table> tags

**Tables** display groups of similar data as a grid-like structure:

* Rows typically show individual data observations
* Table typically show values of a property

For example:

* A row could show a city
* A column could show data that describe a city, e.g.
  * country
  * population
  * mayor

We could say that rows form the "nouns" and that columns form the "adjectives" of tables!

### Structure

As part of semantic HTML, `<table>` tags allow us to make "two-dimensional lists" with headers, rows, columns and footers:

```markup
<table>
    <caption>Explaining the table for accessibility</caption>
    <thead>
        <tr>
            <th scope="col">Column 1 Header</th>
            <th scope="col">Column 2 Header</th>
            <th scope="col">Column 3 Header</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Row 1, Column 1</td>
            <td>Row 1, Column 2</td>
            <td>Row 1, Column 3</td>
        </tr>
        <tr>
            <td>Row 2, Column 1</td>
            <td>Row 2, Column 2</td>
            <td>Row 2, Column 3</td>
        </tr>
    </tbody>
    <tfoot>
        <tr>
            <td>Total, Column 1</td>
            <td>Total, Column 2</td>
            <td>Total, Column 3</td>
        </tr>
    </tfoot>
</table>    
```

### Elements

We will look at the tags above in the table below:

| Tag        | Nesting level | Meaning                                                                                                           |
| ---------- | ------------- | ----------------------------------------------------------------------------------------------------------------- |
| \<table>   | 0             | the table                                                                                                         |
| \<caption> | 1             | a write-up explaining the table (usually used for screen readers for accessibility and hidden from sighted users) |
| \<thead>   | 1             | table heading section (usually a row to describe each column)                                                     |
| \<tr>      | 2             | table row                                                                                                         |
| \<th>      | 3             | table heading                                                                                                     |
| \<tbody>   | 1             | table body (main content)                                                                                         |
| \<td>      | 3             | table definition (data cell)                                                                                      |
| \<tfoot>   | 1             | table footer (usually a row for numerical totals)                                                                 |

### Attributes

One attribute to note is `scope` for table headings; these simply denote whether the heading refers to:

* items vertically below it (`col`) as a column
* items that follow it (`row`) as a row

Older attributes used to live in the `<table>` tag (e.g. `cellspacing` and `cellpadding`) but CSS takes care of them of these days!

{% hint style="warning" %}
Web developers formerly used the `<table>` tag for layout purposes to divide up sections of a page

However, this practice has become highly frowned upon and we prefer to use the `<div>` tag today!
{% endhint %}
