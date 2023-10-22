# ✅ FORENSICS - Wimble

Writeup by: [@goproslowyo](https://github.com/goproslowyo)

## Tags

- easy

Files:

- [wimble.7z](./wimble.7z)

## Description

Author: @JohnHammond

"Gretchen, stop trying to make fetch happen! It's not going to happen!" - Regina George, Mean Girls  Download the files below.

## Writeup

This was a re-used challenge from Nahamcon called 'fetch'. Even the flag was re-used so this challenge was disappointing.

Anyway, the way it's supposed to be done is using PECmd.exe to find some interesting metadata that contains the `flag{...}` string.

Using PECmd.exe you can decompress all the *.pf files or you can just decompress and analyze the WORDPAD pf file and find the flag.

`flag{97f33c9783c21df85d79d613b0b258bd}`
