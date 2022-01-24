---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Websites.dll-Help.xml
Module Name: Az.Websites
ms.assetid: 910239BE-9E48-4DC5-85EA-CC6D466FE62F
online version: https://docs.microsoft.com/en-us/powershell/module/az.websites/new-azwebappsslbinding
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Websites/Websites/help/New-AzWebAppSSLBinding.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Websites/Websites/help/New-AzWebAppSSLBinding.md
ms.openlocfilehash: 2fff18033febbab23083127628959d2fca9305a3
ms.sourcegitcommit: d81c3b0f0f7289104be03869eb675128b61db7d3
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/17/2020
ms.locfileid: "136013464"
---
# New-AzWebAppSSLBinding

## SYNOPSIS
Membuat pengikatan sertifikat SSL untuk Azure Web App.

## SINTAKS

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

## DESKRIPSI
Cmdlet **New-AzWebAppSSLBinding** membuat pengikatan sertifikat Secure Socket Layer (SSL) untuk Azure Web App.
Cmdlet membuat pengikatan SSL dalam dua cara: 
- Anda bisa mengikat Web App ke sertifikat yang sudah ada.
- Anda bisa mengunggah sertifikat baru lalu mengikat Aplikasi Web ke sertifikat baru ini.
Terlepas dari pendekatan mana yang Anda gunakan, sertifikat dan Aplikasi Web harus dikaitkan dengan grup sumber daya Azure yang sama.
Jika Anda memiliki Aplikasi Web di Grup Sumber Daya A dan Anda ingin mengikat Aplikasi Web itu ke sertifikat di Grup Sumber Daya B, satu-satunya cara untuk melakukan itu adalah dengan mengunggah salinan sertifikat ke Grup Sumber Daya A. Jika Anda mengunggah sertifikat baru, ingatlah persyaratan berikut untuk sertifikat Azure SSL: 
- Sertifikat harus berisi kunci privat. 
- Sertifikat harus menggunakan format Informasi Pribadi Exchange (PFX). 
- Nama subjek sertifikat harus sesuai dengan domain yang digunakan untuk mengakses Web App. 
- Sertifikat harus menggunakan enkripsi minimal 2048-bit.

## CONTOH

### Contoh 1: Mengikat sertifikat ke Web App
```powershell
PS C:\>New-AzWebAppSSLBinding -ResourceGroupName "ContosoResourceGroup" -WebAppName "ContosoWebApp" -Thumbprint "E3A38EBA60CAA1C162785A2E1C44A15AD450199C3" -Name "www.contoso.com"
```

Perintah ini mengikat sertifikat Azure yang sudah ada (sertifikat dengan Thumbprint E3A38EBA60CAA1C162785A2E1C44A15AD450199C3) ke aplikasi web bernama ContosoWebApp.

### Contoh 2

Membuat pengikatan sertifikat SSL untuk Azure Web App. (otomatisgenerated)

```powershell <!-- Aladdin Generated Example --> 
New-AzWebAppSSLBinding -Name 'www.contoso.com' -ResourceGroupName 'ContosoResourceGroup' -SslState Disabled -Thumbprint 'E3A38EBA60CAA1C162785A2E1C44A15AD450199C3' -WebAppName 'ContosoWebApp'
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

### -Nama
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
Anda tidak bisa menggunakan parameter *ResourceGroupName* dan parameter *WebApp* di perintah yang sama.

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
Menentukan nama slot penggunaan Web App.
Anda dapat menggunakan cmdlet Get-AzWebAppSlot untuk mendapatkan slot.
Slot penyebaran menyediakan cara untuk Anda melakukan tahapan dan memvalidasi aplikasi web tanpa aplikasi itu bisa diakses melalui internet.
Umumnya, Anda akan menyebarkan perubahan ke situs pengaturan, memvalidasi perubahan tersebut, lalu menyebarkannya ke situs produksi (yang mudah diakses internet).

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
Untuk mendapatkan Web App, gunakan cmdlet Get-AzWebApp baru.
Anda tidak bisa menggunakan parameter *WebApp* di perintah yang sama seperti parameter *ResourceGroupName* dan/atau *WebAppName*.

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
Menentukan nama Aplikasi Web di mana pengikat SSL baru akan dibuat.
Anda tidak bisa menggunakan parameter *WebAppName* dan parameter *WebApp* di perintah yang sama.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUT

### Microsoft.Azure.Commands.WebApps.Models.PSSite

## OUTPUT

### Microsoft.Azure.Management.WebSites.Models.HostNameSslState

## CATATAN

## LINK TERKAIT

[Get-AzWebAppSSLBinding](./Get-AzWebAppSSLBinding.md)

[Remove-AzWebAppSSLBinding](./Remove-AzWebAppSSLBinding.md)

[Get-AzWebAppslot](./Get-AzWebAppSlot.md)

[Get-AzWebApp](./Get-AzWebApp.md)


