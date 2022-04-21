---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Cdn.dll-Help.xml
Module Name: Az.Cdn
ms.assetid: 1A84AF77-1AEF-4FD0-9FAA-D195B361FCEB
online version: https://docs.microsoft.com/powershell/module/az.cdn/set-azcdnendpoint
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/Set-AzCdnEndpoint.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/Set-AzCdnEndpoint.md
ms.openlocfilehash: 8da9bbb458ef82eee386a0f70c064e236034bd34
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142810594"
---
# Set-AzCdnEndpoint

## SYNOPSIS
Memperbarui titik akhir CDN.

## SYNTAX

```
Set-AzCdnEndpoint -CdnEndpoint <PSEndpoint> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
**Cmdlet Set-AzCdnEndpoint** memperbarui titik akhir Azure Content Delivery Network (CDN).

## EXAMPLES

### Contoh 1: Mengatur protokol yang diperbolehkan ke HTTPS saja
```powershell
$endpointObject = Get-AzCdnEndpoint -ResourceGroupName myresourcegroup -ProfileName mycdnprofile -EndpointName myendpoint
$endpointObject.IsHttpAllowed = $false
Set-AzCdnEndpoint -CdnEndpoint $endpointObject
```

```Output
HostName                   : myendpoint.azureedge.net
OriginHostHeader           :
OriginPath                 :
ContentTypesToCompress     : {}
IsCompressionEnabled       : False
IsHttpAllowed              : False
IsHttpsAllowed             : True
QueryStringCachingBehavior : IgnoreQueryString
Origins                    : {mystorage}
OptimizationType           :
ProbePath                  :
GeoFilters                 : {}
DeliveryPolicy             :
ResourceState              : Running
DefaultOriginGroup         :
ResourceGroupName          : myresourcegroup
ProfileName                : mycdnprofile
Location                   : WestUs
Tags                       : {}
Id                         : /subscriptions/11111111-1111-1111-1111-111111111111/resourcegroups/myresourcegroup/providers/Micr
                             osoft.Cdn/profiles/mycdnprofile/endpoints/myendpoint
Name                       : myendpoint
Type                       : Microsoft.Cdn/profiles/endpoints
ProvisioningState          : Succeeded
```

Properti yang diperbolehkan untuk diubah adalah: `ContentTypesToCompress`, , `IsCompressionEnabled`, `IsHttpsAllowed``IsHttpAllowed`, `QueryStringCachingBehavior`, `GeoFilters` dan `Tags`.

## PARAMETERS

### -CdnEndpoint
Menentukan titik akhir yang diperbarui cmdlet ini.

```yaml
Type: Microsoft.Azure.Commands.Cdn.Models.Endpoint.PSEndpoint
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Cdn.Models.Endpoint.PSEndpoint

## OUTPUTS

### Microsoft.Azure.Commands.Cdn.Models.Endpoint.PSEndpoint

## NOTES

## RELATED LINKS

[Get-AzCdnEndpoint](./Get-AzCdnEndpoint.md)

[New-AzCdnEndpoint](./New-AzCdnEndpoint.md)

[Remove-AzCdnEndpoint](./Remove-AzCdnEndpoint.md)

[Start-AzCdnEndpoint](./Start-AzCdnEndpoint.md)

[Stop-AzCdnEndpoint](./Stop-AzCdnEndpoint.md)


