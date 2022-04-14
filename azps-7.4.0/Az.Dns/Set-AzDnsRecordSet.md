---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Dns.dll-Help.xml
Module Name: Az.Dns
ms.assetid: 99E6C4DD-11AF-4DC0-848B-39811240BE06
online version: https://docs.microsoft.com/powershell/module/az.dns/set-azdnsrecordset
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Dns/Dns/help/Set-AzDnsRecordSet.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Dns/Dns/help/Set-AzDnsRecordSet.md
ms.openlocfilehash: 719f7f6257aa792efda7381c1a1707e5e9886763
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141837632"
---
# Set-AzDnsRecordSet

## SYNOPSIS
Memperbarui kumpulan catatan DNS.

## SYNTAX

```
Set-AzDnsRecordSet -RecordSet <DnsRecordSet> [-Overwrite] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzDnsRecordSet** memperbarui kumpulan catatan di layanan DNS Azure dari objek **RecordSet** lokal.
Anda dapat melewati objek **RecordSet** sebagai parameter atau menggunakan operator pipeline.
Anda dapat menggunakan variabel *Konfirmasi* parameter dan $ConfirmPreference Windows PowerShell untuk mengontrol apakah cmdlet meminta konfirmasi.
Kumpulan catatan tidak diperbarui jika telah diubah di DNS Azure sejak objek **RecordSet** lokal diambil.
Ini memberikan perlindungan untuk perubahan serentak.
Anda bisa menyembunyikan perilaku ini menggunakan parameter *Timpa* , yang memperbarui kumpulan catatan terlepas dari perubahan bersamaan.

## EXAMPLES

### Contoh 1: Memperbarui kumpulan catatan
```powershell
$RecordSet = Get-AzDnsRecordSet -ResourceGroupName MyResourceGroup -ZoneName myzone.com -Name www -RecordType A
Add-AzDnsRecordConfig -RecordSet $RecordSet -Ipv4Address 172.16.0.0
Add-AzDnsRecordConfig -RecordSet $RecordSet -Ipv4Address 172.31.255.255
Set-AzDnsRecordSet -RecordSet $RecordSet

# These cmdlets can also be piped:

Get-AzDnsRecordSet -ResourceGroupName MyResourceGroup -ZoneName myzone.com -Name www -RecordType A | Add-AzDnsRecordConfig -Ipv4Address 172.16.0.0 | Add-AzDnsRecordConfig -Ipv4Address 172.31.255.255 | Set-AzDnsRecordSet
```

Perintah pertama menggunakan cmdlet Get-AzDnsRecordSet untuk mendapatkan kumpulan rekaman yang ditentukan, lalu menyimpannya dalam variabel $RecordSet.
Perintah kedua dan ketiga adalah operasi off-line untuk menambahkan dua rekaman A ke kumpulan catatan.
Perintah terakhir menggunakan cmdlet **Set-AzDnsRecordSet** untuk melakukan pembaruan.

### Contoh 2: Memperbarui catatan SOA
```powershell
$RecordSet = Get-AzDnsRecordSet -Name "@" -RecordType SOA -Zone $Zone
$RecordSet.Records[0].Email = "admin.myzone.com"
Set-AzDnsRecordSet -RecordSet $RecordSet
```

Perintah pertama menggunakan cmdlet **Get-AzDnsRecordset** untuk mendapatkan kumpulan rekaman yang ditentukan, lalu menyimpannya dalam variabel $RecordSet.
Perintah kedua memperbarui catatan SOA yang ditentukan dalam $RecordSet.
Perintah akhir menggunakan cmdlet **Set-AzDnsRecordSet** untuk menyebarkan pembaruan dalam $RecordSet.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Timpa
Menunjukkan untuk memperbarui kumpulan catatan terlepas dari perubahan serentak.
Kumpulan catatan tidak akan diperbarui jika telah diubah di DNS Azure sejak objek **RecordSet** lokal diambil.
Ini memberikan perlindungan untuk perubahan serentak.
Untuk menyembunyikan perilaku ini, Anda bisa menggunakan parameter *Timpa* , yang menghasilkan kumpulan catatan yang diperbarui terlepas dari perubahan bersamaan.

```yaml
Type: System.Management.Automation.SwitchParameter
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
Type: Microsoft.Azure.Commands.Dns.DnsRecordSet
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
Type: System.Management.Automation.SwitchParameter
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
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Dns.DnsRecordSet

## OUTPUTS

### Microsoft.Azure.Commands.Dns.DnsRecordSet

## CATATAN
Anda dapat menggunakan parameter *Konfirmasi* untuk mengontrol apakah cmdlet ini meminta konfirmasi.
Secara default, cmdlet meminta Konfirmasi jika variabel $ConfirmPreference Windows PowerShell memiliki nilai Sedang atau lebih rendah.
Jika Anda menentukan *Konfirmasi* atau *Konfirmasi:$True*, cmdlet ini meminta anda untuk konfirmasi sebelum berjalan.
Jika Anda menentukan *Konfirmasi:$False*, cmdlet tidak meminta konfirmasi kepada Anda. 

## RELATED LINKS

[Get-AzDnsRecordSet](./Get-AzDnsRecordSet.md)

[New-AzDnsRecordSet](./New-AzDnsRecordSet.md)

[Remove-AzDnsRecordSet](./Remove-AzDnsRecordSet.md)
