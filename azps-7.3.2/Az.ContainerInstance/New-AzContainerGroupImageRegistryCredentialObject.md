---
external help file: ''
Module Name: Az.ContainerInstance
online version: https://docs.microsoft.com/powershell/module/az.ContainerInstance/new-AzContainerGroupImageRegistryCredentialObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/New-AzContainerGroupImageRegistryCredentialObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/New-AzContainerGroupImageRegistryCredentialObject.md
ms.openlocfilehash: 54af84415bdf676c7547004162465732d793c407
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140382053"
---
# New-AzContainerGroupImageRegistryCredentialObject

## SYNOPSIS
Membuat objek dalam memori untuk ImageRegistryCredential

## SYNTAX

```
New-AzContainerGroupImageRegistryCredentialObject -Server <String> [-AcrIdentity <String>]
 [-Password <SecureString>] [-Username <String>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk ImageRegistryCredential

## EXAMPLES

### Contoh 1: Siapkan kredensial registri gambar untuk membuat grup wadah
```powershell
New-AzContainerGroupImageRegistryCredentialObject -Server "myserver.com" -Username "username" -Password (ConvertTo-SecureString "******" -AsPlainText -Force) 
```

```output
Password          Server       Username
--------          ------       --------
****** myserver.com username
```

Perintah ini menyiapkan kredensial registri gambar untuk membuat grup wadah

## PARAMETERS

### -AcrIdentity
Identitas dengan akses ke ACR.

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

### Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210901.ImageRegistryCredential

## CATATAN

ALIAS

## RELATED LINKS

