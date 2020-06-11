---
title: Alyvix Service | Enterprise Plus Subscription | Contact Form
form:
    name: alyvix_service_enterprise_plus_subscription_contact_form
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
          default: Enterprise Plus Subscription
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
            0_none: "I'm sorry, but I don't remember"
            1_web: 'Web search'
            2_social: 'Social channel'
            3_business: 'Business contact'
            4_suggestion: 'Partner or customer suggestion'
            5_conference: 'Industry conference'

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
            subject: "[Alyvix|Lead] Service request | Enterprise Plus Subscription"
            body: "{% include 'forms/data.html.twig' %}"
        - save:
            fileprefix: contact_form_
            dateformat: Ymd_His
            extension: txt
            body: "{% include 'forms/data.txt.twig' %}"
        - message: Your email was sent. We will answer shortly!
        - display: thank_you
        - captcha: true
---

## **Enterprise Plus** Subscription

Service and support for **12 probes**, *50 test cases* and the following *subscription features*:

<div style="overflow-x:auto;">
    <table style="margin-left:auto;margin-right:auto;border-collapse:collapse">
        <tr>
            <th style="background-color:white;"></th>
            <th style="padding:0 25px 0 25px;">Enterprise Plus</th>
        </tr>
        <tr style="background-color:#f8f9fa;">
            <th style="text-align:right;white-space:nowrap;">Supported probes</th>
            <td style="text-align:center;"><b>12</b></td>
        </tr>
        <tr style="background-color:#f8f9fa;">
            <th style="text-align:right;white-space:nowrap;">Supported test cases</th>
            <td style="text-align:center;"><em>50</em></td>
        </tr>
        <tr style="background-color:#f8f9fa;">
            <th style="text-align:right;white-space:nowrap;">Windows multisession</th>
            <td style="text-align:center;color:green;">&#x2713;</td>
        </tr>
        <tr>
            <th style="text-align:right;white-space:nowrap;">Supported incidents</th>
            <td style="text-align:center;">45/y</td>
        </tr>
        <tr>
            <th style="text-align:right;white-space:nowrap;">Normal response</th>
            <td style="text-align:center;">2h</td>
        </tr>
        <tr>
            <th style="text-align:right;white-space:nowrap;">Critical response</th>
            <td style="text-align:center;">1h</td>
        </tr>
        <tr style="background-color:#f8f9fa;">
            <th style="text-align:right;white-space:nowrap;">Service requests</th>
            <td style="text-align:center;">45/y</td>
        </tr>
        <tr style="background-color:#f8f9fa;">
            <th style="text-align:right;white-space:nowrap;">Service response</th>
            <td style="text-align:center;">2h</td>
        </tr>
        <tr>
            <th style="text-align:right;white-space:nowrap;">Supported people</th>
            <td style="text-align:center;">>3</td>
        </tr>
        <tr>
            <th style="text-align:right;white-space:nowrap;">Remote training</th>
            <td style="text-align:center;color:green">&#x2713;</td>
        </tr>
        <tr style="background-color:#f8f9fa;">
            <th style="background-color:white;"></th>
            <td style="text-align:center;"><b>€16.500/y</b></td>
        </tr>
    </table>
    <br>
</div>

Please, **fill in the form** below and **send the service request** to us: