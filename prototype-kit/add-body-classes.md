# Prototype kit: add body tag styling/classes

Place the following at the top of the file, below ```{% extends "layout-summary.html" %}```.

```
{% set bodyAttributes = { id: "summary-screen" } %}
```

