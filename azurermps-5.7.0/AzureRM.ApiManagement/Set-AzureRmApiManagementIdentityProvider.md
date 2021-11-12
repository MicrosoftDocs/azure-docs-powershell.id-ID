---
external help file: Microsoft.Azure.Commands.ApiManagement.ServiceManagement.dll-Help.xml
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.apimanagement/set-azurermapimanagementidentityprovider
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/ApiManagement/Commands.ApiManagement/help/Set-AzureRmApiManagementIdentityProvider.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/ApiManagement/Commands.ApiManagement/help/Set-AzureRmApiManagementIdentityProvider.md
ms.openlocfilehash: e45ec5a3d49bf82ab945a3ef3b41362a1e1e2bd3
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132422675"
---
# Set-AzureRmApiManagementIdentityProvider

## SYNOPSIS
Memperbarui Konfigurasi Penyedia Identitas yang sudah ada.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Set-AzureRmApiManagementIdentityProvider -Context <PsApiManagementContext>
 -Type <PsApiManagementIdentityProviderType> [-ClientId <String>] [-ClientSecret <String>]
 [-AllowedTenants <String[]>] [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Memperbarui Konfigurasi Penyedia Identitas yang sudah ada.

## EXAMPLES

### Contoh 1
```
PS C:\>$apimContext = New-AzureRmApiManagementContext -ResourceGroupName "Api-Default-WestUS" -ServiceName "contoso"
PS C:\> Set-AzureRmApiManagementIdentityProvider -Context $apimContext -Type Facebook -ClientSecret "updatedSecret" -PassThru
```

Cmdlet memperbarui Rahasia Klien Penyedia Identitas Facebook;

## PARAMETERS

### -AllowedTenants
Daftar Penyewa Azure Active Directory yang diperbolehkan.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ClientId
Id Klien Aplikasi di Penyedia Identitas eksternal.
Id Aplikasi untuk login Facebook, ID Klien untuk masuk ke Google, ID Aplikasi untuk Microsoft.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ClientSecret
Rahasia klien Aplikasi di Penyedia Identitas eksternal, digunakan untuk mengautentikasi permintaan masuk.
For example, it is App Secret for Facebook login, API Key for Google login, Public Key for Microsoft.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Konteks
Contoh PsApiManagementContext.
Parameter ini diperlukan.

```yaml
Type: PsApiManagementContext
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.
 
```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Menunjukkan bahwa cmdlet ini mengembalikan  **PsApiManagementIdentityProvider** yang dimodifikasi cmdlet ini.


```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tipe
Pengidentifikasi Penyedia Identitas yang sudah ada.
Parameter ini diperlukan.

```yaml
Type: PsApiManagementIdentityProviderType
Parameter Sets: (All)
Aliases: 
Accepted values: Facebook, Google, Microsoft, Twitter, Aad

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak berjalan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Tidak ada
Cmdlet ini tidak menerima input apa pun.

## OUTPUTS

### Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementIdentityProvider

## CATATAN

## RELATED LINKS

[New-AzureRmApiManagementIdentityProvider](./New-AzureRmApiManagementIdentityProvider.md)

[Get-AzureRmApiManagementIdentityProvider](./Get-AzureRmApiManagementIdentityProvider.md)

[Remove-AzureRmApiManagementIdentityProvider](./Remove-AzureRmApiManagementIdentityProvider.md)
