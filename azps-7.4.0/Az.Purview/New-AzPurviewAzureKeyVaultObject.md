---
external help file: Az.Purview-help.xml
Module Name: Az.Purview
online version: https://docs.microsoft.com/powershell/module/az.Purview/new-AzPurviewAzureKeyVaultObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewAzureKeyVaultObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewAzureKeyVaultObject.md
ms.openlocfilehash: a5ef1e4895b038f4f51cd345e1bb1e30f545b60f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141994770"
---
# New-AzPurviewAzureKeyVaultObject

## SYNOPSIS
Membuat objek dalam memori untuk AzureKeyVault.

## SYNTAX

```
New-AzPurviewAzureKeyVaultObject [-BaseUrl <String>] [-Description <String>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk AzureKeyVault.

## EXAMPLES

### Contoh 1: Membuat objek koneksi kubah kunci
```powershell
PS C:\> New-AzPurviewAzureKeyVaultObject -BaseUrl 'https://datascankv.vault.azure.net/' -Description 'This is a key vault'

BaseUrl           : https://datascankv.vault.azure.net/
Description       : This is a key vault
Id                :
Name              :
```

Membuat objek koneksi kubah kunci.

## PARAMETERS

### -BaseUrl

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Deskripsi

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Models.Api20211001Preview.AzureKeyVault

## CATATAN

ALIAS

## RELATED LINKS
