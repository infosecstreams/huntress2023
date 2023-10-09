# ✅ WARMUPS - Comprezz

Writeup by: [@goproslowyo](https://github.com/goproslowyo)

## Tags

- easy

Files:

- [comprezz](./comprezz)

## Description

Author: @JohnHammond

Someone stole my S's and replaced them with Z's! Have you ever seen this kind of file before?  Download the file(s) below.

## Writeup

```shell
$ file comprezz
comprezz: compress'd data 16 bits

$ cat comprezz | uncompress
flag{196a71490b7b55c42bf443274f9ff42b}
```

Or just use `zcat`:

```shell
$ zcat comprezz
flag{196a71490b7b55c42bf443274f9ff42b}
```

You can also rename and decompress:

```shell
$ mv comprezz comprezz.gz
$ gzip -d comprezz.gz
$ cat comprezz
flag{196a71490b7b55c42bf443274f9ff42b}
```
