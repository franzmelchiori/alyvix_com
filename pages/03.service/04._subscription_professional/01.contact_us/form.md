---
title: Alyvix Service | Professional Subscription | Contact Form
form:
    name: alyvix_service
    fields:
        - name: name
          label: Name
          placeholder: Enter your name
          autofocus: on
          autocomplete: on
          type: text
          validate:
            required: true

        - name: email
          label: Email
          placeholder: Enter your email address
          type: text
          validate:
            rule: email
            required: true

        - name: service_request
          label: Service request
          default: Professional subscription
          type: text
          readonly: true

        - name: message
          label: Message
          size: long
          placeholder: Enter your message
          type: textarea

    buttons:
        - type: submit
          value: Send the service request
          classes: gdlr-button with-border excerpt-read-more

    process:
        - email:
            from:
              - "{{ config.plugins.email.from }}"
            to:
              - "{{ config.plugins.email.to }}"
            subject: "[Alyvix|Lead] Service request | Professional subscription"
            body: "{% include 'forms/data.html.twig' %}"
        - save:
            fileprefix: contact_form_
            dateformat: Ymd_His
            extension: txt
            body: "{% include 'forms/data.txt.twig' %}"
        - message: Thank you for contacting us!
        - display: thank_you
---

## **Professional** Subscription

Service and support for **5 probes** and *15 test cases* at **€6.600/yr**.

Please, **fill in the form** below and **send the service request** to us:
