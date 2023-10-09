# ✅ FORENSICS - Dumpster Fire

Writeup by: [@goproslowyo](https://github.com/goproslowyo)

## Tags

- easy

Files:

- [dumpster_fire.tar.xz](./dumpster_fire.tar.xz)

## Description

Author: @JohnHammond

We found all this data in the dumpster! Can you find anything interesting in here,  like any cool passwords or anything? Check it out quick before the foxes get to it!  Download the file(s) below.

## Writeup

This was a "filesystem dump" that contained a firefox profile. Inside the profile is a password stored in the password manager that you can extract. Password is crackable with python scripts on github or you can simply drop the .mozilla directory into an existing Firefox install and open the recovered profile.

`flag{35446041dc161cf5c9c325a3d28af3e3}`
