---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Websites.dll-Help.xml
Module Name: Az.Websites
ms.assetid: EE3D2BA0-32E7-4A37-BCAF-F0E8FAAC43CE
online version: https://docs.microsoft.com/powershell/module/az.websites/get-azwebappsslbinding
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/Get-AzWebAppSSLBinding.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Websites/Websites/help/Get-AzWebAppSSLBinding.md
ms.openlocfilehash: 1ab2e9da93abb9f669154876afe1fdcd823a96bc
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136169070"
---
# Get-AzWebAppSSLBinding

## SYNOPSIS
Mendapatkan pengikatan SSL sertifikat Azure Web App.

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
Pengikatan SSL digunakan untuk mengaitkan Web App dengan sertifikat yang diunggah.
Aplikasi Web dapat terikat ke beberapa sertifikat.

## EXAMPLES

### Contoh 1: Mendapatkan pengikatan SSL untuk Web App
```
PS C:\>Get-AzWebAppSSLBinding -ResourceGroupName "ContosoResourceGroup" -WebAppName "ContosoWebApp"
```

Perintah ini mengambil pengikatan SSL untuk Web App ContosoWebApp, yang terkait dengan grup sumber daya ContosoResourceGroup.

### Contoh 2: Menggunakan referensi objek untuk mendapatkan pengikatan SSL untuk Web App
```
PS C:\>$WebApp = Get-AzWebApp -Name "ContosoWebApp"
PS C:\> Get-AzWebAppSSLBinding -WebApp $WebApp
```

Perintah dalam contoh ini juga mendapatkan pengikatan SSL untuk Web App ContosoWebApp; namun, dalam kasus ini, referensi objek digunakan sebagai ganti nama Web App dan nama grup sumber daya terkait.
Referensi objek ini dibuat oleh perintah pertama dalam contoh, yang menggunakan **Get-AzWebApp** untuk membuat referensi objek ke Web App bernama ContosoWebApp.
Referensi objek tersebut disimpan dalam variabel yang bernama $WebApp.
Variabel ini, dan cmdlet **Get-AzWebAppSSLBinding,** lalu digunakan oleh perintah kedua untuk mendapatkan pengikatan SSL.

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

### -Nama
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
Menentukan slot penggunaan Aplikasi Web.
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
Menentukan nama Web App yang dapatkan pengikatan SSL dari cmdlet ini.
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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Microsoft.Azure.Commands.WebApps.Models.PSSite

## OUTPUTS

### Microsoft.Azure.Management.WebSites.Models.HostNameSslState

## CATATAN

## RELATED LINKS

[New-AzWebAppSSLBinding](./New-AzWebAppSSLBinding.md)

[Remove-AzWebAppSSLBinding](./Remove-AzWebAppSSLBinding.md)

[Get-AzWebApp](./Get-AzWebApp.md)


