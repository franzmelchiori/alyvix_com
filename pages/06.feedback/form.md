---
title: Alyvix Feedback
menu: Feedback
onpage_menu: false
visible: false
form:
    name: alyvix_feedback
    fields:
        - name: overall_product_rate:
          type: radio
          label: Please, rate Alyvix overall:
          options:
              5_score: 5 Great &#x1F604;
              4_score: 4
              3_score: 3 Ok &#x1F642;
              2_score: 2
              1_score: 1 Bad &#x1F629;
              0_score: 0
          default: 3_score
          validate:
            required: true

        - name: message
          label: Please, feel free to leave any kind of message:
          size: long
          placeholder: Enter your message
          type: textarea

        - name: g-recaptcha-response:
          label: Captcha
          type: captcha

    buttons:
        - type: submit
          value: Send the feedback
          classes: gdlr-button with-border excerpt-read-more

    process:
        - email:
            from:
              - "{{ config.plugins.email.from }}"
            to:
              - "{{ config.plugins.email.to }}"
            subject: "[Alyvix|Lead] Service request | Standard Subscription"
            body: "{% include 'forms/data.html.twig' %}"
        - save:
            fileprefix: contact_form_
            dateformat: Ymd_His
            extension: txt
            body: "{% include 'forms/data.txt.twig' %}"
        - message: Thank you for contacting us!
        - display: thank_you
        - captcha: true
---

## Product **Feedback**

Your candid feedback power our engines.
