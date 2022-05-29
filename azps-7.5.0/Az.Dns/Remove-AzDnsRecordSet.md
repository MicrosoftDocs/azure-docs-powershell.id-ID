---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Dns.dll-Help.xml
Module Name: Az.Dns
ms.assetid: 505562A4-30BC-44E7-94EF-579763B8D794
online version: https://docs.microsoft.com/powershell/module/az.dns/remove-azdnsrecordset
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Dns/Dns/help/Remove-AzDnsRecordSet.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Dns/Dns/help/Remove-AzDnsRecordSet.md
ms.openlocfilehash: 9bca6a1d675b96567e0ceba4464dcb8156f566d2
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145740358"
---
# Remove-AzDnsRecordSet

## SYNOPSIS
Menghapus kumpulan catatan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.dns/remove-azdnsrecordset) untuk informasi terbaru.

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
Cmdlet **Remove-AzDnsRecordSet** menghapus kumpulan catatan yang ditentukan dari zona yang ditentukan.
Anda tidak dapat menghapus rekaman SOA atau server nama (NS) yang secara otomatis dibuat di puncak zona.
Anda dapat meneruskan objek **RecordSet** ke cmdlet ini dengan menggunakan operator alur atau sebagai parameter.
Untuk mengidentifikasi kumpulan catatan berdasarkan nama dan jenis tanpa menggunakan objek **RecordSet** , Anda harus meneruskan zona sebagai objek **DnsZone** ke cmdlet ini dengan menggunakan operator alur atau sebagai parameter, atau Anda dapat menentukan parameter *ZoneName* dan *ResourceGroupName* .
Anda dapat menggunakan parameter Konfirmasi dan variabel $ConfirmPreference Windows PowerShell untuk mengontrol apakah cmdlet meminta konfirmasi.
Saat menentukan kumpulan catatan menggunakan objek **RecordSet** , kumpulan catatan tidak dihapus jika telah diubah di Azure DNS sejak objek **RecordSet** lokal diambil.
Ini memberikan perlindungan untuk perubahan bersamaan.
Anda dapat menekan ini dengan menggunakan parameter *Timpa* , yang menghapus kumpulan catatan terlepas dari perubahan bersamaan.

## EXAMPLES

### Contoh 1: Menghapus kumpulan catatan
```powershell
$RecordSet = Get-AzDnsRecordSet -Name "www" -ResourceGroupName "MyResourceGroup" -ZoneName "myzone.com"
Remove-AzDnsRecordSet -RecordSet $RecordSet
```

Perintah pertama mendapatkan kumpulan catatan yang ditentukan, lalu menyimpannya dalam variabel $RecordSet. Perintah kedua menghapus kumpulan catatan di $RecordSet.

### Contoh 2: Menghapus kumpulan catatan dan menyembunyikan semua konfirmasi
```powershell
$RecordSet = Get-AzDnsRecordSet -Name "www" -ZoneName "myzone.com" -ResourceGroupName "MyResourceGroup"
Remove-AzDnsRecordSet -RecordSet $RecordSet -Confirm:$False -Overwrite

# Alternatively, the record set can be removed as follows.  In this case,
# because the record set is specified by name rather than by object, the
# Overwrite parameter is not applicable.

Remove-AzDnsRecordSet -Name "www" -ZoneName "myzone.com" -ResourceGroupName "MyResourceGroup" -Confirm:$False
```

Perintah pertama mendapatkan kumpulan catatan yang ditentukan.
Perintah kedua menghapus kumpulan catatan, meskipun telah berubah sementara itu.
Perintah konfirmasi ditekan.

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

### -Name
Menentukan nama **RecordSet** yang akan dihapus.
Saat menentukan kumpulan catatan menurut nama, zona DNS harus ditentukan menggunakan parameter *Zona* atau parameter *ZoneName* dan *ResourceGroupName* .
Atau, kumpulan catatan dapat ditentukan menggunakan objek **RecordSet** , diteruskan menggunakan parameter *RecordSet* .

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
Ini memberikan perlindungan untuk perubahan bersamaan.
Ini dapat ditekan menggunakan parameter *Timpa* , yang menghapus kumpulan catatan terlepas dari perubahan bersamaan.

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
Menentukan objek **RecordSet** yang akan dihapus.
Atau, kumpulan catatan dapat ditentukan menggunakan parameter *Nama* dan *Zona* , atau menggunakan parameter *Nama*, *ZoneName*, dan *ResourceGroupName* .

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
Menentukan jenis catatan DNS.
Nilai yang valid adalah:
- A
- AAAA
- CNAME
- MX
- NS
- PTR
- SRV
- Catatan SOA TXT dihapus secara otomatis saat zona dihapus.
Anda tidak dapat menghapus rekaman SOA secara manual.

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
Menentukan grup sumber daya yang berisi zona DNS yang berisi **RecordSet** untuk dihapus.
Parameter ini hanya berlaku ketika kumpulan catatan dan zona DNS ditentukan menggunakan parameter *Nama* dan *ZoneName* .
Atau, Anda dapat menentukan kumpulan catatan menggunakan parameter *RecordSet* , atau parameter *Nama* dan *Zona* .

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
Menentukan zona DNS yang berisi **RecordSet** untuk dihapus.
Parameter ini hanya berlaku saat menentukan kumpulan catatan menggunakan parameter *Nama* .
Atau, Anda dapat menentukan kumpulan catatan menggunakan parameter *RecordSet* , atau parameter *Name*, *ZoneName*, dan *ResourceGroupName* .

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
Menentukan nama zona yang berisi **RecordSet** untuk dihapus.
Anda juga harus menentukan parameter *Nama* dan *ResourceGroupName* .
Atau, kumpulan catatan dapat ditentukan menggunakan parameter *RecordSet* , atau parameter *Nama* dan *Zona* .

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

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Management.Dns.Models.RecordType

### System.String

### Microsoft.Azure.Commands.Dns.DnsZone

### Microsoft.Azure.Commands.Dns.DnsRecordSet

## OUTPUTS

### System.Boolean

## NOTES
Anda dapat menggunakan parameter *Konfirmasi* untuk mengontrol apakah cmdlet ini meminta konfirmasi kepada Anda.
Secara default, cmdlet meminta konfirmasi kepada Anda jika variabel $ConfirmPreference Windows PowerShell memiliki nilai Sedang atau lebih rendah.
Jika Anda menentukan *Konfirmasi* atau *Konfirmasi:$True*, cmdlet ini akan meminta konfirmasi sebelum dijalankan.
Jika Anda menentukan *Confirm:$False*, cmdlet tidak meminta konfirmasi kepada Anda.

## RELATED LINKS

[Get-AzDnsRecordSet](./Get-AzDnsRecordSet.md)

[New-AzDnsRecordSet](./New-AzDnsRecordSet.md)

[Set-AzDnsRecordSet](./Set-AzDnsRecordSet.md)
