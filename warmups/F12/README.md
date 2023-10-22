# ✅ WARMUPS - F12

Writeup by: [@goproslowyo](https://github.com/goproslowyo)

## Tags

- easy

## Description

Author: @JohnHammond

Remember when Missouri got into hacking!?! You gotta be fast to catch this flag!  Press the `Start` button on the top-right to begin this challenge.

## Writeup

Quick easy challenge. Based on the Missouri F12 view-source fiasco.

Load the page and view the source. Inspect the javascript and you'll see it link to another page `/capture_the_flag.html`. Visit that page and inspect the source code to get the flag.

![Press F12 once](./f12.png)

![Press F12 again](./f12-again.png)

`flag{03e8ba07d1584c17e69ac95c341a2569}`
