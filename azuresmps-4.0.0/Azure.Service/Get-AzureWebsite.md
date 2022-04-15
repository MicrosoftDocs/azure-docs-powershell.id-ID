---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: E4B1AA31-1185-4035-86E6-2BB2587285C6
online version: ''
schema: 2.0.0
ms.openlocfilehash: bcf65e5d36da5164f116f723a09f06e939fce8c8
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142245418"
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

Secara default, **Get-AzureWebsite** mendapatkan semua situs web Azure dalam langganan saat ini dan mengembalikan objek yang menyediakan informasi dasar tentang situs.
Saat Anda menggunakan parameter *Nama* , **Get-AzureWebsite** mengembalikan objek dengan informasi ekstensif, termasuk detail konfigurasi.

Langganan saat ini adalah langganan yang ditetapkan sebagai "saat ini." Untuk menemukan langganan saat ini, gunakan parameter cmdlet [Get-AzureSubscription](/powershell/module/servicemanagement/azure.service/get-azuresubscription) *saat ini*.
Untuk mengubah langganan saat ini, gunakan cmdlet [Select-AzureSubscription](/powershell/module/servicemanagement/azure.service/select-azuresubscription) .

Topik ini menjelaskan cmdlet dalam versi 0.8.10 modul Microsoft Azure PowerShell.
Untuk mendapatkan versi modul yang Anda gunakan, di konsol Azure PowerShell, ketik .`(Get-Module -Name Azure).Version`

## EXAMPLES

### Contoh 1: Dapatkan semua situs web dalam langganan
```
PS C:\> Get-AzureWebsite
```

Perintah ini mendapatkan semua situs web Azure dalam langganan saat ini.

### Contoh 2: Dapatkan situs web berdasarkan nama
```
PS C:\> Get-AzureWebsite -Name ContosoWeb
```

Perintah ini mendapatkan informasi mendetail tentang situs web ContosoWeb Azure, termasuk informasi konfigurasi.
Saat Anda menggunakan parameter *Nama* , **Get-AzureWebsite** mengembalikan objek **SiteWithConfig** dengan informasi yang diperluas tentang situs web.

### Contoh 3: Dapatkan informasi mendetail tentang semua situs web
```
PS C:\> Get-AzureWebsite | ForEach-Object {Get-AzureWebsite -Name $_.Name}
```

Perintah ini mendapatkan informasi mendetail tentang semua situs web dalam langganan.
Ini menggunakan perintah **Get-AzureWebsite** untuk mendapatkan semua situs web lalu menggunakan cmdlet **ForEach-Object** untuk mendapatkan setiap situs web berdasarkan nama.

### Contoh 4: Dapatkan informasi tentang slot penyebaran
```
PS C:\> Get-AzureWebsite -Name ContosoWeb -Slot Staging
```

Perintah ini mendapatkan slot penyebaran Staging dari situs web ContosoWeb.
Slot penyebaran memungkinkan Anda menguji versi situs web Azure yang berbeda tanpa merilisnya ke publik.

### Contoh 5: Dapatkan instans situs web
```
PS C:\>(Get-AzureWebsite -Name ContosoWeb).Instances

InstanceId
----------
2d8e712fb8f85d061c30fd793a534e6700a175f9a9ab12ca55cb3b0edfcc10ee
5834916b8cef49249b18187708223a33fbbc4352d33b48369f3166644bdd3445

PS C:\>(Get-AzureWebsite -Name ContosoWeb).Instances.Count
2
```

Perintah dalam contoh ini menggunakan properti Instans situs web Azure untuk mendapatkan informasi tentang instans situs web yang sedang berjalan saat ini.
Properti **Instances** ditambahkan ke objek **SiteWithConfig** dalam versi 0.8.3 modul Azure.

Perintah pertama mendapatkan ID instans dari semua contoh situs web yang saat ini berjalan.
Perintah kedua mendapatkan jumlah contoh situs web yang berjalan.
Anda dapat menggunakan properti **Count** di array apa pun.

## PARAMETERS

### -Nama
Mendapatkan informasi konfigurasi mendetail tentang situs web tertentu.
Masukkan nama satu situs web dalam langganan.
Secara default, **Get-AzureWebsite** mendapatkan semua situs web dalam langganan saat ini.
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
Menentukan profil Azure tempat cmdlet ini dibaca.
Jika Anda tidak menentukan profil, cmdlet ini akan dibaca dari profil default lokal.

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
Mendapatkan slot penyebaran yang ditentukan dari situs web.
Masukkan nama slot, seperti "Staging" atau "Production".
Untuk informasi selengkapnya tentang slot penyebaran, lihat Penyebaran Bertahap di Situshttps://azure.microsoft.com/en-us/documentation/articles/web-sites-staged-publishing/ Web Microsoft Azure.
Untuk menambahkan slot penyebaran ke situs web Azure yang sudah ada, gunakan cmdlet Set-AzureWebsite.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak
Anda dapat menyalurkan input ke cmdlet ini menurut nama properti, tetapi tidak menurut nilai.

## OUTPUTS

### Microsoft.WindowsAzure.Commands.Utilities.Websites.Services.WebEntities.Site
Secara default, **Get-AzureWebsite** mengembalikan array objek **Situs** .

### Microsoft.WindowsAzure.Commands.Utilities.Websites.Services.WebEntities.SiteWithConfig
Saat Anda menggunakan parameter *Nama* , **Get-AzureWebsite** mengembalikan objek **SiteWithConfig** .

## CATATAN

## RELATED LINKS

[Baru-AzureSitus Web](./New-AzureWebsite.md)

[Hapus-AzureSitus Web](./Remove-AzureWebsite.md)

[Mulai AzureSitus Web](./Start-AzureWebsite.md)

[Berhenti-AzureSitus Web](./Stop-AzureWebsite.md)

[Tampilkan-AzureSitus Web](./Show-AzureWebsite.md)


