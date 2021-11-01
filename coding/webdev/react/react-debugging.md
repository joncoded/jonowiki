---
description: WHY DOESN'T MY REACT CODE WORK? I HATE REACT! AAAAH!
---

# React debugging

### Common things to check first

* `this.state.x` or `this.props.x`?
* handler bindings in `constructor`?
* `import`s
* `export`s
* prop names

### "Template not provided"

> A template was not provided. This is likely because you're using an outdated version of create-react-app. Please note that global installs of create-react-app are no longer supported.

Try this by going back to your project folder: 

```text
$ npm uninstall -g create-react-app
$ npx create-react-app appname
```

