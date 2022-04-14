---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ApiManagement.ServiceManagement.dll-Help.xml
Module Name: Az.ApiManagement
ms.assetid: D5B18FF4-3294-4561-A4CD-CF0FA5E4A59B
online version: https://docs.microsoft.com/powershell/module/az.apimanagement/new-azapimanagementopenidconnectprovider
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/New-AzApiManagementOpenIdConnectProvider.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/New-AzApiManagementOpenIdConnectProvider.md
ms.openlocfilehash: bc24be88c799af86eec7b8c30d2d1b5a97f01033
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142115585"
---
# New-AzApiManagementOpenIdConnectProvider

## SYNOPSIS
Membuat penyedia Koneksi OpenID.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.apimanagement/new-azapimanagementopenidconnectprovider) untuk informasi terbaru.

## SYNTAX

```
New-AzApiManagementOpenIdConnectProvider -Context <PsApiManagementContext> [-OpenIdConnectProviderId <String>]
 -Name <String> -MetadataEndpointUri <String> -ClientId <String> [-ClientSecret <String>]
 [-Description <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzApiManagementOpenIdConnectProvider** membuat penyedia Koneksi OpenID di Azure API Management.

## EXAMPLES

### Contoh 1: Membuat penyedia
```powershell
$apimContext = New-AzApiManagementContext -ResourceGroupName "Api-Default-WestUS" -ServiceName "contoso"
New-AzApiManagementOpenIdConnectProvider -Context $apimContext -OpenIdConnectProviderId "OICProvider01" -Name "Contoso OpenID Connect Provider" -MetadataEndpointUri "https://openid.provider/configuration" -ClientId "12432143" -Description "OpenID Connect provider description"
```

Perintah ini membuat **Penyedia** Koneksi OpenID bernama Penyedia Koneksi Contoso OpenID

### Contoh 2

Membuat penyedia Koneksi OpenID. (autogenerasi)

```powershell
<!-- Aladdin Generated Example --> 
New-AzApiManagementOpenIdConnectProvider -ClientId '12432143' -ClientSecret '000000000000000000000000000000000000000000' -Context <PsApiManagementContext> -Description 'OpenID Connect provider description' -MetadataEndpointUri 'https://openid.provider/configuration' -Name 'Contoso OpenID Connect Provider' -OpenIdConnectProviderId 'OICProvider01'
```

## PARAMETERS

### -ClientId
Menentukan ID klien konsol pengembang.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ClientSecret
Menentukan rahasia klien konsol pengembang.

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

### -Konteks
Menentukan objek **PsApiManagementContext** .

```yaml
Type: Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementContext
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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

### -Deskripsi
Menentukan deskripsi.

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

### -MetadataEndpointUri
Menentukan URI titik akhir metadata penyedia.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Menentukan nama yang mudah dikenali untuk penyedia.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OpenIdConnectProviderId
Menentukan ID untuk penyedia.
Jika Anda tidak menentukan ID, cmdlet ini akan menghasilkannya.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementContext

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementOpenIdConnectProvider

## CATATAN

## RELATED LINKS

[Get-AzApiManagementOpenIdConnectProvider](./Get-AzApiManagementOpenIdConnectProvider.md)

[Remove-AzApiManagementOpenIdConnectProvider](./Remove-AzApiManagementOpenIdConnectProvider.md)

[Set-AzApiManagementOpenIdConnectProvider](./Set-AzApiManagementOpenIdConnectProvider.md)


