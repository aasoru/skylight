---
title: Home
cache_enable: false
content:
    items: '@self.modular'
    order:
        by: default
        dir: asc
        custom:
            - _banner
            - _about
            - _features
            - _services
            - _testimonials
            - _prices
            - _cta1
            - _updates
            - _cta2
            - _cta3
            - _gallery
            - _contact
            - _map
form:
    action: /home
    name: contact
    button_outer_classes: 'form-group col-md-6 col-sm-12'
    fields:
        -
            name: name
            label: Name
            placeholder: 'Your name'
            autocomplete: 'on'
            type: text
            outerclasses: 'form-group col-md-6 col-sm-12'
            classes: col-md-12
            validate:
                required: true
        -
            name: email
            label: Email
            placeholder: 'Your email address'
            type: email
            outerclasses: 'form-group col-md-6 col-sm-12'
            classes: col-md-12
            validate:
                required: true
        -
            name: message
            label: Message
            placeholder: 'Your message'
            type: textarea
            rows: 5
            outerclasses: 'form-group col-md-12'
            classes: col-md-12
            validate:
                required: true
        -
            name: g-recaptcha-response
            label: Captcha
            type: captcha
            outerclasses: 'form-group col-md-12'
            classes: col-md-12
            recaptcha_site_key: null
            recaptcha_not_validated: 'Captcha not valid!'
            validate:
                required: false
    buttons:
        -
            type: submit
            value: Submit
    process:
        -
            captcha:
                recaptcha_secret: null
        -
            email:
                subject: '[Site Contact Form] {{ form.value.name|e }}'
                body: '{% include ''forms/data.html.twig'' %}'
        -
            save:
                fileprefix: contact-
                dateformat: Ymd-His-u
                extension: txt
                body: '{% include ''forms/data.txt.twig'' %}'
        -
            display: thank-you
---

