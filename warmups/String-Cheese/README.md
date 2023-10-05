# ✅ WARMUPS - String Cheese

| Key | Value |
| --- | --- |
| ID | 34 |
| Solves | 1584 |
| Value | 50 |

Writeup by: [@goproslowyo](https://github.com/goproslowyo)

## Tags

- easy

Files:

- [cheese.jpg](https://huntress.ctf.games/files/93a449f37a2360a9af56c3ee022d6962/cheese.jpg?token=eyJ1c2VyX2lkIjozMTgyLCJ0ZWFtX2lkIjo0MDcsImZpbGVfaWQiOjQ2fQ.ZR0T-w.pshkH1K_Z93enenrIxgNMfFs5I8)

## Description

Author: @JohnHammondOh, a cheese stick! This was my favorite snack as a kid. My mom always called it by a different name though...  Download the file(s) below.

## Writeup

The challenge title strongly hints at `strings`.

```bash
$ strings cheese.jpg|grep -i flag
flag{f4d9f0f70bf353f2ca23d81dcf7c9099}
```
