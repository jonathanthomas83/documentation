# Prototype kit: pass data from page to page

## 1. Name attribute

Put a 'name' attribute on your input field. For example, '*address-postcode*'.

```
{{ govukInput({
  label: {
    text: "Postcode"
  },
  classes: "govuk-input--width-10",
  id: "address-postcode",
  name: "address-postcode",
  autocomplete: "postal-code"
}) }}
```

or

```
<input id="address-postcode" name="address-postcode" value="">
```

## 2. Recall the data

On the page you want the entered data to appear. In this example, we want the previously entered post code to prepopulate the Post Code field on the new page. Use the following code:

```
{{ govukInput({
  label: {
    text: "Postcode"
  },
  classes: "govuk-input--width-10",
  id: "more-info-postcode",
  name: "more-info-postcode",
  value: data['address-postcode'],
  autocomplete: "postal-code"
}) }}
```

or

```
<p>{{ data['address-postcode'] }}</p>
```

For further information, see:
https://govuk-prototype-kit.herokuapp.com/docs/examples/pass-data
