# Today's date and date manipulation using 'Moment'

## 1. Install Moment

In the Terminal, navigate to your project folder and type:

```
npm install moment --save
```

## 2. Add today's date code to 'filters.js'

Within your project folder, navigate to:

```
views/routes.js
```
And add the following code in the appropriate place (under '**var filters = {}**'):

```javascript

/*
  ====================================================================
  todayGovuk
  --------------------------------------------------------------------
  Today's date GOV.UK formatted
  ====================================================================

  Usage:

    {{ "" | todayGovuk }}

  = 19 March 2020

*/

filters.todayGovuk = () => {
  return moment().format('D MMMM YYYY')
}

filters.yesterdayGovuk = () => {
  return moment().subtract(1, 'days').format('D MMMM YYYY')
}


/*
====================================================================
govukDate
--------------------------------------------------------------------
Process a date and return it in GOV.UK format
Accepts arrays (as provided by design system date inputs) as
well as javascript dates
====================================================================

Usage:

  {{ [1,1,1970] | govukDate }}

= 1 January 1970

*/

filters.govukDate = (date, format) => {
if (Array.isArray(date)){
  return filters.arrayToGovukDate(date, format)
}
else return filters.dateToGovukDate(date, format)
}

/*
====================================================================
arrayToGovukDate
--------------------------------------------------------------------
Convert array to govuk date
====================================================================

Usage:

{{ [1, 2, 2020] | arrayToGovukDate }}

= 1 February 2020

*/

filters.arrayToGovukDate = (array, format) => {
let dateObject = filters.arrayToDateObject(array)
let govukDate = filters.dateToGovukDate(dateObject, format)
return govukDate
}

/*
====================================================================
dateToGovukDate
--------------------------------------------------------------------
Convert date object to govuk date (1 February 2020)
====================================================================

Usage:

{{ date | dateToGovukDate }}

= 1 February 2020

*/

filters.dateToGovukDate = (date, format=false) => {
if (date){
  let theDate = moment(date)
  if (theDate.isValid()){
    return theDate.format(format || 'D MMMM YYYY')
  }
}
return ''
}

/* End of Today's date */

```

## 3. Add references to dates in the page template

Add references to the date on the screen you'd like the date to appear. Radio buttons would look like this, 'todayGovuk' and 'yesterdayGovuk':

```javascript
{% from "govuk/components/radios/macro.njk" import govukRadios %}

{% set dlwHtml %}
{{ govukDateInput({
  id: "date-last-worked",
  namePrefix: "date-last-worked",
  fieldset: {
    legend: {
      text: "Date the claim was received"
    }
  }
}) }}
{% endset -%}

{% set todayText %}
  Today, {{ '' | todayGovuk }}
{% endset -%}

{% set yesterdayText %}
  Yesterday, {{ '' | yesterdayGovuk }}
{% endset -%}

{{ govukRadios({
  idPrefix: "contact",
  name: "contact",
  fieldset: {
    legend: {
      text: "When was the claim received?",
      isPageHeading: true,
      classes: "govuk-fieldset__legend--l"
    }
  },
  items: [
    {
      value: "yes",
      text: todayText
    },
    {
      value: "no",
      text: yesterdayText
    },
    {
      value: "no",
      text: "A different date",
      conditional: {
        html: dlwHtml
      }
    }
  ]
}) }}

```

## 4. Manipulating dates

Add a code block to provide a date that is 8 years from today's date.

```javascript
HSns
```
