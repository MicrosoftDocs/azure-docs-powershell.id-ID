---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Cdn.dll-Help.xml
Module Name: Az.Cdn
ms.assetid: 53246003-D1E9-4863-94E9-8E0BF1272134
online version: https://docs.microsoft.com/powershell/module/az.cdn/get-azcdncustomdomain
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/Get-AzCdnCustomDomain.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/Get-AzCdnCustomDomain.md
ms.openlocfilehash: 21565d6669e247ce60a310e98cd7d9a8b4106a35
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142259755"
---
# Get-AzCdnCustomDomain

## SYNOPSIS
Mendapatkan domain kustom CDN.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.cdn/get-azcdncustomdomain) untuk informasi terbaru.

## SYNTAX

### ByFieldsParameterSet (Default)
```
Get-AzCdnCustomDomain [-CustomDomainName <String>] -EndpointName <String> -ProfileName <String>
 -ResourceGroupName <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByObjectParameterSet
```
Get-AzCdnCustomDomain [-CustomDomainName <String>] -CdnEndpoint <PSEndpoint>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
**Cmdlet Get-AzCdnCustomDomain** mendapatkan domain kustom Azure Content Delivery Network (CDN) dan pengaturan terkaitnya.

## EXAMPLES

### Contoh 1
```powershell
Get-AzCdnCustomDomain -ResourceGroupName myresourcegroup -ProfileName mycdnprofile -EndpointName myendpoint
```

```Output
HostName                        : cdn.example.com
ValidationData                  :
ResourceState                   : Active
CustomHttpsProvisioningState    : Disabled
CustomHttpsProvisioningSubstate : None
ResourceGroupName               : myresourcegroup
ProfileName                     : mycdnprofile
EndpointName                    : myendpoint
Id                              : /subscriptions/11111111-1111-1111-1111-111111111111/resourcegroups/myresourcegroup/providers
                                  /Microsoft.Cdn/profiles/mycdnprofile/endpoints/myendpoint/customdomains/cdn-example-com
Name                            : cdn-example-com
Type                            : Microsoft.Cdn/profiles/endpoints/customdomains
ProvisioningState               : Succeeded
```

## PARAMETERS

### -CdnEndpoint
Menentukan objek titik akhir CDN yang menjadi anggota domain kustom.

```yaml
Type: Microsoft.Azure.Commands.Cdn.Models.Endpoint.PSEndpoint
Parameter Sets: ByObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -CustomDomainName
Menentukan nama domain kustom.
Nama domain kustom berbeda dari nama host domain kustom.

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

### -EndpointName
Menentukan nama titik akhir tempat domain kustom berada.

```yaml
Type: System.String
Parameter Sets: ByFieldsParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProfileName
Menentukan nama Profil tempat domain kustom berada.

```yaml
Type: System.String
Parameter Sets: ByFieldsParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya tempat domain kustom berada.

```yaml
Type: System.String
Parameter Sets: ByFieldsParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Cdn.Models.Endpoint.PSEndpoint

## OUTPUTS

### Microsoft.Azure.Commands.Cdn.Models.CustomDomain.PSCustomDomain

## CATATAN

## RELATED LINKS

[New-AzCdnCustomDomain](./New-AzCdnCustomDomain.md)

[Remove-AzCdnCustomDomain](./Remove-AzCdnCustomDomain.md)


