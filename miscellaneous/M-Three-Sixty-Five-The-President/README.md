# ✅ MISCELLANEOUS - M Three Sixty Five - The President

Writeup by: [@goproslowyo](https://github.com/goproslowyo)

## Tags

- easy

## Description

Author: @David Carter

For this challenge, you can connect into a PowerShell Core instance. Note that this is running out of a Linux-based Docker container, so you do not have a full-blown Windows operating system or pure PowerShell.    When you connect to the session for the very first time, you will be authenticated into a Microsoft 365 environment. WARNING: Once you disconnect, you will need to restart your container to reauthenticate    For all of the M365-related challenges, you can use this same container for all the associated tasks in this group. If your container does not seem to be able to authenticate, please wait some time -- perhaps Microsoft might not like multiple logins at the same time ;)   One of the users in this environment seems to have unintentionally left some information in their account details. Can you track down The President?  Press the `Start` button on the top-right to begin this challenge.

## Writeup

We can use the AADInternals function `Get-AADIntUsers` to get the desired information.

```powershell
PS /home/user> Get-AADIntUsers

AlternateEmailAddresses                :
AlternateMobilePhones                  :
AlternativeSecurityIds                 :
BlockCredential                        : false
City                                   : Overland Park
CloudExchangeRecipientDisplayType      : 1073741824
Country                                : United States
Department                             : Manufacturing
DirSyncEnabled                         :
DirSyncProvisioningErrors              :
DisplayName                            : Lee Gu
Errors                                 :
Fax                                    :
FirstName                              : Lee
ImmutableId                            :
IndirectLicenseErrors                  :
IsBlackberryUser                       : false
IsLicensed                             : true
LastDirSyncTime                        :
LastName                               : Gu
LastPasswordChangeTimestamp            : 2023-09-20T20:54:58Z
LicenseAssignmentDetails               : LicenseAssignmentDetails
LicenseReconciliationNeeded            : false
Licenses                               : Licenses
LiveId                                 : 10032002F3B3252E
MSExchRecipientTypeDetails             :
MSRtcSipDeploymentLocator              :
MSRtcSipPrimaryUserAddress             :
MobilePhone                            :
OathTokenMetadata                      :
ObjectId                               : 0b838a0a-f67c-448b-8731-ee3ddb18a605
Office                                 : 23/3101
OverallProvisioningStatus              : PendingInput
PasswordNeverExpires                   :
PasswordResetNotRequiredDuringActivate :
PhoneNumber                            : +1 913 555 0101
PortalSettings                         :
PostalCode                             : 66210
PreferredDataLocation                  :
PreferredLanguage                      : en-US
ProxyAddresses                         : ProxyAddresses
ReleaseTrack                           :
ServiceInformation                     : ServiceInformation
SignInName                             : LeeG@4rhdc6.onmicrosoft.com
SoftDeletionTimestamp                  :
State                                  : KS
StreetAddress                          : 10801 Mastin Blvd., Suite 620
StrongAuthenticationMethods            :
StrongAuthenticationPhoneAppDetails    :
StrongAuthenticationProofupTime        :
StrongAuthenticationRequirements       :
StrongAuthenticationUserDetails        :
StrongPasswordRequired                 :
StsRefreshTokensValidFrom              : 2023-09-20T20:54:58Z
Title                                  : Director
UsageLocation                          : US
UserLandingPageIdentifierForO365Shell  :
UserPrincipalName                      : LeeG@4rhdc6.onmicrosoft.com
UserThemeIdentifierForO365Shell        :
UserType                               : Member
ValidationStatus                       : Healthy
WhenCreated                            : 2023-09-16T10:24:35Z

AlternateEmailAddresses                :
AlternateMobilePhones                  :
AlternativeSecurityIds                 :
BlockCredential                        : false
City                                   : San Diego
CloudExchangeRecipientDisplayType      : 1073741824
Country                                : United States
Department                             : Marketing
DirSyncEnabled                         :
DirSyncProvisioningErrors              :
DisplayName                            : Alex Wilber
Errors                                 :
Fax                                    :
FirstName                              : Alex
ImmutableId                            :
IndirectLicenseErrors                  :
IsBlackberryUser                       : false
IsLicensed                             : true
LastDirSyncTime                        :
LastName                               : Wilber
LastPasswordChangeTimestamp            : 2023-09-20T20:54:59Z
LicenseAssignmentDetails               : LicenseAssignmentDetails
LicenseReconciliationNeeded            : false
Licenses                               : Licenses
LiveId                                 : 10032002F3B26E8B
MSExchRecipientTypeDetails             :
MSRtcSipDeploymentLocator              :
MSRtcSipPrimaryUserAddress             :
MobilePhone                            :
OathTokenMetadata                      :
ObjectId                               : 0ce655b4-3623-4931-ad67-7592e8c6ce9c
Office                                 : 131/1104
OverallProvisioningStatus              : PendingInput
PasswordNeverExpires                   :
PasswordResetNotRequiredDuringActivate :
PhoneNumber                            : +1 858 555 0110
PortalSettings                         :
PostalCode                             : 92121
PreferredDataLocation                  :
PreferredLanguage                      : en-US
ProxyAddresses                         : ProxyAddresses
ReleaseTrack                           :
ServiceInformation                     : ServiceInformation
SignInName                             : AlexW@4rhdc6.onmicrosoft.com
SoftDeletionTimestamp                  :
State                                  : CA
StreetAddress                          : 9256 Towne Center Dr., Suite 400
StrongAuthenticationMethods            :
StrongAuthenticationPhoneAppDetails    :
StrongAuthenticationProofupTime        :
StrongAuthenticationRequirements       :
StrongAuthenticationUserDetails        :
StrongPasswordRequired                 :
StsRefreshTokensValidFrom              : 2023-09-20T20:54:59Z
Title                                  : Marketing Assistant
UsageLocation                          : US
UserLandingPageIdentifierForO365Shell  :
UserPrincipalName                      : AlexW@4rhdc6.onmicrosoft.com
UserThemeIdentifierForO365Shell        :
UserType                               : Member
ValidationStatus                       : Healthy
WhenCreated                            : 2023-09-16T10:24:44Z

AlternateEmailAddresses                : AlternateEmailAddresses
AlternateMobilePhones                  :
AlternativeSecurityIds                 :
BlockCredential                        : false
City                                   :
CloudExchangeRecipientDisplayType      : 1073741824
Country                                :
Department                             :
DirSyncEnabled                         :
DirSyncProvisioningErrors              :
DisplayName                            : FNU LNU
Errors                                 :
Fax                                    :
FirstName                              : FNU
ImmutableId                            :
IndirectLicenseErrors                  :
IsBlackberryUser                       : false
IsLicensed                             : true
LastDirSyncTime                        :
LastName                               : LNU
LastPasswordChangeTimestamp            : 2023-09-20T20:54:57Z
LicenseAssignmentDetails               : LicenseAssignmentDetails
LicenseReconciliationNeeded            : false
Licenses                               : Licenses
LiveId                                 : 10032002F3A23780
MSExchRecipientTypeDetails             :
MSRtcSipDeploymentLocator              :
MSRtcSipPrimaryUserAddress             :
MobilePhone                            :
OathTokenMetadata                      :
ObjectId                               : 183037f1-027d-4206-84af-95106f08e16c
Office                                 :
OverallProvisioningStatus              : PendingInput
PasswordNeverExpires                   :
PasswordResetNotRequiredDuringActivate :
PhoneNumber                            :
PortalSettings                         :
PostalCode                             :
PreferredDataLocation                  :
PreferredLanguage                      : en
ProxyAddresses                         : ProxyAddresses
ReleaseTrack                           :
ServiceInformation                     : ServiceInformation
SignInName                             : HuntressCTFAdmin@4rhdc6.onmicrosoft.com
SoftDeletionTimestamp                  :
State                                  :
StreetAddress                          :
StrongAuthenticationMethods            : StrongAuthenticationMethods
StrongAuthenticationPhoneAppDetails    :
StrongAuthenticationProofupTime        :
StrongAuthenticationRequirements       :
StrongAuthenticationUserDetails        : StrongAuthenticationUserDetails
StrongPasswordRequired                 :
StsRefreshTokensValidFrom              : 2023-09-20T20:54:57Z
Title                                  :
UsageLocation                          : US
UserLandingPageIdentifierForO365Shell  :
UserPrincipalName                      : HuntressCTFAdmin@4rhdc6.onmicrosoft.com
UserThemeIdentifierForO365Shell        :
UserType                               : Member
ValidationStatus                       : Healthy
WhenCreated                            : 2023-09-16T06:40:10Z

AlternateEmailAddresses                :
AlternateMobilePhones                  :
AlternativeSecurityIds                 :
BlockCredential                        : false
City                                   :
CloudExchangeRecipientDisplayType      : 1073741824
Country                                :
Department                             :
DirSyncEnabled                         :
DirSyncProvisioningErrors              :
DisplayName                            : CompromisedAcct
Errors                                 :
Fax                                    :
FirstName                              : Hack
ImmutableId                            :
IndirectLicenseErrors                  :
IsBlackberryUser                       : false
IsLicensed                             : true
LastDirSyncTime                        :
LastName                               : Me
LastPasswordChangeTimestamp            : 2023-10-16T13:41:31Z
LicenseAssignmentDetails               : LicenseAssignmentDetails
LicenseReconciliationNeeded            : false
Licenses                               : Licenses
LiveId                                 : 10032002F6FF7CB1
MSExchRecipientTypeDetails             :
MSRtcSipDeploymentLocator              :
MSRtcSipPrimaryUserAddress             :
MobilePhone                            :
OathTokenMetadata                      :
ObjectId                               : 32ee9aa5-dc31-4b36-9d38-e514ff8da818
Office                                 :
OverallProvisioningStatus              : PendingInput
PasswordNeverExpires                   : false
PasswordResetNotRequiredDuringActivate :
PhoneNumber                            :
PortalSettings                         :
PostalCode                             :
PreferredDataLocation                  :
PreferredLanguage                      : en-US
ProxyAddresses                         : ProxyAddresses
ReleaseTrack                           :
ServiceInformation                     : ServiceInformation
SignInName                             : HackMe@4rhdc6.onmicrosoft.com
SoftDeletionTimestamp                  :
State                                  :
StreetAddress                          :
StrongAuthenticationMethods            :
StrongAuthenticationPhoneAppDetails    :
StrongAuthenticationProofupTime        :
StrongAuthenticationRequirements       :
StrongAuthenticationUserDetails        :
StrongPasswordRequired                 : true
StsRefreshTokensValidFrom              : 2023-10-16T13:41:31Z
Title                                  :
UsageLocation                          : US
UserLandingPageIdentifierForO365Shell  :
UserPrincipalName                      : HackMe@4rhdc6.onmicrosoft.com
UserThemeIdentifierForO365Shell        :
UserType                               : Member
ValidationStatus                       : Healthy
WhenCreated                            : 2023-09-20T21:18:33Z

AlternateEmailAddresses                :
AlternateMobilePhones                  :
AlternativeSecurityIds                 :
BlockCredential                        : false
City                                   : Louisville
CloudExchangeRecipientDisplayType      : 1073741824
Country                                : United States
Department                             : Engineering
DirSyncEnabled                         :
DirSyncProvisioningErrors              :
DisplayName                            : Johanna Lorenz
Errors                                 :
Fax                                    :
FirstName                              : Johanna
ImmutableId                            :
IndirectLicenseErrors                  :
IsBlackberryUser                       : false
IsLicensed                             : true
LastDirSyncTime                        :
LastName                               : Lorenz
LastPasswordChangeTimestamp            : 2023-09-20T20:55:00Z
LicenseAssignmentDetails               : LicenseAssignmentDetails
LicenseReconciliationNeeded            : false
Licenses                               : Licenses
LiveId                                 : 10032002F3B325E5
MSExchRecipientTypeDetails             :
MSRtcSipDeploymentLocator              :
MSRtcSipPrimaryUserAddress             :
MobilePhone                            :
OathTokenMetadata                      :
ObjectId                               : 38e85aa3-f8c4-417f-b59b-8163f332640d
Office                                 : 23/2102
OverallProvisioningStatus              : PendingInput
PasswordNeverExpires                   :
PasswordResetNotRequiredDuringActivate :
PhoneNumber                            : +1 502 555 0102
PortalSettings                         :
PostalCode                             : 40223
PreferredDataLocation                  :
PreferredLanguage                      : en-US
ProxyAddresses                         : ProxyAddresses
ReleaseTrack                           :
ServiceInformation                     : ServiceInformation
SignInName                             : JohannaL@4rhdc6.onmicrosoft.com
SoftDeletionTimestamp                  :
State                                  : KY
StreetAddress                          : 9900 Corporate Campus Dr., Suite 3000
StrongAuthenticationMethods            :
StrongAuthenticationPhoneAppDetails    :
StrongAuthenticationProofupTime        :
StrongAuthenticationRequirements       :
StrongAuthenticationUserDetails        :
StrongPasswordRequired                 :
StsRefreshTokensValidFrom              : 2023-09-20T20:55:00Z
Title                                  : Senior Engineer
UsageLocation                          : US
UserLandingPageIdentifierForO365Shell  :
UserPrincipalName                      : JohannaL@4rhdc6.onmicrosoft.com
UserThemeIdentifierForO365Shell        :
UserType                               : Member
ValidationStatus                       : Healthy
WhenCreated                            : 2023-09-16T10:24:52Z

AlternateEmailAddresses                :
AlternateMobilePhones                  :
AlternativeSecurityIds                 :
BlockCredential                        : false
City                                   : Tulsa
CloudExchangeRecipientDisplayType      : 1073741824
Country                                : United States
Department                             : Retail
DirSyncEnabled                         :
DirSyncProvisioningErrors              :
DisplayName                            : Lynne Robbins
Errors                                 :
Fax                                    :
FirstName                              : Lynne
ImmutableId                            :
IndirectLicenseErrors                  :
IsBlackberryUser                       : false
IsLicensed                             : true
LastDirSyncTime                        :
LastName                               : Robbins
LastPasswordChangeTimestamp            : 2023-09-20T20:55:00Z
LicenseAssignmentDetails               : LicenseAssignmentDetails
LicenseReconciliationNeeded            : false
Licenses                               : Licenses
LiveId                                 : 10032002F3B32605
MSExchRecipientTypeDetails             :
MSRtcSipDeploymentLocator              :
MSRtcSipPrimaryUserAddress             :
MobilePhone                            :
OathTokenMetadata                      :
ObjectId                               : 578075eb-5400-4fe7-a225-cd8e0f3242f8
Office                                 : 20/1104
OverallProvisioningStatus              : PendingInput
PasswordNeverExpires                   :
PasswordResetNotRequiredDuringActivate :
PhoneNumber                            : +1 918 555 0104
PortalSettings                         :
PostalCode                             : 74133
PreferredDataLocation                  :
PreferredLanguage                      : en-US
ProxyAddresses                         : ProxyAddresses
ReleaseTrack                           :
ServiceInformation                     : ServiceInformation
SignInName                             : LynneR@4rhdc6.onmicrosoft.com
SoftDeletionTimestamp                  :
State                                  : OK
StreetAddress                          : 7633 E. 63rd Place, Suite 300
StrongAuthenticationMethods            :
StrongAuthenticationPhoneAppDetails    :
StrongAuthenticationProofupTime        :
StrongAuthenticationRequirements       :
StrongAuthenticationUserDetails        :
StrongPasswordRequired                 :
StsRefreshTokensValidFrom              : 2023-09-20T20:55:00Z
Title                                  : Planner
UsageLocation                          : US
UserLandingPageIdentifierForO365Shell  :
UserPrincipalName                      : LynneR@4rhdc6.onmicrosoft.com
UserThemeIdentifierForO365Shell        :
UserType                               : Member
ValidationStatus                       : Healthy
WhenCreated                            : 2023-09-16T10:24:57Z

AlternateEmailAddresses                :
AlternateMobilePhones                  :
AlternativeSecurityIds                 :
BlockCredential                        : false
City                                   : Fort Lauderdale
CloudExchangeRecipientDisplayType      : 1073741824
Country                                : United States
Department                             : R&D
DirSyncEnabled                         :
DirSyncProvisioningErrors              :
DisplayName                            : Henrietta Mueller
Errors                                 :
Fax                                    :
FirstName                              : Henrietta
ImmutableId                            :
IndirectLicenseErrors                  :
IsBlackberryUser                       : false
IsLicensed                             : true
LastDirSyncTime                        :
LastName                               : Mueller
LastPasswordChangeTimestamp            : 2023-09-20T20:54:59Z
LicenseAssignmentDetails               : LicenseAssignmentDetails
LicenseReconciliationNeeded            : false
Licenses                               : Licenses
LiveId                                 : 10032002F3B26EE6
MSExchRecipientTypeDetails             :
MSRtcSipDeploymentLocator              :
MSRtcSipPrimaryUserAddress             :
MobilePhone                            :
OathTokenMetadata                      :
ObjectId                               : 6b5d422b-3317-4193-9f38-37b3c700789f
Office                                 : 18/1106
OverallProvisioningStatus              : PendingInput
PasswordNeverExpires                   :
PasswordResetNotRequiredDuringActivate :
PhoneNumber                            : +1 954 555 0118
PortalSettings                         :
PostalCode                             : 33309
PreferredDataLocation                  :
PreferredLanguage                      : en-US
ProxyAddresses                         : ProxyAddresses
ReleaseTrack                           :
ServiceInformation                     : ServiceInformation
SignInName                             : HenriettaM@4rhdc6.onmicrosoft.com
SoftDeletionTimestamp                  :
State                                  : FL
StreetAddress                          : 6750 North Andrews Ave., Suite 400
StrongAuthenticationMethods            :
StrongAuthenticationPhoneAppDetails    :
StrongAuthenticationProofupTime        :
StrongAuthenticationRequirements       :
StrongAuthenticationUserDetails        :
StrongPasswordRequired                 :
StsRefreshTokensValidFrom              : 2023-09-20T20:54:59Z
Title                                  : Developer
UsageLocation                          : US
UserLandingPageIdentifierForO365Shell  :
UserPrincipalName                      : HenriettaM@4rhdc6.onmicrosoft.com
UserThemeIdentifierForO365Shell        :
UserType                               : Member
ValidationStatus                       : Healthy
WhenCreated                            : 2023-09-16T10:24:49Z

AlternateEmailAddresses                :
AlternateMobilePhones                  :
AlternativeSecurityIds                 :
BlockCredential                        : false
City                                   : Charlotte
CloudExchangeRecipientDisplayType      : 1073741824
Country                                : United States
Department                             : Legal
DirSyncEnabled                         :
DirSyncProvisioningErrors              :
DisplayName                            : Joni Sherman
Errors                                 :
Fax                                    :
FirstName                              : Joni
ImmutableId                            :
IndirectLicenseErrors                  :
IsBlackberryUser                       : false
IsLicensed                             : true
LastDirSyncTime                        :
LastName                               : Sherman
LastPasswordChangeTimestamp            : 2023-09-20T20:55:00Z
LicenseAssignmentDetails               : LicenseAssignmentDetails
LicenseReconciliationNeeded            : false
Licenses                               : Licenses
LiveId                                 : 10032002F3B325F5
MSExchRecipientTypeDetails             :
MSRtcSipDeploymentLocator              :
MSRtcSipPrimaryUserAddress             :
MobilePhone                            :
OathTokenMetadata                      :
ObjectId                               : 718bb614-ccf0-48f8-84a2-8df4f09efa14
Office                                 : 20/1109
OverallProvisioningStatus              : PendingInput
PasswordNeverExpires                   :
PasswordResetNotRequiredDuringActivate :
PhoneNumber                            : +1 980 555 0101
PortalSettings                         :
PostalCode                             : 28273
PreferredDataLocation                  :
PreferredLanguage                      : en-US
ProxyAddresses                         : ProxyAddresses
ReleaseTrack                           :
ServiceInformation                     : ServiceInformation
SignInName                             : JoniS@4rhdc6.onmicrosoft.com
SoftDeletionTimestamp                  :
State                                  : NC
StreetAddress                          : 8055 Microsoft Way
StrongAuthenticationMethods            :
StrongAuthenticationPhoneAppDetails    :
StrongAuthenticationProofupTime        :
StrongAuthenticationRequirements       :
StrongAuthenticationUserDetails        :
StrongPasswordRequired                 :
StsRefreshTokensValidFrom              : 2023-09-20T20:55:00Z
Title                                  : Paralegal
UsageLocation                          : US
UserLandingPageIdentifierForO365Shell  :
UserPrincipalName                      : JoniS@4rhdc6.onmicrosoft.com
UserThemeIdentifierForO365Shell        :
UserType                               : Member
ValidationStatus                       : Healthy
WhenCreated                            : 2023-09-16T10:24:55Z

AlternateEmailAddresses                :
AlternateMobilePhones                  :
AlternativeSecurityIds                 :
BlockCredential                        : false
City                                   : Bellevue
CloudExchangeRecipientDisplayType      : 1073741824
Country                                : United States
Department                             : Retail
DirSyncEnabled                         :
DirSyncProvisioningErrors              :
DisplayName                            : Adele Vance
Errors                                 :
Fax                                    :
FirstName                              : Adele
ImmutableId                            :
IndirectLicenseErrors                  :
IsBlackberryUser                       : false
IsLicensed                             : true
LastDirSyncTime                        :
LastName                               : Vance
LastPasswordChangeTimestamp            : 2023-09-20T20:54:58Z
LicenseAssignmentDetails               : LicenseAssignmentDetails
LicenseReconciliationNeeded            : false
Licenses                               : Licenses
LiveId                                 : 10032002F3B32559
MSExchRecipientTypeDetails             :
MSRtcSipDeploymentLocator              :
MSRtcSipPrimaryUserAddress             :
MobilePhone                            :
OathTokenMetadata                      :
ObjectId                               : a2f01482-575c-46ae-802a-267392b0cd8f
Office                                 : 18/2111
OverallProvisioningStatus              : PendingInput
PasswordNeverExpires                   :
PasswordResetNotRequiredDuringActivate :
PhoneNumber                            : +1 425 555 0109
PortalSettings                         :
PostalCode                             : 98004
PreferredDataLocation                  :
PreferredLanguage                      : en-US
ProxyAddresses                         : ProxyAddresses
ReleaseTrack                           :
ServiceInformation                     : ServiceInformation
SignInName                             : AdeleV@4rhdc6.onmicrosoft.com
SoftDeletionTimestamp                  :
State                                  : WA
StreetAddress                          : 205 108th Ave. NE, Suite 400
StrongAuthenticationMethods            :
StrongAuthenticationPhoneAppDetails    :
StrongAuthenticationProofupTime        :
StrongAuthenticationRequirements       :
StrongAuthenticationUserDetails        :
StrongPasswordRequired                 :
StsRefreshTokensValidFrom              : 2023-09-20T20:54:58Z
Title                                  : Retail Manager
UsageLocation                          : US
UserLandingPageIdentifierForO365Shell  :
UserPrincipalName                      : AdeleV@4rhdc6.onmicrosoft.com
UserThemeIdentifierForO365Shell        :
UserType                               : Member
ValidationStatus                       : Healthy
WhenCreated                            : 2023-09-16T10:24:41Z

AlternateEmailAddresses                :
AlternateMobilePhones                  :
AlternativeSecurityIds                 :
BlockCredential                        : false
City                                   : Birmingham
CloudExchangeRecipientDisplayType      : 1073741824
Country                                : United States
Department                             : HR
DirSyncEnabled                         :
DirSyncProvisioningErrors              :
DisplayName                            : Diego Siciliani
Errors                                 :
Fax                                    :
FirstName                              : Diego
ImmutableId                            :
IndirectLicenseErrors                  :
IsBlackberryUser                       : false
IsLicensed                             : true
LastDirSyncTime                        :
LastName                               : Siciliani
LastPasswordChangeTimestamp            : 2023-09-20T20:54:59Z
LicenseAssignmentDetails               : LicenseAssignmentDetails
LicenseReconciliationNeeded            : false
Licenses                               : Licenses
LiveId                                 : 10032002F3B26EAA
MSExchRecipientTypeDetails             :
MSRtcSipDeploymentLocator              :
MSRtcSipPrimaryUserAddress             :
MobilePhone                            :
OathTokenMetadata                      :
ObjectId                               : a3527d86-a02c-4cc4-af15-eb89a1825013
Office                                 : 14/1108
OverallProvisioningStatus              : PendingInput
PasswordNeverExpires                   :
PasswordResetNotRequiredDuringActivate :
PhoneNumber                            : +1 205 555 0108
PortalSettings                         :
PostalCode                             : 35243
PreferredDataLocation                  :
PreferredLanguage                      : en-US
ProxyAddresses                         : ProxyAddresses
ReleaseTrack                           :
ServiceInformation                     : ServiceInformation
SignInName                             : DiegoS@4rhdc6.onmicrosoft.com
SoftDeletionTimestamp                  :
State                                  : AL
StreetAddress                          : 3535 Gradview Parkway Suite 335
StrongAuthenticationMethods            :
StrongAuthenticationPhoneAppDetails    :
StrongAuthenticationProofupTime        :
StrongAuthenticationRequirements       :
StrongAuthenticationUserDetails        :
StrongPasswordRequired                 :
StsRefreshTokensValidFrom              : 2023-09-20T20:54:59Z
Title                                  : HR Manager
UsageLocation                          : US
UserLandingPageIdentifierForO365Shell  :
UserPrincipalName                      : DiegoS@4rhdc6.onmicrosoft.com
UserThemeIdentifierForO365Shell        :
UserType                               : Member
ValidationStatus                       : Healthy
WhenCreated                            : 2023-09-16T10:24:45Z

AlternateEmailAddresses                :
AlternateMobilePhones                  :
AlternativeSecurityIds                 :
BlockCredential                        : false
City                                   : Tulsa
CloudExchangeRecipientDisplayType      : 1073741824
Country                                : United States
Department                             : Engineering
DirSyncEnabled                         :
DirSyncProvisioningErrors              :
DisplayName                            : Lidia Holloway
Errors                                 :
Fax                                    :
FirstName                              : Lidia
ImmutableId                            :
IndirectLicenseErrors                  :
IsBlackberryUser                       : false
IsLicensed                             : true
LastDirSyncTime                        :
LastName                               : Holloway
LastPasswordChangeTimestamp            : 2023-09-20T20:55:00Z
LicenseAssignmentDetails               : LicenseAssignmentDetails
LicenseReconciliationNeeded            : false
Licenses                               : Licenses
LiveId                                 : 10032002F3B325FB
MSExchRecipientTypeDetails             :
MSRtcSipDeploymentLocator              :
MSRtcSipPrimaryUserAddress             :
MobilePhone                            :
OathTokenMetadata                      :
ObjectId                               : ab658cc5-fe15-4a7e-8a87-8dda42818a27
Office                                 : 20/2107
OverallProvisioningStatus              : PendingInput
PasswordNeverExpires                   :
PasswordResetNotRequiredDuringActivate :
PhoneNumber                            : +1 918 555 0107
PortalSettings                         :
PostalCode                             : 74133
PreferredDataLocation                  :
PreferredLanguage                      : en-US
ProxyAddresses                         : ProxyAddresses
ReleaseTrack                           :
ServiceInformation                     : ServiceInformation
SignInName                             : LidiaH@4rhdc6.onmicrosoft.com
SoftDeletionTimestamp                  :
State                                  : OK
StreetAddress                          : 7633 E. 63rd Place, Suite 300
StrongAuthenticationMethods            :
StrongAuthenticationPhoneAppDetails    :
StrongAuthenticationProofupTime        :
StrongAuthenticationRequirements       :
StrongAuthenticationUserDetails        :
StrongPasswordRequired                 :
StsRefreshTokensValidFrom              : 2023-09-20T20:55:00Z
Title                                  : Product Manager
UsageLocation                          : US
UserLandingPageIdentifierForO365Shell  :
UserPrincipalName                      : LidiaH@4rhdc6.onmicrosoft.com
UserThemeIdentifierForO365Shell        :
UserType                               : Member
ValidationStatus                       : Healthy
WhenCreated                            : 2023-09-16T10:24:56Z

AlternateEmailAddresses                :
AlternateMobilePhones                  :
AlternativeSecurityIds                 :
BlockCredential                        : false
City                                   : Seattle
CloudExchangeRecipientDisplayType      : 1073741824
Country                                : United States
Department                             : Operations
DirSyncEnabled                         :
DirSyncProvisioningErrors              :
DisplayName                            : Nestor Wilke
Errors                                 :
Fax                                    :
FirstName                              : Nestor
ImmutableId                            :
IndirectLicenseErrors                  :
IsBlackberryUser                       : false
IsLicensed                             : true
LastDirSyncTime                        :
LastName                               : Wilke
LastPasswordChangeTimestamp            : 2023-09-20T20:54:58Z
LicenseAssignmentDetails               : LicenseAssignmentDetails
LicenseReconciliationNeeded            : false
Licenses                               : Licenses
LiveId                                 : 10032002F3B3254A
MSExchRecipientTypeDetails             :
MSRtcSipDeploymentLocator              :
MSRtcSipPrimaryUserAddress             :
MobilePhone                            :
OathTokenMetadata                      :
ObjectId                               : c168db1f-588b-4746-aa22-44396fe83c30
Office                                 : 36/2121
OverallProvisioningStatus              : PendingInput
PasswordNeverExpires                   :
PasswordResetNotRequiredDuringActivate :
PhoneNumber                            : +1 206 555 0105
PortalSettings                         :
PostalCode                             : 98109
PreferredDataLocation                  :
PreferredLanguage                      : en-US
ProxyAddresses                         : ProxyAddresses
ReleaseTrack                           :
ServiceInformation                     : ServiceInformation
SignInName                             : NestorW@4rhdc6.onmicrosoft.com
SoftDeletionTimestamp                  :
State                                  : WA
StreetAddress                          : 320 Westlake Ave N. Thomas St.
StrongAuthenticationMethods            :
StrongAuthenticationPhoneAppDetails    :
StrongAuthenticationProofupTime        :
StrongAuthenticationRequirements       :
StrongAuthenticationUserDetails        :
StrongPasswordRequired                 :
StsRefreshTokensValidFrom              : 2023-09-20T20:54:58Z
Title                                  : Director
UsageLocation                          : US
UserLandingPageIdentifierForO365Shell  :
UserPrincipalName                      : NestorW@4rhdc6.onmicrosoft.com
UserThemeIdentifierForO365Shell        :
UserType                               : Member
ValidationStatus                       : Healthy
WhenCreated                            : 2023-09-16T10:24:39Z

AlternateEmailAddresses                :
AlternateMobilePhones                  :
AlternativeSecurityIds                 :
BlockCredential                        : false
City                                   : Louisville
CloudExchangeRecipientDisplayType      : 1073741824
Country                                : United States
Department                             : Executive Management
DirSyncEnabled                         :
DirSyncProvisioningErrors              :
DisplayName                            : Patti Fernandez
Errors                                 :
Fax                                    :
FirstName                              : Patti
ImmutableId                            :
IndirectLicenseErrors                  :
IsBlackberryUser                       : false
IsLicensed                             : true
LastDirSyncTime                        :
LastName                               : Fernandez
LastPasswordChangeTimestamp            : 2023-09-20T20:54:57Z
LicenseAssignmentDetails               : LicenseAssignmentDetails
LicenseReconciliationNeeded            : false
Licenses                               : Licenses
LiveId                                 : 10032002F3B32527
MSExchRecipientTypeDetails             :
MSRtcSipDeploymentLocator              :
MSRtcSipPrimaryUserAddress             :
MobilePhone                            :
OathTokenMetadata                      :
ObjectId                               : d15033b7-6556-4bcd-8ec5-0c3f7ff7e9be
Office                                 : 15/1102
OverallProvisioningStatus              : PendingInput
PasswordNeverExpires                   :
PasswordResetNotRequiredDuringActivate :
PhoneNumber                            : flag{1e674f0dd1434f2bb3fe5d645b0f9cc3}
PortalSettings                         :
PostalCode                             : 40223
PreferredDataLocation                  :
PreferredLanguage                      : en-US
ProxyAddresses                         : ProxyAddresses
ReleaseTrack                           :
ServiceInformation                     : ServiceInformation
SignInName                             : PattiF@4rhdc6.onmicrosoft.com
SoftDeletionTimestamp                  :
State                                  : KY
StreetAddress                          : 9900 Corporate Campus Dr., Suite 3000
StrongAuthenticationMethods            :
StrongAuthenticationPhoneAppDetails    :
StrongAuthenticationProofupTime        :
StrongAuthenticationRequirements       :
StrongAuthenticationUserDetails        :
StrongPasswordRequired                 :
StsRefreshTokensValidFrom              : 2023-09-20T20:54:57Z
Title                                  : President
UsageLocation                          : US
UserLandingPageIdentifierForO365Shell  :
UserPrincipalName                      : PattiF@4rhdc6.onmicrosoft.com
UserThemeIdentifierForO365Shell        :
UserType                               : Member
ValidationStatus                       : Healthy
WhenCreated                            : 2023-09-16T10:24:34Z

AlternateEmailAddresses                :
AlternateMobilePhones                  :
AlternativeSecurityIds                 :
BlockCredential                        : false
City                                   : Cairo
CloudExchangeRecipientDisplayType      : 1073741824
Country                                : Egypt
Department                             : Finance
DirSyncEnabled                         :
DirSyncProvisioningErrors              :
DisplayName                            : Pradeep Gupta
Errors                                 :
Fax                                    :
FirstName                              : Pradeep
ImmutableId                            :
IndirectLicenseErrors                  :
IsBlackberryUser                       : false
IsLicensed                             : true
LastDirSyncTime                        :
LastName                               : Gupta
LastPasswordChangeTimestamp            : 2023-09-20T20:55:01Z
LicenseAssignmentDetails               : LicenseAssignmentDetails
LicenseReconciliationNeeded            : false
Licenses                               : Licenses
LiveId                                 : 10032002F3B26F5B
MSExchRecipientTypeDetails             :
MSRtcSipDeploymentLocator              :
MSRtcSipPrimaryUserAddress             :
MobilePhone                            :
OathTokenMetadata                      :
ObjectId                               : e65bc282-d8ea-4018-a5b3-3e3f03cdec35
Office                                 : 98/2202
OverallProvisioningStatus              : PendingInput
PasswordNeverExpires                   :
PasswordResetNotRequiredDuringActivate :
PhoneNumber                            : +20 255501070
PortalSettings                         :
PostalCode                             :
PreferredDataLocation                  :
PreferredLanguage                      : en-US
ProxyAddresses                         : ProxyAddresses
ReleaseTrack                           :
ServiceInformation                     : ServiceInformation
SignInName                             : PradeepG@4rhdc6.onmicrosoft.com
SoftDeletionTimestamp                  :
State                                  :
StreetAddress                          : Smart Village, Kilo 28, Cairo/Alex Desert Road
StrongAuthenticationMethods            :
StrongAuthenticationPhoneAppDetails    :
StrongAuthenticationProofupTime        :
StrongAuthenticationRequirements       :
StrongAuthenticationUserDetails        :
StrongPasswordRequired                 :
StsRefreshTokensValidFrom              : 2023-09-20T20:55:01Z
Title                                  : Accountant
UsageLocation                          : US
UserLandingPageIdentifierForO365Shell  :
UserPrincipalName                      : PradeepG@4rhdc6.onmicrosoft.com
UserThemeIdentifierForO365Shell        :
UserType                               : Member
ValidationStatus                       : Healthy
WhenCreated                            : 2023-09-16T10:25:00Z

AlternateEmailAddresses                :
AlternateMobilePhones                  :
AlternativeSecurityIds                 :
BlockCredential                        : false
City                                   : Bloomington
CloudExchangeRecipientDisplayType      : 1073741824
Country                                : United States
Department                             : R&D
DirSyncEnabled                         :
DirSyncProvisioningErrors              :
DisplayName                            : Grady Archie
Errors                                 :
Fax                                    :
FirstName                              : Grady
ImmutableId                            :
IndirectLicenseErrors                  :
IsBlackberryUser                       : false
IsLicensed                             : true
LastDirSyncTime                        :
LastName                               : Archie
LastPasswordChangeTimestamp            : 2023-09-20T20:54:59Z
LicenseAssignmentDetails               : LicenseAssignmentDetails
LicenseReconciliationNeeded            : false
Licenses                               : Licenses
LiveId                                 : 10032002F3B26ECC
MSExchRecipientTypeDetails             :
MSRtcSipDeploymentLocator              :
MSRtcSipPrimaryUserAddress             :
MobilePhone                            :
OathTokenMetadata                      :
ObjectId                               : eec05309-74b1-4e89-a379-9e2199ba9826
Office                                 : 19/2109
OverallProvisioningStatus              : PendingInput
PasswordNeverExpires                   :
PasswordResetNotRequiredDuringActivate :
PhoneNumber                            : +1 309 555 0104
PortalSettings                         :
PostalCode                             : 61704
PreferredDataLocation                  :
PreferredLanguage                      : en-US
ProxyAddresses                         : ProxyAddresses
ReleaseTrack                           :
ServiceInformation                     : ServiceInformation
SignInName                             : GradyA@4rhdc6.onmicrosoft.com
SoftDeletionTimestamp                  :
State                                  : IL
StreetAddress                          : 2203 E. Empire St., Suite J
StrongAuthenticationMethods            :
StrongAuthenticationPhoneAppDetails    :
StrongAuthenticationProofupTime        :
StrongAuthenticationRequirements       :
StrongAuthenticationUserDetails        :
StrongPasswordRequired                 :
StsRefreshTokensValidFrom              : 2023-09-20T20:54:59Z
Title                                  : Designer
UsageLocation                          : US
UserLandingPageIdentifierForO365Shell  :
UserPrincipalName                      : GradyA@4rhdc6.onmicrosoft.com
UserThemeIdentifierForO365Shell        :
UserType                               : Member
ValidationStatus                       : Healthy
WhenCreated                            : 2023-09-16T10:24:47Z

AlternateEmailAddresses                :
AlternateMobilePhones                  :
AlternativeSecurityIds                 :
BlockCredential                        : false
City                                   : Pittsburgh
CloudExchangeRecipientDisplayType      : 1073741824
Country                                : United States
Department                             : Marketing
DirSyncEnabled                         :
DirSyncProvisioningErrors              :
DisplayName                            : Megan Bowen
Errors                                 :
Fax                                    :
FirstName                              : Megan
ImmutableId                            :
IndirectLicenseErrors                  :
IsBlackberryUser                       : false
IsLicensed                             : true
LastDirSyncTime                        :
LastName                               : Bowen
LastPasswordChangeTimestamp            : 2023-09-20T20:55:00Z
LicenseAssignmentDetails               : LicenseAssignmentDetails
LicenseReconciliationNeeded            : false
Licenses                               : Licenses
LiveId                                 : 10032002F3B32613
MSExchRecipientTypeDetails             :
MSRtcSipDeploymentLocator              :
MSRtcSipPrimaryUserAddress             :
MobilePhone                            :
OathTokenMetadata                      :
ObjectId                               : ef935576-05f9-46fd-bf19-995d14926ea1
Office                                 : 12/1110
OverallProvisioningStatus              : PendingInput
PasswordNeverExpires                   :
PasswordResetNotRequiredDuringActivate :
PhoneNumber                            : +1 412 555 0109
PortalSettings                         :
PostalCode                             : 15212
PreferredDataLocation                  :
PreferredLanguage                      : en-US
ProxyAddresses                         : ProxyAddresses
ReleaseTrack                           :
ServiceInformation                     : ServiceInformation
SignInName                             : MeganB@4rhdc6.onmicrosoft.com
SoftDeletionTimestamp                  :
State                                  : PA
StreetAddress                          : 30 Isabella St., Second Floor
StrongAuthenticationMethods            :
StrongAuthenticationPhoneAppDetails    :
StrongAuthenticationProofupTime        :
StrongAuthenticationRequirements       :
StrongAuthenticationUserDetails        :
StrongPasswordRequired                 :
StsRefreshTokensValidFrom              : 2023-09-20T20:55:00Z
Title                                  : Marketing Manager
UsageLocation                          : US
UserLandingPageIdentifierForO365Shell  :
UserPrincipalName                      : MeganB@4rhdc6.onmicrosoft.com
UserThemeIdentifierForO365Shell        :
UserType                               : Member
ValidationStatus                       : Healthy
WhenCreated                            : 2023-09-16T10:24:59Z

AlternateEmailAddresses                :
AlternateMobilePhones                  :
AlternativeSecurityIds                 :
BlockCredential                        : false
City                                   : Tulsa
CloudExchangeRecipientDisplayType      : 1073741824
Country                                : United States
Department                             : Sales
DirSyncEnabled                         :
DirSyncProvisioningErrors              :
DisplayName                            : Isaiah Langer
Errors                                 :
Fax                                    :
FirstName                              : Isaiah
ImmutableId                            :
IndirectLicenseErrors                  :
IsBlackberryUser                       : false
IsLicensed                             : true
LastDirSyncTime                        :
LastName                               : Langer
LastPasswordChangeTimestamp            : 2023-09-20T20:54:59Z
LicenseAssignmentDetails               : LicenseAssignmentDetails
LicenseReconciliationNeeded            : false
Licenses                               : Licenses
LiveId                                 : 10032002F3B26EF5
MSExchRecipientTypeDetails             :
MSRtcSipDeploymentLocator              :
MSRtcSipPrimaryUserAddress             :
MobilePhone                            :
OathTokenMetadata                      :
ObjectId                               : f1d16e98-cd61-41d8-afea-399b1a6e6323
Office                                 : 20/1101
OverallProvisioningStatus              : PendingInput
PasswordNeverExpires                   :
PasswordResetNotRequiredDuringActivate :
PhoneNumber                            : +1 918 555 0101
PortalSettings                         :
PostalCode                             : 74133
PreferredDataLocation                  :
PreferredLanguage                      : en-US
ProxyAddresses                         : ProxyAddresses
ReleaseTrack                           :
ServiceInformation                     : ServiceInformation
SignInName                             : IsaiahL@4rhdc6.onmicrosoft.com
SoftDeletionTimestamp                  :
State                                  : OK
StreetAddress                          : 7633 E. 63rd Place, Suite 300
StrongAuthenticationMethods            :
StrongAuthenticationPhoneAppDetails    :
StrongAuthenticationProofupTime        :
StrongAuthenticationRequirements       :
StrongAuthenticationUserDetails        :
StrongPasswordRequired                 :
StsRefreshTokensValidFrom              : 2023-09-20T20:54:59Z
Title                                  : Sales Rep
UsageLocation                          : US
UserLandingPageIdentifierForO365Shell  :
UserPrincipalName                      : IsaiahL@4rhdc6.onmicrosoft.com
UserThemeIdentifierForO365Shell        :
UserType                               : Member
ValidationStatus                       : Healthy
WhenCreated                            : 2023-09-16T10:24:50Z

AlternateEmailAddresses                :
AlternateMobilePhones                  :
AlternativeSecurityIds                 :
BlockCredential                        : false
City                                   : San Diego
CloudExchangeRecipientDisplayType      : 1073741824
Country                                : United States
Department                             : Sales & Marketing
DirSyncEnabled                         :
DirSyncProvisioningErrors              :
DisplayName                            : Miriam Graham
Errors                                 :
Fax                                    :
FirstName                              : Miriam
ImmutableId                            :
IndirectLicenseErrors                  :
IsBlackberryUser                       : false
IsLicensed                             : true
LastDirSyncTime                        :
LastName                               : Graham
LastPasswordChangeTimestamp            : 2023-09-20T20:54:58Z
LicenseAssignmentDetails               : LicenseAssignmentDetails
LicenseReconciliationNeeded            : false
Licenses                               : Licenses
LiveId                                 : 10032002F3B3253D
MSExchRecipientTypeDetails             :
MSRtcSipDeploymentLocator              :
MSRtcSipPrimaryUserAddress             :
MobilePhone                            :
OathTokenMetadata                      :
ObjectId                               : fee33a0e-c6cf-4a34-9ed6-6e4c7bf62521
Office                                 : 131/2103
OverallProvisioningStatus              : PendingInput
PasswordNeverExpires                   :
PasswordResetNotRequiredDuringActivate :
PhoneNumber                            : +1 858 555 0109
PortalSettings                         :
PostalCode                             : 92121
PreferredDataLocation                  :
PreferredLanguage                      : en-US
ProxyAddresses                         : ProxyAddresses
ReleaseTrack                           :
ServiceInformation                     : ServiceInformation
SignInName                             : MiriamG@4rhdc6.onmicrosoft.com
SoftDeletionTimestamp                  :
State                                  : CA
StreetAddress                          : 9255 Towne Center Dr., Suite 400
StrongAuthenticationMethods            :
StrongAuthenticationPhoneAppDetails    :
StrongAuthenticationProofupTime        :
StrongAuthenticationRequirements       :
StrongAuthenticationUserDetails        :
StrongPasswordRequired                 :
StsRefreshTokensValidFrom              : 2023-09-20T20:54:58Z
Title                                  : Director
UsageLocation                          : US
UserLandingPageIdentifierForO365Shell  :
UserPrincipalName                      : MiriamG@4rhdc6.onmicrosoft.com
UserThemeIdentifierForO365Shell        :
UserType                               : Member
ValidationStatus                       : Healthy
WhenCreated                            : 2023-09-16T10:24:37Z
```

`flag{1e674f0dd1434f2bb3fe5d645b0f9cc3}`
