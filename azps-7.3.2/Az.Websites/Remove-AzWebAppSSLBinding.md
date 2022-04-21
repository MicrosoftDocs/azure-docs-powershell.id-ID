---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Websites.dll-Help.xml
Module Name: Az.Websites
ms.assetid: 3AB3D398-E5DB-4214-BA27-6E3B7D
online version: https://docs.microsoft.com/powershell/module/az.websites/remove-azwebappsslbinding
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/Remove-AzWebAppSSLBinding.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/Remove-AzWebAppSSLBinding.md
ms.openlocfilehash: 0197ad85cb825994d6d6131beb48e3f30e5a7579
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142689274"
---
# Remove-AzWebAppSSLBinding

## SYNOPSIS
Menghapus pengikat SSL dari sertifikat yang diunggah.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.websites/remove-azwebappsslbinding) untuk informasi terbaru.

## SYNTAX

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

## DESCRIPTION
Cmdlet **Remove-AzWebAppSSLBinding** menghapus pengikatan Secure Sockets Layer (SSL) dari Azure Web App.
Pengikat SSL digunakan untuk mengaitkan Aplikasi Web dengan sertifikat.

## EXAMPLES

### Contoh 1: Menghapus pengikat SSL untuk aplikasi web
```
PS C:\>Remove-AzWebAppSSLBinding -ResourceGroupName "ContosoResourceGroup" -WebAppName "ContosoWebApp" -Name "www.contoso.com"
```

Perintah ini menghapus pengikat SSL untuk aplikasi web ContosoWebApp.
Karena parameter *DeleteCertificate* tidak disertakan, sertifikat akan dihapus jika tidak lagi memiliki pengikatan SSL.

### Contoh 2: Menghapus pengikatan SSL tanpa menghapus sertifikat
```
PS C:\>Remove-AzWebAppSSLBinding -ResourceGroupName "ContosoResourceGroup" -WebAppName "ContosoWebApp" -Name "www.contoso.com" -DeleteCertificate $False
```

Mirip dengan Contoh 1, perintah ini juga menghapus pengikat SSL untuk ContosoWebApp Aplikasi Web.
Namun, dalam hal ini, parameter *DeleteCertificate* disertakan, dan nilai parameter diatur ke $False.
Itu berarti bahwa sertifikat tidak akan dihapus terlepas apakah sertifikat tersebut memiliki pengikat SSL atau tidak.

### Contoh 3: Menggunakan referensi objek untuk menghapus pengikat SSL
```
PS C:\>$WebApp = Get-AzWebApp -Name "ContosoWebApp"
PS C:\> Remove-AzWebAppSSLBinding -WebApp $WebApp -Name "www.contoso.com"
```

Contoh ini menggunakan referensi objek ke situs web Web App untuk menghapus pengikat SSL untuk Aplikasi Web.
Perintah pertama menggunakan cmdlet Get-AzWebApp untuk membuat referensi objek ke Web App bernama ContosoWebApp.
Referensi objek tersebut disimpan dalam variabel bernama $WebApp.
Perintah kedua menggunakan referensi objek dan cmdlet **Remove-AzWebAppSSLBinding** untuk menghapus pengikat SSL.

## PARAMETERS

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

### -DeleteCertificate
Menentukan tindakan yang akan dilakukan jika pengikatan SSL yang dihapus adalah satu-satunya pengikatan yang digunakan oleh sertifikat.
Jika *DeleteCertificate* diatur ke $False, sertifikat tidak akan dihapus saat penjilidan dihapus.
Jika *DeleteCertificate* diatur ke $True atau tidak disertakan dalam perintah, sertifikat akan dihapus bersama dengan pengikatan SSL.
Sertifikat hanya akan dihapus jika pengikatan SSL yang dihapus adalah satu-satunya pengikatan yang digunakan oleh sertifikat.
Jika sertifikat memiliki lebih dari satu pengikatan, sertifikat tidak akan dihapus terlepas dari nilai parameter *DeleteCertificate* .

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

### -Paksa
Memaksa perintah untuk berjalan tanpa meminta konfirmasi pengguna.

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
Menentukan nama Web App.

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
Parameter Sets: S1
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Slot
Menentukan slot penyebaran Web App.
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
Untuk mendapatkan Web App, gunakan cmdlet Get-AzWebApp.
Anda tidak dapat menggunakan parameter *WebApp* dalam perintah yang sama seperti parameter *ResourceGroupName* dan/atau *WebAppName*.

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
Menentukan nama Web App.
Anda tidak dapat menggunakan parameter *WebAppName* dan parameter *WebApp* dalam perintah yang sama.

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
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Cmdlet tidak dijalankan. Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Situs Microsoft.Azure.Commands.WebApps.Models.PSSite

## OUTPUTS

### System.Void

## NOTES

## RELATED LINKS

[Get-AzWebAppSSLBinding](./Get-AzWebAppSSLBinding.md)

[New-AzWebAppSSLBinding](./New-AzWebAppSSLBinding.md)

[Get-AzWebAppSlot](./Get-AzWebAppSlot.md)

[Get-AzWebApp](./Get-AzWebApp.md)


