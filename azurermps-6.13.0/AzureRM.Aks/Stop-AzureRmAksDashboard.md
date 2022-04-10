---
external help file: Microsoft.Azure.Commands.Aks.dll-Help.xml
Module Name: AzureRM.Aks
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.aks/stop-azurermaksdashboard
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Aks/Commands.Aks/help/Stop-AzureRmAksDashboard.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Aks/Commands.Aks/help/Stop-AzureRmAksDashboard.md
ms.openlocfilehash: e8e45cc0b7da0c10994a01bcf9d79ec2648b0f1b1aa9be9fdff6d1627e3ce74f
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "140865230"
---
# Stop-AzureRmAksDashboard

## SYNOPSIS
Hentikan kubectl LINUX yang dibuat di Start-AzureRmK nodesDashboard.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Stop-AzureRmAksDashboard [-PassThru] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Hentikan kubectl LINUX yang dibuat di Start-AzureRmK nodesDashboard.

## EXAMPLES

### Contoh 1
```
PS C:\> Stop-AzureRmKubernetesDashboard
```

Menghentikan penyiapan azure AZURE yang sudah ada dengan menjalankan Start-AzureRmK nodesDashboard.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Mengembalikan true jika linux LINUX ditutup.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### System.Boolean

## CATATAN

## RELATED LINKS
