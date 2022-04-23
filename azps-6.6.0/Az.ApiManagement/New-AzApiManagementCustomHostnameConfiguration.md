---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ApiManagement.dll-Help.xml
Module Name: Az.ApiManagement
online version: https://docs.microsoft.com/powershell/module/az.apimanagement/new-azapimanagementcustomhostnameconfiguration
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/New-AzApiManagementCustomHostnameConfiguration.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ApiManagement/ApiManagement/help/New-AzApiManagementCustomHostnameConfiguration.md
ms.openlocfilehash: 379bfa603a6b181df373feae8d113d1e7ea3e9e1
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143303363"
---
# New-AzApiManagementCustomHostnameConfiguration

## SYNOPSIS
Membuat contoh `PsApiManagementCustomHostNameConfiguration`.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.apimanagement/new-azapimanagementcustomhostnameconfiguration) untuk informasi terbaru.

## SYNTAX

### NoChangeCertificate (Default)
```
New-AzApiManagementCustomHostnameConfiguration -Hostname <String> -HostnameType <PsApiManagementHostnameType>
 -HostNameCertificateInformation <PsApiManagementCertificateInformation> [-DefaultSslBinding]
 [-NegotiateClientCertificate] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### SslCertificateFromFile
```
New-AzApiManagementCustomHostnameConfiguration -Hostname <String> -HostnameType <PsApiManagementHostnameType>
 -PfxPath <String> [-PfxPassword <SecureString>] [-DefaultSslBinding] [-NegotiateClientCertificate]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### SslCertificateFromKeyVault
```
New-AzApiManagementCustomHostnameConfiguration -Hostname <String> -HostnameType <PsApiManagementHostnameType>
 -KeyVaultId <String> [-IdentityClientId <String>] [-DefaultSslBinding] [-NegotiateClientCertificate]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzApiManagementCustomHostnameConfiguration** adalah perintah penolong yang membuat contoh **PsApiManagementCustomHostNameConfiguration**.
Perintah ini digunakan dengan cmdlet New-AzApiManagement dan Set-AzApiManagement.

## EXAMPLES

### Contoh 1: Membuat dan menginisialisasi contoh PsApiManagementCustomHostNameConfiguration menggunakan Sertifikat Ssl dari file
```powershell
PS C:\>$portal = New-AzApiManagementCustomHostnameConfiguration -Hostname "portal.contoso.com" -HostnameType Portal -PfxPath "C:\contoso\certificates\apimanagement.pfx" -PfxPassword "1111" -DefaultSslBinding
PS C:\>$customConfig = @($portal)
PS C:\>New-AzApiManagement -ResourceGroupName "ContosoGroup" -Location "West US" -Name "ContosoApi" -Organization Contoso -AdminEmail admin@contoso.com -CustomHostnameConfiguration $customConfig
```

Perintah ini membuat dan menginisialisasi contoh **PsApiManagementCustomHostNameConfiguration** untuk Portal. Lalu membuat layanan ApiManagement baru dengan konfigurasi nama host kustom.

### Contoh 2: Membuat dan menginisialisasi contoh PsApiManagementCustomHostNameConfiguration menggunakan Secret dari KeyVault Resource
```powershell
PS C:\>$portal = New-AzApiManagementCustomHostnameConfiguration -Hostname "portal.contoso.com" -HostnameType Portal -KeyVaultId "https://apim-test-keyvault.vault.azure.net/secrets/api-portal-custom-ssl.pfx"

PS C:\>$customConfig = @($portal)
PS C:\>New-AzApiManagement -ResourceGroupName "ContosoGroup" -Location "West US" -Name "ContosoApi" -Organization Contoso -AdminEmail admin@contoso.com -CustomHostnameConfiguration $customConfig -SystemAssignedIdentity
```

Perintah ini membuat dan menginisialisasi contoh **PsApiManagementCustomHostNameConfiguration**.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

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

### -DefaultSslBinding
Menentukan apakah nilai adalah rahasia dan harus dienkripsi atau tidak.
Parameter ini bersifat opsional.
Nilai Default adalah false.

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

### -Hostname
Nama Host Kustom

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

### -HostNameCertificateInformation
Konfigurasi Sertifikat yang Sudah Ada.

```yaml
Type: Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementCertificateInformation
Parameter Sets: NoChangeCertificate
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -HostnameType
Tipe Nama Host

```yaml
Type: Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementHostnameType
Parameter Sets: (All)
Aliases:
Accepted values: Proxy, Portal, Management, Scm, DeveloperPortal, Configuration, Data

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IdentityClientId
User-Assigned Managed Identity ClientId digunakan untuk mengautentikasi ke KeyVault untuk mengambil Sertifikat SSL Kustom.

```yaml
Type: System.String
Parameter Sets: SslCertificateFromKeyVault
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyVaultId
KeyVaultId ke rahasia menyimpan Sertifikat SSL Kustom.

```yaml
Type: System.String
Parameter Sets: SslCertificateFromKeyVault
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NegotiateClientCertificate
Menentukan apakah nilai adalah rahasia dan harus dienkripsi atau tidak.
Parameter ini bersifat opsional.
Nilai Default adalah false.

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

### -PfxPassword
Kata sandi untuk file sertifikat .pfx.

```yaml
Type: System.Security.SecureString
Parameter Sets: SslCertificateFromFile
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PfxPath
Jalur ke file sertifikat .pfx.

```yaml
Type: System.String
Parameter Sets: SslCertificateFromFile
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

### Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementCertificateInformation

## OUTPUTS

### Microsoft.Azure.Commands.ApiManagement.Models.PsApiManagementCustomHostNameConfiguration

## NOTES

## RELATED LINKS

[New-AzApiManagement](./New-AzApiManagement.md)

[Set-AzApiManagement](./Set-AzApiManagement.md)
