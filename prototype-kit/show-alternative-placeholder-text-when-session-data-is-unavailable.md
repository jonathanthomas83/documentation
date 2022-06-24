# Prototype kit: Show alternative placeholder text when session data is unavailable

Prototypes often accrue session data as user journey's progress.

So if you send someone a URL to visit the screen directly (without going through the entire journey), ie. to advise on a Jira ticket, for example, session data is often unavailable and not shown. Gaps are shown in the UI where unavailable session data should be and these gaps provide no detail as to what should be shown. This is particularly prevalent on summary screens which are populated by data that is usually gathered within the journey.

To show placeholder text where session data values would normally be shown, use the following code:

## HTML template
```
<dt class="govuk-summary-list__key">
  Date of verification
</dt>
<dd class="govuk-summary-list__value">
  {{ data['relationship-decision-date'] or '[Date of appointee relationship verification]'}}
</dd>
```

Outputs:

> 24 June 2022

Or:

> [Date of appointee relationship verification]

If session data is unavailable, which is a lot more helpful to developers than an empty line.

## Nunjucks template
```
{
  key: {
    text: "Date of birth"
  },
  value: {
    html: data['customer-dob'] or '[Customer Date of Birth]'
  }
}
```

Outputs:

> 24 June 2022

Or:

> [Customer Date of Birth]

If session data is unavailable, which is a lot more helpful to developers than an empty line.
