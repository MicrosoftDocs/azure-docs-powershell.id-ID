---
external help file: Az.Purview-help.xml
Module Name: Az.Purview
online version: https://docs.microsoft.com/powershell/module/az.Purview/new-AzPurviewAzureKeyVaultObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewAzureKeyVaultObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewAzureKeyVaultObject.md
ms.openlocfilehash: 2e82ac3cdb274647ad0711ed1fd6c199d816b72d
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145653736"
---
# New-AzPurviewAzureKeyVaultObject

## SYNOPSIS
Buat objek dalam memori untuk AzureKeyVault.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.purview/new-azpurviewazurekeyvaultobject) untuk informasi terbaru.

## SYNTAX

```
New-AzPurviewAzureKeyVaultObject [-BaseUrl <String>] [-Description <String>] [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk AzureKeyVault.

## EXAMPLES

### Contoh 1: Membuat objek koneksi brankas kunci
```powershell
PS C:\> New-AzPurviewAzureKeyVaultObject -BaseUrl 'https://datascankv.vault.azure.net/' -Description 'This is a key vault'

BaseUrl           : https://datascankv.vault.azure.net/
Description       : This is a key vault
Id                :
Name              :
```

Buat objek koneksi brankas kunci.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Models.Api20211001Preview.AzureKeyVault

## NOTES

ALIAS

## RELATED LINKS
