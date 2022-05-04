---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ResourceManager.dll-Help.xml
Module Name: Az.Resources
ms.assetid: DC870E11-2129-4906-8357-D9BC1CF2E08E
online version: https://docs.microsoft.com/powershell/module/az.resources/get-azlocation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzLocation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzLocation.md
ms.openlocfilehash: b104b2da54fd473fff7d94d5a4a732c95e6c9363
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144713830"
---
# Get-AzLocation

## SYNOPSIS
Mendapatkan semua lokasi dan penyedia sumber daya yang didukung untuk setiap lokasi.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.resources/get-azlocation) untuk informasi terbaru.

## SYNTAX

```
Get-AzLocation [-ApiVersion <String>] [-Pre] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzLocation** mendapatkan semua lokasi dan penyedia sumber daya yang didukung untuk setiap lokasi.

## EXAMPLES

### Contoh 1: Mendapatkan semua lokasi dan penyedia sumber daya yang didukung
```powershell
Get-AzLocation
```

Perintah ini mendapatkan semua lokasi dan penyedia sumber daya yang didukung untuk setiap lokasi.

### Contoh 2: Mendapatkan semua lokasi yang mendukung penyedia sumber daya Microsoft.AppConfiguration
```powershell
Get-AzLocation | Where-Object {$_.Providers -contains "Microsoft.AppConfiguration"}
```

```output
Location    : eastasia
DisplayName : East Asia
Providers   : {Microsoft.Devices, Microsoft.Cache, Microsoft.AppConfiguration, microsoft.insights…}

Location    : southeastasia
DisplayName : Southeast Asia
Providers   : {Microsoft.Devices, Microsoft.Cache, Microsoft.AppConfiguration, microsoft.insights…}

Location    : centralus
DisplayName : Central US
Providers   : {Microsoft.Devices, Microsoft.Cache, Microsoft.AppConfiguration, microsoft.insights…}
...
```

Contoh ini mendapatkan semua lokasi yang mendukung penyedia sumber daya "Microsoft.AppConfiguration".

## PARAMETERS

### -ApiVersion
Menentukan versi API yang didukung oleh Penyedia sumber daya.
Anda dapat menentukan versi yang berbeda dari versi default.

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

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

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

### -Pra
Menunjukkan bahwa cmdlet ini mempertimbangkan versi API pra-rilis ketika secara otomatis menentukan versi mana yang akan digunakan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.SdkModels.PSResourceProviderLocation

## NOTES

## RELATED LINKS
