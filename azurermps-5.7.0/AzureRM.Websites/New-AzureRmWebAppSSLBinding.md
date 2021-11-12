---
external help file: Microsoft.Azure.Commands.Websites.dll-Help.xml
Module Name: AzureRM
ms.assetid: 910239BE-9E48-4DC5-85EA-CC6D466FE62F
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.websites/new-azurermwebappsslbinding
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Websites/Commands.Websites/help/New-AzureRmWebAppSSLBinding.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Websites/Commands.Websites/help/New-AzureRmWebAppSSLBinding.md
ms.openlocfilehash: d3971c2838b3fed04e1aa38d96e2cd27b2e8276e
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132423700"
---
# New-AzureRmWebAppSSLBinding

## SYNOPSIS
Membuat pengikatan sertifikat SSL untuk Azure Web App.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### S1
```
New-AzureRmWebAppSSLBinding [-ResourceGroupName] <String> [-WebAppName] <String> [[-Slot] <String>]
 [-Name] <String> [[-SslState] <SslState>] [-CertificateFilePath] <String> [-CertificatePassword] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### S2
```
New-AzureRmWebAppSSLBinding [-ResourceGroupName] <String> [-WebAppName] <String> [[-Slot] <String>]
 [-Name] <String> [[-SslState] <SslState>] [-Thumbprint] <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### S3
```
New-AzureRmWebAppSSLBinding [-WebApp] <Site> [-Name] <String> [[-SslState] <SslState>]
 [-CertificateFilePath] <String> [-CertificatePassword] <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### S4
```
New-AzureRmWebAppSSLBinding [-WebApp] <Site> [-Name] <String> [[-SslState] <SslState>] [-Thumbprint] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureRmWebAppSSLBinding** membuat pengikatan sertifikat Secure Socket Layer (SSL) untuk Azure Web App.
Cmdlet membuat pengikatan SSL dalam dua cara: 

- Anda bisa mengikat Web App ke sertifikat yang sudah ada.
- Anda bisa mengunggah sertifikat baru lalu mengikat Aplikasi Web ke sertifikat baru ini.

Terlepas dari pendekatan mana yang Anda gunakan, sertifikat dan Aplikasi Web harus dikaitkan dengan grup sumber daya Azure yang sama.
Jika Anda memiliki Aplikasi Web di Grup Sumber Daya A dan Anda ingin mengikat Aplikasi Web itu ke sertifikat di Grup Sumber Daya B, satu-satunya cara untuk melakukan itu adalah dengan mengunggah salinan sertifikat ke Grup Sumber Daya A.

Jika Anda mengunggah sertifikat baru, ingatlah persyaratan berikut untuk sertifikat Azure SSL: 

- Sertifikat harus berisi kunci privat. 
- Sertifikat harus menggunakan format Informasi Pribadi Exchange (PFX). 
- Nama subjek sertifikat harus sesuai dengan domain yang digunakan untuk mengakses Web App. 
- Sertifikat harus menggunakan enkripsi minimal 2048-bit.

## EXAMPLES

### Contoh 1: Mengikat sertifikat ke Web App
```
PS C:\>New-AzureRmWebAppSSLBinding -ResourceGroupName "ContosoResourceGroup" -WebAppName "ContosoWebApp" -Thumbprint "E3A38EBA60CAA1C162785A2E1C44A15AD450199C3" -Name "www.contoso.com"
```

Perintah ini mengikat sertifikat Azure yang sudah ada (sertifikat dengan Thumbprint E3A38EBA60CAA1C162785A2E1C44A15AD450199C3) ke aplikasi web bernama ContosoWebApp.

## PARAMETERS

### -CertificateFilePath
Menentukan jalur file untuk sertifikat yang akan diunggah.

Parameter *CertificateFilePath* hanya diperlukan jika sertifikat belum diunggah ke Azure.

```yaml
Type: String
Parameter Sets: S1, S3
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificatePassword
Menentukan kata sandi dekripsi untuk sertifikat.

```yaml
Type: String
Parameter Sets: S1, S3
Aliases: 

Required: True
Position: 5
Default value: None
Accept pipeline input: False
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

### -Nama
Menentukan nama Aplikasi Web.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya tempat sertifikat ditetapkan.

Anda tidak bisa menggunakan parameter *ResourceGroupName* dan parameter *WebApp* di perintah yang sama.

```yaml
Type: String
Parameter Sets: S1, S2
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Slot
Menentukan nama slot penggunaan Web App.
Anda dapat menggunakan cmdlet Get-AzureRMWebAppSlot untuk mendapatkan slot.

Slot penyebaran menyediakan cara untuk Anda melakukan tahapan dan memvalidasi aplikasi web tanpa aplikasi itu bisa diakses melalui internet.
Umumnya, Anda akan menyebarkan perubahan ke situs pengaturan, memvalidasi perubahan tersebut, lalu menyebarkannya ke situs produksi (yang mudah diakses internet).

```yaml
Type: String
Parameter Sets: S1, S2
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SslState
Menentukan apakah sertifikat diaktifkan.
Atur parameter *SSLState* ke 1 untuk mengaktifkan sertifikat, atau atur *SSLState* ke 0 untuk menonaktifkan sertifikat.

```yaml
Type: SslState
Parameter Sets: (All)
Aliases: 
Accepted values: Disabled, SniEnabled, IpBasedEnabled

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Thumbprint
Menentukan pengidentifikasi unik untuk sertifikat.

```yaml
Type: String
Parameter Sets: S2, S4
Aliases: 

Required: True
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WebApp
Menentukan Aplikasi Web.
Untuk mendapatkan Web App, gunakan cmdlet Get-AzureRmWebApp baru.

Anda tidak bisa menggunakan parameter *WebApp* di perintah yang sama seperti parameter *ResourceGroupName* dan/atau *WebAppName*.

```yaml
Type: Site
Parameter Sets: S3, S4
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WebAppName
Menentukan nama Aplikasi Web di mana pengikat SSL baru akan dibuat.

Anda tidak bisa menggunakan parameter *WebAppName* dan parameter *WebApp* di perintah yang sama.

```yaml
Type: String
Parameter Sets: S1, S2
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Situs
Parameter 'WebApp' menerima nilai tipe 'Situs' dari saluran

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureRmWebAppSSLBinding](./Get-AzureRmWebAppSSLBinding.md)

[Remove-AzureRmWebAppSSLBinding](./Remove-AzureRmWebAppSSLBinding.md)

[Get-AzureRMWebAppSlot](./Get-AzureRMWebAppSlot.md)

[Get-AzureRmWebApp](./Get-AzureRmWebApp.md)


