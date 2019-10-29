### Prevent Clickjacking

`X-Frame-Options: deny`

or

`X-Frame-Options: sameorigin`

or

`X-Frame-Options: allow-from https://example.com`

PLUS Content Security Policy at the Server side

`Content-Security-Policy: frame-ancestors 'none';`



### ADD CSRF token

### ADD SameSite attribute

Set-Cookie: CookieName=CookieValue; SameSite=Strict;
