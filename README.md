# The process of sending SMS via API
To send an SMS via API, the API token must be regenerated in the panel. This token must be added as Header to the request.

`X-Auth-Token: token`

*Request*

```
POST /api/v1/sms/send
 {
   "senderName":"FirmaABC",
   "body":"Witaj w SMSPoint",
   "phone":"49123456789",
}
```

1. Nazwa nadawcy (maks. 11 symboli)
1. Numer odbiorcy
1. Treść wiadomości

*Example*

```
curl -X POST --header 'Content-Type: application/json;charset=UTF-8'
  --header 'Accept: application/json'
  --header 'X-Auth-Token: 56b560a2-57cd-4071-8e6e-6eacb1979107' -d '{
  "senderName":"FirmaABC",
  "body":"Witaj w SMSPoint",
  "phone":"49123456789"
  }
}' 'https://celman.nvt-it.pl/public/api/v1/sms/send'
```

## SMS has been successfully sent
*Response 200 (application/json)*

```
{
  "success": true
}
```
true / false

## The SMS could not be sent
*Response 200 (application/json)*

```
{
  "success": false,
  "errorMessage": "Token hasn't been provided"
}
```
true / false with error description
