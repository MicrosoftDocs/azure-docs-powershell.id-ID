---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Websites.dll-Help.xml
Module Name: Az.Websites
ms.assetid: 910239BE-9E48-4DC5-85EA-CC6D466FE62F
online version: https://docs.microsoft.com/powershell/module/az.websites/new-azwebappsslbinding
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/New-AzWebAppSSLBinding.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/New-AzWebAppSSLBinding.md
ms.openlocfilehash: 5fc8a096ad3a3d1dbda8119c3e2674262285155d
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144731192"
---
# New-AzWebAppSSLBinding

## SYNOPSIS
Membuat pengikatan sertifikat SSL untuk Azure Web App.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.websites/new-azwebappsslbinding) untuk informasi terbaru.

## SYNTAX

### S1
```
New-AzWebAppSSLBinding [-ResourceGroupName] <String> [-WebAppName] <String> [[-Slot] <String>] [-Name] <String>
 [[-SslState] <SslState>] [-CertificateFilePath] <String> [-CertificatePassword] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### S2
```
New-AzWebAppSSLBinding [-ResourceGroupName] <String> [-WebAppName] <String> [[-Slot] <String>] [-Name] <String>
 [[-SslState] <SslState>] [-Thumbprint] <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### S3
```
New-AzWebAppSSLBinding [-WebApp] <PSSite> [-Name] <String> [[-SslState] <SslState>]
 [-CertificateFilePath] <String> [-CertificatePassword] <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### S4
```
New-AzWebAppSSLBinding [-WebApp] <PSSite> [-Name] <String> [[-SslState] <SslState>] [-Thumbprint] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzWebAppSSLBinding** membuat pengikatan sertifikat Secure Socket Layer (SSL) untuk Azure Web App.
Cmdlet membuat pengikatan SSL dengan dua cara: 
- Anda dapat mengikat Aplikasi Web ke sertifikat yang sudah ada.
- Anda dapat mengunggah sertifikat baru lalu mengikat Aplikasi Web ke sertifikat baru ini.
Terlepas dari pendekatan mana yang Anda gunakan, sertifikat dan Aplikasi Web harus dikaitkan dengan grup sumber daya Azure yang sama.
Jika Anda memiliki Aplikasi Web di Grup Sumber Daya A dan Anda ingin mengikat Aplikasi Web tersebut ke sertifikat di Grup Sumber Daya B, satu-satunya cara untuk melakukannya adalah dengan mengunggah salinan sertifikat ke Grup Sumber Daya A. Jika Anda mengunggah sertifikat baru, ingatlah persyaratan berikut untuk sertifikat Azure SSL: 
- Sertifikat harus memuat kunci privat. 
- Sertifikat harus menggunakan format Exchange Informasi Pribadi (PFX). 
- Nama subjek sertifikat harus cocok dengan domain yang digunakan untuk mengakses Aplikasi Web. 
- Sertifikat harus menggunakan minimal enkripsi 2048-bit.

## EXAMPLES

### Contoh 1: Mengikat sertifikat ke Aplikasi Web
```powershell
New-AzWebAppSSLBinding -ResourceGroupName "ContosoResourceGroup" -WebAppName "ContosoWebApp" -Thumbprint "E3A38EBA60CAA1C162785A2E1C44A15AD450199C3" -Name "www.contoso.com"
```

Perintah ini mengikat sertifikat Azure yang ada (sertifikat dengan Thumbprint E3A38EBA60CAA1C162785A2E1C44A15AD450199C3) ke aplikasi web bernama ContosoWebApp.

### Contoh 2

Membuat pengikatan sertifikat SSL untuk Azure Web App. (dibuat otomatis)

```powershell
<!-- Aladdin Generated Example --> 
New-AzWebAppSSLBinding -Name 'www.contoso.com' -ResourceGroupName 'ContosoResourceGroup' -SslState Disabled -Thumbprint 'E3A38EBA60CAA1C162785A2E1C44A15AD450199C3' -WebAppName 'ContosoWebApp'
```

powershell

### Contoh 3

Membuat pengikatan sertifikat SSL untuk Azure Web App. (dibuat otomatis)

<!-- Aladdin Generated Example -->


```powershell
New-AzWebAppSSLBinding -CertificateFilePath <String> -CertificatePassword <String> -Name 'www.contoso.com' -ResourceGroupName 'ContosoResourceGroup' -SslState Disabled -WebAppName 'ContosoWebApp'
```

## PARAMETERS

### -CertificateFilePath
Menentukan jalur file untuk sertifikat yang akan diunggah.
Parameter *CertificateFilePath* hanya diperlukan jika sertifikat belum diunggah ke Azure.

```yaml
Type: System.String
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
Type: System.String
Parameter Sets: S1, S3
Aliases:

Required: True
Position: 5
Default value: None
Accept pipeline input: False
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

### -Name
Menentukan nama Aplikasi Web.

```yaml
Type: System.String
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
Anda tidak dapat menggunakan parameter *ResourceGroupName* dan parameter *WebApp* dalam perintah yang sama.

```yaml
Type: System.String
Parameter Sets: S1, S2
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Slot
Menentukan nama slot penyebaran Aplikasi Web.
Anda dapat menggunakan cmdlet Get-AzWebAppSlot untuk mendapatkan slot.
Slot penyebaran menyediakan cara bagi Anda untuk menggelar dan memvalidasi aplikasi web tanpa aplikasi tersebut dapat diakses melalui Internet.
Biasanya Anda akan menyebarkan perubahan Anda ke situs penahapan, memvalidasi perubahan tersebut, lalu menyebarkan ke situs produksi (dapat diakses internet).

```yaml
Type: System.String
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
Type: System.Nullable`1[Microsoft.Azure.Management.WebSites.Models.SslState]
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
Type: System.String
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
Untuk mendapatkan Aplikasi Web, gunakan cmdlet Get-AzWebApp.
Anda tidak dapat menggunakan parameter *WebApp* dalam perintah yang sama dengan parameter *ResourceGroupName* dan/atau *WebAppName*.

```yaml
Type: Microsoft.Azure.Commands.WebApps.Models.PSSite
Parameter Sets: S3, S4
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WebAppName
Menentukan nama Aplikasi Web tempat pengikatan SSL baru sedang dibuat.
Anda tidak dapat menggunakan parameter *WebAppName* dan parameter *WebApp* dalam perintah yang sama.

```yaml
Type: System.String
Parameter Sets: S1, S2
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.WebApps.Models.PSSite

## OUTPUTS

### Microsoft.Azure.Management.WebSites.Models.HostNameSslState

## NOTES

## RELATED LINKS

[Get-AzWebAppSSLBinding](./Get-AzWebAppSSLBinding.md)

[Remove-AzWebAppSSLBinding](./Remove-AzWebAppSSLBinding.md)

[Get-AzWebAppSlot](./Get-AzWebAppSlot.md)

[Get-AzWebApp](./Get-AzWebApp.md)


