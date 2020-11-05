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
            subject: "[Alyvix|Lead] Service request | Professional Subscription"
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

## **Professional** Subscription

Service and support for **5 Alyvix Server** instances, along with the following *subscription features*:

<div style="overflow-x:auto;">
    <table style="margin-left:auto;margin-right:auto;border-collapse:collapse">
        <tr>
            <th style="background-color:white;"></th>
            <th style="padding:0 25px 0 25px;">Professional</th>
        </tr>
        <tr style="background-color:#f8f9fa;">
            <th style="text-align:right;white-space:nowrap;">Alyvix Server<sup>1</sup></th>
            <td style="text-align:center;"><b>5 instance</b></td>
        </tr>
        <tr style="background-color:#f8f9fa;">
            <th style="text-align:right;white-space:nowrap;">Windows sessions<sup>2</sup></th>
            <td style="text-align:center;"><b>5/instance</b></td>
        </tr>
        <tr>
            <th style="text-align:right;white-space:nowrap;">Supported incidents</th>
            <td style="text-align:center;">15/year</td>
        </tr>
        <tr>
            <th style="text-align:right;white-space:nowrap;">Normal response</th>
            <td style="text-align:center;">4 hours</td>
        </tr>
        <tr>
            <th style="text-align:right;white-space:nowrap;">Critical response</th>
            <td style="text-align:center;">2 hours</td>
        </tr>
        <tr style="background-color:#f8f9fa;">
            <th style="text-align:right;white-space:nowrap;">Service requests</th>
            <td style="text-align:center;">15/year</td>
        </tr>
        <tr style="background-color:#f8f9fa;">
            <th style="text-align:right;white-space:nowrap;">Service response</th>
            <td style="text-align:center;">4 hours</td>
        </tr>
        <tr>
            <th style="text-align:right;white-space:nowrap;">People supported</th>
            <td style="text-align:center;">2 person</td>
        </tr>
        <tr>
            <th style="text-align:right;white-space:nowrap;">Remote training</th>
            <td style="text-align:center;color:red">&#x2717; extra €/day</td>
        </tr>
        <tr style="background-color:#f8f9fa;">
            <th style="background-color:white;"></th>
            <td style="text-align:center;"><b>6.600 €/year</b></td>
        </tr>
    </table>
<br>
</div>

<div style="text-align:center;">
    <font size="1">1. Alyvix Server is a Windows service installed on a Windows 64-bit OS where English is the recommended language. <i>Microsoft licences are not included in the subscription.</i></font><br>

    <font size="1">2. Windows Terminal Server is required when managing more than 1 Windows session with Alyvix Server. <i>Microsoft licences are not included in the subscription.</i></font><br>
<br>
</div>

Please, **fill in the form** below and **send the service request** to us:
