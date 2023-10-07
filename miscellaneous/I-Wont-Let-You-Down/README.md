# ✅ MISCELLANEOUS - I Wont Let You Down

Writeup by: [@goproslowyo](https://github.com/goproslowyo)

## Tags

- easy

## Description

Author: @proslasher

OK Go take a look at this IP:   Connect here: http://155.138.162.158
\# DO NOT USE BURP SUITE, OR YOU WILL BE DISQUALIFIED.

## Writeup

The challenge description has us visit a webpage at `http://155.138.162.158/`.

The web site tells us to use nmap. Nmap the IP find 8888 and 42069 open.

Both ports give us the flag after connecting with telnet and waiting for the rickroll that the title hints at to finish:

```shell
$ telnet 155.138.162.158 8888
[...snip...]
flag{93671c2c38ee872508770361ace37b02}
```
