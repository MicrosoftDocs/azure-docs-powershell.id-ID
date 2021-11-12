---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: E4B1AA31-1185-4035-86E6-2BB2587285C6
online version: ''
schema: 2.0.0
ms.openlocfilehash: bcf65e5d36da5164f116f723a09f06e939fce8c8
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132426270"
---
# Get-AzureWebsite

## SYNOPSIS
Mendapatkan situs web Azure dalam langganan saat ini.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureWebsite [-Name <String>] [-Slot <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureWebsite** mendapatkan informasi tentang situs web Azure dalam langganan saat ini.

Secara default, **Get-AzureWebsite** mendapatkan semua situs web Azure dalam langganan saat ini dan mengembalikan objek yang menyediakan informasi dasar tentang situs tersebut.
Ketika menggunakan parameter *Nama,* **Get-AzureWebsite akan** mengembalikan objek dengan informasi ekstensif, termasuk detail konfigurasi.

Langganan saat ini adalah langganan yang ditetapkan sebagai "saat ini." Untuk menemukan langganan saat ini, *gunakan* Parameter terbaru cmdlet [Get-AzureSubscription.](/powershell/module/servicemanagement/azure.service/get-azuresubscription)
Untuk mengubah langganan saat ini, gunakan cmdlet [Select-AzureSubscription.](/powershell/module/servicemanagement/azure.service/select-azuresubscription)

Topik ini menguraikan cmdlet dalam modul Microsoft Azure PowerShell versi 0.8.10.
Untuk mendapatkan versi modul yang Anda gunakan, di konsol Azure PowerShell, ketik `(Get-Module -Name Azure).Version` .

## EXAMPLES

### Contoh 1: Dapatkan semua situs web dalam langganan
```
PS C:\> Get-AzureWebsite
```

Perintah ini akan mendapatkan semua situs web Azure dalam langganan saat ini.

### Contoh 2: Dapatkan situs web berdasarkan nama
```
PS C:\> Get-AzureWebsite -Name ContosoWeb
```

Perintah ini mendapatkan informasi mendetail tentang situs web Azure ContosoWeb, termasuk informasi konfigurasi.
Ketika menggunakan parameter *Nama,* **Get-AzureWebsite akan** mengembalikan **objek SiteWithConfig** dengan informasi yang diperluas tentang situs web tersebut.

### Contoh 3: Mendapatkan informasi detail tentang semua situs web
```
PS C:\> Get-AzureWebsite | ForEach-Object {Get-AzureWebsite -Name $_.Name}
```

Perintah ini mendapatkan informasi mendetail tentang semua situs web dalam langganan.
Perintah ini menggunakan **perintah Get-AzureWebsite** untuk mendapatkan semua situs web, lalu menggunakan cmdlet **ForEach-Object** untuk mendapatkan setiap situs web berdasarkan nama.

### Contoh 4: Mendapatkan informasi tentang slot penyebaran
```
PS C:\> Get-AzureWebsite -Name ContosoWeb -Slot Staging
```

Perintah ini akan mendapatkan slot Penempatan dari situs web ContosoWeb.
Slot penyebaran memungkinkan Anda menguji versi berbeda dari situs web Azure Anda tanpa melepasnya ke publik.

### Contoh 5: Dapatkan contoh situs web
```
PS C:\>(Get-AzureWebsite -Name ContosoWeb).Instances

InstanceId
----------
2d8e712fb8f85d061c30fd793a534e6700a175f9a9ab12ca55cb3b0edfcc10ee
5834916b8cef49249b18187708223a33fbbc4352d33b48369f3166644bdd3445

PS C:\>(Get-AzureWebsite -Name ContosoWeb).Instances.Count
2
```

Perintah dalam contoh ini menggunakan properti Instances dari situs web Azure untuk mendapatkan informasi tentang contoh situs web yang saat ini berjalan.
Properti **Instances** ditambahkan ke objek **SiteWithConfig** dalam versi 0.8.3 modul Azure.

Perintah pertama mendapatkan ID contoh semua instans yang saat ini berjalan dari sebuah situs web.
Perintah kedua mendapatkan jumlah contoh situs web yang berjalan.
Anda dapat menggunakan properti **Count** di setiap larik.

## PARAMETERS

### -Nama
Mendapatkan informasi konfigurasi mendetail tentang situs web yang ditentukan.
Masukkan nama salah satu situs web dalam langganan.
Secara default, **Get-AzureWebsite mendapatkan** semua situs web dalam langganan saat ini.
Nilai *Nama* tidak mendukung karakter wildcard.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure yang akan dibaca cmdlet ini.
Jika Anda tidak menentukan profil, cmdlet ini akan membaca dari profil default lokal.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Slot
Mendapatkan slot penggunaan tertentu dari situs web.
Masukkan nama slot, seperti "Produksi" atau "Produksi".
Untuk informasi selengkapnya tentang slot penyebaran, lihat Penyebaran Tahapan Microsoft Azure Situs Web https://azure.microsoft.com/en-us/documentation/articles/web-sites-staged-publishing/ .
Untuk menambahkan slot penyebaran ke situs web Azure yang sudah ada, gunakan cmdlet Set-AzureWebsite cmdlet.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Tidak ada
Anda dapat pipa input ke cmdlet ini berdasarkan nama properti, tetapi tidak menurut nilai.

## OUTPUTS

### Microsoft.WindowsAzure.Commands.Utilities.Websites.Services.WebEntities.Site
Secara default, **Get-AzureWebsite** mengembalikan array **objek** Situs.

### Microsoft.WindowsAzure.commands.Utilities.Websites.Services.WebEntities.SiteWithConfig
Ketika menggunakan parameter *Name,* **Get-AzureWebsite akan** mengembalikan objek **SiteWithConfig.**

## CATATAN

## RELATED LINKS

[New-AzureWebsite](./New-AzureWebsite.md)

[Remove-AzureWebsite](./Remove-AzureWebsite.md)

[Start-AzureWebsite](./Start-AzureWebsite.md)

[Stop-AzureWebsite](./Stop-AzureWebsite.md)

[Show-AzureWebsite](./Show-AzureWebsite.md)


