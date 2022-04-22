---
external help file: Microsoft.Azure.Commands.Websites.dll-Help.xml
Module Name: AzureRM.WebSites
ms.assetid: EE3D2BA0-32E7-4A37-BCAF-F0E8FAAC43CE
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.websites/get-azurermwebappsslbinding
schema: 2.0.0
ms.openlocfilehash: 103c5e75b433fcb585113e8ef6bc89aab1f82d7b
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142989281"
---
# Get-AzureRmWebAppSSLBinding

## SYNOPSIS
Mendapatkan penjilidan SSL sertifikat Azure Web App.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### S1
```
Get-AzureRmWebAppSSLBinding [[-Name] <String>] [-ResourceGroupName] <String> [-WebAppName] <String>
 [[-Slot] <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### S2
```
Get-AzureRmWebAppSSLBinding [[-Name] <String>] [-WebApp] <Site> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmWebAppSSLBinding** mendapatkan pengikatan Secure Sockets Layer (SSL) untuk Azure Web App.
Pengikat SSL digunakan untuk mengaitkan Aplikasi Web dengan sertifikat yang diunggah.
Web Apps dapat terikat ke beberapa sertifikat.

## EXAMPLES

### Contoh 1: Dapatkan pengikat SSL untuk Aplikasi Web
```
PS C:\>Get-AzureRmWebAppSSLBinding -ResourceGroupName "ContosoResourceGroup" -WebAppName "ContosoWebApp"
```

Perintah ini mengambil pengikat SSL untuk Web App ContosoWebApp, yang terkait dengan grup sumber daya ContosoResourceGroup.

### Contoh 2: Menggunakan referensi objek untuk mendapatkan pengikat SSL untuk Aplikasi Web
```
PS C:\>$WebApp = Get-AzureRmWebApp -Name "ContosoWebApp"
PS C:\> Get-AzureRmWebAppSSLBinding -WebApp $WebApp
```

Perintah dalam contoh ini juga mendapatkan pengikat SSL untuk Aplikasi Web ContosoWebApp; namun, dalam hal ini, referensi objek digunakan sebagai ganti nama Web App dan nama grup sumber daya terkait.
Referensi objek ini dibuat oleh perintah pertama dalam contoh, yang menggunakan **Get-AzureRmWebApp** untuk membuat referensi objek ke Aplikasi Web bernama ContosoWebApp.
Referensi objek tersebut disimpan dalam variabel bernama $WebApp.

Variabel ini, dan cmdlet **Get-AzureRmWebAppSSLBinding** , kemudian digunakan oleh perintah kedua untuk mendapatkan pengikat SSL.

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

### -Nama
Menentukan nama pengikat SSL.

```yaml
Type: String
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
Menentukan nama Web App tempat cmdlet ini mendapatkan pengikat SSL.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Situs
Parameter 'WebApp' menerima nilai tipe 'Situs' dari saluran

## OUTPUTS

## NOTES

## RELATED LINKS

[Baru-AzureRmWebAppSSLBinding](./New-AzureRmWebAppSSLBinding.md)

[Hapus-AzureRmWebAppSSLBinding](./Remove-AzureRmWebAppSSLBinding.md)

[Get-AzureRmWebApp](./Get-AzureRmWebApp.md)


