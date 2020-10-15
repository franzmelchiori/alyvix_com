---
title: Alyvix Feedback
menu: Feedback
redirect: 'https://review.capterra.com/SS-Alyvix-146702-3634877551-en'
onpage_menu: false
visible: false
form:
    name: alyvix_feedback
    fields:
        - name: overall_product_rate:
          type: radio
          label: Please rate Alyvix overall:
          options:
              5_score: 5 Great &#x1F604;
              4_score: 4
              3_score: 3 Ok &#x1F642;
              2_score: 2
              1_score: 1 Bad &#x1F629;
          default: 3_score
          validate:
            required: true

        - name: visual_transaction_definition_sentiment:
          type: radio
          label: How do you feel about the visual transaction definition?
          options:
              good_score: Good &#x1F44D;
              ok_score: Ok
              poor_score: Poor &#x1F44E;
          default: ok_score

        - name: test_case_building_sentiment:
          type: radio
          label: How do you feel about test case building?
          options:
              good_score: Good &#x1F44D;
              ok_score: Ok
              poor_score: Poor &#x1F44E;
          default: ok_score

        - name: performance_transaction_measures_sentiment:
          type: radio
          label: How do you feel about the performance transaction measures?
          options:
              good_score: Good &#x1F44D;
              ok_score: Ok
              poor_score: Poor &#x1F44E;
          default: ok_score

        - name: name
          label: Name
          placeholder: I want to remain anonymous
          autocomplete: on
          type: text

        - name: email
          label: Email
          placeholder: I don't want to be contacted
          type: text
          validate:
            rule: email

        - name: message
          label: Feel free to leave a message on any topic:
          size: long
          placeholder: I have nothing to add
          type: textarea

        - name: g-recaptcha-response:
          label: Captcha
          type: captcha

    buttons:
        - type: submit
          value: Send your feedback
          classes: gdlr-button with-border excerpt-read-more

    process:
        - email:
            from:
              - "{{ config.plugins.email.from }}"
            to:
              - "{{ config.plugins.email.to }}"
            subject: "[Alyvix|Market] Feedback"
            body: "{% include 'forms/data.html.twig' %}"
        - save:
            fileprefix: contact_form_
            dateformat: Ymd_His
            extension: txt
            body: "{% include 'forms/data.txt.twig' %}"
        - message: Your feedback was sent.
        - display: thank_you
        - captcha: true
---

## Product **Feedback**

Your candid feedback powers our engines.
