---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: CF7E7C62-88FC-48CA-940F-9A6C7442BEF2
online version: ''
schema: 2.0.0
ms.openlocfilehash: ba639a114db5c572d2d48541c9479296d9021a17
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142723762"
---
# Publish-AzureServiceProject

## SYNOPSIS
Menerbitkan layanan saat ini ke Windows Azure.

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
Topik ini menjelaskan cmdlet dalam versi 0.8.10 modul Microsoft Azure PowerShell.
Untuk mendapatkan versi modul yang Anda gunakan, di konsol Azure PowerShell, ketik .`(Get-Module -Name Azure).Version`

Cmdlet **Publish-AzureServiceProject** menerbitkan layanan saat ini ke awan.
Anda dapat menentukan konfigurasi penerbitan (seperti **Langganan**, **StorageAccountName**, **Lokasi**, **Slot**) pada baris perintah, atau dalam pengaturan lokal melalui cmdlet **Set-AzureServiceProject** .

## EXAMPLES

### Contoh 1: Menerbitkan proyek layanan dengan nilai default
```
PS C:\> Publish-AzureServiceProject
```

Contoh ini menerbitkan layanan saat ini, menggunakan pengaturan layanan saat ini dan profil publikasi Azure saat ini.

### Contoh 2: Membuat paket penyebaran
```
PS C:\> Publish-AzureServiceProject -PackageOnly
```

Contoh ini membuat file paket penyebaran (.cspkg) di direktori layanan dan tidak diterbitkan ke Windows Azure.

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
Jika Anda menentukan parameter ini, tentukan parameter *Paket* .

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

### -Luncurkan
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
Nilai yang memungkinkan adalah: 
  
- Di mana saja Asia
- Di mana saja Eropa
- Di mana saja AS
- Asia Timur
- AS Timur
- As Tengah Utara
- Eropa Utara
- As Tengah Selatan
- Asia Tenggara
- Eropa Barat
- AS Barat
 
Jika tidak ada Lokasi yang ditentukan, lokasi yang ditentukan dalam panggilan terakhir ke **Set-AzureServiceProject** akan digunakan. Jika tidak ada Lokasi yang ditentukan, Lokasi akan dipilih secara acak dari lokasi 'North Central US' dan 'South Central US'.

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
Menentukan file paket yang akan digunakan.
Tentukan file lokal yang memiliki ekstensi nama file .cspkg atau URI blob yang berisi paket.
Jika Anda menentukan parameter ini, jangan tentukan parameter *ServiceName* .

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

### -ServiceName
Menentukan nama yang akan digunakan untuk layanan saat menerbitkan ke Windows Azure.
Nama menentukan bagian label dalam subdomain cloudapp.net yang digunakan untuk mengatasi layanan ketika dihosting di Windows Azure (yaitu, **name.cloudapp.net**).
Nama apa pun yang ditentukan saat menerbitkan layanan menimpa nama yang diberikan saat layanan dibuat.
(Lihat cmdlet **New-AzureServiceProject** ).

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
Slot penyebaran yang akan digunakan untuk layanan ini.
Nilai yang memungkinkan adalah 'Staging' dan 'Production'.
Jika tidak ada slot yang ditentukan, slot yang disediakan dalam panggilan terakhir untuk Set-AzureDeploymentSlot digunakan.
Jika tidak ada slot yang telah ditentukan, slot 'Produksi' digunakan.

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
Menentukan nama akun penyimpanan Azure Windows yang akan digunakan saat menerbitkan layanan.
Nilai ini tidak digunakan hingga layanan diterbitkan.
Ketika parameter ini tidak ditentukan, nilai diperoleh dari perintah **Set-AzureServiceProject** terakhir.
Jika tidak ada akun penyimpanan yang pernah ditentukan, akun penyimpanan yang cocok dengan nama layanan akan digunakan.
Jika tidak ada akun penyimpanan tersebut, cmdlet akan mencoba membuat yang baru.
Namun, upaya tersebut mungkin gagal jika akun penyimpanan yang cocok dengan nama layanan ada di langganan lain.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Enable-AzureServiceProjectRemoteDesktop](./Enable-AzureServiceProjectRemoteDesktop.md)

[Set-AzureServiceProject](./Set-AzureServiceProject.md)


