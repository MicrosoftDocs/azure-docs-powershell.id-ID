---
external help file: Microsoft.WindowsAzure.Commands.Profile.dll-Help.xml
ms.assetid: 32BC6CE6-60EF-4A46-912B-8FE4FCCDF7CC
online version: ''
schema: 2.0.0
ms.openlocfilehash: b33233d214964e443a37deebfc92a3c00c14855b
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132423613"
---
# Get-AzureSubscription

## SYNOPSIS
Mendapatkan langganan Azure di akun Azure.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### ByName (Default)
```
Get-AzureSubscription [-SubscriptionName <String>] [-ExtendedDetails] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

### ById
```
Get-AzureSubscription [-SubscriptionId <String>] [-ExtendedDetails] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

### Default
```
Get-AzureSubscription [-Default] [-ExtendedDetails] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### Saat ini
```
Get-AzureSubscription [-Current] [-ExtendedDetails] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureSubscription** mendapatkan langganan di akun Azure Anda.
Anda dapat menggunakan cmdlet ini untuk mendapatkan informasi tentang langganan dan untuk pipet langganan ke cmdlet lainnya.

**Get-AzureSubscription** memerlukan akses ke akun Azure Anda.
Sebelum menjalankan **Get-AzureSubscription,** Anda harus menjalankan cmdlet **Add-AzureAccount** atau cmdlet yang mengunduh dan menginstal file pengaturan penerbitan (**Get-AzurePublishSettingsFile,** **Import-AzurePublishSettingsFile.**

Topik ini menguraikan cmdlet dalam modul Microsoft Azure PowerShell versi 0.8.10.
Untuk mendapatkan versi modul yang Anda gunakan, di konsol Azure PowerShell, ketik `(Get-Module -Name Azure).Version` .

## EXAMPLES

### Contoh 1: Dapatkan semua langganan
```
C:\PS>Get-AzureSubscription
```

Perintah ini akan mendapatkan semua langganan dalam akun tersebut.

### Contoh 2: Dapatkan langganan dengan nama
```
C:\PS>Get-AzureSubscription -SubscriptionName "MyProdSubscription"
```

Perintah ini hanya mendapatkan langganan "MyProdSubsciption".

### Contoh 3: Dapatkan langganan default
```
C:\PS>(Get-AzureSubscription -Default).SubscriptionName
```

Perintah ini hanya mendapatkan nama langganan default.
Perintah akan mendapatkan langganan terlebih dahulu, lalu menggunakan metode titik untuk mendapatkan properti **SubscriptionName** dari langganan.

### Contoh 4: Mendapatkan properti langganan yang dipilih
```
C:\PS>Get-AzureSubscription -Current | Format-List -Property SubscriptionName, Certificate
```

Perintah ini mengembalikan daftar dengan nama dan sertifikat langganan saat ini.
Langganan ini **menggunakan perintah Get-AzureSubscription** untuk mendapatkan langganan saat ini.
Kemudian, program akan pipet **langganan ke perintah Format-Daftar** yang menampilkan properti yang dipilih dalam daftar.

### Contoh 5: Gunakan file data langganan alternatif
```
C:\PS>Get-AzureSubscription -SubscriptionDataFile "C:\Temp\MySubscriptions.xml"
```

Perintah ini mendapatkan langganan dari C:\Temp\MySubscriptions.xml file data langganan.
Gunakan parameter **SubscriptionDataFile** jika Anda menentukan file data langganan alternatif ketika menjalankan cmdlet **Add-AzureAccount** atau **Import-PublishSettingsFile.**

## PARAMETERS

### -Saat Ini
Hanya mendapatkan langganan saat ini, langganan yang ditetapkan sebagai "saat ini." Secara default, **Get-AzureSubscription** akan mendapatkan semua langganan dalam akun Azure Anda.
Untuk menetapkan langganan sebagai "saat ini," gunakan parameter **Saat** Ini dari cmdlet **Select-AzureSubscription.**

```yaml
Type: SwitchParameter
Parameter Sets: Current
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Default
Hanya mendapatkan langganan default, misalnya langganan yang ditetapkan sebagai "default." Secara default, **Get-AzureSubscription** akan mendapatkan semua langganan dalam akun Azure Anda.
Untuk menetapkan langganan sebagai "default," gunakan parameter **Default** dari cmdlet **Select-AzureSubscription.**

```yaml
Type: SwitchParameter
Parameter Sets: Default
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExtendedDetails
Mengembalikan informasi kuota untuk langganan, selain pengaturan standar.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure yang akan dibaca cmdlet ini. Jika Anda tidak menentukan profil, cmdlet ini akan membaca dari profil default lokal.

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

### -SubscriptionId
```yaml
Type: String
Parameter Sets: ById
Aliases: Id

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SubscriptionName
Mendapatkan langganan tertentu saja.
Masukkan nama langganan.
Nilainya peka huruf besar-kecil.
Karakter wildcard tidak didukung.
Secara default, **Get-AzureSubscription** akan mendapatkan semua langganan dalam akun Azure Anda.

```yaml
Type: String
Parameter Sets: ByName
Aliases: Name

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
Anda dapat pipa input ke **properti SubscriptionName** menurut nama, tetapi tidak menurut nilai.

## OUTPUTS

### Microsoft.WindowsAzure.commands.utilities.common.WindowsAzureSubscription

## CATATAN
* Get-AzureSubscription mendapatkan data dari file data langganan yang dibuat cmdlet **Add-AzureAccount** dan **Import-PublishSettingsFile.**

## RELATED LINKS

[Add-AzureAccount](./Add-AzureAccount.md)

[Get-AzurePublishSettingsFile](./Get-AzurePublishSettingsFile.md)

[Import-AzurePublishSettingsFile](./Import-AzurePublishSettingsFile.md)

[Remove-AzureSubscription](./Remove-AzureSubscription.md)

[Set-AzureSubscription](./Set-AzureSubscription.md)


