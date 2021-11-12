---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: CF7E7C62-88FC-48CA-940F-9A6C7442BEF2
online version: ''
schema: 2.0.0
ms.openlocfilehash: ba639a114db5c572d2d48541c9479296d9021a17
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132420247"
---
# Publish-AzureServiceProject

## SYNOPSIS
Terbitkan layanan saat ini Windows Azure.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

[!INCLUDE [rdfe-deprecation-banner](../../includes/rdfe-deprecation-banner.md)]

## SYNTAX

### PublishFromServiceDefinition (Default)
```
Publish-AzureServiceProject [-ServiceName <String>] [-StorageAccountName <String>] [-Location <String>]
 [-Slot <String>] [-Launch] [-AffinityGroup <String>] [-DeploymentName <String>] [-ForceUpgrade]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### PublishFromPackage
```
Publish-AzureServiceProject [-Package <String>] -Configuration <String> [-StorageAccountName <String>]
 [-Location <String>] [-Slot <String>] [-Launch] [-AffinityGroup <String>] [-DeploymentName <String>]
 [-ForceUpgrade] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Topik ini menguraikan cmdlet dalam modul Microsoft Azure PowerShell versi 0.8.10.
Untuk mendapatkan versi modul yang Anda gunakan, di konsol Azure PowerShell, ketik `(Get-Module -Name Azure).Version` .

Cmdlet **Publish-AzureServiceProject** menerbitkan layanan saat ini ke awan.
Anda dapat menentukan konfigurasi penerbitan (seperti **Langganan,** **StorageAccountName**, **Lokasi,** **Slot**) di baris perintah, atau di pengaturan lokal melalui cmdlet **Set-AzureServiceProject.**

## EXAMPLES

### Contoh 1: Menerbitkan proyek layanan dengan nilai default
```
PS C:\> Publish-AzureServiceProject
```

Contoh ini menerbitkan layanan saat ini, menggunakan pengaturan layanan saat ini dan profil penerbitan Azure saat ini.

### Contoh 2: Membuat paket penyebaran
```
PS C:\> Publish-AzureServiceProject -PackageOnly
```

Contoh ini membuat file paket penyebaran (.cspkg) dalam direktori layanan dan tidak diterbitkan ke Windows Azure.

## PARAMETERS

### -AffinityGroup
Menentukan grup affinity yang Anda inginkan untuk digunakan oleh layanan.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ag

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Configuration
Menentukan file konfigurasi layanan.
Jika Anda menentukan parameter ini, tentukan parameter *Package.*

```yaml
Type: String
Parameter Sets: PublishFromPackage
Aliases: cc

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DeploymentName
Menentukan nama penyebaran.

```yaml
Type: String
Parameter Sets: (All)
Aliases: dn

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ForceUpgrade
```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: f

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Launch
Membuka jendela browser sehingga Anda bisa menampilkan aplikasi setelah disebarkan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: ln

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Lokasi
Kawasan tempat aplikasi akan dihosting.
Nilai yang mungkin adalah: 
  
- Asia mana pun
- Eropa di mana saja
- US di mana saja
- Asia Timur
- AS Timur
- As Tengah Utara
- Eropa Utara
- As Tengah Selatan
- Asia Tenggara
- Eropa Barat
- AS Barat
 
Jika tidak ada Lokasi yang ditentukan, lokasi yang ditentukan dalam panggilan terakhir untuk **Set-AzureServiceProject** akan digunakan. Jika tidak ada Lokasi yang pernah ditentukan, Lokasi akan dipilih secara acak dari lokasi 'As Pusat Utara' dan 'As Pusat Selatan'.

```yaml
Type: String
Parameter Sets: (All)
Aliases: l

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Paket
Menentukan file paket untuk disebarkan.
Tentukan file lokal yang memiliki ekstensi nama file .cspkg atau URI blob yang berisi paket tersebut.
Jika Anda menentukan parameter ini, jangan tentukan parameter *ServiceName.*

```yaml
Type: String
Parameter Sets: PublishFromPackage
Aliases: sp

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

### -ServiceName
Menentukan nama yang akan digunakan untuk layanan ketika menerbitkan ke Windows Azure.
Nama menentukan bagian label di subdomain cloudapp.net yang digunakan untuk menangani layanan ketika dihosting di Windows Azure (yaitu, **nama**.cloudapp.net).
Setiap nama yang ditentukan saat menerbitkan layanan akan menimpa nama yang diberikan ketika layanan tersebut dibuat.
(Lihat cmdlet **New-AzureServiceProject).**

```yaml
Type: String
Parameter Sets: PublishFromServiceDefinition
Aliases: sv

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Slot
Slot penggunaan yang akan digunakan untuk layanan ini.
Nilai yang mungkin adalah 'Produksi' dan 'Produksi'.
Jika tidak ada slot yang ditentukan, slot yang disediakan di panggilan Set-AzureDeploymentSlot terakhir digunakan.
Jika tidak ada slot yang telah ditentukan, slot 'Produksi' akan digunakan.

```yaml
Type: String
Parameter Sets: (All)
Aliases: sl

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageAccountName
Menentukan Windows penyimpanan Azure yang akan digunakan saat menerbitkan layanan.
Nilai ini tidak digunakan hingga layanan diterbitkan.
Ketika parameter ini tidak ditentukan, nilai diperoleh dari perintah **Set-AzureServiceProject** terakhir.
Jika tidak ada akun penyimpanan yang pernah ditentukan, akun penyimpanan yang cocok dengan nama layanan akan digunakan.
Jika tidak ada akun penyimpanan tersebut, cmdlet akan berusaha membuat akun penyimpanan baru.
Namun, usaha tersebut dapat gagal jika akun penyimpanan yang cocok dengan nama layanan ada di langganan lain.

```yaml
Type: String
Parameter Sets: (All)
Aliases: st

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Enable-AzureServiceProjectRemoteDesktop](./Enable-AzureServiceProjectRemoteDesktop.md)

[Set-AzureServiceProject](./Set-AzureServiceProject.md)


