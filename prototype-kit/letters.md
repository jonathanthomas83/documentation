# Prototype kit: letters

## CSS

```
.content-letter {
  font-family: 'Arial', sans-serif !important;
  border: 2px solid #505a5f;
  box-shadow: 4px 4px 0 rgba(#505a5f, 0.4);
  padding: 30px 15px 50px 15px;
  min-height: 90em;
  position: relative;
  * {
    font-family: 'Arial', sans-serif !important;
  }
  @media (min-width: 40.0625em) {
    .main-container {
      padding-right: 20%;
    }
  }
}


.page-number {
  position: absolute;
  right: 45px;
  bottom: 15px;
}

.address-row {
  display: flex;
  width: 150%;
  padding: 0;
  padding-top: 80px;
  @media (max-width: 40.0625em) {
    flex-direction: column;
  }
  .address-row-item {
    flex-grow: 1;
  }
}

.letter-content-row {
  display: flex;
  width: 100%;
  padding: 0;
  padding-top: 20px;
  @media (max-width: 40.0625em) {
    flex-direction: column;
  }
  @media (min-width: 40.0625em) {
    .letter-content-primary {
      width: 70%;
      padding-right: 40px;
    }
    .letter-content-clerical {
      width: 100%;
      padding-right: 40px;
    }
    .letter-content-secondary {
      width: 30%;
    }
  }
}

.colour-distinction.taller-lines {
  * {
    //line-height: 2.2 !important;
  }
}

//*****

.instructions img {
  display: block;
  max-width: 100%;
  width: 400px;
  border: 2px solid #505a5f;
  box-shadow: 4px 4px 0 rgba(#505a5f, 0.4);
  margin-bottom: 60px;
  margin-top: 20px;
}

.alt-format-text {
  border: 2px solid black;
  padding: 10px;
}

.grey-box-text {
  background-color: govuk-colour('light-grey');
  padding: 10px;
}

.app-actions-force-inline {
  width: 50%;
}

.govuk-summary-list__actions-list-item:not(:last-child) {
  border-right: none;
}

.app-type-force-normal {
  font-weight: normal !important;
}

.app-dwp-logo {
  svg {
    max-width: 8em;
    height: auto;
  }
}

.app-ni-logo {
  svg {
    max-width: 18em;
    height: auto;
  }
}

.app-content-letter-table {
  .govuk-table__cell,
  .govuk-table__header {
    border-bottom: none;
  }
}

.app-page-number-row,
.app-page-number-row p {
  width: calc(100% - 30px);
  text-align: right;
  position: absolute;
  bottom: 0;
}

```

## HTML

```
{% extends "layout.html" %}

{% set claimantName = 'Mrs J Doe' %}
{% set claimantFullName = 'Jane Doe' %}
{% set claimantNino = 'XX123456X' %}
{% set claimantAddress1 = '1 Address Street' %}
{% set claimantTown = 'Newcastle' %}
{% set claimantPostCode = 'NE1 EBR' %}
{% set claimLetterDate = '08 August 2022' %}
{% set claimDate = '01 February 2022' %}
{% set claimRate = '£156.66' %}
{% set claimStartDate = '10 August 2022' %}
{% set claimInterimDate = '22 August 2022' %}
{% set claimEndDate = '09 May 2023' %}
{% set claimFirstPayment = '£290.94' %}
{% set claimTimeToPaymentStart = '5' %}
{% set claimTimeToPaymentEnd = '10' %}
{% set claimPayFrequency = '4 weeks' %}
{% set claimPayDay = 'Monday' %}
{% set claimPayStart = '19 September 2022' %}


{% block pageTitle %}
GOV.UK Prototype Kit
{% endblock %}

{% block content %}
        <div class="govuk-grid-row">
          <div class="govuk-grid-column-full">

            <div id="contentToTest" class="content-letter colour-distinction taller-lines">

              <div class="govuk-!-margin-top-4">



              </div>

              <div class="address-row">
                <div class="address-row-item">
                  <p>
                    {{ claimantName }} <br><br>
                    {{ claimantAddress1 }} <br>
                    {{ claimantTown }} <br>
                    {{ claimantPostCode }}
                  </p>
                </div>
                <div class="address-row-item">
                  <p>
                    Maternity Allowance<br>
                    Mail Handling Site A<br>
                    Wolverhampton<br>
                    WV98 1SU<br>

                  </p>
                  <p><strong>www.gov.uk</strong></p>
                  <p>
                    Telephone: 0800 169 0283<br>
                    Textphone: 0800 169 0286<br>
                  </p>
                  <p>Your reference:<br>
                    {{ claimantNino }}</p>
                  <p>{{ claimLetterDate }}</p>

                </div>
              </div>



              <div class="letter-content-row">

                <div class="letter-content-primary" style="width: 100%">

                  <h2 class="govuk-heading-l govuk-!-margin-top-5 govuk-!-margin-bottom-0">We will pay you Maternity Allowance</h2>

                  <hr class="govuk-section-break govuk-section-break--visible govuk-!-margin-bottom-3">

                  <p class="govuk-!-font-weight-bold">We have many different ways we can communicate with you. If you would like Braille, British Sign Language, a hearing loop, translations, large print, audio or something else please tell us using the phone number at the top of this letter.</p>

                  <p>
                    Dear {{ claimantFullName }}
                  </p>

                  <p>Thank you for claiming Maternity Allowance. We will pay you {{ claimRate }} for each week from {{ claimStartDate }} to {{ claimEndDate }}. </p>

                  <p>Your first payment will be {{ claimFirstPayment }} for the period from {{ claimStartDate }} to {{ claimInterimDate }}. You will get this payment within {{ claimTimeToPaymentEnd }} working days. You will then get a payment at the end of every {{ claimPayFrequency }}.</p>

                  <p>We will send payments to the account you requested.</p>


                  <p>You do not have to take any further action.</p>

                  <h3 class="govuk-heading-s">How we calculate Maternity Allowance</h3>
                  <p>If you are employed, Maternity Allowance is calculated on the highest 13 weeks of earnings from your test period. If you are self-employed, it is worked out on the National Insurance (NI) contributions you made during your test period. The test period is the 66 weeks before the week you expect to have your baby.</p>

                  <p>The amount may be based, either in part or in full, on earnings information that your employer has given HMRC or from the payslips you have sent us.</p>


                </div>


                <div class="app-page-number-row">
                      <p>
                          Page 1 of 5
                      </p>
                  </div>

              </div>

              </div>





              <div id="contentToTest" class="content-letter colour-distinction taller-lines govuk-!-margin-top-9">

                <div class="letter-content-row">

                  <div class="letter-content-primary" style="width: 100%">


                    <h3 class="govuk-heading-m">If you need help<h3>
                    <h4 class="govuk-heading-s">Contact us</h4>
                    <p>For more information about this letter or your claim, contact us using the phone number or address at the start of this letter. You will need to provide your reference number. Calls to 0800 numbers are free from landlines and mobile phones.</p>

                    <h4 class="govuk-heading-s">Get advice</h4>
                    <p>If you live in England or Wales you can get free, independent and confidential advice about Maternity Allowance and other benefits. Call Civil Legal Advice on <strong>0345 345 4345</strong>. You can visit their website at <strong>www.gov.uk/civil-legal-advice</strong>.</p>

                    <p>Calls to <strong>0345</strong> numbers cost no more than a standard geographic call, and count towards any free or inclusive minutes in your landline or mobile phone contract.</p>

                    <p>Yours sincerely,</p>
                    <p>  Office manager</p>

                    <hr class="govuk-section-break govuk-section-break--visible govuk-!-margin-top-5 govuk-!-margin-bottom-5">

                    <h3 class="govuk-heading-m">Payment into an account</h3>
                    <h4 class="govuk-heading-s">Changes to your account</h4>
                    <p>Tell us immediately if your account details change, including:</p>
                    <ul class="govuk-list govuk-list--bullet">
                      <li>what changed</li>
                      <li>when it changed</li>
                      <li>what the new details are</li>
                    </ul>

                    <h4 class="govuk-heading-s">Viewing payments</h4>
                    <p>You can view your Maternity Allowance payments on account statements. The statements may show your National Insurance number next to the payments. If you think a payment is wrong, contact us immediately. We will tell you if the payment amount changes.</p>

                    <h4 class="govuk-heading-s">If we pay you too much money</h4>
                    <p>We have the right to take back any money we pay that you are not entitled to.</p>

                    <p>For example, you may give us information that means you are entitled to less money. We might not be able to change the payment amount in advance and would need to take back the appropriate amount. We will contact you before we take back any money.</p>


                    <hr class="govuk-section-break govuk-section-break--visible govuk-!-margin-top-5 govuk-!-margin-bottom-5">

                    <h3 class="govuk-heading-m">If you are self-employed</h3>
                    <p>From 6 April 2015, HMRC changed the way it collects Class 2 National Insurance (NI) contributions from self-employed people. There is more information at <strong>www.gov.uk</strong>.</p>

                    <p>You can pay your Class 2 NI contribution early to help you qualify for the standard rate of Maternity Allowance if you are self-employed and: </p>
                    <ul class="govuk-list govuk-list--bullet">
                      <li>your baby was due on or after July 2015</li>
                      <li>you have not yet filed your self-assessment, and</li>
                      <li>you have not paid your Class 2 NI contributions due to the change</li>
                    </ul>


                  </div>


                <div class="app-page-number-row">
                      <p>
                          Page 2 of 5
                      </p>
                  </div>

              </div>

          </div>





              <div id="contentToTest" class="content-letter colour-distinction taller-lines govuk-!-margin-top-9">

                <div class="letter-content-row">

                  <div class="letter-content-primary" style="width: 100%">

                    <p>In some cases we need to tell HMRC that you have claimed Maternity Allowance. HMRC may ask you to pay your Class 2 NI contributions early. If you do, we may be able to increase your Maternity Allowance to the standard rate. Contact us if you pay later than one month after the date of this letter. We will tell you if the payment amount changes.</p>

                    <p>If you are self-employed with a budgeting account, HMRC may allocate money you have paid towards your Class 2 NI contributions. HMRC will contact you if this happens. If you decide not to use money from your budgeting account to pay your Class 2 NI contributions, tell us immediately. You may have to repay some of your Maternity Allowance.</p>

                    <h4 class="govuk-heading-s">National Insurance credits</h4>
                    <p>We will usually give contributions to your National Insurance account for each week that you get Maternity Allowance. These contributions are called credits. They may help you get State Pension and other social security benefits in the future.</p>

                    <p>If you are self-employed, you do not have to pay the self-employed National Insurance contributions for each week you get Maternity Allowance.</p>

                    <p>A week runs Sunday to Saturday.</p>

                    <hr class="govuk-section-break govuk-section-break--visible govuk-!-margin-top-5 govuk-!-margin-bottom-5">

                    <h3 class="govuk-heading-m">If you are sick</h3>
                    <p>If you were sick before your Maternity Allowance began, or if you are still sick when it ends, you may be able to receive:</p>
                    <ul class="govuk-list govuk-list--bullet">
                      <li>Statutory Sick Pay (SSP) from your employer or</li>
                      <li>Employment and Support Allowance (ESA) from Jobcentre Plus</li>
                    </ul>

                    <p>You cannot get SSP or ESA and Maternity Allowance at the same time.</p>

                    <hr class="govuk-section-break govuk-section-break--visible govuk-!-margin-top-5 govuk-!-margin-bottom-5">

                    <h3 class="govuk-heading-m">Changes you must tell us about</h3>
                   <p>You or your representative must contact us at the phone number or address provided at the start of this letter if any of the following changes occur. You will need to provide your National Insurance number.</p>

                   <p>If you do not tell us about changes, action may be taken against you.</p>

                   <h4 class="govuk-heading-s">If your baby is born earlier than expected</h4>
                   <p>Tell us if your baby is born:</p>
                   <ul class="govuk-list govuk-list--bullet">
                     <li>earlier than the 30th week of pregnancy</li>
                     <li>later than the 30th week of pregnancy but before your Maternity Allowance Period has started</li>
                  </ul>


                    <!--hr class="govuk-section-break govuk-section-break--visible govuk-!-margin-bottom-4 govuk-!-margin-top-9" -->


                  </div>


                <div class="app-page-number-row">
                      <p>
                          Page 3 of 5
                      </p>
                  </div>

              </div>

          </div>



          <div id="contentToTest" class="content-letter colour-distinction taller-lines govuk-!-margin-top-9">

            <div class="letter-content-row">

              <div class="letter-content-primary" style="width: 100%">


                <p>You will still get the same amount of Maternity Allowance, but you will get it from the day after your baby is born.</p>

                <h4 class="govuk-heading-s">If you work during your Maternity Allowance Period</h4>
                <p>You can work up to 10 days as an employed or self-employed person without losing any Maternity Allowance. These are ‘Keeping in Touch’ days and help you keep in touch with your employer or business. Any amount of work you do in one day will count as ‘one day’ even if it is only an hour or a half day.</p>

                <p>An employer cannot demand that you use a ‘Keep in Touch’ day. It is your choice.</p>

                <h4 class="govuk-heading-s">If you get Shared Parental Leave or Statutory Shared Parental Pay</h4>
                <p>You and your partner or the baby’s other parent may be able to get Shared Parental Leave or Statutory Shared Parental Leave after your baby is born.</p>

                <p>If you are eligible and decide to take either benefit, you must tell us at least 8 weeks in advance that you want to end your Maternity Allowance early. If you have returned to work, your Maternity Allowance will end in the week you tell us. The end date will be the last date of your benefit week. For example, if your Maternity Allowance began on a Tuesday, the benefit week will end on a Monday.</p>

                <p>For more information visit <strong>www.gov.uk/shared-parental-leave-and-pay</strong>.</p>

                <h4 class="govuk-heading-s">Other changes that affect your benefit</h4>
                <p>You must also tell us if you:</p>
                <ul class="govuk-list govuk-list--bullet">
                  <li>take part in the business of your self-employed spouse or civil partner</li>
                  <li>go abroad outside the European Economic Area or Switzerland</li>
                  <li>go to the Ilse of Man or Channel Isles and want to get your money while there</li>
                  <li>go into prison or are held in legal custody (being in prison or held by police)</li>
                  <li>claim or get Statutory Maternity Pay (SMP), Statutory Paternity Pay (SPP) or Statutory Adoption Pay (SAP)</li>
                  <li>move to a different address</li>
                  <li>start to get or get an increase in an occupational pension from an employer</li>
                </ul>

                <p>Also tell us if anyone else claims money for you or receives money added to their benefit for you.</p>

                <p>Your representative must also tell us if you die.</p>


                <hr class="govuk-section-break govuk-section-break--visible govuk-!-margin-top-5 govuk-!-margin-bottom-5">

                <h3 class="govuk-heading-m">If you disagree with a decision</h3>

                <h4 class="govuk-heading-s">You can ask us to explain why</h4>
                <p>You, or someone who has the authority to act for you, can phone or write to us within one month of the date on this letter to ask us to explain our decision in writing.</p>



              </div>


            <div class="app-page-number-row">
                  <p>
                      Page 4 of 5
                  </p>
              </div>

          </div>

      </div>



      <div id="contentToTest" class="content-letter colour-distinction taller-lines govuk-!-margin-top-9">

        <div class="letter-content-row">

          <div class="letter-content-primary" style="width: 100%">

            <h4 class="govuk-heading-s">You can also ask us to reconsider a decision</h4>
            <p>Tell us if you have more information, or if you think we have overlooked something which might change the decision. Do this within one month of the date on this letter. </p>

            <p>We will look at what you tell us and send you a letter to tell you what we have decided, and why. We call this letter a Mandatory Reconsideration Notice.</>

            <h4 class="govuk-heading-s">When you have done this you can appeal</h4>
            <p>If you disagree with the Mandatory Reconsideration Notice, you can appeal to a tribunal.</p>

            <p>You must wait for the Mandatory Reconsideration Notice before you start an appeal.</p>

            <hr class="govuk-section-break govuk-section-break--visible govuk-!-margin-top-5 govuk-!-margin-bottom-5">

            <h3 class="govuk-heading-m">Equality and Diversity</h3>
            <p>We treat people fairly, regardless of their disability, ethnicity, gender, sexual orientation, transgender status, marital or civil partnership status, age, religion or beliefs.</p>

            <hr class="govuk-section-break govuk-section-break--visible govuk-!-margin-top-5 govuk-!-margin-bottom-5">

            <h3 class="govuk-heading-m">How we handle personal information</h3>
            <p>We treat personal information carefully. We may use it for any of our purposes. To learn more about information rights and how we use information, please see our DWP Personal Information Charter at <strong>www.gov.uk/dwp/personal-information-charter</strong>. </p>



          </div>


        <div class="app-page-number-row">
              <p>
                  Page 5 of 5
              </p>
          </div>

      </div>
    </div>






        </div>


      {% endblock %}

```

