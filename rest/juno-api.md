# Juno API

**Version:** v1\
**Description:** Previously intended for Noren's use only, the Juno API now allows anyone to check a Roblox user's blacklist status from Noren.

***

## Base URL

```
https://juno.norentech.vercel.app/api
```

***

## Ratelimits

Rate limits are enforced **per IP address** to keep our systems safe.

| Access Type                | Limit                       |
| -------------------------- | --------------------------- |
| Public (no authentication) | 10 requests per 60 seconds  |
| Authenticated (API key)    | 100 requests per 60 seconds |

When the rate limit is exceeded, the API responds with **HTTP 429**.

***

## Authentication

Authentication is **optional**.

* Public requests may be made without authentication.
* To receive higher rate limits, include an API key using a **Bearer token** in the `Authorization` header.
* API keys are issued for **Noren's internal use only**.

**Header Example**

```
Authorization: Bearer YOUR_API_KEY
```

***

## Endpoint

### Check Blacklist

Check whether a specific Roblox user ID is blacklisted.

**Method**\
`POST`

**Path**\
`/checkBlacklist`

**Full URL**\
&#xNAN;**`https://juno.vercel.app/api/checkBlacklist`**

***

## Request

### Headers

| Header          | Required | Description                           |
| --------------- | -------- | ------------------------------------- |
| `Content-Type`  | Yes      | Must be `application/json`            |
| `Authorization` | No       | Bearer API key for higher rate limits |

***

### Request Body

The request body must be JSON.

| Field    | Type   | Required | Description                             |
| -------- | ------ | -------- | --------------------------------------- |
| `UserId` | String | Yes      | Numeric string representing the user ID |

**Example Body**

```
{"UserId": "12345"}
```

***

## Responses

### 200 OK

Request completed successfully.

**Example Response**

```html
{
    "Blacklisted": false,
    "Message": "User isn't blacklisted."
}
```

**OR**

```
{
  "Blacklisted": true,
  "Message": "An active blacklist record was found.",
  "BlacklistId": "",
  "UserId": "",
  "Reason": "",
  "AppealsAllowed": "Yes/No",
  "ModeratorNote": "",
  "ExpiryDate": "YYYY-MM-DD"
}
```

***

### 400 Bad Request

Returned when the request body is missing or invalid.

**Example**

```html
{
    "error": "Invalid parameter UserId. Must be a numeric string."
}
```

***

### 429 Too Many Requests

Returned when the rate limit has been exceeded.

**Example**

```html
{
    "error": "Rate limit exceeded",
    "message": "Too many requests. Maximum 10 requests per 60 seconds.",
    "retryAfter": 60
}
```

***

### 500 Internal Server Error

Returned when an unexpected server error occurs.

***

## Examples

### cURL

```html
curl -X POST https://juno.vercel.app/api/checkBlacklist \
  -H "Content-Type: application/json" \
  -d '{"UserId":"12345"}'
```

***

### JavaScript (Unauthenticated)

```javascript
fetch('https://juno.vercel.app/api/checkBlacklist', {
    method: 'POST',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify({ UserId: '12345' })
})
.then(res => res.json())
.then(data => console.log(data));
```

***

### JavaScript (Authenticated)

```javascript
fetch('https://juno.vercel.app/api/checkBlacklist', {
    method: 'POST',
    headers: {
        'Content-Type': 'application/json',
        'Authorization': 'Bearer YOUR_API_KEY'
    },
    body: JSON.stringify({ UserId: '12345' })
})
.then(res => res.json())
.then(data => console.log(data));
```

***

## Usage Notes

* This API is intended strictly for blacklist verification.
* Do not expose API keys in client-side or public applications.
* Always validate user input before making requests.

***

## Support

For questions or issues, please [contact us](https://app.gitbook.com/s/Rj5umFSPEKFhW4JqM6l9/support/contact). However, we do not provide guidance or assistance for using this API.
