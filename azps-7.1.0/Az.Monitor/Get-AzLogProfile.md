---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Monitor.dll-Help.xml
Module Name: Az.Monitor
ms.assetid: 019EFD94-4087-45F6-812D-FBDFE1B2E48A
online version: https://docs.microsoft.com/powershell/module/az.monitor/get-azlogprofile
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/Get-AzLogProfile.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/Get-AzLogProfile.md
ms.openlocfilehash: 4e2b769ab7ec10532e247fd8fda2507caebdd401
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136733030"
---
# Get-AzLogProfile

## SYNOPSIS
Mendapatkan profil log.

## SYNTAX

```
Get-AzLogProfile [-Name <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzLogProfile** mendapatkan profil log.

## EXAMPLES

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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
Menentukan nama profil log untuk mendapatkannya.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands. Insights. OutputClasses.PSLogProfileCollection

## CATATAN

## RELATED LINKS

[Add-AzLogProfile](./Add-AzLogProfile.md)

[Remove-AzLogProfile](./Remove-AzLogProfile.md)


