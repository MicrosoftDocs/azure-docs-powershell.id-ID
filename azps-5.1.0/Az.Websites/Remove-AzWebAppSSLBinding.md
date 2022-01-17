---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Websites.dll-Help.xml
Module Name: Az.Websites
ms.assetid: 3AB3D398-E5DB-4214-BA27-6E3B7D225550
online version: https://docs.microsoft.com/en-us/powershell/module/az.websites/remove-azwebappsslbinding
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Websites/Websites/help/Remove-AzWebAppSSLBinding.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Websites/Websites/help/Remove-AzWebAppSSLBinding.md
ms.openlocfilehash: bed5cb961fd39975b3f10debe8791a418fd5dcda
ms.sourcegitcommit: d81c3b0f0f7289104be03869eb675128b61db7d3
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/17/2020
ms.locfileid: "136017688"
---
# Remove-AzWebAppSSLBinding

## SYNOPSIS
Menghapus pengikatan SSL dari sertifikat yang diunggah.

## SINTAKS

### S1
```
Remove-AzWebAppSSLBinding [-Name] <String> [[-DeleteCertificate] <Boolean>] [-Force]
 [-ResourceGroupName] <String> [-WebAppName] <String> [[-Slot] <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### S2
```
Remove-AzWebAppSSLBinding [-Name] <String> [[-DeleteCertificate] <Boolean>] [-Force] [-WebApp] <PSSite>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESKRIPSI
Cmdlet **Remove-AzWebAppSSLBinding** menghapus pengikatan Lapisan Soket Aman (SSL) dari Azure Web App.
Pengikatan SSL digunakan untuk mengaitkan Web App dengan sertifikat.

## CONTOH

### Contoh 1: Menghapus pengikatan SSL untuk aplikasi web
```
PS C:\>Remove-AzWebAppSSLBinding -ResourceGroupName "ContosoResourceGroup" -WebAppName "ContosoWebApp" -Name "www.contoso.com"
```

Perintah ini menghapus pengikatan SSL untuk aplikasi web ContosoWebApp.
Karena parameter *DeleteCertificate* tidak disertakan, sertifikat akan dihapus jika tidak lagi memiliki pengikatan SSL.

### Contoh 2: Menghapus pengikatan SSL tanpa menghapus sertifikat
```
PS C:\>Remove-AzWebAppSSLBinding -ResourceGroupName "ContosoResourceGroup" -WebAppName "ContosoWebApp" -Name "www.contoso.com" -DeleteCertificate $False
```

Sama dengan Contoh 1, perintah ini juga menghapus pengikatan SSL untuk Web App ContosoWebApp.
Namun dalam kasus ini, parameter *DeleteCertificate* disertakan, dan nilai parameter diatur ke $False.
Ini berarti bahwa sertifikat tidak akan dihapus terlepas dari apakah sertifikat tersebut memiliki pengikatan SSL atau tidak.

### Contoh 3: Menggunakan referensi objek untuk menghapus pengikatan SSL
```
PS C:\>$WebApp = Get-AzWebApp -Name "ContosoWebApp"
PS C:\> Remove-AzWebAppSSLBinding -WebApp $WebApp -Name "www.contoso.com"
```

Contoh ini menggunakan referensi objek ke situs web Web App untuk menghapus pengikatan SSL untuk Web App.
Perintah pertama menggunakan cmdlet Get-AzWebApp untuk membuat referensi objek ke Aplikasi Web bernama ContosoWebApp.
Referensi objek tersebut disimpan dalam variabel yang bernama $WebApp.
Perintah kedua menggunakan referensi objek dan cmdlet **Remove-AzWebAppSSLBinding** untuk menghapus pengikatan SSL.

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

### -DeleteCertificate
Menentukan tindakan untuk dilakukan jika pengikatan SSL yang dihapus adalah satu-satunya pengikatan yang digunakan oleh sertifikat.
Jika *DeleteCertificate* disetel ke $False otomatis, sertifikat tidak akan dihapus saat pengikatan dihapus.
Jika *DeleteCertificate* disetel ke $True atau tidak disertakan dalam perintah, sertifikat akan dihapus bersama dengan pengikat SSL.
Sertifikat hanya akan dihapus jika pengikatan SSL yang dihapus adalah satu-satunya pengikatan yang digunakan oleh sertifikat.
Jika sertifikat memiliki lebih dari satu pengikatan, sertifikat tidak akan dihapus terlepas dari nilai parameter *DeleteCertificate.*

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Memaksa perintah untuk dijalankan tanpa meminta konfirmasi pengguna.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
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
Parameter Sets: S1
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Slot
Menentukan slot penggunaan Web App.
Untuk mendapatkan slot penyebaran, gunakan cmdlet Get-AzWebAppSlot.

```yaml
Type: System.String
Parameter Sets: S1
Aliases:

Required: False
Position: 2
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
Parameter Sets: S2
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WebAppName
Menentukan nama Aplikasi Web.
Anda tidak bisa menggunakan parameter *WebAppName* dan parameter *WebApp* di perintah yang sama.

```yaml
Type: System.String
Parameter Sets: S1
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Cmdlet tidak berjalan. Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUT

### Microsoft.Azure.Commands.WebApps.Models.PSSite

## OUTPUT

### System.Void

## CATATAN

## LINK TERKAIT

[Get-AzWebAppSSLBinding](./Get-AzWebAppSSLBinding.md)

[New-AzWebAppSSLBinding](./New-AzWebAppSSLBinding.md)

[Get-AzWebAppslot](./Get-AzWebAppSlot.md)

[Get-AzWebApp](./Get-AzWebApp.md)


