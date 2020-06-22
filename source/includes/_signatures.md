# Signatures

## Sign data with a cryptographic key

```http
POST https://api.karmahostage.com/sign
X-API-KEY: "sk_xxx"
Content-Type: application/json

{
  "plainText":"this is a test",
  "keyId":"e4dea538-37d3-40df-99a7-da9992d3300c"
}
```

```java
karmahostage.keys()
            .retrieve("e4dea538-37d3-40df-99a7-da9992d3300c")
            .sign("this is a test")
```

```shell
curl "http://api.karmahostage.com/sign"
  -H "X-API-KEY: sk_xxx"
  -H "Content-Type: application/json"  
  -x POST
  -d '{"keyId":"e4dea538-37d3-40df-99a7-da9992d3300c", "plainText":"this is a test"}'
```

> The above command returns JSON structured like this:

```json
{
  "signature": "vault:v1:kNIPpLY6/GfN09oj39k45PM+i8capcFSqFcM411gZaYLjZ1DgyOReg60s35grYT/Zkl21dwhmya1ZVOcU6Gcim63Yn1nF/znnAhgWEVTEeRfsp9UC6V37hyxjfzqd2jZKPzoKEH9JlDlxM47OlvOjJgZm1jKhFk9wKxZd7T8d0onu/EVU+mrahHOC6ubkRkNo2+oa4yLuUvLeg1HvkTF6QYQYzHVynzVFwzhF60+gb2nQFukyOWOcjzKgNPS8VkXlBws0ZmmUEcQyq/ImV0FLH/8PN2P/zNODvqCzTASCgkfE14n+DX2j0Nf4zceyU66fttJNhIxTAA0K5tEgQgWvOxJYyreKCiNY4SeXZ3GScYPrs3hC8v5zUhbImbpB8ZLDvk1aFeELwnOqs6THfjYmUXbGGZMK7rA2rZvZUwvd/9p79IYXev6I/XV+JpPMfVG26bJo+gHzVSLMbFTX7/Lvyie4ePEdS69FzhAspuJZXCZjVmzIDW1TK99EJde45Yg0vziae8RRn4bdkvdJYvBq0MxrrV3RuAgedTTkG4vJnzcVFQKpj8uMO2Q3QhJrG1Hh0/qxHAD0WRcuTLmkFYQ+rAPSKDbqfpv4/Jt1u18jc0r4uv9Vab71Epjt+UYRFVx38/0cnp1gj9fWUqnvGugo+iqC0iRC2ErEm5hRxuv/uo="
}
```

This endpoint will create a digital signature of the plain text using the key you requested.

# Signature Verification

## Validate a signature with known plaintext

```http
POST https://api.karmahostage.com/public/verify-signature
X-API-KEY: "sk_xxx"
Content-Type: application/json

{
  "plainText":"this is a test",
  "keyId":"e4dea538-37d3-40df-99a7-da9992d3300c",
  "signature": "vault:v1:kNIPpLY6/GfN09oj39k45PM+i8capcFSqFcM411gZaYLjZ1DgyOReg60s35grYT/Zkl21dwhmya1ZVOcU6Gcim63Yn1nF/znnAhgWEVTEeRfsp9UC6V37hyxjfzqd2jZKPzoKEH9JlDlxM47OlvOjJgZm1jKhFk9wKxZd7T8d0onu/EVU+mrahHOC6ubkRkNo2+oa4yLuUvLeg1HvkTF6QYQYzHVynzVFwzhF60+gb2nQFukyOWOcjzKgNPS8VkXlBws0ZmmUEcQyq/ImV0FLH/8PN2P/zNODvqCzTASCgkfE14n+DX2j0Nf4zceyU66fttJNhIxTAA0K5tEgQgWvOxJYyreKCiNY4SeXZ3GScYPrs3hC8v5zUhbImbpB8ZLDvk1aFeELwnOqs6THfjYmUXbGGZMK7rA2rZvZUwvd/9p79IYXev6I/XV+JpPMfVG26bJo+gHzVSLMbFTX7/Lvyie4ePEdS69FzhAspuJZXCZjVmzIDW1TK99EJde45Yg0vziae8RRn4bdkvdJYvBq0MxrrV3RuAgedTTkG4vJnzcVFQKpj8uMO2Q3QhJrG1Hh0/qxHAD0WRcuTLmkFYQ+rAPSKDbqfpv4/Jt1u18jc0r4uv9Vab71Epjt+UYRFVx38/0cnp1gj9fWUqnvGugo+iqC0iRC2ErEm5hRxuv/uo="
}
```

```shell
curl "http://api.karmahostage.com/sign"
  -H "X-API-KEY: sk_xxx"
  -H "Content-Type: application/json"  
  -x POST
  -d '{"keyId":"e4dea538-37d3-40df-99a7-da9992d3300c", "plainText":"this is a test", "signature": "vault:v1:kNIPpLY6/GfN09oj39k45PM+i8capcFSqFcM411gZaYLjZ1DgyOReg60s35grYT/Zkl21dwhmya1ZVOcU6Gcim63Yn1nF/znnAhgWEVTEeRfsp9UC6V37hyxjfzqd2jZKPzoKEH9JlDlxM47OlvOjJgZm1jKhFk9wKxZd7T8d0onu/EVU+mrahHOC6ubkRkNo2+oa4yLuUvLeg1HvkTF6QYQYzHVynzVFwzhF60+gb2nQFukyOWOcjzKgNPS8VkXlBws0ZmmUEcQyq/ImV0FLH/8PN2P/zNODvqCzTASCgkfE14n+DX2j0Nf4zceyU66fttJNhIxTAA0K5tEgQgWvOxJYyreKCiNY4SeXZ3GScYPrs3hC8v5zUhbImbpB8ZLDvk1aFeELwnOqs6THfjYmUXbGGZMK7rA2rZvZUwvd/9p79IYXev6I/XV+JpPMfVG26bJo+gHzVSLMbFTX7/Lvyie4ePEdS69FzhAspuJZXCZjVmzIDW1TK99EJde45Yg0vziae8RRn4bdkvdJYvBq0MxrrV3RuAgedTTkG4vJnzcVFQKpj8uMO2Q3QhJrG1Hh0/qxHAD0WRcuTLmkFYQ+rAPSKDbqfpv4/Jt1u18jc0r4uv9Vab71Epjt+UYRFVx38/0cnp1gj9fWUqnvGugo+iqC0iRC2ErEm5hRxuv/uo="}'
```

> The above command returns JSON structured like this:

```json
{
  "valid": true
}
```
