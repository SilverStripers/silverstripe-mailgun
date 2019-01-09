# silverstripe-mailgun
Mailgun integration for SilverStripe ^4

Create a config file with following contents in the mysite/_config directory

```

---
Name: myemailconfig
After:
  - '#emailconfig'
---
SilverStripe\Core\Injector\Injector:
  Swift_Transport:
    class: Swift_SmtpTransport
    properties:
      Host: smtp.mailgun.org
      Port: 25
    calls:
      Username: [ setUsername, ['<your SMTP username>'] ]
      Password: [ setPassword, ['<your SMTP password>'] ]
  
  
```