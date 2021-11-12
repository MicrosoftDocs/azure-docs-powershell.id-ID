---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 64EF867E-5142-4317-9552-8BC94117208D
online version: ''
schema: 2.0.0
ms.openlocfilehash: b1f56f7064cec1e3cf8005134cc16453524c2097
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132427450"
---
# Set-AzureDataDisk

## SYNOPSIS
Memodifikasi host cache disk data yang sudah ada di komputer virtual Azure.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### NoResize
```
Set-AzureDataDisk [-HostCaching] <String> [-LUN] <Int32> -VM <IPersistentVM> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

### Ubah ukuran
```
Set-AzureDataDisk [-DiskName] <String> [-ResizedSizeInGB] <Int32> -VM <IPersistentVM>
 [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureDataDisk** memodifikasi atribut cache dari disk data yang sudah ada di komputer virtual Azure.
Tentukan disk data mana yang diperbarui dengan nomor unit logikanya (LUN).

## EXAMPLES

### Contoh 1: Mengubah host cache untuk disk data
```
PS C:\> Get-AzureVM "ContosoService" | Set-AzureDataDisk -VM "VirtualMachine07" -LUN 2 -HostCaching ReadOnly | Update-AzureVM
```

Perintah ini mendapatkan mesin virtual yang dijalankan pada layanan bernama ContosoService menggunakan cmdlet **Get-AzureVM.**
Perintah itu meneruskannya ke cmdlet saat ini dengan menggunakan operator pipeline.
Cmdlet tersebut mengatur disk data di LUN 2 dari mesin virtual yang bernama VirtualMachine07 untuk menggunakan cache host ReadOnly.
Perintah memperbarui mesin virtual agar mencerminkan perubahan Anda menggunakan cmdlet **Update-AzureVM.**

### Contoh 2: Modifikasi host cache untuk semua disk data pada komputer virtual
```
PS C:\> Get-AzureVM "ContosoService" -Name "VirtualMachine07" | Get-AzureDataDisk | Set-AzureDataDisk -HostCaching ReadWrite | Update-AzureVM
```

Perintah ini mendapatkan objek untuk mesin virtual bernama VirtualMachine07 di layanan awan ContosoService.
Perintah itu meneruskannya ke cmdlet **Get-AzureDataDisk,** yang mendapatkan disk data untuk komputer virtual tersebut.
Cmdlet saat ini lalu mengatur mode cache host dari setiap disk data ke ReadWrite.
Perintah memperbarui mesin virtual untuk mencerminkan perubahan Anda.

## PARAMETERS

### -DiskName
Menentukan nama konfigurasi disk data yang dimodifikasi cmdlet ini.

```yaml
Type: String
Parameter Sets: Resize
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostCaching

> [!WARNING]
> Disk Caching tidak didukung untuk disk 4 TiB dan lebih besar. Jika beberapa disk terpasang pada VM, setiap disk yang lebih kecil dari 4 TiB akan mendukung caching.
>
> Mengubah pengaturan cache disk Azure akan melepaskan dan melampirkan kembali disk target. Jika vm adalah disk sistem operasi, VM akan dimulai ulang. Hentikan semua aplikasi/layanan yang mungkin terpengaruh oleh gangguan ini sebelum mengubah pengaturan singgahan disk. Tidak mengikuti rekomendasi tersebut dapat menyebabkan kerusakan data.

Menentukan pengaturan cache tingkat host di disk.
Nilai valid adalah:

- Tidak ada
- ReadOnly
- ReadWrite

```yaml
Type: String
Parameter Sets: NoResize
Aliases:

Required: True
Position: 0
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

### -LUN
Menentukan LUN untuk drive data di komputer virtual.
Nilai valid adalah: 0 sampai 15.

```yaml
Type: Int32
Parameter Sets: NoResize
Aliases:

Required: True
Position: 1
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

### -ResizedSizeInGB
Menentukan ukuran baru, dalam gigabyte, untuk disk data.
Ukuran baru harus lebih besar dari ukuran saat ini.

```yaml
Type: Int32
Parameter Sets: Resize
Aliases:

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Menentukan objek mesin virtual yang dilampirkan ke disk data.
Untuk mendapatkan objek mesin virtual, gunakan cmdlet **Get-AzureVM.**

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

## CATATAN

## RELATED LINKS

[Add-AzureDataDisk](./Add-AzureDataDisk.md)

[Get-AzureVM](./Get-AzureVM.md)

[Get-AzureDataDisk](./Get-AzureDataDisk.md)

[Remove-AzureDataDisk](./Remove-AzureDataDisk.md)

[Update-AzureVM](./Update-AzureVM.md)


