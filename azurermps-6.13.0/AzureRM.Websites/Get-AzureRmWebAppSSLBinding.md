---
external help file: Microsoft.Azure.Commands.Websites.dll-Help.xml
Module Name: AzureRM.Websites
ms.assetid: EE3D2BA0-32E7-4A37-BCAF-F0E8FAAC43CE
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.websites/get-azurermwebappsslbinding
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Websites/Commands.Websites/help/Get-AzureRmWebAppSSLBinding.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Websites/Commands.Websites/help/Get-AzureRmWebAppSSLBinding.md
ms.openlocfilehash: ae97bc08e5ba8c801e3bf5126c6e48dfb7910751
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132426280"
---
# Get-AzureRmWebAppSSLBinding

## SYNOPSIS
Mendapatkan pengikatan SSL sertifikat Azure Web App.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### S1
```
Get-AzureRmWebAppSSLBinding [[-Name] <String>] [-ResourceGroupName] <String> [-WebAppName] <String>
 [[-Slot] <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### S2
```
Get-AzureRmWebAppSSLBinding [[-Name] <String>] [-WebApp] <PSSite> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmWebAppSSLBinding** mendapatkan pengikatan Lapisan Soket Aman (SSL) untuk Azure Web App.
Pengikatan SSL digunakan untuk mengaitkan Web App dengan sertifikat yang diunggah.
Aplikasi Web dapat terikat ke beberapa sertifikat.

## EXAMPLES

### Contoh 1: Mendapatkan pengikatan SSL untuk Web App
```
PS C:\>Get-AzureRmWebAppSSLBinding -ResourceGroupName "ContosoResourceGroup" -WebAppName "ContosoWebApp"
```

Perintah ini mengambil pengikatan SSL untuk Web App ContosoWebApp, yang terkait dengan grup sumber daya ContosoResourceGroup.

### Contoh 2: Menggunakan referensi objek untuk mendapatkan pengikatan SSL untuk Web App
```
PS C:\>$WebApp = Get-AzureRmWebApp -Name "ContosoWebApp"
PS C:\> Get-AzureRmWebAppSSLBinding -WebApp $WebApp
```

Perintah dalam contoh ini juga mendapatkan pengikatan SSL untuk Web App ContosoWebApp; namun, dalam kasus ini, referensi objek digunakan sebagai ganti nama Web App dan nama grup sumber daya terkait.
Referensi objek ini dibuat oleh perintah pertama dalam contoh, yang menggunakan **Get-AzureRmWebApp** untuk membuat referensi objek ke Web App bernama ContosoWebApp.
Referensi objek tersebut disimpan dalam variabel yang bernama $WebApp.
Variabel ini, dan cmdlet **Get-AzureRmWebAppSSLBinding,** lalu digunakan oleh perintah kedua untuk mendapatkan pengikatan SSL.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

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
Untuk mendapatkan slot penyebaran, gunakan cmdlet Get-AzureRMWebAppSlot.

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
Untuk mendapatkan Web App, gunakan cmdlet Get-AzureRmWebApp baru.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Microsoft.Azure.Management.WebSites.Models.Site
Parameter: WebApp (ByValue)

## OUTPUTS

### Microsoft.Azure.Management.WebSites.Models.HostNameSslState

## CATATAN

## RELATED LINKS

[New-AzureRmWebAppSSLBinding](./New-AzureRmWebAppSSLBinding.md)

[Remove-AzureRmWebAppSSLBinding](./Remove-AzureRmWebAppSSLBinding.md)

[Get-AzureRmWebApp](./Get-AzureRmWebApp.md)


