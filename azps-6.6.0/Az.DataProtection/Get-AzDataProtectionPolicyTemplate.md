---
external help file: ''
Module Name: Az.DataProtection
online version: https://docs.microsoft.com/powershell/module/az.dataprotection/get-azdataprotectionpolicytemplate
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Get-AzDataProtectionPolicyTemplate.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Get-AzDataProtectionPolicyTemplate.md
ms.openlocfilehash: f9f501496814d57ad7b2c54c59b09d4174586f22
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142085612"
---
# Get-AzDataProtectionPolicyTemplate

## SYNOPSIS
Mendapatkan templat kebijakan default untuk tipe sumber data yang dipilih.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.dataprotection/get-azdataprotectionpolicytemplate) untuk informasi terbaru.

## SYNTAX

```
Get-AzDataProtectionPolicyTemplate -DatasourceType <DatasourceTypes> [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan templat kebijakan default untuk tipe sumber data yang dipilih.

## EXAMPLES

### Contoh 1: Dapatkan templat kebijakan default Disk Azure
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
Tipe Sumber Data

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Models.Api20210701.IBackupPolicy

## CATATAN

ALIAS

## RELATED LINKS

