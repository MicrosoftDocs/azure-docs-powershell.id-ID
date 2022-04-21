---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.dll-Help.xml
ms.assetid: 64EF867E-5142-4317-9552-8BC94117208D
online version: ''
schema: 2.0.0
ms.openlocfilehash: b1f56f7064cec1e3cf8005134cc16453524c2097
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142723096"
---
# Set-AzureDataDisk

## SYNOPSIS
Mengubah cache host disk data yang sudah ada di mesin virtual Azure.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### NoResize
```
Set-AzureDataDisk [-HostCaching] <String> [-LUN] <Int32> -VM <IPersistentVM> [-Profile <AzureSMProfile>]
 [-InformationAction <ActionPreference>] [-InformationVariable <String>] [<CommonParameters>]
```

### Mengubah ukuran
```
Set-AzureDataDisk [-DiskName] <String> [-ResizedSizeInGB] <Int32> -VM <IPersistentVM>
 [-Profile <AzureSMProfile>] [-InformationAction <ActionPreference>] [-InformationVariable <String>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureDataDisk** mengubah atribut cache disk data yang sudah ada di mesin virtual Azure.
Tentukan disk data mana yang akan diperbarui oleh nomor unit logikanya (LUN).

## EXAMPLES

### Contoh 1: Mengubah cache host untuk disk data
```
PS C:\> Get-AzureVM "ContosoService" | Set-AzureDataDisk -VM "VirtualMachine07" -LUN 2 -HostCaching ReadOnly | Update-AzureVM
```

Perintah ini mendapatkan mesin virtual yang berjalan pada layanan bernama ContosoService menggunakan cmdlet **Get-AzureVM** .
Perintah meneruskannya ke cmdlet saat ini menggunakan operator pipeline.
Cmdlet tersebut mengatur disk data di LUN 2 mesin virtual bernama VirtualMachine07 untuk menggunakan cache host ReadOnly.
Perintah memperbarui mesin virtual untuk mencerminkan perubahan Anda menggunakan cmdlet **Update-AzureVM** .

### Contoh 2: Modifikasi cache host untuk semua disk data di mesin virtual
```
PS C:\> Get-AzureVM "ContosoService" -Name "VirtualMachine07" | Get-AzureDataDisk | Set-AzureDataDisk -HostCaching ReadWrite | Update-AzureVM
```

Perintah ini mendapatkan objek untuk mesin virtual bernama VirtualMachine07 pada layanan cloud ContosoService.
Perintah mengirimkannya ke cmdlet **Get-AzureDataDisk** , yang mendapatkan disk data untuk mesin virtual tersebut.
Cmdlet saat ini kemudian mengatur mode cache host dari setiap disk data ke ReadWrite.
Perintah memperbarui mesin virtual untuk mencerminkan perubahan Anda.

## PARAMETERS

### -DiskName
Menentukan nama konfigurasi disk data yang diubah cmdlet ini.

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
> Cache Disk tidak didukung untuk disk 4 TiB dan lebih besar. Jika beberapa disk dilampirkan ke VM Anda, setiap disk yang lebih kecil dari 4 TiB akan mendukung cache.
>
> Mengubah pengaturan cache disk Azure akan dihapus dan melampirkan kembali disk target. Jika disk sistem operasi, VM akan dimulai ulang. Hentikan semua aplikasi/layanan yang mungkin terpengaruh oleh gangguan ini sebelum mengubah pengaturan cache disk. Tidak mengikuti rekomendasi tersebut dapat mengakibatkan kerusakan data.

Menentukan setelan cache tingkat host disk.
Nilai yang valid adalah:

- Tidak
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

### -LUN
Menentukan LUN untuk drive data di mesin virtual.
Nilai yang valid adalah: 0 hingga 15.

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
Untuk mendapatkan objek mesin virtual, gunakan cmdlet **Get-AzureVM** .

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

## NOTES

## RELATED LINKS

[Add-AzureDataDisk](./Add-AzureDataDisk.md)

[Get-AzureVM](./Get-AzureVM.md)

[Get-AzureDataDisk](./Get-AzureDataDisk.md)

[Hapus-AzureDataDisk](./Remove-AzureDataDisk.md)

[Perbarui-AzureVM](./Update-AzureVM.md)


