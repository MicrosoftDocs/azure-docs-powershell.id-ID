---
external help file: ''
Module Name: Az.DataProtection
online version: https://docs.microsoft.com/powershell/module/az.dataprotection/get-azdataprotectionpolicytemplate
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Get-AzDataProtectionPolicyTemplate.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Get-AzDataProtectionPolicyTemplate.md
ms.openlocfilehash: 3d032e3e19b05248efc6b3af9a94596780034087
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138258827"
---
# Get-AzDataProtectionPolicyTemplate

## SYNOPSIS
Mendapatkan templat kebijakan default untuk tipe sumber data yang dipilih.

## SYNTAX

```
Get-AzDataProtectionPolicyTemplate -DatasourceType <DatasourceTypes> [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan templat kebijakan default untuk tipe sumber data yang dipilih.

## EXAMPLES

### Contoh 1: Dapatkan templat kebijakan default Azure Disk
```powershell
PS C:\> Get-AzDataProtectionPolicyTemplate -DatasourceType AzureDisk

DatasourceType            ObjectType
--------------            ----------
{Microsoft.Compute/disks} BackupPolicy
```

Perintah ini mengembalikan templat kebijakan default untuk tipe sumber data tertentu.
Gunakan templat kebijakan ini untuk membuat kebijakan baru.

## PARAMETERS

### -DatasourceType
Tipe SumberData

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Models.Api20210701.IBackupPolicy

## CATATAN

ALIAS

## RELATED LINKS

