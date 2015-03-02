# Form Builder Email Extentions

This module does provide two seperate added functionalities to FormBuilder. 

1\. The module does allow users to set default "From" email addresses for emails send to administrators.

There's a global address, which is set in the modules settings, and a additional field in the settings for "Send an email to administrator(s)", where one can set a form specific emailaddress to override the global one. Both of those are overridden if you chose to use the "Email from field" setting and the returned value is not blank.

2\. The module does add an additional syntax for the textfield where administrator emails are set. 

If you have a pagefield in your form, where one can choose from the potential users, that should be emailed you don't need to write extensive conditional lines like this:

```php
personInCharge=SomeUser?someuser@example.com
personInCharge=AnotherUser?anotheruser@example.com
```

You can simply add a email field to the template of those users and use the email provided there.

```php
!personInCharge?email
```

The syntax says get the user(s) from the field `personInCharge` and send email(s) to the addresses provided by the `email` field of the selected page.
