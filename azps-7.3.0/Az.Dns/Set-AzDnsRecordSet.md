---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Dns.dll-Help.xml
Module Name: Az.Dns
ms.assetid: 99E6C4DD-11AF-4DC0-848B-39811240BE06
online version: https://docs.microsoft.com/powershell/module/az.dns/set-azdnsrecordset
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Dns/Dns/help/Set-AzDnsRecordSet.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Dns/Dns/help/Set-AzDnsRecordSet.md
ms.openlocfilehash: 9f785de2b91b5f72b7f784e3af7fd1420f12abcf
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140004014"
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
Cmdlet **Set-AzDnsRecordSet** memperbarui kumpulan catatan di layanan Azure DNS dari objek **RecordSet** lokal.
Anda bisa melewati **objek RecordSet** sebagai parameter atau dengan menggunakan operator saluran.
Anda dapat menggunakan *perintah* Konfirmasi parameter $ConfirmPreference Windows PowerShell variabel untuk mengontrol apakah cmdlet meminta konfirmasi Anda.
Kumpulan catatan tidak diperbarui jika telah diubah di Azure DNS sejak objek **RecordSet** lokal diambil.
Ini menyediakan perlindungan untuk perubahan serentak.
Anda dapat menyembunyikan perilaku ini menggunakan parameter *Timpa* , yang memperbarui kumpulan rekaman terlepas dari perubahan serentak.

## EXAMPLES

### Contoh 1: Memperbarui kumpulan rekaman
```
PS C:\>$RecordSet = Get-AzDnsRecordSet -ResourceGroupName MyResourceGroup -ZoneName myzone.com -Name www -RecordType A
PS C:\> Add-AzDnsRecordConfig -RecordSet $RecordSet -Ipv4Address 172.16.0.0
PS C:\> Add-AzDnsRecordConfig -RecordSet $RecordSet -Ipv4Address 172.31.255.255
PS C:\> Set-AzDnsRecordSet -RecordSet $RecordSet

# These cmdlets can also be piped:

PS C:\> Get-AzDnsRecordSet -ResourceGroupName MyResourceGroup -ZoneName myzone.com -Name www -RecordType A | Add-AzDnsRecordConfig -Ipv4Address 172.16.0.0 | Add-AzDnsRecordConfig -Ipv4Address 172.31.255.255 | Set-AzDnsRecordSet
```

Perintah pertama menggunakan cmdlet Get-AzDnsRecordSet cmdlet untuk mendapatkan kumpulan data tertentu, lalu menyimpannya dalam $RecordSet variabel.
Perintah kedua dan ketiga adalah operasi yang tidak berjaga-sebentar untuk menambahkan dua data A ke kumpulan data.
Perintah final menggunakan cmdlet **Set-AzDnsRecordSet** untuk melakukan pembaruan.

### Contoh 2: Memperbarui rekaman SOA
```
PS C:\>$RecordSet = Get-AzDnsRecordSet -Name "@" -RecordType SOA -Zone $Zone
PS C:\> $RecordSet.Records[0].Email = "admin.myzone.com"
PS C:\> Set-AzDnsRecordSet -RecordSet $RecordSet
```

Perintah pertama menggunakan cmdlet **Get-AzDnsRecordset** untuk mendapatkan kumpulan data yang ditentukan, lalu menyimpannya dalam $RecordSet data.
Perintah kedua memperbarui data SOA tertentu di $RecordSet.
Perintah final menggunakan cmdlet **Set-AzDnsRecordSet** untuk menyebarkan pembaruan di $RecordSet.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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

### -Overwrite
Menunjukkan untuk memperbarui kumpulan catatan terlepas dari perubahan serentak.
Kumpulan catatan tidak akan diperbarui jika telah diubah di Azure DNS sejak objek **RecordSet** lokal diambil.
Ini menyediakan perlindungan untuk perubahan serentak.
Untuk menyembunyikan perilaku ini, Anda dapat menggunakan parameter *Overwrite* , yang menghasilkan kumpulan rekaman yang diperbarui terlepas dari perubahan serentak.

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
Menentukan **RecordSet untuk** diperbarui.

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
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak berjalan. Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Dns.DnsRecordSet

## OUTPUTS

### Microsoft.Azure.Commands.Dns.DnsRecordSet

## CATATAN
Anda dapat menggunakan parameter *Konfirmasi* untuk mengontrol apakah cmdlet ini meminta konfirmasi.
Secara default, cmdlet akan meminta konfirmasi Anda jika $ConfirmPreference Windows PowerShell variabel memiliki nilai Sedang atau lebih rendah.
Jika Anda menentukan *Konfirmasi* *atau Konfirmasi:$True* lanjut, cmdlet ini akan meminta konfirmasi sebelum dijalankan.
Jika Anda menentukan *Confirm:$False*, cmdlet tidak akan meminta konfirmasi Anda. 

## RELATED LINKS

[Get-AzDnsRecordSet](./Get-AzDnsRecordSet.md)

[New-AzDnsRecordSet](./New-AzDnsRecordSet.md)

[Remove-AzDnsRecordSet](./Remove-AzDnsRecordSet.md)
