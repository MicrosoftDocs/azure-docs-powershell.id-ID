---
external help file: ''
Module Name: Az.DataProtection
online version: https://docs.microsoft.com/powershell/module/az.dataprotection/get-azdataprotectionoperation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Get-AzDataProtectionOperation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Get-AzDataProtectionOperation.md
ms.openlocfilehash: 476728b1411da1a03a6f83466f0817083708b0bd
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140058071"
---
# Get-AzDataProtectionOperation

## SYNOPSIS
Mengembalikan daftar operasi yang tersedia.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.dataprotection/get-azdataprotectionoperation) untuk informasi terkini.

## SYNTAX

```
Get-AzDataProtectionOperation [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mengembalikan daftar operasi yang tersedia.

## EXAMPLES

### Contoh 1: Mendapatkan daftar operasi yang tersedia
```powershell
PS C:\> Get-AzDataProtectionOperation

IsDataAction Name                                                                                                Origin
------------ ----                                                                                                ------
             Microsoft.DataProtection/locations/getBackupStatus/action                                           user
             Microsoft.DataProtection/backupVaults/backupInstances/write                                         user
             Microsoft.DataProtection/backupVaults/backupInstances/delete                                        user
             Microsoft.DataProtection/backupVaults/backupInstances/read                                          user
             Microsoft.DataProtection/backupVaults/backupInstances/read                                          user
             Microsoft.DataProtection/backupVaults/backupInstances/backup/action                                 user
             Microsoft.DataProtection/backupVaults/backupInstances/sync/action                                   user
             Microsoft.DataProtection/backupVaults/backupInstances/operationResults/read                         user
             Microsoft.DataProtection/backupVaults/backupInstances/stopProtection/action                         user
             Microsoft.DataProtection/backupVaults/backupInstances/suspendBackups/action                         user
             Microsoft.DataProtection/backupVaults/backupInstances/resumeProtection/action                       user
             Microsoft.DataProtection/backupVaults/backupInstances/resumeBackups/action                          user
             Microsoft.DataProtection/backupVaults/backupInstances/validateRestore/action                        user
             Microsoft.DataProtection/backupVaults/backupInstances/restore/action                                user
             Microsoft.DataProtection/backupVaults/backupPolicies/write                                          user
             Microsoft.DataProtection/backupVaults/backupPolicies/delete                                         user
             Microsoft.DataProtection/backupVaults/backupPolicies/read                                           user
             Microsoft.DataProtection/backupVaults/backupPolicies/read                                           user
             Microsoft.DataProtection/backupVaults/backupResourceGuardProxies/read                               user
             Microsoft.DataProtection/backupVaults/backupResourceGuardProxies/read                               user
             Microsoft.DataProtection/backupVaults/backupResourceGuardProxies/write                              user
             Microsoft.DataProtection/backupVaults/backupResourceGuardProxies/delete                             user
             Microsoft.DataProtection/backupVaults/backupResourceGuardProxies/unlockDelete/action                user
             Microsoft.DataProtection/backupVaults/backupInstances/recoveryPoints/read                           user
             Microsoft.DataProtection/backupVaults/backupInstances/recoveryPoints/read                           user
             Microsoft.DataProtection/backupVaults/backupInstances/findRestorableTimeRanges/action               user
             Microsoft.DataProtection/backupVaults/write                                                         user
             Microsoft.DataProtection/backupVaults/read                                                          user
             Microsoft.DataProtection/backupVaults/delete                                                        user
             Microsoft.DataProtection/backupVaults/operationResults/read                                         user
             Microsoft.DataProtection/locations/checkNameAvailability/action                                     user
             Microsoft.DataProtection/backupVaults/read                                                          user
             Microsoft.DataProtection/backupVaults/read                                                          user
             Microsoft.DataProtection/subscriptions/resourceGroups/providers/resourceGuards/write                user
             Microsoft.DataProtection/subscriptions/resourceGroups/providers/resourceGuards/read                 user
             Microsoft.DataProtection/subscriptions/resourceGroups/providers/resourceGuards/delete               user
             Microsoft.DataProtection/subscriptions/resourceGroups/providers/resourceGuards/read                 user
             Microsoft.DataProtection/subscriptions/providers/resourceGuards/read                                user
             Microsoft.DataProtection/subscriptions/resourceGroups/providers/resourceGuards/write                user
             Microsoft.DataProtection/subscriptions/resourceGroups/providers/resourceGuards/{operationName}/read user
             Microsoft.DataProtection/subscriptions/resourceGroups/providers/resourceGuards/{operationName}/read user
             Microsoft.DataProtection/subscriptions/providers/locations/checkFeatureSupport/action               user
             Microsoft.DataProtection/locations/operationStatus/read                                             user
             Microsoft.DataProtection/backupVaults/operationStatus/read                                          user
             Microsoft.DataProtection/subscriptions/resourceGroups/providers/operationStatus/read                user
             Microsoft.DataProtection/locations/operationResults/read                                            user
             Microsoft.DataProtection/backupVaults/validateForBackup/action                                      user
             Microsoft.DataProtection/backupVaults/backupJobs/read                                               user
             Microsoft.RecoveryServices/Vaults/backupJobs/read                                                   user
             Microsoft.DataProtection/register/action                                                            user
             Microsoft.DataProtection/unregister/action                                                          user
             Microsoft.DataProtection/operations/read                                                            user
```

Perintah di atas berisi daftar operasi yang tersedia.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Models.Api20210701.IClientDiscoveryValueForSingleApi

## CATATAN

ALIAS

## RELATED LINKS

