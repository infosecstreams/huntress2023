# ✅ MISCELLANEOUS - M Three Sixty Five - Teams

Writeup by: [@goproslowyo](https://github.com/goproslowyo)

## Tags

- easy

## Description

Author: @David Carter

For this challenge, you can connect into a PowerShell Core instance. Note that this is running out of a Linux-based Docker container, so you do not have a full-blown Windows operating system or pure PowerShell.    When you connect to the session for the very first time, you will be authenticated into a Microsoft 365 environment. WARNING: Once you disconnect, you will need to restart your container to reauthenticate    For all of the M365-related challenges, you can use this same container for all the associated tasks in this group. If your container does not seem to be able to authenticate, please wait some time -- perhaps Microsoft might not like multiple logins at the same time ;)   We observed saw some sensitive information being shared over a Microsoft Teams message! Can you track it down?  Press the `Start` button on the top-right to begin this challenge.

## Writeup

We can use the AADInternals function `Get-AADIntTeamsMessages` to get the desired information.

```powershell
PS /home/user> Get-AADIntTeamsMessages

ClientMessageId : 8803098928400015000
Id              : 1695838171758
MessageType     : Text
DisplayName     : FNU LNU
ArrivalTime     : 09/27/2023 18:09:31
DeletionTime    :
Link            : 19:8tLE5Hp0MfXN3KZ3gBdcGMUs3Td78d3i5uk6uSC9rE81@thread.tacv2
Content         : flag{f17cf5c1e2e94ddb62b98af0fbbd46e1}
Type            : Message

ClientMessageId : 8803098928400015000
Id              : 1695838171758
MessageType     : Text
DisplayName     : FNU LNU
ArrivalTime     : 09/27/2023 18:09:31
DeletionTime    :
Link            : 19:8tLE5Hp0MfXN3KZ3gBdcGMUs3Td78d3i5uk6uSC9rE81@thread.tacv2
Content         : flag{f17cf5c1e2e94ddb62b98af0fbbd46e1}
Type            : Message
```

`flag{f17cf5c1e2e94ddb62b98af0fbbd46e1}`
