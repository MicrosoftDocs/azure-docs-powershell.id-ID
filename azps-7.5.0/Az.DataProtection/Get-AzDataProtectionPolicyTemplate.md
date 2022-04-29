---
external help file: ''
Module Name: Az.DataProtection
online version: https://docs.microsoft.com/powershell/module/az.dataprotection/get-azdataprotectionpolicytemplate
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Get-AzDataProtectionPolicyTemplate.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Get-AzDataProtectionPolicyTemplate.md
ms.openlocfilehash: 674370ece7bcc2055f900d38fc53d9609586eedd
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144218918"
---
# Get-AzDataProtectionPolicyTemplate

## SYNOPSIS
Mendapatkan templat kebijakan default untuk jenis sumber data yang dipilih.

## SYNTAX

```
Get-AzDataProtectionPolicyTemplate -DatasourceType <DatasourceTypes> [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan templat kebijakan default untuk jenis sumber data yang dipilih.

## EXAMPLES

### Contoh 1: Mendapatkan templat kebijakan default Azure Disk
```powershell
Get-AzDataProtectionPolicyTemplate -DatasourceType AzureDisk
```

```output
DatasourceType            ObjectType
--------------            ----------
{Microsoft.Compute/disks} BackupPolicy
```

Perintah ini mengembalikan templat kebijakan default untuk jenis sumber data tertentu.
Gunakan templat kebijakan ini untuk membuat kebijakan baru.

## PARAMETERS

### -DatasourceType
Jenis Sumber Data

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Support.DatasourceTypes
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Models.Api20210701.IBackupPolicy

## NOTES

ALIAS

## RELATED LINKS

