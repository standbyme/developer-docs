# Channel Add Leader

Gives the role of Leader for a user in the current channel.

| URL                          | Requires Auth | HTTP Method |
| ---------------------------- | ------------- | ----------- |
| `/api/v1/channels.addLeader` | `yes`         | `POST`      |

## Payload

| Argument | Example             | Required | Description      |
| -------- | ------------------- | -------- | ---------------- |
| `roomId` | `ByehQjC44FwMeiLbX` | Required | The channel's id |
| `userId` | `oCHkav5Zf6vmpu2W2` | Required | The user's id    |

## Example Call

```bash
curl -H "X-Auth-Token: 9HqLlyZOugoStsXCUfD_0YdwnNnunAJF8V47U3QHXSq" \
     -H "X-User-Id: aobEdbYhXfu5hkeqG" \
     -H "Content-type: application/json" \
     https://localhost:3000/api/v1/channels.addLeader \
     -d '{"roomId": "ByehQjC44FwMeiLbX", "userId": "oCHkav5Zf6vmpu2W2"}'
```

## Success Example Result

```javascript
{
    "success": true
}
```

## Bad Request Example Result

If the user is already a leader, it will return a `400 bad request` status.

```javascript
{
    "success": false,
    "error": "User is already a leader [error-user-already-leader]",
    "errorType": "error-user-already-leader"
}
```

## Change Log

| Version | Description |
| ------- | ----------- |
| 0.75.0  | Added.      |
