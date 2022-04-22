---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: BFD4E4AD-8F1B-4E4E-BF52-435A6EEAA060
online version: ''
schema: 2.0.0
ms.openlocfilehash: 166d2e4ee0ad7f62fbdb60f8cad8a9f62a6e4a15
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142915823"
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

### Contoh 1: Menambahkan IP Publik ke mesin virtual yang sudah ada
```
PS C:\> Get-AzureVM -ServiceName "FTPInAzure" -Name "FTPInstance" | Set-AzurePublicIP -PublicIPName "ftpip" | Update-AzureVM
```

Perintah ini mendapatkan mesin virtual bernama FTPInstance dalam layanan bernama FTPInAzure dengan menggunakan cmdlet **Get-AzureVM** .
Perintah melewati mesin virtual tersebut ke cmdlet saat ini menggunakan operator pipeline.
Cmdlet saat ini menambahkan ftpip Nama IP Publik.
Perintah melewati mesin virtual ke cmdlet **Update-AzureVM** , yang mengimplementasikan perubahan Anda.

### Contoh 2: Menambahkan IP Publik ke mesin virtual baru
```
PS C:\> New-AzureVMConfig -Name "FTPInstance" -InstanceSize Small -ImageName "Image07" | Add-AzureProvisioningConfig -Windows -AdminUsername "AdminMain" -Password "password" | Set-AzurePublicIP -PublicIPName "ftpip" | New-AzureVM -ServiceName "FTPinAzure" -Location "North Central US"
```

Perintah ini membuat objek konfigurasi mesin virtual menggunakan cmdlet **New-AzureVMConfig** .
Perintah melewati objek tersebut ke cmdlet **Add-AzureProvisioningConfig** , yang menyediakan konfigurasi tambahan.
Cmdlet saat ini menambahkan ftpip Nama IP Publik.
Perintah melewati konfigurasi ke cmdlet **New-AzureVM** , yang membuat mesin virtual.

### Contoh 3: Menambahkan IP Publik dan label ke mesin virtual yang sudah ada
```
PS C:\> Get-AzureVM -ServiceName "FTPInAzure" -Name "FTPInstance" | Set-AzurePublicIP -PublicIPName "ftpip" -DomainNameLabel "ipname" | Update-AzureVM
```

Perintah ini mendapatkan mesin virtual bernama FTPInstance dalam layanan bernama FTPInAzure dengan menggunakan cmdlet **Get-AzureVM** .
Perintah melewati mesin virtual tersebut ke cmdlet saat ini menggunakan operator pipeline.
Cmdlet saat ini menambahkan ftpip Nama IP Publik dan nama ip label.
Perintah memperbarui mesin virtual, yang mengimplementasikan perubahan Anda.

### Contoh 4: Menambahkan IP Publik dan label ke mesin virtual baru
```
PS C:\> New-AzureVMConfig -Name "FTPInstance" -InstanceSize Small -ImageName $images[50].ImageName | Add-AzureProvisioningConfig -Windows -AdminUsername "AdminMain" -Password "password" | Set-AzurePublicIP -PublicIPName "ftpip" -DomainNameLabel "ipname" | New-AzureVM -ServiceName "FTPinAzure" -Location "North Central US"
```

Perintah ini membuat objek konfigurasi mesin virtual, lalu mengirimkan objek tersebut ke **Add-AzureProvisioningConfig**, yang menyediakan konfigurasi tambahan.
Cmdlet saat ini menambahkan ftpip Nama IP Publik dan nama ip label.
Perintah membuat mesin virtual.

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
Menentukan periode waktu habis diam TCP dalam menit.

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
Menentukan bagaimana cmdlet ini merespons kejadian informasi.

Nilai yang dapat diterima untuk parameter ini adalah:

- Lanjutkan
- Mengabaikan
- Menanyakan
- DiamKontinue
- Stop
- Menangguhkan

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsAzure.Commands.ServiceManagement.Model.IPersistentVM

## NOTES

## RELATED LINKS

[Get-AzurePublicIP](./Get-AzurePublicIP.md)

[Get-AzureVM](./Get-AzureVM.md)

[AzureVM baru](./New-AzureVM.md)

[AzureVMConfig baru](./New-AzureVMConfig.md)

[Hapus-AzurePublicIP](./Remove-AzurePublicIP.md)

[Perbarui-AzureVM](./Update-AzureVM.md)


