---
title: 9. Contact
menu: Contact
cache_enable: false
content:
    items: @self.children
    order:
        by: ordering
        dir: asc
    limit: 4
    pagination: false
form:
    name: contact
    action: '/#contact'
    fields:
        - name: email
          label: Email
          placeholder: Entrez votre adresse email
          type: email
          validate:
            required: true
        - name: message
          label: Message
          placeholder: Entrez votre message
          type: textarea
          validate:
            required: true
    buttons:
        - type: submit
          value: Envoyer
        - type: reset
          value: Annuler
    process:
        - email:
            subject: "[Site Contact Form] {{ form.value.name|e }}"
            body: "{% include 'forms/data.html.twig' %}"
        - save:
            fileprefix: contact-
            dateformat: Ymd-His-u
            extension: txt
            body: "{% include 'forms/data.txt.twig' %}"
        - message: Merci ! Votre message a bien été enregistré et je vous contacterai dans les meilleurs délais.
        - display: '/'
        - reset: true
---

70 route de Vannes  
44100 NANTES  
T 06 66 95 96 53

SARL au capital de 2000 euros  
inscrite au conseil régional des architectes de Pays de la Loire au N° s083963

SIRET : 82818340000013