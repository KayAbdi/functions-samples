# New user email

This sample shows how to send welcome email when a new user signs up and a goodbye email when the user deletes his account.


## Functions Code

See file [functions/index.js](functions/index.js) for the email sending code.

Sending emails is performed using [nodemailer](https://www.npmjs.com/package/bad-words) a node based Email client with comprehensive EMail server setup. In this sample we're showing how to send email through SMTP using a Gmail account. Be aware that Gmail has an [email sending quota](). If you are planning on sending a large number of emails you should use a professional email sending platform such as Sendgrid

The dependencies are listed in [functions/package.json](functions/package.json).

## Trigger rules

The function triggers on account creation and account deletion.


## Setting up the sample

Set the `gmail.email` and `gmail.password` Google Cloud environment variables to match the email and password of the Gmail account used to send emails. For this use:

```bash
firebase env:set gmail.email="myusername@gmail.com" gmail.password="secretpassword"
```

This sample comes with a web-based UI for testing the function. To set it up:

 - Create a Firebase Project using the Firebase Developer Console
 - Enable Google Provider in the Auth section
 - Import and configure Firebase in the `public/index.html` where the `TODO` is located


## Deploy and test

This sample comes with a web-based UI for testing the function. To test it out:

 - Deploy your project using `firebase deploy`
 - Open the app using `firebase open`, Sign in using Google Sign-In and delete your accounts and you should receive email confirmations.