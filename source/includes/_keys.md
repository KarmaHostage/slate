# Keys

## Get All Cryptographic keys

```http
GET https://api.karmahostage.com/keys
X-API-KEY: "sk_xxx"
```

```java
karmahostage.keys()
            .list()
```

```shell
curl "http://api.karmahostage.com/keys"
  -H "X-API-KEY: sk_xxx"
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": "e4dea538-37d3-40df-99a7-da9992d3300c",
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

## Get a single cryptographic key

```http
GET https://api.karmahostage.com/keys/$key_id
X-API-KEY: "sk_xxx"
```

```java
karmahostage.keys()
            .retrieve("e4dea538-37d3-40df-99a7-da9992d3300c")
```

```shell
curl "http://api.karmahostage.com/keys/$key_id"
  -H "X-API-KEY: sk_xxx"
```

> This returns a json of the following format:

```json
  {
    "id": "e4dea538-37d3-40df-99a7-da9992d3300c",
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
```
