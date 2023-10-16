# ✅ MISCELLANEOUS - M Three Sixty Five - General Info

Writeup by: [@goproslowyo](https://github.com/goproslowyo)

## Tags

- easy

## Description

Author: @David Carter

For this challenge, you can connect into a PowerShell Core instance. Note that this is running out of a Linux-based Docker container, so you do not have a full-blown Windows operating system or pure PowerShell.    Connect with SSH, with username `user` and SSH password `userpass`.    When you connect to the session for the very first time, you will be authenticated into a Microsoft 365 environment. WARNING: Once you disconnect, you will need to restart your container to reauthenticate    For all of the M365-related challenges, you can use this same container for all the associated tasks in this group. If your container does not seem to be able to authenticate, please wait some time -- perhaps Microsoft might not like multiple logins at the same time ;)   Welcome to our hackable M365 tenant! Can you find any juicy details, like perhaps the street address this organization is associated with?  Press the `Start` button on the top-right to begin this challenge.

## Writeup

We can use the AADInternals function `Get-AADIntTenantDetails` to get the desired information.

```powershell
PS /home/user> Get-AADIntTenantDetails

odata.type                                : Microsoft.DirectoryServices.TenantDetail
objectType                                : Company
objectId                                  : 05985beb-42bc-4c24-bf49-c1730a825406
deletionTimestamp                         :
assignedPlans                             : {@{assignedTimestamp=09/16/2023 06:40:21; capabilityStatus=Enabled; service=exchange; servic
                                            ePlanId=9f431833-0334-42de-a7dc-70aa40db46db}, @{assignedTimestamp=09/16/2023 06:40:21; capa
                                            bilityStatus=Enabled; service=exchange; servicePlanId=5136a095-5cf0-4aff-bec3-e84448b38ea5},
                                             @{assignedTimestamp=09/16/2023 06:40:17; capabilityStatus=Enabled; service=M365LabelAnalyti
                                            cs; servicePlanId=d9fa6af4-e046-4c89-9226-729a0786685d}, @{assignedTimestamp=09/16/2023 06:4
                                            0:19; capabilityStatus=Enabled; service=MicrosoftCommunicationsOnline; servicePlanId=0feaeb3
                                            2-d00e-4d66-bd5a-43b5b83db82c}…}
authorizedServiceInstance                 : {exchange/namprd04-012-01, ccibotsprod/NA001, YammerEnterprise/NA030, WhiteboardServices/NA0
                                            01…}
city                                      : Ellicott City
cloudRtcUserPolicies                      :
companyLastDirSyncTime                    :
companyTags                               : {o365.microsoft.com/startdate=638304432108764015, azure.microsoft.com/developer365=active, o
                                            365.microsoft.com/version=15, o365.microsoft.com/signupexperience=GeminiSignUpUI}
compassEnabled                            :
country                                   :
countryLetterCode                         : US
dirSyncEnabled                            :
displayName                               : HuntressCTF
isMultipleDataLocationsForServicesEnabled :
marketingNotificationEmails               : {}
postalCode                                : 21043
preferredLanguage                         : en
privacyProfile                            :
provisionedPlans                          : {@{capabilityStatus=Enabled; provisioningStatus=Success; service=exchange}, @{capabilityStat
                                            us=Enabled; provisioningStatus=Success; service=exchange}, @{capabilityStatus=Enabled; provi
                                            sioningStatus=Success; service=exchange}, @{capabilityStatus=Enabled; provisioningStatus=Suc
                                            cess; service=exchange}…}
provisioningErrors                        : {}
releaseTrack                              :
replicationScope                          : NA
securityComplianceNotificationMails       : {}
securityComplianceNotificationPhones      : {}
selfServePasswordResetPolicy              :
state                                     : MD
street                                    : flag{dd7bf230fde8d4836917806aff6a6b27}
technicalNotificationMails                : {huntressctf@outlook.com}
telephoneNumber                           : 8005555555
tenantType                                :
createdDateTime                           : 09/16/2023 06:40:09
verifiedDomains                           : {@{capabilities=Email, OfficeCommunicationsOnline; default=True; id=000520000FC960F2; initia
                                            l=True; name=4rhdc6.onmicrosoft.com; type=Managed}}
windowsCredentialsEncryptionCertificate   :
```

`flag{dd7bf230fde8d4836917806aff6a6b27}`
