# Prototype kit: Replace header

Place the following after ```{% block pageTitle %}``` block.

```
{% block header %}
<header class="govuk-header summary" role="banner" data-module="govuk-header">
  <div class="govuk-header__container govuk-width-container">
    <div class="govuk-header__content">
      <a href="/" class="govuk-header__link govuk-header__link--service-name">
        Maternity Allowance
      </a>
    </div>

    <nav aria-label="Menu" class="govuk-header__navigation ">
      <button type="button" class="govuk-header__menu-button govuk-js-header-toggle" aria-controls="navigation" aria-label="Show or hide menu">Menu</button>

      <ul id="navigation" class="govuk-header__navigation-list">
        <li class="govuk-header__navigation-item">
          <a class="govuk-header__link" href="/beta-private/iteration-7/scenario-1/start-a-claim/">
            Start a claim
          </a>
        </li>
        <li class="govuk-header__navigation-item">
          <a class="govuk-header__link" href="/beta-private/iteration-7/scenario-1/find-a-claim/">
            Find a claim
          </a>
        </li>
      </ul>
    </nav>
  </div>
</header>
{% endblock %}
```
or

```
{% block header %}
<header class="govuk-header " role="banner" data-module="govuk-header">
  <div class="govuk-header__container govuk-width-container">
    <div class="govuk-header__content">
      <a href="/" class="govuk-header__link govuk-header__link--service-name">
        Maternity Allowance
      </a>
    </div>
  </div>
</header>
{% endblock %}
```