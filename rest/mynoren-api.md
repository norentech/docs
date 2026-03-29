# myNoren API

**Version:** v1\
**Description:** Previously intended for Noren's use only, the myNoren API now allows anyone to check a Roblox user's blacklist status from Noren.

***

## Base URL

```
https://my.norentech.vercel.app/api
```

***

## Ratelimits

Rate limits are enforced **per IP address** to keep our systems safe.

| Access Type                | Limit                       |
| -------------------------- | --------------------------- |
| Public (no authentication) | 10 requests per 60 seconds  |
| Authenticated (API key)    | 100 requests per 60 seconds |

***

## Check blacklist

<mark style="color:green;">`POST`</mark> `/checkBlacklist`

Check a Roblox user's blacklist status.

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body**

| Name     | Type   | Description                |
| -------- | ------ | -------------------------- |
| `UserId` | string | Roblox user ID of the user |

**Response**

{% tabs %}
{% tab title="200 OK" %}
```json
{
    "Blacklisted": false,
    "Message": "User isn't blacklisted."
}
```

**OR**

```json
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
{% endtab %}

{% tab title="400 Bad Request" %}
```json
{
    "error": "Invalid parameter UserId. Must be a numeric string."
}
```
{% endtab %}

{% tab title="429 Too Many Requests" %}
```json
{
    "error": "Rate limit exceeded",
    "message": "Too many requests. Maximum 10 requests per 60 seconds.",
    "retryAfter": 60
}
```
{% endtab %}

{% tab title="500 Internal Server Error " %}
Retured when an unexpected internal error occurs.
{% endtab %}
{% endtabs %}

**Examples**

{% tabs %}
{% tab title="cURL" %}
```c
curl -X POST https://my.norentech.vercel.app/api/checkBlacklist \
  -H "Content-Type: application/json" \
  -d '{"UserId":"12345"}'
```
{% endtab %}

{% tab title="JavaScript (Unauthenticated)" %}
```javascript
fetch('https://my.norentech.vercel.app/api/checkBlacklist', {
    method: 'POST',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify({ UserId: '12345' })
})
.then(res => res.json())
.then(data => console.log(data));
```
{% endtab %}

{% tab title="JavaScript (Authenticated)" %}
```javascript
fetch('https://my.norentech.vercel.app/api/checkBlacklist', {
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
{% endtab %}
{% endtabs %}

***

## Support

For questions or issues, please [contact us](https://app.gitbook.com/s/Rj5umFSPEKFhW4JqM6l9/support/contact). However, we do not provide guidance or assistance for using this API.
