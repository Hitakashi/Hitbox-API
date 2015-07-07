Hitbox-API
==========

This is an unofficial documentation of hitbox.tv API. 

Chat Documentation: Old: http://hitakashi.github.io/Hitbox-Chat-Methods/ | New: https://github.com/Hitakashi/Hitbox-Chat-Doc

Chat Documentation Repo: https://github.com/Hitakashi/Hitbox-Chat-Methods | https://github.com/Hitakashi/Hitbox-Chat-Doc

### Repo Information

The current layout of the API documentation is sorted by what the API deals with, if it's updating user information it belongs in `/user`, if it deals with statistics in stored with `/channel` (While stats are stored within the users settings, without a channel you won't have any stats), etc.



### Hitbox Information

I have created two accounts on hitbox called `hitakashi-stream-int` and `hitakashi-test-unint` that are setup with a stream and without a stream respectively to test unauthenticated API endpoints on.

Please **always** use HTTPS on the API, or at the very least any API requiring auth tokens.

Do not post user passwords through your server. Instead POST it inside the browser via javascript. I recommend saving the auth token inside a cookie or local storage, but it [looks like](https://www.reddit.com/r/hitbox/comments/2flgvy/tnotifier_beta_has_begun/ckai8z6) you can pass the token to your server.

## Contribute

If you want to contribute to the documentation use the example below and send a pull request.

Example API Documentation.

# ABC API
***


| Endpoint | Description |
| ---- | --------------- |
| [GET /](/.md#get-) | Returns stream stats |

## `GET /`

Returns

| Parameter | Required? | Type | Description |
| --- | --- | --- | --- |
| authToken | Yes | string | User's Auth Token |

### Example URL

https://www.hitbox.tv/api/

### Example Response 

```javascript

```
