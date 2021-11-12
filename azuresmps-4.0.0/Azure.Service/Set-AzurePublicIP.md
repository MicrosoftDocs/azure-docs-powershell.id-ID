---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: BFD4E4AD-8F1B-4E4E-BF52-435A6EEAA060
online version: ''
schema: 2.0.0
ms.openlocfilehash: 166d2e4ee0ad7f62fbdb60f8cad8a9f62a6e4a15
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132427429"
---
# Set-AzurePublicIP

## SYNOPSIS
Menambahkan IP Publik ke mesin virtual Azure.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Set-AzurePublicIP [-PublicIPName] <String> [[-IdleTimeoutInMinutes] <Int32>] [[-DomainNameLabel] <String>]
 -VM <IPersistentVM> [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>]
 [-InformationVariable <String>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzurePublicIP** menambahkan IP Publik ke mesin virtual Azure.
Jika Anda menjalankan cmdlet ini untuk mesin virtual yang sudah ada, perbarui mesin virtual untuk menerapkan perubahan Anda.
Anda bisa menentukan label nama domain untuk membuat entri DNS terkait untuk IP publik.

## EXAMPLES

### Contoh 1: Menambahkan IP Publik ke komputer virtual yang sudah ada
```
PS C:\> Get-AzureVM -ServiceName "FTPInAzure" -Name "FTPInstance" | Set-AzurePublicIP -PublicIPName "ftpip" | Update-AzureVM
```

Perintah ini mendapatkan mesin virtual yang bernama FTPInstance dalam layanan yang bernama FTPInAzure menggunakan cmdlet **Get-AzureVM.**
Perintah itu melewati mesin virtual itu ke cmdlet saat ini dengan menggunakan operator pipeline.
Cmdlet saat ini menambahkan ftpip nama IP publik.
Perintah tersebut melewati mesin virtual ke cmdlet **Update-AzureVM,** yang menerapkan perubahan Anda.

### Contoh 2: Tambahkan IP Publik ke komputer virtual baru
```
PS C:\> New-AzureVMConfig -Name "FTPInstance" -InstanceSize Small -ImageName "Image07" | Add-AzureProvisioningConfig -Windows -AdminUsername "AdminMain" -Password "password" | Set-AzurePublicIP -PublicIPName "ftpip" | New-AzureVM -ServiceName "FTPinAzure" -Location "North Central US"
```

Perintah ini akan membuat objek konfigurasi mesin virtual menggunakan cmdlet **New-AzureVMConfig.**
Perintah melewati objek itu ke cmdlet **Add-AzureProvisioningConfig,** yang menyediakan konfigurasi tambahan.
Cmdlet saat ini menambahkan ftpip nama IP publik.
Perintah meneruskan konfigurasi ke cmdlet **New-AzureVM,** yang membuat mesin virtual.

### Contoh 3: Tambahkan IP Publik dan label ke mesin virtual yang sudah ada
```
PS C:\> Get-AzureVM -ServiceName "FTPInAzure" -Name "FTPInstance" | Set-AzurePublicIP -PublicIPName "ftpip" -DomainNameLabel "ipname" | Update-AzureVM
```

Perintah ini mendapatkan mesin virtual yang bernama FTPInstance dalam layanan yang bernama FTPInAzure menggunakan cmdlet **Get-AzureVM.**
Perintah itu melewati mesin virtual itu ke cmdlet saat ini dengan menggunakan operator pipeline.
Cmdlet saat ini menambahkan ftpip nama IP publik dan label ipname.
Perintah akan memperbarui mesin virtual, yang menerapkan perubahan Anda.

### Contoh 4: Tambahkan IP Publik dan label ke mesin virtual baru
```
PS C:\> New-AzureVMConfig -Name "FTPInstance" -InstanceSize Small -ImageName $images[50].ImageName | Add-AzureProvisioningConfig -Windows -AdminUsername "AdminMain" -Password "password" | Set-AzurePublicIP -PublicIPName "ftpip" -DomainNameLabel "ipname" | New-AzureVM -ServiceName "FTPinAzure" -Location "North Central US"
```

Perintah ini akan membuat objek konfigurasi mesin virtual, lalu meneruskan objek tersebut ke **Add-AzureProvisioningConfig**, yang menyediakan konfigurasi tambahan.
Cmdlet saat ini menambahkan ftpip nama IP publik dan label ipname.
Perintah akan membuat mesin virtual.

## PARAMETERS

### -DomainNameLabel
Menentukan nama yang akan digunakan untuk entri DNS terkait untuk alamat IP publik.

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

### -IdleTimeoutInMinutes
Menentukan periode waktu habis tcp diam dalam menit.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationAction
Menentukan bagaimana cmdlet merespons kejadian informasi.

Nilai yang dapat diterima untuk parameter ini adalah:

- Lanjutkan
- Abaikan
- Pemeriksaan
- SilentlyContinue
- Stop
- Tangguhkan

```yaml
Type: ActionPreference
Parameter Sets: (All)
Aliases: infa

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InformationVariable
Menentukan variabel informasi.

```yaml
Type: String
Parameter Sets: (All)
Aliases: iv

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -PublicIPName
Menentukan nama IP Publik.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Menentukan mesin virtual tempat cmdlet ini menambahkan IP Publik.

```yaml
Type: IPersistentVM
Parameter Sets: (All)
Aliases: InputObject

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

### Microsoft.WindowsAzure.commands.ServiceManagement.Model.IPersistentVM

## CATATAN

## RELATED LINKS

[Get-AzurePublicIP](./Get-AzurePublicIP.md)

[Get-AzureVM](./Get-AzureVM.md)

[New-AzureVM](./New-AzureVM.md)

[New-AzureVMConfig](./New-AzureVMConfig.md)

[Remove-AzurePublicIP](./Remove-AzurePublicIP.md)

[Update-AzureVM](./Update-AzureVM.md)


