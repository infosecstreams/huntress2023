# ✅ MISCELLANEOUS - Babel

Writeup by: [@goproslowyo](https://github.com/goproslowyo)

## Tags

- medium

Files:

- [babel](./babel)

## Description

Author: @JohnHammond

It's babel! Just a bunch of gibberish, right?  Download the file below.

## Writeup

This was a C# file. We can look at the encoding function and reverse it. Here's the reverse in python:

```python
def reverse(txtstr, key='lQwSYRxgfBHqNucMsVonkpaTiteDhbXzLPyEWImKAdjZFCOvJGrU'):
    alphabet = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ"
    reversed_text = ""
    substitution_dict = dict()

    for i in range(len(alphabet)):
        substitution_dict[key[i]] = alphabet[i]

    for char in txtstr:
        if ('A' <= char <= 'Z') or ('a' <= char <= 'z'):
            reversed_text += substitution_dict[char]
        else:
            reversed_text += char

    return reversed_text

if __name__ == "__main__":
    print(reverse(encoded_str))
```

We can then run this, base64 decode the output, and grep for our flag:

```shell
 python rev.py| base64 -d | grep -a flag
flag{b6cfb6656ea0ac92849a06ead582456c}
```
