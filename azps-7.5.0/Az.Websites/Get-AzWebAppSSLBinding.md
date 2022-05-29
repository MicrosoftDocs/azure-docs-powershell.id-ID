---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Websites.dll-Help.xml
Module Name: Az.Websites
ms.assetid: EE3D2BA0-32E7-4A37-BCAF-F0E8FAAC43CE
online version: https://docs.microsoft.com/powershell/module/az.websites/get-azwebappsslbinding
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/Get-AzWebAppSSLBinding.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/Get-AzWebAppSSLBinding.md
ms.openlocfilehash: d2969a78c33fce6233751afcd27fa98f063e5c60
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145700002"
---
# Get-AzWebAppSSLBinding

## SYNOPSIS
Mendapatkan pengikatan SSL sertifikat Azure Web App.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.websites/get-azwebappsslbinding) untuk informasi terbaru.

## SYNTAX

### S1
```
Get-AzWebAppSSLBinding [[-Name] <String>] [-ResourceGroupName] <String> [-WebAppName] <String>
 [[-Slot] <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### S2
```
Get-AzWebAppSSLBinding [[-Name] <String>] [-WebApp] <PSSite> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzWebAppSSLBinding** mendapatkan pengikatan Secure Sockets Layer (SSL) untuk Azure Web App.
Pengikatan SSL digunakan untuk mengaitkan Aplikasi Web dengan sertifikat yang diunggah.
Web Apps dapat terikat ke beberapa sertifikat.

## EXAMPLES

### Contoh 1: Mendapatkan pengikatan SSL untuk Aplikasi Web
```powershell
Get-AzWebAppSSLBinding -ResourceGroupName "ContosoResourceGroup" -WebAppName "ContosoWebApp"
```

Perintah ini mengambil pengikatan SSL untuk Aplikasi Web ContosoWebApp, yang terkait dengan grup sumber daya ContosoResourceGroup.

### Contoh 2: Gunakan referensi objek untuk mendapatkan pengikatan SSL untuk Aplikasi Web
```powershell
$WebApp = Get-AzWebApp -Name "ContosoWebApp"
Get-AzWebAppSSLBinding -WebApp $WebApp
```

Perintah dalam contoh ini juga mendapatkan pengikatan SSL untuk Aplikasi Web ContosoWebApp; namun, dalam hal ini, referensi objek digunakan alih-alih nama Aplikasi Web dan nama grup sumber daya terkait.
Referensi objek ini dibuat oleh perintah pertama dalam contoh, yang menggunakan **Get-AzWebApp** untuk membuat referensi objek ke Aplikasi Web bernama ContosoWebApp.
Referensi objek tersebut disimpan dalam variabel bernama $WebApp.
Variabel ini, dan cmdlet **Get-AzWebAppSSLBinding** , kemudian digunakan oleh perintah kedua untuk mendapatkan pengikatan SSL.

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

### -Name
Menentukan nama pengikatan SSL.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
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
Menentukan slot penyebaran Aplikasi Web.
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
Untuk mendapatkan Aplikasi Web, gunakan cmdlet Get-AzWebApp.

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
Menentukan nama Aplikasi Web tempat cmdlet ini mendapatkan pengikatan SSL.
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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.WebApps.Models.PSSite

## OUTPUTS

### Microsoft.Azure.Management.WebSites.Models.HostNameSslState

## NOTES

## RELATED LINKS

[New-AzWebAppSSLBinding](./New-AzWebAppSSLBinding.md)

[Remove-AzWebAppSSLBinding](./Remove-AzWebAppSSLBinding.md)

[Get-AzWebApp](./Get-AzWebApp.md)


