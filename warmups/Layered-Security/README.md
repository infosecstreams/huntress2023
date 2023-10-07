# ✅ WARMUPS - Layered Security

Writeup by: [@goproslowyo](https://github.com/goproslowyo)

## Tags

- easy

Files:

- [layered_security](./layered_security)

## Description

Author: @JohnHammond

It takes a team to do security right, so we have layered our defenses!  Download the file(s) below.

## Writeup

This one's title hints at layers and we're given a GIMP project according to the `file` command.

```shell
$  file layered_security
layered_security: GIMP XCF image data, version 011, 1024 x 1024, RGB Color
```

We can open it in GIMP and if you one-by-one hide each layer you'll find the flag one layer.
