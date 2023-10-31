# ✅ MISCELLANEOUS - M Three Sixty Five - Conditional Access

Writeup by: [@goproslowyo](https://github.com/goproslowyo)

## Tags

- easy

## Description

Author: @David Carter

For this challenge, you can connect into a PowerShell Core instance. Note that this is running out of a Linux-based Docker container, so you do not have a full-blown Windows operating system or pure PowerShell.    When you connect to the session for the very first time, you will be authenticated into a Microsoft 365 environment. WARNING: Once you disconnect, you will need to restart your container to reauthenticate    For all of the M365-related challenges, you can use this same container for all the associated tasks in this group. If your container does not seem to be able to authenticate, please wait some time -- perhaps Microsoft might not like multiple logins at the same time ;)   This tenant looks to have some odd  Conditional Access Policies. Can you find a weird one?  Press the `Start` button on the top-right to begin this challenge.

## Writeup

We can use the AADInternals function `Get-AADIntConditionalAccessPolicies` to get the desired information.

{% raw %}
```powershell
PS /home/user> Get-AADIntConditionalAccessPolicies

odata.type          : Microsoft.DirectoryServices.Policy
objectType          : Policy
objectId            : 16a4aa28-93af-4238-b877-dc869968b5be
deletionTimestamp   :
displayName         : flag{d02fd5f79caa273ea535a526562fd5f7}
keyCredentials      : {}
policyType          : 18
policyDetail        : {{"Version":1,"CreatedDateTime":"2023-09-26T15:33:28.0547019Z","ModifiedDateTime":"2023-09-27T15:37:03.5072379Z","
                      State":"Enabled","Conditions":{"Applications":{"Include":[{"Applications":["All"]}]},"Users":{"Include":[{"Roles":
                      ["9b895d92-2cd3-44c7-9d02-a6ac2d5ea5c3","c4e39bd9-1100-46d3-8c65-fb160da0071f","b0f54661-2d74-4c50-afa3-1ec803f12e
                      fe","158c047a-c907-4556-b7ef-446551a6b5f7","b1be1c3e-b65d-4f19-8427-f6fa0d97feb9","29232cdf-9323-42fd-ade2-1d097af
                      3e4de","62e90394-69f5-4237-9190-012177145e10","729827e3-9c14-49f7-bb1b-9608f156bbb8","966707d0-3269-4727-9be2-8c3a
                      10f19b9d","7be44c8a-adaf-4e2a-84d6-ab2649e08a13","194ae4cb-b126-40b2-bd5b-6091b380977d","f28a1f50-f6e7-4571-818b-6
                      a12f2af6b6c","fe930be7-5e62-47db-91af-98c3a49a38b1","0526716b-113d-4c15-b2c8-68e3c22b9f80","fdd7a751-b60b-444a-984
                      c-02652fe8fa1c","4d6ac14f-3453-41d0-bef9-a3e0c569773a","2b745bdf-0803-4d80-aa65-822c4493daac","11648597-926c-4cf3-
                      9c36-bcebb0ba8dcc","e8611ab8-c189-46e8-94e1-60213ab1f814","f023fd81-a637-4b56-95fd-791ac0226033","69091246-20e8-4a
                      56-aa4d-066075b2a7a8"]}],"Exclude":[{"Users":["183037f1-027d-4206-84af-95106f08e16c"]}]}},"Controls":[{"Control":[
                      "Mfa"]}],"EnforceAllPoliciesForEas":true,"IncludeOtherLegacyClientTypeForEvaluation":true}}
policyIdentifier    :
tenantDefaultPolicy :

odata.type          : Microsoft.DirectoryServices.Policy
objectType          : Policy
objectId            : 781fecfa-78c7-41b3-9961-fd82132465e3
deletionTimestamp   :
displayName         : Default Policy
keyCredentials      : {}
policyType          : 18
policyDetail        : {{"Version":0,"State":"Disabled"}}
policyIdentifier    : 09/27/2023 15:37:04
tenantDefaultPolicy : 18
```
{% endraw %}

`flag{d02fd5f79caa273ea535a526562fd5f7}`
