---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ResourceManager.dll-Help.xml
Module Name: Az.Resources
ms.assetid: DC870E11-2129-4906-8357-D9BC1CF2E08E
online version: https://docs.microsoft.com/powershell/module/az.resources/get-azlocation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzLocation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzLocation.md
ms.openlocfilehash: d426037b5af2153e802206dd81be4e2b5722baaf
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140305825"
---
# Get-AzLocation

## SYNOPSIS
Mendapatkan semua lokasi dan penyedia sumber daya yang didukung untuk setiap lokasi.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.resources/get-azlocation) untuk informasi terkini.

## SYNTAX

```
Get-AzLocation [-ApiVersion <String>] [-Pre] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzLocation** mendapatkan semua lokasi dan penyedia sumber daya yang didukung untuk setiap lokasi.

## EXAMPLES

### Contoh 1: Dapatkan semua lokasi dan penyedia sumber daya yang didukung
```
PS C:\>Get-AzLocation
```

Perintah ini mendapatkan semua lokasi dan penyedia sumber daya yang didukung untuk setiap lokasi.

### Contoh 2: Dapatkan semua lokasi penyedia sumber daya pendukung Microsoft.AppConfiguration
```
PS C:\>Get-AzLocation | Where-Object {$_.Providers -contains "Microsoft.AppConfiguration"}

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
Anda bisa menentukan versi yang berbeda dari versi default.

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

### -Pra
Cmdlet ini mempertimbangkan versi API prari release ketika cmdlet menentukan versi mana yang akan digunakan secara otomatis.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.SdkModels.PSResourceProviderLocation

## CATATAN

## RELATED LINKS
