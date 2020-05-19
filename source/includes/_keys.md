# Keys

## Get All Cryptographic keys

```http
GET https://api.karmahostage.com/keys
X-API-KEY: "sk_xxx"
```

```shell
curl "http://api.karmahostage.com/keys"
  -H "X-API-KEY: sk_xxx"
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "My Secret Cryptographic Key",
    "description": "My key that I'll use for secret things",
    "creationDate": "2020-02-18 20:21",
    "latestVersion": 2,
    "minimumDecryptionVersion": 1,
    "minimumEncryptionVersion": 2,
    "type": "AES_GCM",
    "exportable": false,
    "deletable": false,
    "derived": false
  }
]
```

This endpoint retrieves all keys linked to your application.
