---
external help file: ''
Module Name: Az.ContainerInstance
online version: https://docs.microsoft.com/powershell/module/az.ContainerInstance/new-AzContainerGroupImageRegistryCredentialObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/New-AzContainerGroupImageRegistryCredentialObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/New-AzContainerGroupImageRegistryCredentialObject.md
ms.openlocfilehash: e5559e2b339fa73a2ba27b3f24ddd46bd6bad321
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/02/2021
ms.locfileid: "136157672"
---
# New-AzContainerGroupImageRegistryCredentialObject

## SYNOPSIS
Membuat objek dalam memori untuk ImageRegistryCredential

## SYNTAX

```
New-AzContainerGroupImageRegistryCredentialObject -Server <String> -Username <String>
 [-Password <SecureString>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk ImageRegistryCredential

## EXAMPLES

### Contoh 1: Siapkan kredensial registri gambar untuk membuat grup wadah
```powershell
PS C:\> New-AzContainerGroupImageRegistryCredentialObject -Server "myserver.com" -Username "username" -Password (ConvertTo-SecureString "******" -AsPlainText -Force) 


Password          Server       Username
--------          ------       --------
****** myserver.com username
```

Perintah ini menyiapkan kredensial registri gambar untuk membuat grup wadah

## PARAMETERS

### -Password
Kata sandi untuk registri privat.

```yaml
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Server
Server registri gambar Docker tanpa protokol seperti "http" dan "https".

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama pengguna
Nama pengguna untuk registri privat.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210301.ImageRegistryCredential

## CATATAN

ALIAS

## RELATED LINKS

