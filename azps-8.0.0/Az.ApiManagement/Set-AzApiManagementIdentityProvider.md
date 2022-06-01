---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ApiManagement.ServiceManagement.dll-Help.xml
Module Name: Az.ApiManagement
online version: https://docs.microsoft.com/powershell/module/az.apimanagement/set-azapimanagementidentityprovider
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/Set-AzApiManagementIdentityProvider.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/Set-AzApiManagementIdentityProvider.md
ms.openlocfilehash: 08d6808e96f1b42609a43f5fc2cd132d70018c3b
ms.sourcegitcommit: 22f85a560177b7234f114dd21a108e3bc8b1608b
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/01/2022
ms.locfileid: "145977349"
---
# Set-AzApiManagementIdentityProvider

## SYNOPSIS
Memperbarui Konfigurasi Penyedia Identitas yang ada.

## SYNTAX

### ExpandedParameter (Default)
```
Set-AzApiManagementIdentityProvider -Context <PsApiManagementContext>
 -Type <PsApiManagementIdentityProviderType> [-ClientId <String>] [-ClientSecret <String>]
 [-AllowedTenants <String[]>] [-Authority <String>] [-SignupPolicyName <String>] [-SigninPolicyName <String>]
 [-ProfileEditingPolicyName <String>] [-PasswordResetPolicyName <String>] [-SigninTenant <String>] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByInputObject
```
Set-AzApiManagementIdentityProvider -InputObject <PsApiManagementIdentityProvider> [-ClientId <String>]
 [-ClientSecret <String>] [-AllowedTenants <String[]>] [-Authority <String>] [-SignupPolicyName <String>]
 [-SigninPolicyName <String>] [-ProfileEditingPolicyName <String>] [-PasswordResetPolicyName <String>]
 [-SigninTenant <String>] [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Memperbarui Konfigurasi Penyedia Identitas yang ada.

## EXAMPLES

### Contoh 1: Memperbarui IdP facebook
```powershell
$apimContext = New-AzApiManagementContext -ResourceGroupName "Api-Default-WestUS" -ServiceName "contoso"
Set-AzApiManagementIdentityProvider -Context $apimContext -Type Facebook -ClientSecret "updatedSecret" -PassThru
```

Cmdlet memperbarui Rahasia Klien IdP Facebook;

### Contoh 2

Memperbarui Konfigurasi Penyedia Identitas yang ada. (dibuat otomatis)

<!-- Aladdin Generated Example -->
```powershell
Set-AzApiManagementIdentityProvider -AllowedTenants 'samirtestbc.onmicrosoft.com' -Authority <String> -ClientId 'clientid' -ClientSecret 'updatedSecret' -Context <PsApiManagementContext> -PasswordResetPolicyName <String> -ProfileEditingPolicyName <String> -SigninPolicyName <String> -SignupPolicyName B2C_1_signup-policy -Type Facebook
```

## PARAMETERS

### -AllowedTenants
Daftar Penyewa Azure Active Directory yang diizinkan.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Otoritas
OpenID Koneksi nama host titik akhir penemuan untuk AAD atau AAD B2C. Parameter ini bersifat opsional.

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

### -ClientId
Id Klien Aplikasi di Penyedia Identitas eksternal.
Ini adalah ID Aplikasi untuk login Facebook, ID Klien untuk login Google, ID Aplikasi untuk Microsoft.

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

### -ClientSecret
Rahasia klien Aplikasi di Penyedia Identitas eksternal, digunakan untuk mengautentikasi permintaan masuk.
Misalnya, itu adalah Rahasia Aplikasi untuk login Facebook, Kunci API untuk login Google, Kunci Umum untuk Microsoft.

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

### -Context
Instans PsApiManagementContext.
Parameter ini diperlukan.

```yaml
Type: Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementContext
Parameter Sets: ExpandedParameter
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

### -InputObject
Instans PsApiManagementIdentityProvider. Parameter ini diperlukan.

```yaml
Type: Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementIdentityProvider
Parameter Sets: ByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru
Menunjukkan bahwa cmdlet ini mengembalikan  **PsApiManagementIdentityProvider** yang dimodifikasi cmdlet ini.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PasswordResetPolicyName
Nama Kebijakan Reset Kata Sandi. Hanya berlaku untuk Penyedia Identitas AAD B2C. Parameter ini bersifat opsional.

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

### -ProfileEditingPolicyName
Nama Kebijakan Pengeditan Profil. Hanya berlaku untuk Penyedia Identitas AAD B2C. Parameter ini bersifat opsional.

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

### -SigninPolicyName
Nama Kebijakan Masuk. Hanya berlaku untuk Penyedia Identitas AAD B2C. Parameter ini bersifat opsional.

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

### -SigninTenant
Penyewa Masuk untuk mengambil alih di AAD B2C alih-alih `common` Penyewa

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

### -SignupPolicyName
Nama Kebijakan Pendaftaran. Hanya berlaku untuk Penyedia Identitas AAD B2C. Parameter ini bersifat opsional.

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

### -Type
Pengidentifikasi Penyedia Identitas yang ada.
Parameter ini diperlukan.

```yaml
Type: Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementIdentityProviderType
Parameter Sets: ExpandedParameter
Aliases:
Accepted values: Facebook, Google, Microsoft, Twitter, Aad, AadB2C

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Menunjukkan yang akan terjadi jika cmdlet dijalankan. Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementContext

### Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementIdentityProviderType

### System.String

### System.String[]

### System.Management.Automation.SwitchParameter

## OUTPUTS

### Microsoft.Azure.Commands.ApiManagement.ServiceManagement.Models.PsApiManagementIdentityProvider

## NOTES

## RELATED LINKS

[New-AzApiManagementIdentityProvider](./New-AzApiManagementIdentityProvider.md)

[Get-AzApiManagementIdentityProvider](./Get-AzApiManagementIdentityProvider.md)

[Remove-AzApiManagementIdentityProvider](./Remove-AzApiManagementIdentityProvider.md)
