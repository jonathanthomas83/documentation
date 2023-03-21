# Prototype kit: sticky menu

## Javascript

Place in 'javascripts/application.js'.

```
$(document).ready(function () {
  $('ul.dwp-sub-navigation__list li a').on('click', function(){
          $('ul.dwp-sub-navigation__list li a').removeAttr('aria-current');
          $(this).attr('aria-current', 'page');
  });

  $('ul.dwp-sub-navigation__list li a.top').on('click', function(){
          $('ul.dwp-sub-navigation__list li a').removeAttr('aria-current');
          $('ul.dwp-sub-navigation__list li a.decision').attr('aria-current', 'page');
  });

  $(document).scroll(function() {
    var y = $(this).scrollTop();
    if (y > 300) {
      $('.float-right').show();
    } else {
      $('.float-right').hide();
    }
  });

  window.GOVUKFrontend.initAll()
})
```

## HTML

```
<nav class="dwp-sub-navigation govuk-!-margin-top-6" aria-label="Sub navigation">

  <ul class="dwp-sub-navigation__list">
    <li class="dwp-sub-navigation__item">
      <a class="dwp-sub-navigation__link decision" aria-current="page" href="#decision">Decision</a>
    </li>

    <li class="dwp-sub-navigation__item">
      <a class="dwp-sub-navigation__link" href="#test-period-dates">Test Period dates</a>
    </li>

    <li class="dwp-sub-navigation__item">
      <a class="dwp-sub-navigation__link" href="#map-dates">Maternity Allowance Period dates</a>
    </li>

    <li class="dwp-sub-navigation__item">
      <a class="dwp-sub-navigation__link" href="#employment-and-earnings">Employment and earnings</a>
    </li>

    <li class="dwp-sub-navigation__item float-right">
      <a class="dwp-sub-navigation__link top" href="#">
        Top
          <svg class="app-c-back-to-top__icon" xmlns="http://www.w3.org/2000/svg" width="13" height="17" viewBox="0 0 13 17" aria-hidden="true" focusable="false">
          <path fill="currentColor" d="M6.5 0L0 6.5 1.4 8l4-4v12.7h2V4l4.3 4L13 6.4z"></path>
        </svg></a>
    </li>
  </ul>

</nav>
```

## CSS

```
// Based on https://github.com/dwp/design-system-community-backlog/issues/63
// Note - this code for prototype purposes only. It is not production code.

.dwp-sub-navigation {
    background-color: govuk-colour("white");
    position: -webkit-sticky;
    position: sticky;
    top: 0;
    z-index: 1;
}
.dwp-sub-navigation__list {
    box-shadow: inset 0 -1px 0 #b1b4b6;
    width: 100%;
}
.dwp-sub-navigation__list {
    list-style: none;
    margin: 0;
    padding: 0;
}

.dwp-sub-navigation__item {
    box-shadow: none;
    display: inline-block;
    margin-right: 20px;
    margin-top: 0;
}

.dwp-sub-navigation__item {
    font-size: 19px;
    font-size: 1.1875rem;
    line-height: 1.31579;
}
.dwp-sub-navigation__link[aria-current="page"] {
    color: #0b0c0c;
    position: relative;
    text-decoration: none;
}
.dwp-sub-navigation__link {
    padding-left: 0;
}
.dwp-sub-navigation__link {
    display: block;
    padding-top: 12px;
    padding-bottom: 12px;
    padding-left: 15px;
    text-decoration: none;
    position: relative;
}
.dwp-sub-navigation__item {
    font-size: 19px;
    font-size: 1.1875rem;
    line-height: 1.31579;
    font-weight: bold;
}
.dwp-sub-navigation__link {
    padding-left: 0;
}
.dwp-sub-navigation__link:link, .dwp-sub-navigation__link:visited {
    color: #1d70b8;
}
.dwp-sub-navigation__link[aria-current="page"] {
    color: #0b0c0c;
}
.dwp-sub-navigation__link[aria-current="page"]::before {
    height: 5px;
    width: 100%;
}
.dwp-sub-navigation__link[aria-current="page"]::before {
    background-color: #1d70b8;
    content: "";
    display: block;
    height: 100%;
    position: absolute;
    bottom: 0;
    left: 0;
    width: 5px;
}
.dwp-sub-navigation__link[aria-current="page"]::before {
    height: 5px;
    width: 100%;
}
```
