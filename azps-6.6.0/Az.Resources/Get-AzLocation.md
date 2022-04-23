---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ResourceManager.dll-Help.xml
Module Name: Az.Resources
ms.assetid: DC870E11-2129-4906-8357-D9BC1CF2E08E
online version: https://docs.microsoft.com/powershell/module/az.resources/get-azlocation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzLocation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzLocation.md
ms.openlocfilehash: d426037b5af2153e802206dd81be4e2b5722baaf
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143086049"
---
# Get-AzLocation

## SYNOPSIS
Mendapatkan semua lokasi dan penyedia sumber daya yang didukung untuk setiap lokasi.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.resources/get-azlocation) untuk informasi terbaru.

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

### Contoh 2: Dapatkan semua lokasi yang mendukung penyedia sumber daya Microsoft.AppConfiguration
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
Menunjukkan bahwa cmdlet ini mempertimbangkan versi API prarilis ketika secara otomatis menentukan versi mana yang akan digunakan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.ResourceManager.Cmdlets.SdkModels.PSResourceProviderLocation

## NOTES

## RELATED LINKS
