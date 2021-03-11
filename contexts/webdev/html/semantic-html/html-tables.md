---
description: displaying data in cells on an HTML page
---

# 🚧 HTML tables

As part of semantic HTML, **tables** allow us to make "two-dimensional lists" with headers, rows, columns and footers:

```markup
<table>
    <caption>Explaining the table for accessibility</caption>
    <thead>
        <tr>
            <th>Column 1 Header</th>
            <th>Column 2 Header</th>
            <th>Column 3 Header</th>
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

