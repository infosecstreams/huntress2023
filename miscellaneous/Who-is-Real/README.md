# ✅ MISCELLANEOUS - Who is Real?

Writeup by: [@goproslowyo](https://github.com/goproslowyo)

## Tags

- easy

## Description

Author: @JohnHammond

This is not a technical challenge, but it is a good test of your eye!  Now we live in a world of generative AI, for better or for worse. The fact of the matter is, threat actors can scheme up fake personas to lure you into a scam or social engineering... so, can you determine which profile picture is real and which is fake?  Play a game to train yourself on identifying what stands out for AI generated people. After a streak of 10 correct selections, you'll receive the flag!  Press the `Start` button on the top-right to begin this challenge.

## Writeup

While it's possible that detecting AI generated faces could be useful in the future, I believe that there will eventually be tools with much higher accuracy than relying solely on human judgement. In my personal opinion, this challenge was not very exciting. It seemed more like a guessing game rather than a showcase of real skills. There isn't any direct connection to cybersecurity or and I don't understand the value it brings in terms of learning.

`flag{10c0e4ed5fcc3259a1b0229264961590}`

---

EDIT! I came back and played with the challenge with a friend after I completed it and we found that it's vulnerable to race conditions. Also, the right-side image is always the correct image to choose. So if you rapidly click the right-side image 5-10 times in a row an fire off multiple requests you'll get the flag. I think this is a much cooler solution and ... maybe the intended way? Not sure.
