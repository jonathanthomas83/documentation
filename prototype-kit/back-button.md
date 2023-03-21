# Prototype kit: back button

Place the following before ```{% block content %}```.

```
{% block beforeContent %}
  {{ govukBackLink({
    text: "Back",
    href: "javascript:history.go(-1)"
  }) }}
{% endblock %}
```

