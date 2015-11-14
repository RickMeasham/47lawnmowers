Who uses this API?
Example: You want to give micro loans to people in the community at an (ahem) reasonable interest rate. But you want to be sure your customers have passed the 100 point verification so you can trust them. You enter the customers address, mobile number and email information they give you in the ev widget which verifies that the customer is a verified customer with Australia Post which helps you crosscheck their identity claims to carry your transaction with confidence..

EV Widget (JS):
http://192.168.210.14/ev.html

When going through the widget, people should be using 11111111 as  a document number for things like driver’s licence, etc. For data sources that don’t require a number, e.g. Australian electoral roll, make sure that the street number field has value 1.

e.g.

POST http://host/ev/registrations

{
    "name": {
        "firstName": "John",
        "lastName": "Smith"
    },
    "address": {
        "streetNumber": "1",
        "streetName": "Bourke",
        "streetType": "ST",
        "suburb": "Melbourne",
        "state": "VIC",
        "postcode": "3000"
    },
    "contacts": {
        "email": "test@test123.com",
        "phone": {
            "mobile": "+61400123456"
        }
    },
    "gender": "M",
    "dateOfBirth": "01/01/1980"
}

The response will look something like this:


{
  "registrationId": "ddcb30a9-6ed0-49c7-9b4a-b168b522cfba",
  "widgetSessionId": "5221163e3704fef5d1b807905ee3d10e56b0f8d1",
  "identityCheckResult": {
    "overallStatus": "NOT_VERIFIED_IN_PROGRESS",
    "dataSources": [
      {
        "name": "Dunn & Bradstreet",
        "code": "DNB",
        "status": "NOT_VERIFIED_FAILED"
      },
      {
        "name": "Electoral Roll - VIC",
        "code": "ER_VIC",
        "status": "NOT_VERIFIED_FAILED"
      }
    ]
  }
}
