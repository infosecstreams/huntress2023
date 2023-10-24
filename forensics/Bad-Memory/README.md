# ✅ FORENSICS - Bad Memory

Writeup by: [@goproslowyo](https://github.com/goproslowyo)

## Tags

- medium

## Description

Author: @JohnHammond

A user came to us and said they forgot their password. Can you recover it? The flag is the MD5 hash of the recovered password wrapped in the proper flag format.  Download the file below. Note, this is a large 600MB file and may take some time to download.   image.zip

  !!! (file not provided in writeup repo like usual due to size.) !!!

## Writeup

```shell
$ functions volatility
volatility () {
 docker run --rm --name=vol3 -v $PWD:/workspace sk4la/volatility3 -f /workspace/image.bin $@
}

$ volatility windows.hashdump.Hashdump
Volatility 3 Framework 2.0.1
Progress:  100.00  PDB scanning finished
User rid lmhash nthash

Administrator 500 aad3b435b51404eeaad3b435b51404ee 31d6cfe0d16ae931b73c59d7e0c089c0
Guest 501 aad3b435b51404eeaad3b435b51404ee 31d6cfe0d16ae931b73c59d7e0c089c0
DefaultAccount 503 aad3b435b51404eeaad3b435b51404ee 31d6cfe0d16ae931b73c59d7e0c089c0
WDAGUtilityAccount 504 aad3b435b51404eeaad3b435b51404ee 4cff1380be22a7b2e12d22ac19e2cdc0
congo 1001 aad3b435b51404eeaad3b435b51404ee ab395607d3779239b83eed9906b4fb92
```

Crack the NT hash `ab395607d3779239b83eed9906b4fb92` to `goldfish#`.

Convert to md5.

```shell
$ echo "flag{$(echo -n 'goldfish#'|md5sum|awk '{print $1}')}"
flag{2eb53da441962150ae7d3840444dfdde}
```
