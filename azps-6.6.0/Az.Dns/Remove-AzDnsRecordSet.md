---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Dns.dll-Help.xml
Module Name: Az.Dns
ms.assetid: 505562A4-30BC-44E7-94EF-579763B8D794
online version: https://docs.microsoft.com/powershell/module/az.dns/remove-azdnsrecordset
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Dns/Dns/help/Remove-AzDnsRecordSet.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Dns/Dns/help/Remove-AzDnsRecordSet.md
ms.openlocfilehash: c70fc7837943ae7ac06f7def6f94e98871e9c2ca
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143148639"
---
# Remove-AzDnsRecordSet

## SYNOPSIS
Menghapus kumpulan catatan.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.dns/remove-azdnsrecordset) untuk informasi terbaru.

## SYNTAX

### Bidang
```
Remove-AzDnsRecordSet -Name <String> -RecordType <RecordType> -ZoneName <String> -ResourceGroupName <String>
 [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Campuran
```
Remove-AzDnsRecordSet -Name <String> -RecordType <RecordType> -Zone <DnsZone> [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Objek
```
Remove-AzDnsRecordSet -RecordSet <DnsRecordSet> [-Overwrite] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzDnsRecordSet** menghapus kumpulan rekaman tertentu dari zona yang ditentukan.
Anda tidak dapat menghapus catatan SOA atau server nama (NS) yang secara otomatis dibuat di apex zona.
Anda dapat mengirimkan objek **RecordSet** ke cmdlet ini menggunakan operator pipeline atau sebagai parameter.
Untuk mengidentifikasi catatan yang diatur menurut nama dan mengetik tanpa menggunakan objek **RecordSet** , Anda harus melewati zona sebagai objek **DnsZone** ke cmdlet ini dengan menggunakan operator pipeline atau sebagai parameter, atau sebagai alternatif Anda bisa menentukan parameter *ZoneName* dan *ResourceGroupName* .
Anda dapat menggunakan variabel Konfirmasi parameter dan $ConfirmPreference Windows PowerShell untuk mengontrol apakah cmdlet meminta konfirmasi.
Saat menentukan kumpulan catatan menggunakan objek **RecordSet** , kumpulan catatan tidak dihapus jika telah diubah di Azure DNS sejak objek **RecordSet** lokal diambil.
Ini memberikan perlindungan untuk perubahan serentak.
Anda bisa menyembunyikan ini dengan menggunakan parameter *Timpa* , yang menghapus kumpulan rekaman terlepas dari perubahan bersamaan.

## EXAMPLES

### Contoh 1: Menghapus kumpulan catatan
```
PS C:\> $RecordSet = Get-AzDnsRecordSet -Name "www" -ResourceGroupName "MyResourceGroup" -ZoneName "myzone.com"
PS C:\> Remove-AzDnsRecordSet -RecordSet $RecordSet
```

Perintah pertama mendapatkan kumpulan rekaman yang ditentukan, lalu menyimpannya dalam variabel $RecordSet. Perintah kedua menghapus kumpulan catatan dalam $RecordSet.

### Contoh 2: Menghapus kumpulan rekaman dan menyembunyikan semua konfirmasi
```
PS C:\> $RecordSet = Get-AzDnsRecordSet -Name "www" -ZoneName "myzone.com" -ResourceGroupName "MyResourceGroup"
PS C:\> Remove-AzDnsRecordSet -RecordSet $RecordSet -Confirm:$False -Overwrite

# Alternatively, the record set can be removed as follows.  In this case,
# because the record set is specified by name rather than by object, the
# Overwrite parameter is not applicable.

PS C:\> Remove-AzDnsRecordSet -Name "www" -ZoneName "myzone.com" -ResourceGroupName "MyResourceGroup" -Confirm:$False
```

Perintah pertama akan mendapatkan kumpulan rekaman yang ditentukan.
Perintah kedua menghapus kumpulan catatan, bahkan jika telah berubah sementara itu.
Perintah konfirmasi disempurnakan.

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

### -Nama
Menentukan nama **Kumpulan Data** untuk dihapus.
Saat menentukan catatan yang diatur menurut nama, zona DNS harus ditentukan menggunakan parameter *Zona* atau parameter *ZoneName* dan *ResourceGroupName* .
Alternatifnya, kumpulan catatan dapat ditentukan menggunakan objek **RecordSet** , yang dikirim menggunakan parameter *RecordSet* .

```yaml
Type: System.String
Parameter Sets: Fields, Mixed
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Timpa
Saat menentukan kumpulan catatan menggunakan objek **RecordSet** , kumpulan catatan tidak dihapus jika telah diubah di Azure DNS sejak objek **RecordSet** lokal diambil.
Ini memberikan perlindungan untuk perubahan serentak.
Ini dapat disempurnakan menggunakan parameter *Timpa* , yang menghapus kumpulan rekaman terlepas dari perubahan bersamaan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Object
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
passthru

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
Menentukan objek **RecordSet** untuk dihapus.
Alternatifnya, kumpulan catatan dapat ditentukan menggunakan parameter *Nama* dan *Zona* , atau menggunakan parameter *Name*, *ZoneName*, dan *ResourceGroupName* .

```yaml
Type: Microsoft.Azure.Commands.Dns.DnsRecordSet
Parameter Sets: Object
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -RecordType
Menentukan tipe catatan DNS.
Nilai yang valid adalah:
- J
- AAAA
- CNAME
- MX
- NS
- PTR
- SRV
- Rekaman SOA TXT dihapus secara otomatis saat zona dihapus.
Anda tidak bisa menghapus catatan SOA secara manual.

```yaml
Type: Microsoft.Azure.Management.Dns.Models.RecordType
Parameter Sets: Fields, Mixed
Aliases:
Accepted values: A, AAAA, CAA, CNAME, MX, NS, PTR, SOA, SRV, TXT

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan grup sumber daya yang berisi zona DNS yang berisi **Kumpulan Rekaman** untuk dihapus.
Parameter ini hanya berlaku ketika kumpulan catatan dan zona DNS ditentukan menggunakan parameter *Nama* dan *Nama Zona* .
Alternatifnya, Anda dapat menentukan kumpulan rekaman menggunakan parameter *RecordSet* , atau parameter *Name* and *Zone* .

```yaml
Type: System.String
Parameter Sets: Fields
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Zona
Menentukan zona DNS yang berisi **KumpulanData** untuk dihapus.
Parameter ini hanya berlaku ketika menentukan kumpulan rekaman menggunakan parameter *Nama* .
Alternatifnya, Anda dapat menentukan kumpulan catatan menggunakan parameter *RecordSet* , atau parameter *Name*, *ZoneName*, dan *ResourceGroupName* .

```yaml
Type: Microsoft.Azure.Commands.Dns.DnsZone
Parameter Sets: Mixed
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ZoneName
Menentukan nama zona yang berisi **Kumpulan Data** untuk dihapus.
Anda juga harus menentukan parameter *Nama* dan *ResourceGroupName* .
Alternatifnya, kumpulan catatan dapat ditentukan menggunakan parameter *RecordSet* , atau parameter *Nama* dan *Zona* .

```yaml
Type: System.String
Parameter Sets: Fields
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak dijalankan.

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

### Microsoft.Azure.Management.Dns.Models.RecordType

### System.String

### Microsoft.Azure.Commands.Dns.DnsZone

### Microsoft.Azure.Commands.Dns.DnsRecordSet

## OUTPUTS

### System.Boolean

## NOTES
Anda dapat menggunakan parameter *Konfirmasi* untuk mengontrol apakah cmdlet ini meminta konfirmasi.
Secara default, cmdlet meminta Konfirmasi jika variabel $ConfirmPreference Windows PowerShell memiliki nilai Sedang atau lebih rendah.
Jika Anda menentukan *Konfirmasi* atau *Konfirmasi:$True*, cmdlet ini meminta anda untuk konfirmasi sebelum berjalan.
Jika Anda menentukan *Konfirmasi:$False*, cmdlet tidak meminta konfirmasi kepada Anda.

## RELATED LINKS

[Get-AzDnsRecordSet](./Get-AzDnsRecordSet.md)

[New-AzDnsRecordSet](./New-AzDnsRecordSet.md)

[Set-AzDnsRecordSet](./Set-AzDnsRecordSet.md)
