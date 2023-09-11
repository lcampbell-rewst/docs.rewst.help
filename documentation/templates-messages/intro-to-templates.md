# Intro to Templates

### Overview

Templates are used so that you can have a standardized set of text used in several places.

For example, if you want to create a ticket and always use the same HTML for the ticket description, you would create a template and in the input, reference the template instead of having to type that same text each time.

### Templates and Jinja

The great thing about our templates is that you can set Context Variables within them.

In our example below, we are sending an e-mail to a new user that has been created.

```django
Hi {{ CTX.first_name }},

Welcome to Rewst!

Your email account has been provisioned and you should be able to access it at:
https://outlook.office.com/mail/

username: {{ CTX.email }}
password: {{ CTX.password }}

We're excited to have you on the team!
```

In the input for the "Send Mail" action, you would use:

`{{ template("<template-id>")}}`

The template ID can be taken from the URL, when you are editing the template.

The URL will look similar to below:

[https://app.rewst.io/organizations/40f8b55a-e8a9-42fc-8dc1-179616275f10/templates/768f5d45-5fe7-4c1f-b2c1-932dcbdcb1d7](https://app.rewst.io/organizations/40f8b55a-e8a9-42fc-8dc1-179616275f10/templates/768f5d45-5fe7-4c1f-b2c1-932dcbdcb1d7)

The template ID is "768f5d45-5fe7-4c1f-b2c1-932dcbdcb1d7"

`{{ template("768f5d45-5fe7-4c1f-b2c1-932dcbdcb1d7") }}`
