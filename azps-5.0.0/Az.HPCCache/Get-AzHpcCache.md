---
external help file: Microsoft.Azure.PowerShell.Cmdlets.HPCCache.dll-Help.xml
Module Name: Az.HPCCache
online version: https://docs.microsoft.com/en-us/powershell/module/az.hpccache/get-azhpccache
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/HPCCache/HPCCache/help/Get-AzHpcCache.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/HPCCache/HPCCache/help/Get-AzHpcCache.md
ms.openlocfilehash: 82b5bdd7e10b8119a058ab3a30f6836ff9255d01
ms.sourcegitcommit: b4a38bcb0501a9016a4998efd377aa75d3ef9ce8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2020
ms.locfileid: "132408373"
---
# Get-AzHpcCache

## SYNOPSIS
Mendapatkan singgahan.

## SINTAKS

```
Get-AzHpcCache [-ResourceGroupName <String>] [-Name <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESKRIPSI
Cmdlet **Get-AzHpcCache** mendapatkan satu singgahan, singgahan dalam grup sumber daya tertentu, atau daftar singgahan langganan yang beragam.

## CONTOH

### Contoh 1
```powershell
PS C:\> Get-AzHPCCache -ResourceGroupName rgtest -CacheName cachetest
```

### Contoh 2
```powershell
PS C:\> Get-AzHPCCache -ResourceGroupName rgtest
```

### Contoh 3
```powershell
PS C:\> Get-AzHPCCache
```

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama singgahan tertentu.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: CacheName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya di bawah yang ingin Anda list cache(s).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUT

### System.String

## OUTPUT

### Microsoft.Azure.PowerShell.Cmdlets.HPCCache.Models.PSHPCCache

## CATATAN

## LINK TERKAIT
