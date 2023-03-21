# Prototype kit: Transaction view

## CSS

```
.nobordery {
  border-bottom: 0px;
  font-weight: normal;
}

.doubleborder {
  border-bottom: 2px solid $govuk-input-border-colour;
  font-weight: normal;
}

.transactions {
  .govuk-\!-width-one-half {
    width: 90% !important;
  }
  .govuk-summary-list__value {
    width: 25%;
  }
  .govuk-summary-list__actions {
    width: 20%;
  }
}
```


## HTML

```  
<div class="transactions">
<div class="govuk-grid-row">
<div class="govuk-grid-column-two-thirds">

  <h2 class="govuk-heading-m" id="employment-and-earnings">Highest Earning Weeks</h2>

  <dl class="govuk-summary-list">
    <div class="govuk-summary-list__row">
      <dt class="govuk-summary-list__key govuk-!-width-one-half">
        {{ data['ma-week-1'] }}
      </dt>
      <dd class="govuk-summary-list__value govuk-table__cell--numeric">
        &nbsp;
      </dd>
      <dd class="govuk-summary-list__value govuk-table__cell--numeric">
        <strong>{{ '£' + data['ma-week-1-total-amount'].toFixed(2) }}</strong>
      </dd>
      <dd class="govuk-summary-list__actions">
        <a class="govuk-link" href="../rti/change.html">
          Change<span class="govuk-visually-hidden"> name</span>
        </a>
      </dd>
    </div>
    <div class="govuk-summary-list__row">
      <dt class="govuk-summary-list__key nobordery">
        {{ data['ma-employer-1'] }}
      </dt>
      <dd class="govuk-summary-list__value nobordery govuk-table__cell--numeric">
        {{ data['ma-week-1-employer-1-source'] }}
      </dd>
      <dd class="govuk-summary-list__value nobordery govuk-table__cell--numeric">
        {{  '£' + data['ma-week-1-employer-1-amount'].toFixed(2) }}
      </dd>
      <dd class="govuk-summary-list__actions nobordery">
        &nbsp;
      </dd>
    </div>
    <div class="govuk-summary-list__row">
      <dt class="govuk-summary-list__key doubleborder">
        {{ data['ma-employer-2'] }}
      </dt>
      <dd class="govuk-summary-list__value doubleborder govuk-table__cell--numeric">
        {{ data['ma-week-1-employer-1-source'] }}
      </dd>
      <dd class="govuk-summary-list__value doubleborder govuk-table__cell--numeric">
        {{  '£' + data['ma-week-1-employer-2-amount'].toFixed(2) }}
      </dd>
      <dd class="govuk-summary-list__actions doubleborder">
        &nbsp;
      </dd>
    </div>
  </dl>


  <dl class="govuk-summary-list">
    <div class="govuk-summary-list__row">
      <dt class="govuk-summary-list__key govuk-!-width-one-half">
        {{ data['ma-week-2'] }}
      </dt>
      <dd class="govuk-summary-list__value govuk-table__cell--numeric">
        &nbsp;
      </dd>
      <dd class="govuk-summary-list__value govuk-table__cell--numeric">
        <strong>{{ '£' + data['ma-week-2-total-amount'].toFixed(2) }}</strong>
      </dd>
      <dd class="govuk-summary-list__actions">
        <a class="govuk-link" href="#">
          Change<span class="govuk-visually-hidden"> name</span>
        </a>
      </dd>
    </div>
    <div class="govuk-summary-list__row">
      <dt class="govuk-summary-list__key nobordery">
        {{ data['ma-employer-1'] }}
      </dt>
      <dd class="govuk-summary-list__value nobordery govuk-table__cell--numeric">
        {{ data['ma-week-2-employer-1-source'] }}
      </dd>
      <dd class="govuk-summary-list__value nobordery govuk-table__cell--numeric">
        {{  '£' + data['ma-week-2-employer-1-amount'].toFixed(2) }}
      </dd>
      <dd class="govuk-summary-list__actions nobordery">
        &nbsp;
      </dd>
    </div>
    <div class="govuk-summary-list__row">
      <dt class="govuk-summary-list__key doubleborder">
        {{ data['ma-employer-2'] }}
      </dt>
      <dd class="govuk-summary-list__value doubleborder govuk-table__cell--numeric">
        {{ data['ma-week-2-employer-1-source'] }}
      </dd>
      <dd class="govuk-summary-list__value doubleborder govuk-table__cell--numeric">
        {{  '£' + data['ma-week-2-employer-2-amount'].toFixed(2) }}
      </dd>
      <dd class="govuk-summary-list__actions doubleborder">
        &nbsp;
      </dd>
    </div>
  </dl>


  <dl class="govuk-summary-list">
    <div class="govuk-summary-list__row">
      <dt class="govuk-summary-list__key govuk-!-width-one-half">
        {{ data['ma-week-3'] }}
      </dt>
      <dd class="govuk-summary-list__value govuk-table__cell--numeric">
        &nbsp;
      </dd>
      <dd class="govuk-summary-list__value govuk-table__cell--numeric">
        <strong>{{ '£' + data['ma-week-3-total-amount'].toFixed(2) }}</strong>
      </dd>
      <dd class="govuk-summary-list__actions">
        <a class="govuk-link" href="#">
          Change<span class="govuk-visually-hidden"> name</span>
        </a>
      </dd>
    </div>
    <div class="govuk-summary-list__row">
      <dt class="govuk-summary-list__key nobordery">
        {{ data['ma-employer-1'] }}
      </dt>
      <dd class="govuk-summary-list__value nobordery govuk-table__cell--numeric">
        {{ data['ma-week-3-employer-1-source'] }}
      </dd>
      <dd class="govuk-summary-list__value nobordery govuk-table__cell--numeric">
        {{  '£' + data['ma-week-3-employer-1-amount'].toFixed(2) }}
      </dd>
      <dd class="govuk-summary-list__actions nobordery">
        &nbsp;
      </dd>
    </div>
    <div class="govuk-summary-list__row">
      <dt class="govuk-summary-list__key doubleborder">
        {{ data['ma-employer-2'] }}
      </dt>
      <dd class="govuk-summary-list__value doubleborder govuk-table__cell--numeric">
        {{ data['ma-week-3-employer-1-source'] }}
      </dd>
      <dd class="govuk-summary-list__value doubleborder govuk-table__cell--numeric">
        {{  '£' + data['ma-week-3-employer-2-amount'].toFixed(2) }}
      </dd>
      <dd class="govuk-summary-list__actions doubleborder">
        &nbsp;
      </dd>
    </div>
  </dl>


  <dl class="govuk-summary-list">
    <div class="govuk-summary-list__row">
      <dt class="govuk-summary-list__key govuk-!-width-one-half">
        {{ data['ma-week-4'] }}
      </dt>
      <dd class="govuk-summary-list__value govuk-table__cell--numeric">
        &nbsp;
      </dd>
      <dd class="govuk-summary-list__value govuk-table__cell--numeric">
        <strong>{{ '£' + data['ma-week-4-total-amount'].toFixed(2) }}</strong>
      </dd>
      <dd class="govuk-summary-list__actions">
        <a class="govuk-link" href="#">
          Change<span class="govuk-visually-hidden"> name</span>
        </a>
      </dd>
    </div>
    <div class="govuk-summary-list__row">
      <dt class="govuk-summary-list__key nobordery">
        {{ data['ma-employer-1'] }}
      </dt>
      <dd class="govuk-summary-list__value nobordery govuk-table__cell--numeric">
        {{ data['ma-week-4-employer-1-source'] }}
      </dd>
      <dd class="govuk-summary-list__value nobordery govuk-table__cell--numeric">
        {{  '£' + data['ma-week-4-employer-1-amount'].toFixed(2) }}
      </dd>
      <dd class="govuk-summary-list__actions nobordery">
        &nbsp;
      </dd>
    </div>
    <div class="govuk-summary-list__row">
      <dt class="govuk-summary-list__key doubleborder">
        {{ data['ma-employer-2'] }}
      </dt>
      <dd class="govuk-summary-list__value doubleborder govuk-table__cell--numeric">
        {{ data['ma-week-4-employer-1-source'] }}
      </dd>
      <dd class="govuk-summary-list__value doubleborder govuk-table__cell--numeric">
        {{  '£' + data['ma-week-4-employer-2-amount'].toFixed(2) }}
      </dd>
      <dd class="govuk-summary-list__actions doubleborder">
        &nbsp;
      </dd>
    </div>
  </dl>


  <dl class="govuk-summary-list">
    <div class="govuk-summary-list__row">
      <dt class="govuk-summary-list__key govuk-!-width-one-half">
        {{ data['ma-week-5'] }}
      </dt>
      <dd class="govuk-summary-list__value govuk-table__cell--numeric">
        &nbsp;
      </dd>
      <dd class="govuk-summary-list__value govuk-table__cell--numeric">
        <strong>{{ '£' + data['ma-week-5-total-amount'].toFixed(2) }}</strong>
      </dd>
      <dd class="govuk-summary-list__actions">
        <a class="govuk-link" href="../rti/change.html">
          Change<span class="govuk-visually-hidden"> name</span>
        </a>
      </dd>
    </div>
    <div class="govuk-summary-list__row">
      <dt class="govuk-summary-list__key nobordery">
        {{ data['ma-employer-1'] }}
      </dt>
      <dd class="govuk-summary-list__value nobordery govuk-table__cell--numeric">
        {{ data['ma-week-5-employer-1-source'] }}
      </dd>
      <dd class="govuk-summary-list__value nobordery govuk-table__cell--numeric">
        {{  '£' + data['ma-week-5-employer-1-amount'].toFixed(2) }}
      </dd>
      <dd class="govuk-summary-list__actions nobordery">
        &nbsp;
      </dd>
    </div>
    <div class="govuk-summary-list__row">
      <dt class="govuk-summary-list__key doubleborder">
        {{ data['ma-employer-2'] }}
      </dt>
      <dd class="govuk-summary-list__value doubleborder govuk-table__cell--numeric">
        {{ data['ma-week-5-employer-1-source'] }}
      </dd>
      <dd class="govuk-summary-list__value doubleborder govuk-table__cell--numeric">
        {{  '£' + data['ma-week-5-employer-2-amount'].toFixed(2) }}
      </dd>
      <dd class="govuk-summary-list__actions doubleborder">
        &nbsp;
      </dd>
    </div>
  </dl>


  <dl class="govuk-summary-list">
    <div class="govuk-summary-list__row">
      <dt class="govuk-summary-list__key govuk-!-width-one-half">
        {{ data['ma-week-6'] }}
      </dt>
      <dd class="govuk-summary-list__value govuk-table__cell--numeric">
        &nbsp;
      </dd>
      <dd class="govuk-summary-list__value govuk-table__cell--numeric">
        <strong>{{ '£' + data['ma-week-6-total-amount'].toFixed(2) }}</strong>
      </dd>
      <dd class="govuk-summary-list__actions">
        <a class="govuk-link" href="#">
          Change<span class="govuk-visually-hidden"> name</span>
        </a>
      </dd>
    </div>
    <div class="govuk-summary-list__row">
      <dt class="govuk-summary-list__key nobordery">
        {{ data['ma-employer-1'] }}
      </dt>
      <dd class="govuk-summary-list__value nobordery govuk-table__cell--numeric">
        {{ data['ma-week-6-employer-1-source'] }}
      </dd>
      <dd class="govuk-summary-list__value nobordery govuk-table__cell--numeric">
        {{  '£' + data['ma-week-6-employer-1-amount'].toFixed(2) }}
      </dd>
      <dd class="govuk-summary-list__actions nobordery">
        &nbsp;
      </dd>
    </div>
    <div class="govuk-summary-list__row">
      <dt class="govuk-summary-list__key doubleborder">
        {{ data['ma-employer-2'] }}
      </dt>
      <dd class="govuk-summary-list__value doubleborder govuk-table__cell--numeric">
        {{ data['ma-week-6-employer-1-source'] }}
      </dd>
      <dd class="govuk-summary-list__value doubleborder govuk-table__cell--numeric">
        {{  '£' + data['ma-week-6-employer-2-amount'].toFixed(2) }}
      </dd>
      <dd class="govuk-summary-list__actions doubleborder">
        &nbsp;
      </dd>
    </div>
  </dl>


  <dl class="govuk-summary-list">
    <div class="govuk-summary-list__row">
      <dt class="govuk-summary-list__key govuk-!-width-one-half">
        {{ data['ma-week-7'] }}
      </dt>
      <dd class="govuk-summary-list__value govuk-table__cell--numeric">
        &nbsp;
      </dd>
      <dd class="govuk-summary-list__value govuk-table__cell--numeric">
        <strong>{{ '£' + data['ma-week-7-total-amount'].toFixed(2) }}</strong>
      </dd>
      <dd class="govuk-summary-list__actions">
        <a class="govuk-link" href="#">
          Change<span class="govuk-visually-hidden"> name</span>
        </a>
      </dd>
    </div>
    <div class="govuk-summary-list__row">
      <dt class="govuk-summary-list__key nobordery">
        {{ data['ma-employer-1'] }}
      </dt>
      <dd class="govuk-summary-list__value nobordery govuk-table__cell--numeric">
        {{ data['ma-week-7-employer-1-source'] }}
      </dd>
      <dd class="govuk-summary-list__value nobordery govuk-table__cell--numeric">
        {{  '£' + data['ma-week-7-employer-1-amount'].toFixed(2) }}
      </dd>
      <dd class="govuk-summary-list__actions nobordery">
        &nbsp;
      </dd>
    </div>
    <div class="govuk-summary-list__row">
      <dt class="govuk-summary-list__key doubleborder">
        {{ data['ma-employer-2'] }}
      </dt>
      <dd class="govuk-summary-list__value doubleborder govuk-table__cell--numeric">
        {{ data['ma-week-7-employer-1-source'] }}
      </dd>
      <dd class="govuk-summary-list__value doubleborder govuk-table__cell--numeric">
        {{  '£' + data['ma-week-7-employer-2-amount'].toFixed(2) }}
      </dd>
      <dd class="govuk-summary-list__actions doubleborder">
        &nbsp;
      </dd>
    </div>
  </dl>


  <dl class="govuk-summary-list">
    <div class="govuk-summary-list__row">
      <dt class="govuk-summary-list__key govuk-!-width-one-half">
        {{ data['ma-week-8'] }}
      </dt>
      <dd class="govuk-summary-list__value govuk-table__cell--numeric">
        &nbsp;
      </dd>
      <dd class="govuk-summary-list__value govuk-table__cell--numeric">
        <strong>{{ '£' + data['ma-week-8-total-amount'].toFixed(2) }}</strong>
      </dd>
      <dd class="govuk-summary-list__actions">
        <a class="govuk-link" href="#">
          Change<span class="govuk-visually-hidden"> name</span>
        </a>
      </dd>
    </div>
    <div class="govuk-summary-list__row">
      <dt class="govuk-summary-list__key nobordery">
        {{ data['ma-employer-1'] }}
      </dt>
      <dd class="govuk-summary-list__value nobordery govuk-table__cell--numeric">
        {{ data['ma-week-8-employer-1-source'] }}
      </dd>
      <dd class="govuk-summary-list__value nobordery govuk-table__cell--numeric">
        {{  '£' + data['ma-week-8-employer-1-amount'].toFixed(2) }}
      </dd>
      <dd class="govuk-summary-list__actions nobordery">
        &nbsp;
      </dd>
    </div>
    <div class="govuk-summary-list__row">
      <dt class="govuk-summary-list__key doubleborder">
        {{ data['ma-employer-2'] }}
      </dt>
      <dd class="govuk-summary-list__value doubleborder govuk-table__cell--numeric">
        {{ data['ma-week-8-employer-1-source'] }}
      </dd>
      <dd class="govuk-summary-list__value doubleborder govuk-table__cell--numeric">
        {{  '£' + data['ma-week-8-employer-2-amount'].toFixed(2) }}
      </dd>
      <dd class="govuk-summary-list__actions doubleborder">
        &nbsp;
      </dd>
    </div>
  </dl>


  <dl class="govuk-summary-list">
    <div class="govuk-summary-list__row">
      <dt class="govuk-summary-list__key govuk-!-width-one-half">
        {{ data['ma-week-9'] }}
      </dt>
      <dd class="govuk-summary-list__value govuk-table__cell--numeric">
        &nbsp;
      </dd>
      <dd class="govuk-summary-list__value govuk-table__cell--numeric">
        <strong>{{ '£' + data['ma-week-9-total-amount'].toFixed(2) }}</strong>
      </dd>
      <dd class="govuk-summary-list__actions">
        <a class="govuk-link" href="#">
          Change<span class="govuk-visually-hidden"> name</span>
        </a>
      </dd>
    </div>
    <div class="govuk-summary-list__row">
      <dt class="govuk-summary-list__key nobordery">
        {{ data['ma-employer-1'] }}
      </dt>
      <dd class="govuk-summary-list__value nobordery govuk-table__cell--numeric">
        {{ data['ma-week-9-employer-1-source'] }}
      </dd>
      <dd class="govuk-summary-list__value nobordery govuk-table__cell--numeric">
        {{  '£' + data['ma-week-9-employer-1-amount'].toFixed(2) }}
      </dd>
      <dd class="govuk-summary-list__actions nobordery">
        &nbsp;
      </dd>
    </div>
    <div class="govuk-summary-list__row">
      <dt class="govuk-summary-list__key doubleborder">
        {{ data['ma-employer-2'] }}
      </dt>
      <dd class="govuk-summary-list__value doubleborder govuk-table__cell--numeric">
        {{ data['ma-week-9-employer-1-source'] }}
      </dd>
      <dd class="govuk-summary-list__value doubleborder govuk-table__cell--numeric">
        {{  '£' + data['ma-week-9-employer-2-amount'].toFixed(2) }}
      </dd>
      <dd class="govuk-summary-list__actions doubleborder">
        &nbsp;
      </dd>
    </div>
  </dl>


  <dl class="govuk-summary-list">
    <div class="govuk-summary-list__row">
      <dt class="govuk-summary-list__key govuk-!-width-one-half">
        {{ data['ma-week-10'] }}
      </dt>
      <dd class="govuk-summary-list__value govuk-table__cell--numeric">
        &nbsp;
      </dd>
      <dd class="govuk-summary-list__value govuk-table__cell--numeric">
        <strong>{{ '£' + data['ma-week-10-total-amount'].toFixed(2) }}</strong>
      </dd>
      <dd class="govuk-summary-list__actions">
        <a class="govuk-link" href="#">
          Change<span class="govuk-visually-hidden"> name</span>
        </a>
      </dd>
    </div>
    <div class="govuk-summary-list__row">
      <dt class="govuk-summary-list__key nobordery">
        {{ data['ma-employer-1'] }}
      </dt>
      <dd class="govuk-summary-list__value nobordery govuk-table__cell--numeric">
        {{ data['ma-week-10-employer-1-source'] }}
      </dd>
      <dd class="govuk-summary-list__value nobordery govuk-table__cell--numeric">
        {{  '£' + data['ma-week-10-employer-1-amount'].toFixed(2) }}
      </dd>
      <dd class="govuk-summary-list__actions nobordery">
        &nbsp;
      </dd>
    </div>
    <div class="govuk-summary-list__row">
      <dt class="govuk-summary-list__key doubleborder">
        {{ data['ma-employer-2'] }}
      </dt>
      <dd class="govuk-summary-list__value doubleborder govuk-table__cell--numeric">
        {{ data['ma-week-10-employer-1-source'] }}
      </dd>
      <dd class="govuk-summary-list__value doubleborder govuk-table__cell--numeric">
        {{  '£' + data['ma-week-10-employer-2-amount'].toFixed(2) }}
      </dd>
      <dd class="govuk-summary-list__actions doubleborder">
        &nbsp;
      </dd>
    </div>
  </dl>


  <dl class="govuk-summary-list">
    <div class="govuk-summary-list__row">
      <dt class="govuk-summary-list__key govuk-!-width-one-half">
        {{ data['ma-week-11'] }}
      </dt>
      <dd class="govuk-summary-list__value govuk-table__cell--numeric">
        &nbsp;
      </dd>
      <dd class="govuk-summary-list__value govuk-table__cell--numeric">
        <strong>{{ '£' + data['ma-week-11-total-amount'].toFixed(2) }}</strong>
      </dd>
      <dd class="govuk-summary-list__actions">
        <a class="govuk-link" href="#">
          Change<span class="govuk-visually-hidden"> name</span>
        </a>
      </dd>
    </div>
    <div class="govuk-summary-list__row">
      <dt class="govuk-summary-list__key nobordery">
        {{ data['ma-employer-1'] }}
      </dt>
      <dd class="govuk-summary-list__value nobordery govuk-table__cell--numeric">
        {{ data['ma-week-11-employer-1-source'] }}
      </dd>
      <dd class="govuk-summary-list__value nobordery govuk-table__cell--numeric">
        {{  '£' + data['ma-week-11-employer-1-amount'].toFixed(2) }}
      </dd>
      <dd class="govuk-summary-list__actions nobordery">
        &nbsp;
      </dd>
    </div>
    <div class="govuk-summary-list__row">
      <dt class="govuk-summary-list__key doubleborder">
        {{ data['ma-employer-2'] }}
      </dt>
      <dd class="govuk-summary-list__value doubleborder govuk-table__cell--numeric">
        {{ data['ma-week-11-employer-1-source'] }}
      </dd>
      <dd class="govuk-summary-list__value doubleborder govuk-table__cell--numeric">
        {{  '£' + data['ma-week-11-employer-2-amount'].toFixed(2) }}
      </dd>
      <dd class="govuk-summary-list__actions doubleborder">
        &nbsp;
      </dd>
    </div>
  </dl>


  <dl class="govuk-summary-list">
    <div class="govuk-summary-list__row">
      <dt class="govuk-summary-list__key govuk-!-width-one-half">
        {{ data['ma-week-12'] }}
      </dt>
      <dd class="govuk-summary-list__value govuk-table__cell--numeric">
        &nbsp;
      </dd>
      <dd class="govuk-summary-list__value govuk-table__cell--numeric">
        <strong>{{ '£' + data['ma-week-12-total-amount'].toFixed(2) }}</strong>
      </dd>
      <dd class="govuk-summary-list__actions">
        <a class="govuk-link" href="#">
          Change<span class="govuk-visually-hidden"> name</span>
        </a>
      </dd>
    </div>
    <div class="govuk-summary-list__row">
      <dt class="govuk-summary-list__key nobordery">
        {{ data['ma-employer-1'] }}
      </dt>
      <dd class="govuk-summary-list__value nobordery govuk-table__cell--numeric">
        {{ data['ma-week-12-employer-1-source'] }}
      </dd>
      <dd class="govuk-summary-list__value nobordery govuk-table__cell--numeric">
        {{  '£' + data['ma-week-12-employer-1-amount'].toFixed(2) }}
      </dd>
      <dd class="govuk-summary-list__actions nobordery">
        &nbsp;
      </dd>
    </div>
    <div class="govuk-summary-list__row">
      <dt class="govuk-summary-list__key doubleborder">
        {{ data['ma-employer-2'] }}
      </dt>
      <dd class="govuk-summary-list__value doubleborder govuk-table__cell--numeric">
        {{ data['ma-week-12-employer-1-source'] }}
      </dd>
      <dd class="govuk-summary-list__value doubleborder govuk-table__cell--numeric">
        {{  '£' + data['ma-week-12-employer-2-amount'].toFixed(2) }}
      </dd>
      <dd class="govuk-summary-list__actions doubleborder">
        &nbsp;
      </dd>
    </div>
  </dl>


  <dl class="govuk-summary-list">
    <div class="govuk-summary-list__row">
      <dt class="govuk-summary-list__key govuk-!-width-one-half">
        {{ data['ma-week-13'] }}
      </dt>
      <dd class="govuk-summary-list__value govuk-table__cell--numeric">
        &nbsp;
      </dd>
      <dd class="govuk-summary-list__value govuk-table__cell--numeric">
        <strong>{{ '£' + data['ma-week-13-total-amount'].toFixed(2) }}</strong>
      </dd>
      <dd class="govuk-summary-list__actions">
        <a class="govuk-link" href="#">
          Change<span class="govuk-visually-hidden"> name</span>
        </a>
      </dd>
    </div>
    <div class="govuk-summary-list__row">
      <dt class="govuk-summary-list__key nobordery">
        {{ data['ma-employer-1'] }}
      </dt>
      <dd class="govuk-summary-list__value nobordery govuk-table__cell--numeric">
        {{ data['ma-week-13-employer-1-source'] }}
      </dd>
      <dd class="govuk-summary-list__value nobordery govuk-table__cell--numeric">
        {{  '£' + data['ma-week-13-employer-1-amount'].toFixed(2) }}
      </dd>
      <dd class="govuk-summary-list__actions nobordery">
        &nbsp;
      </dd>
    </div>
    <div class="govuk-summary-list__row">
      <dt class="govuk-summary-list__key doubleborder">
        {{ data['ma-employer-2'] }}
      </dt>
      <dd class="govuk-summary-list__value doubleborder govuk-table__cell--numeric">
        {{ data['ma-week-13-employer-1-source'] }}
      </dd>
      <dd class="govuk-summary-list__value doubleborder govuk-table__cell--numeric">
        {{  '£' + data['ma-week-13-employer-2-amount'].toFixed(2) }}
      </dd>
      <dd class="govuk-summary-list__actions doubleborder">
        &nbsp;
      </dd>
    </div>
  </dl>
</div>
</div>
</div>
```

