# ✅ WARMUPS - Dialtone

| Key | Value |
| --- | --- |
| ID | 18 |
| Solves | 268 |
| Value | 50 |

Writeup by: [@goproslowyo](https://github.com/goproslowyo)

## Tags

- easy

Files:

- [dialtone.wav](https://huntress.ctf.games/files/f45233d4c250e2f75e5aae03725fffc7/dialtone.wav?token=eyJ1c2VyX2lkIjozMTgyLCJ0ZWFtX2lkIjo0MDcsImZpbGVfaWQiOjEzfQ.ZSAzjA.b-JhfFtFpRVoapgeiePi_Dc2VXU)

## Description

Author: @JohnHammond#6971Well would you listen to those notes, that must be some long phone number or something!  Download the file(s) below.

## Writeup

# x

Used http://dialabc.com/sound/detect/index.html to get the key presses.

Got `13040004482820197714705083053746380382743933853520408575731743622366387462228661894777288573`

Used https://www.mobilefish.com/services/big_number/big_number.php to convert from Hex to Decimal

`666C61677B36633733336566303962633466326134333133666636333038376532356436377D`

Use [CyberChef to convert from hex to ascii](https://gchq.github.io/CyberChef/#recipe=From_Hex('None')&input=NjY2QzYxNjc3QjM2NjMzNzMzMzM2NTY2MzAzOTYyNjMzNDY2MzI2MTM0MzMzMTMzNjY2NjM2MzMzMDM4Mzc2NTMyMzU2NDM2Mzc3RA)

`flag{6c733ef09bc4f2a4313ff63087e25d67}`
