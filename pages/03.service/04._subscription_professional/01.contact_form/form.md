---
title: Alyvix Service | Professional Subscription | Contact Form
form:
    name: alyvix_service_professional_subscription_contact_form
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
          default: Professional Subscription
          type: text
          readonly: true

        - name: agree_to_terms:
          type: checkbox
          label: "I would like to integrate Alyvix with my current monitoring system"
          validate:
            required: false

        - name: pages.order.by
          type: select
          size: long
          classes: fancy
          label: 'How did you find out about Alyvix?'
          options:
            default: "I don't remember"
            source_1: 'Web search'
            source_2: 'Social channel'
            source_3: 'Commercial contact'
            source_4: 'Partner or customer suggestion'
            source_5: 'Industry conference'

        - name: message
          label: Message
          size: long
          placeholder: Enter your message
          type: textarea

        - name: g-recaptcha-response:
          label: Captcha
          type: captcha

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
            subject: "[Alyvix|Lead] Service request | Professional Subscription"
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

## **Professional** Subscription

Service and support for **5 probes**, *15 test cases* and the following *subscription features*:

<div style="overflow-x:auto;">
    <table style="margin-left:auto;margin-right:auto;border-collapse:collapse">
        <tr>
            <th style="background-color:white;"></th>
            <th style="padding:0 25px 0 25px;">Professional</th>
        </tr>
        <tr style="background-color:#f8f9fa;">
            <th style="text-align:right;white-space:nowrap;">Supported probes</th>
            <td style="text-align:center;"><b>5</b></td>
        </tr>
        <tr style="background-color:#f8f9fa;">
            <th style="text-align:right;white-space:nowrap;">Supported test cases</th>
            <td style="text-align:center;"><em>15</em></td>
        </tr>
        <tr style="background-color:#f8f9fa;">
            <th style="text-align:right;white-space:nowrap;">Windows multisession</th>
            <td style="text-align:center;color:green;">&#x2713;</td>
        </tr>
        <tr>
            <th style="text-align:right;white-space:nowrap;">Supported incidents</th>
            <td style="text-align:center;">15/y</td>
        </tr>
        <tr>
            <th style="text-align:right;white-space:nowrap;">Normal response</th>
            <td style="text-align:center;">4h</td>
        </tr>
        <tr>
            <th style="text-align:right;white-space:nowrap;">Critical response</th>
            <td style="text-align:center;">2h</td>
        </tr>
        <tr style="background-color:#f8f9fa;">
            <th style="text-align:right;white-space:nowrap;">Service requests</th>
            <td style="text-align:center;">15/y</td>
        </tr>
        <tr style="background-color:#f8f9fa;">
            <th style="text-align:right;white-space:nowrap;">Service response</th>
            <td style="text-align:center;">4h</td>
        </tr>
        <tr>
            <th style="text-align:right;white-space:nowrap;">Supported people</th>
            <td style="text-align:center;">2</td>
        </tr>
        <tr>
            <th style="text-align:right;white-space:nowrap;">Remote training</th>
            <td style="text-align:center;color:red">&#x2717;</td>
        </tr>
        <tr style="background-color:#f8f9fa;">
            <th style="background-color:white;"></th>
            <td style="text-align:center;"><b>€6.600/y</b></td>
        </tr>
    </table>
    <br>
</div>

Please, **fill in the form** below and **send the service request** to us:
