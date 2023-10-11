# ✅ WARMUPS - Baking

Writeup by: [@goproslowyo](https://github.com/goproslowyo)

## Tags

- easy

## Description

Author: @JohnHammond

Do you know how to make cookies? How about HTTP flavored?  Press the `Start` button in the top-right to begin this challenge.

## Writeup

This was a fun quick challenege. We want to bake "magic cookies" and it gives us a 120 hour timer. We obviously don't want to wait that long. The app returns a base64 encoded cookie with the "cooking information". We'll modify it and send it back to the server:

```shell
$ echo 'eyJyZWNpcGUiOiAiTWFnaWMgQ29va2llcyIsICJ0aW1lIjogIjEwLzExLzIwMjMsIDEzOjA3OjIxIn0=' | base64 -d
{"recipe": "Magic Cookies", "time": "10/11/2023, 13:07:21"}
```

I changed the cookie to be 7 days into the past, `10/04/2023` and reloaded the page:

`eyJyZWNpcGUiOiAiTWFnaWMgQ29va2llcyIsICJ0aW1lIjogIjEwLzQvMjAyMywgMTM6MDc6MjEifQ==`

to get the flag:

`flag{c36fb6ebdbc2c44e6198bf4154d94ed4}`
