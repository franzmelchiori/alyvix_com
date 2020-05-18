---
title: Alyvix Service | Enterprise Subscription | Contact Form
form:
    name: alyvix_service_enterprise_subscription_contact_form
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
          default: Enterprise Subscription
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
            subject: "[Alyvix|Lead] Service request | Enterprise Subscription"
            body: "{% include 'forms/data.html.twig' %}"
        - save:
            fileprefix: contact_form_
            dateformat: Ymd_His
            extension: txt
            body: "{% include 'forms/data.txt.twig' %}"
        - message: Thank you for contacting us!
        - display: thank_you
---

## **Enterprise** Subscription

Service and support for **8 probes**, *30 test cases* and the following *subscription features*:

<div style="overflow-x:auto;">
    <table style="margin-left:auto;margin-right:auto;border-collapse:collapse">
        <tr>
            <th style="background-color:white;"></th>
            <th style="padding:0 25px 0 25px;">Enterprise</th>
        </tr>
        <tr style="background-color:#f8f9fa;">
            <th style="text-align:right;white-space:nowrap;">Supported probes</th>
            <td style="text-align:center;"><b>8</b></td>
        </tr>
        <tr style="background-color:#f8f9fa;">
            <th style="text-align:right;white-space:nowrap;">Supported test cases</th>
            <td style="text-align:center;"><em>30</em></td>
        </tr>
        <tr style="background-color:#f8f9fa;">
            <th style="text-align:right;white-space:nowrap;">Windows multisession</th>
            <td style="text-align:center;color:green;">&#x2713;</td>
        </tr>
        <tr>
            <th style="text-align:right;white-space:nowrap;">Supported incidents</th>
            <td style="text-align:center;">25/y</td>
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
            <td style="text-align:center;">25/y</td>
        </tr>
        <tr style="background-color:#f8f9fa;">
            <th style="text-align:right;white-space:nowrap;">Service response</th>
            <td style="text-align:center;">4h</td>
        </tr>
        <tr>
            <th style="text-align:right;white-space:nowrap;">Supported people</th>
            <td style="text-align:center;">3</td>
        </tr>
        <tr>
            <th style="text-align:right;white-space:nowrap;">Remote training</th>
            <td style="text-align:center;color:red">&#x2717;</td>
        </tr>
        <tr style="background-color:#f8f9fa;">
            <th style="background-color:white;"></th>
            <td style="text-align:center;"><b>€11.000/y</b></td>
        </tr>
    </table>
    <br>
</div>

Please, **fill in the form** below and **send the service request** to us:
