---
external help file: Microsoft.Azure.Commands.Websites.dll-Help.xml
Module Name: AzureRM.WebSites
ms.assetid: 3AB3D398-E5DB-4214-BA27-6E3B7D225550
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.websites/remove-azurermwebappsslbinding
schema: 2.0.0
ms.openlocfilehash: 06bb13207a666b4537c267e391818865e4165e74
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143167553"
---
# Remove-AzureRmWebAppSSLBinding

## SYNOPSIS
Menghapus pengikat SSL dari sertifikat yang diunggah.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### S1
```
Remove-AzureRmWebAppSSLBinding [-Name] <String> [[-DeleteCertificate] <Boolean>] [-Force]
 [-ResourceGroupName] <String> [-WebAppName] <String> [[-Slot] <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### S2
```
Remove-AzureRmWebAppSSLBinding [-Name] <String> [[-DeleteCertificate] <Boolean>] [-Force] [-WebApp] <Site>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureRmWebAppSSLBinding** menghapus penjilidan Secure Sockets Layer (SSL) dari Azure Web App.
Pengikat SSL digunakan untuk mengaitkan Aplikasi Web dengan sertifikat.

## EXAMPLES

### Contoh 1: Menghapus pengikat SSL untuk aplikasi web
```
PS C:\>Remove-AzureRmWebAppSSLBinding -ResourceGroupName "ContosoResourceGroup" -WebAppName "ContosoWebApp" -Name "www.contoso.com"
```

Perintah ini menghapus pengikat SSL untuk aplikasi web ContosoWebApp.
Karena parameter *DeleteCertificate* tidak disertakan, sertifikat akan dihapus jika tidak lagi memiliki pengikatan SSL.

### Contoh 2: Menghapus pengikatan SSL tanpa menghapus sertifikat
```
PS C:\>Remove-AzureRmWebAppSSLBinding -ResourceGroupName "ContosoResourceGroup" -WebAppName "ContosoWebApp" -Name "www.contoso.com" -DeleteCertificate $False
```

Mirip dengan Contoh 1, perintah ini juga menghapus pengikat SSL untuk ContosoWebApp Aplikasi Web.
Namun, dalam hal ini, parameter *DeleteCertificate* disertakan, dan nilai parameter diatur ke $False.
Itu berarti bahwa sertifikat tidak akan dihapus terlepas apakah sertifikat tersebut memiliki pengikat SSL atau tidak.

### Contoh 3: Menggunakan referensi objek untuk menghapus pengikat SSL
```
PS C:\>$WebApp = Get-AzureRmWebApp -Name "ContosoWebApp"
PS C:\> Remove-AzureRmWebAppSSLBinding -WebApp $WebApp -Name "www.contoso.com"
```

Contoh ini menggunakan referensi objek ke situs web Web App untuk menghapus pengikat SSL untuk Aplikasi Web.

Perintah pertama menggunakan cmdlet Get-AzureRmWebApp untuk membuat referensi objek ke Web App bernama ContosoWebApp.
Referensi objek tersebut disimpan dalam variabel bernama $WebApp.

Perintah kedua menggunakan referensi objek dan cmdlet **Remove-AzureRmWebAppSSLBinding** untuk menghapus pengikat SSL.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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

### -DeleteCertificate
Menentukan tindakan yang akan dilakukan jika pengikatan SSL yang dihapus adalah satu-satunya pengikatan yang digunakan oleh sertifikat.
Jika *DeleteCertificate* diatur ke $False, sertifikat tidak akan dihapus saat penjilidan dihapus.
Jika *DeleteCertificate* diatur ke $True atau tidak disertakan dalam perintah, sertifikat akan dihapus bersama dengan pengikatan SSL.

Sertifikat hanya akan dihapus jika pengikatan SSL yang dihapus adalah satu-satunya pengikatan yang digunakan oleh sertifikat.
Jika sertifikat memiliki lebih dari satu pengikatan, sertifikat tidak akan dihapus terlepas dari nilai parameter *DeleteCertificate* .

```yaml
Type: Boolean
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
Type: SwitchParameter
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

Anda tidak dapat menggunakan parameter *ResourceGroupName* dan parameter *WebApp* dalam perintah yang sama.

```yaml
Type: String
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
Untuk mendapatkan slot penyebaran, gunakan cmdlet Get-AzureRMWebAppSlot.

```yaml
Type: String
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
Untuk mendapatkan Web App, gunakan cmdlet Get-AzureRmWebApp.

Anda tidak dapat menggunakan parameter *WebApp* dalam perintah yang sama seperti parameter *ResourceGroupName* dan/atau *WebAppName*.

```yaml
Type: Site
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
Type: String
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
Type: SwitchParameter
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
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Situs
Parameter 'WebApp' menerima nilai tipe 'Situs' dari saluran

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureRmWebAppSSLBinding](./Get-AzureRmWebAppSSLBinding.md)

[Baru-AzureRmWebAppSSLBinding](./New-AzureRmWebAppSSLBinding.md)

[Get-AzureRMWebAppSlot](./Get-AzureRMWebAppSlot.md)

[Get-AzureRmWebApp](./Get-AzureRmWebApp.md)


