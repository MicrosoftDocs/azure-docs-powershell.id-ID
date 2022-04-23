---
external help file: Microsoft.Azure.Commands.Dns.dll-Help.xml
ms.assetid: 99E6C4DD-11AF-4DC0-848B-39811240BE06
online version: ''
schema: 2.0.0
ms.openlocfilehash: 8c6479f9358322ae76eeb2fdf3cb9f2bb922e462
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143053829"
---
# Set-AzureRmDnsRecordSet

## SYNOPSIS
Memperbarui kumpulan catatan DNS.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Set-AzureRmDnsRecordSet -RecordSet <DnsRecordSet> [-Overwrite] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureRmDnsRecordSet** memperbarui kumpulan catatan di layanan DNS Azure dari objek **RecordSet** lokal.

Anda dapat melewati objek **RecordSet** sebagai parameter atau menggunakan operator pipeline.

Anda dapat menggunakan variabel *Konfirmasi* parameter dan $ConfirmPreference Windows PowerShell untuk mengontrol apakah cmdlet meminta konfirmasi.

Kumpulan catatan tidak diperbarui jika telah diubah di DNS Azure sejak objek **RecordSet** lokal diambil.
Ini memberikan perlindungan untuk perubahan serentak.
Anda bisa menyembunyikan perilaku ini menggunakan parameter *Timpa* , yang memperbarui kumpulan catatan terlepas dari perubahan bersamaan.

## EXAMPLES

### Contoh 1: Memperbarui kumpulan catatan
```
PS C:\>$RecordSet = Get-AzureRmDnsRecordSet -ResourceGroupName MyResourceGroup -ZoneName myzone.com -Name www -RecordType A
PS C:\> Add-AzureRmDnsRecordConfig -RecordSet $RecordSet -Ipv4Address 172.16.0.0
PS C:\> Add-AzureRmDnsRecordConfig -RecordSet $RecordSet -Ipv4Address 172.31.255.255
PS C:\> Set-AzureRmDnsRecordSet -RecordSet $RecordSet

# These cmdlets can also be piped:

PS C:\> Get-AzureRmDnsRecordSet -ResourceGroupName MyResourceGroup -ZoneName myzone.com -Name www -RecordType A | Add-AzureRmDnsRecordConfig -Ipv4Address 172.16.0.0 | Add-AzureRmDnsRecordConfig -Ipv4Address 172.31.255.255 | Set-AzureRmDnsRecordSet
```

Perintah pertama menggunakan cmdlet Get-AzureRmDnsRecordSet untuk mendapatkan kumpulan rekaman yang ditentukan, lalu menyimpannya dalam variabel $RecordSet.

Perintah kedua dan ketiga adalah operasi off-line untuk menambahkan dua rekaman A ke kumpulan catatan.

Perintah terakhir menggunakan cmdlet **Set-AzureRmDnsRecordSet** untuk melakukan pembaruan.

### Contoh 2: Memperbarui catatan SOA
```
PS C:\>$RecordSet = Get-AzureRmDnsRecordSet -Name "@" -RecordType SOA -Zone $Zone
PS C:\> $RecordSet.Records[0].Email = "admin.myzone.com"
PS C:\> Set-AzureRmDnsRecordSet -RecordSet $RecordSet
```

Perintah pertama menggunakan cmdlet **Get-AzureRmDnsRecordset** untuk mendapatkan kumpulan rekaman yang ditentukan, lalu menyimpannya dalam variabel $RecordSet.

Perintah kedua memperbarui catatan SOA yang ditentukan dalam $RecordSet.

Perintah terakhir menggunakan cmdlet **Set-AzureRmDnsRecordSet** untuk menyebarkan pembaruan dalam $RecordSet.

## PARAMETERS

### -Timpa
Menunjukkan untuk memperbarui kumpulan catatan terlepas dari perubahan serentak.

Kumpulan catatan tidak akan diperbarui jika telah diubah di DNS Azure sejak objek **RecordSet** lokal diambil.
Ini memberikan perlindungan untuk perubahan serentak.
Untuk menyembunyikan perilaku ini, Anda bisa menggunakan parameter *Timpa* , yang menghasilkan kumpulan catatan yang diperbarui terlepas dari perubahan bersamaan.

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

### -RecordSet
Menentukan **Kumpulan Data** untuk diperbarui.

```yaml
Type: DnsRecordSet
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak dijalankan. Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak dijalankan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Dns.DnsRecordSet
Anda dapat mengirimkan objek **RecordSet** ke cmdlet ini.

## OUTPUTS

### Microsoft.Azure.Commands.Dns.DnsRecordSet
Cmdlet ini mengembalikan objek yang mewakili objek **RecordSet** yang diperbarui.

## NOTES
Anda dapat menggunakan parameter *Konfirmasi* untuk mengontrol apakah cmdlet ini meminta konfirmasi.
Secara default, cmdlet meminta Konfirmasi jika variabel $ConfirmPreference Windows PowerShell memiliki nilai Sedang atau lebih rendah.

Jika Anda menentukan *Konfirmasi* atau *Konfirmasi:$True*, cmdlet ini meminta anda untuk konfirmasi sebelum berjalan.
Jika Anda menentukan *Konfirmasi:$False*, cmdlet tidak meminta konfirmasi kepada Anda. 

## RELATED LINKS

[Get-AzureRmDnsRecordSet](./Get-AzureRmDnsRecordSet.md)

[New-AzureRmDnsRecordSet](./New-AzureRmDnsRecordSet.md)

[Remove-AzureRmDnsRecordSet](./Remove-AzureRmDnsRecordSet.md)
