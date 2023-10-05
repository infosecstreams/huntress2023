# ✅ WARMUPS - Notepad

| Key    | Value |
| ------ | ----- |
| ID     | 31    |
| Solves | 1767  |
| Value  | 50    |

Writeup by: [@goproslowyo](https://github.com/goproslowyo)

## Tags

- easy

Files:

- [notepad](https://huntress.ctf.games/files/d753e9f1fe7f8d22715c877a579f982b/notepad?token=eyJ1c2VyX2lkIjozMTgyLCJ0ZWFtX2lkIjo0MDcsImZpbGVfaWQiOjIxfQ.ZR0T-w.3zvnWABjXkyfFGyU55J-kRh8pWQ)

## Description

Author: @JohnHammondJust a sanity check... you do know how to use a computer, right? Download the files below.

## Writeup

Let's just try to read the file...

```bash
$ cat notepad
+------------------------------------------------------+
| [✖] [□] [▬]  Notepad                               - |
|------------------------------------------------------|
| File   Edit   Format   View   Help                   |
|------------------------------------------------------|
|                                                      |
|                                                      |
|   New Text Document - Notepad                        |
|                                                      |
|     flag{2dd41e3da37ef1238954d8e7f3217cd8}           |
|                                                      |
|                                                      |
|                                                      |
|                                                      |
|                                                      |
|                                                      |
|                                                      |
|                                                      |
|                                                      |
|                                                      |
+------------------------------------------------------+
| Ln 1, Col 40                                         |
+------------------------------------------------------+
```

Oh look, a flag.

`flag{2dd41e3da37ef1238954d8e7f3217cd8}`
