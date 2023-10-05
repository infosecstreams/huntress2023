# ✅ WARMUPS - Book By Its Cover

| Key    | Value |
| ------ | ----- |
| ID     | 23    |
| Solves | 1216  |
| Value  | 50    |

Writeup by: [@goproslowyo](https://github.com/goproslowyo)

## Tags

- easy

Files:

- [book.rar](https://huntress.ctf.games/files/9c01905f2c4b6c78c6982fc45b0f3f32/book.rar?token=eyJ1c2VyX2lkIjozMTgyLCJ0ZWFtX2lkIjo0MDcsImZpbGVfaWQiOjE3fQ.ZR0T-g.aUaBgFAZbLpIJNC3hWJzEI42ggY)

## Description

Author: @JohnHammondThey say you aren't supposed to judge a book by its cover, but this is one of my favorites! Download the file below.

## Writeup

The challenge `Book By It's Cover` hint at us to never judge a book by it's cover. Same in cyber.

Let's use the `file` command to see what the file the gave us really is...

```bash
$ file book.rar
book.rar: PNG image data, 800 x 200, 8-bit/color RGB, non-interlaced
```

Ah, an image! Let's open it in an image viewer for our flag:

![We didn't judge this book.rar by it's cover](./flag.png)
