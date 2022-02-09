---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Dns.dll-Help.xml
Module Name: Az.Dns
ms.assetid: 505562A4-30BC-44E7-94EF-579763B8D794
online version: https://docs.microsoft.com/powershell/module/az.dns/remove-azdnsrecordset
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Dns/Dns/help/Remove-AzDnsRecordSet.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Dns/Dns/help/Remove-AzDnsRecordSet.md
ms.openlocfilehash: e8bd035812b8a19b189c5281d3ff6ff7fe2b423e
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138313852"
---
# Remove-AzDnsRecordSet

## SYNOPSIS
Menghapus kumpulan catatan.

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

### Object
```
Remove-AzDnsRecordSet -RecordSet <DnsRecordSet> [-Overwrite] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzDnsRecordSet** menghapus kumpulan data tertentu dari zona yang ditentukan.
Anda tidak dapat menghapus rekaman SOA atau server nama (NS) yang secara otomatis dibuat di zona apex.
Anda dapat menyampaikan **objek RecordSet** ke cmdlet ini menggunakan operator pipeline atau sebagai parameter.
Untuk mengidentifikasi kumpulan rekaman berdasarkan nama dan tipe tanpa menggunakan objek **RecordSet** , Anda harus melewati zona sebagai objek **DnsZone** ke cmdlet ini menggunakan operator pipeline atau sebagai parameter, atau alternatifnya Anda dapat menentukan parameter *ZoneName* dan *ResourceGroupName* .
Anda dapat menggunakan parameter Konfirmasi dan $ConfirmPreference Windows PowerShell variabel untuk mengontrol apakah cmdlet meminta konfirmasi Anda.
Saat menentukan kumpulan data menggunakan objek **RecordSet** , kumpulan data tidak dihapus jika telah diubah di Azure DNS sejak objek **RecordSet** lokal diambil.
Ini menyediakan perlindungan untuk perubahan serentak.
Anda dapat menyembunyikan hal ini menggunakan parameter *Timpa* , yang menghapus kumpulan rekaman terlepas dari perubahan serentak.

## EXAMPLES

### Contoh 1: Menghapus kumpulan rekaman
```
PS C:\> $RecordSet = Get-AzDnsRecordSet -Name "www" -ResourceGroupName "MyResourceGroup" -ZoneName "myzone.com"
PS C:\> Remove-AzDnsRecordSet -RecordSet $RecordSet
```

Perintah pertama mendapatkan kumpulan data tertentu, lalu menyimpannya dalam $RecordSet tertentu. Perintah kedua menghapus kumpulan rekaman di $RecordSet.

### Contoh 2: Menghapus kumpulan data dan menyembunyikan semua konfirmasi
```
PS C:\> $RecordSet = Get-AzDnsRecordSet -Name "www" -ZoneName "myzone.com" -ResourceGroupName "MyResourceGroup"
PS C:\> Remove-AzDnsRecordSet -RecordSet $RecordSet -Confirm:$False -Overwrite

# Alternatively, the record set can be removed as follows.  In this case,
# because the record set is specified by name rather than by object, the
# Overwrite parameter is not applicable.

PS C:\> Remove-AzDnsRecordSet -Name "www" -ZoneName "myzone.com" -ResourceGroupName "MyResourceGroup" -Confirm:$False
```

Perintah pertama mendapatkan kumpulan data tertentu.
Perintah kedua menghapus kumpulan catatan tersebut, meskipun telah berubah untuk sementara.
Perintah konfirmasi akan disingggahkan.

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

### -Nama
Menentukan nama **RecordSet untuk** dihapus.
Saat menentukan kumpulan catatan menurut nama, zona DNS harus ditentukan *menggunakan parameter Zona* atau parameter *ZoneName* dan *ResourceGroupName* .
Alternatifnya, kumpulan rekaman dapat ditentukan menggunakan objek **RecordSet** , yang diteruskan menggunakan parameter *RecordSet* .

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

### -Overwrite
Saat menentukan kumpulan data menggunakan objek **RecordSet** , kumpulan data tidak dihapus jika telah diubah di Azure DNS sejak objek **RecordSet** lokal diambil.
Ini menyediakan perlindungan untuk perubahan serentak.
Hal ini dapat menyembunyikan penggunaan parameter *Overwrite* , yang menghapus kumpulan data terlepas dari perubahan serentak.

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
Alternatifnya, kumpulan catatan dapat ditentukan menggunakan parameter *Nama* dan *Zona* , atau menggunakan parameter *Nama*, *Nama ZoneName*, *dan ResourceGroupName* .

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
Nilai valid adalah:
- A
- AAAA
- CNAME
- MX
- NS
- PTR
- SRV
- Catatan TXT SOA akan dihapus secara otomatis saat zona dihapus.
Anda tidak dapat menghapus catatan SOA secara manual.

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
Menentukan grup sumber daya yang berisi zona DNS yang berisi **RecordSet untuk** dihapus.
Parameter ini hanya berlaku ketika kumpulan catatan dan zona DNS ditentukan menggunakan parameter *Nama dan* *Nama ZoneName* .
Alternatifnya, Anda dapat menentukan kumpulan rekaman menggunakan parameter *RecordSet* , atau *parameter Nama* *dan* Zona.

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

### -Zone
Menentukan zona DNS yang berisi **RecordSet yang** akan dihapus.
Parameter ini hanya berlaku ketika menentukan kumpulan data menggunakan parameter *Name* .
Alternatifnya, Anda bisa menentukan kumpulan catatan menggunakan parameter *RecordSet* , atau parameter *Name*, *ZoneName*, *dan ResourceGroupName* .

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
Menentukan nama zona yang berisi **RecordSet untuk** dihapus.
Anda juga harus menentukan *parameter Nama* dan *ResourceGroupName* .
Alternatifnya, kumpulan catatan dapat ditentukan menggunakan parameter *RecordSet* , atau *parameter Nama* *dan* Zona.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

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

## CATATAN
Anda dapat menggunakan parameter *Konfirmasi* untuk mengontrol apakah cmdlet ini meminta konfirmasi.
Secara default, cmdlet meminta konfirmasi Anda jika variabel $ConfirmPreference Windows PowerShell memiliki nilai Sedang atau lebih rendah.
Jika Anda menentukan *Konfirmasi* *atau Konfirmasi:$True* lanjut, cmdlet ini akan meminta konfirmasi sebelum dijalankan.
Jika Anda menentukan *Confirm:$False*, cmdlet tidak akan meminta konfirmasi Anda.

## RELATED LINKS

[Get-AzDnsRecordSet](./Get-AzDnsRecordSet.md)

[New-AzDnsRecordSet](./New-AzDnsRecordSet.md)

[Set-AzDnsRecordSet](./Set-AzDnsRecordSet.md)
