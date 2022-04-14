---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Cdn.dll-Help.xml
Module Name: Az.Cdn
ms.assetid: 8C4E824F-FB4A-4DE7-8FD9-3FDA3848F25C
online version: https://docs.microsoft.com/powershell/module/az.cdn/test-azcdncustomdomain
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/Test-AzCdnCustomDomain.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/Test-AzCdnCustomDomain.md
ms.openlocfilehash: 63b8d858f1182a13550176aabd4598a2049528bb
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142218619"
---
# Test-AzCdnCustomDomain

## SYNOPSIS
Memeriksa apakah domain kustom bisa ditambahkan ke titik akhir.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.cdn/test-azcdncustomdomain) untuk informasi terbaru.

## SYNTAX

### ByFieldsParameterSet (Default)
```
Test-AzCdnCustomDomain -EndpointName <String> -ProfileName <String> -ResourceGroupName <String>
 -CustomDomainHostName <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByObjectParameterSet
```
Test-AzCdnCustomDomain -CdnEndpoint <PSEndpoint> -CustomDomainHostName <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
**Cmdlet Test-AzCdnCustomDomain** memeriksa apakah domain kustom dapat ditambahkan ke titik akhir dengan memvalidasi pemetaan CName.

## EXAMPLES

### Contoh 1
```powershell
Test-AzCdnCustomDomain -ResourceGroupName myresourcegroup -ProfileName mycdnprofile -EndpointName myendpoint -CustomDomainHostName cdn.example.com
```

```Output
CustomDomainValidated Reason Message
--------------------- ------ -------
                 True
```

## PARAMETERS

### -CdnEndpoint
Menentukan titik akhir tempat Anda ingin menambahkan domain kustom.

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

### -CustomDomainHostName
Menentukan nama host domain kustom.

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
Menentukan nama titik akhir tempat Anda ingin menambahkan domain kustom.

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
Menentukan nama profil.

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
Menentukan nama grup sumber daya.

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

### Microsoft.Azure.Commands.Cdn.Models.Endpoint.PSValidateCustomDomainOutput

## CATATAN

## RELATED LINKS

[Get-AzCdnCustomDomain](./Get-AzCdnCustomDomain.md)

[New-AzCdnCustomDomain](./New-AzCdnCustomDomain.md)

[Remove-AzCdnCustomDomain](./Remove-AzCdnCustomDomain.md)


