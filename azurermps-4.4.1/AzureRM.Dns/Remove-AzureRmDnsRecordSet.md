---
external help file: Microsoft.Azure.Commands.Dns.dll-Help.xml
Module Name: AzureRM.Dns
ms.assetid: 505562A4-30BC-44E7-94EF-579763B8D794
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Dns/Commands.Dns/help/Remove-AzureRmDnsRecordSet.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Dns/Commands.Dns/help/Remove-AzureRmDnsRecordSet.md
ms.openlocfilehash: e009eea8276bbfe9653c506864604ca955a6367f
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132426851"
---
# Remove-AzureRmDnsRecordSet

## SYNOPSIS
Menghapus kumpulan catatan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### Bidang
```
Remove-AzureRmDnsRecordSet -Name <String> -RecordType <RecordType> -ZoneName <String>
 -ResourceGroupName <String> [-Force] [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### Campuran
```
Remove-AzureRmDnsRecordSet -Name <String> -RecordType <RecordType> -Zone <DnsZone> [-Force] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Object
```
Remove-AzureRmDnsRecordSet -RecordSet <DnsRecordSet> [-Overwrite] [-Force] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureRmDnsRecordSet** menghapus kumpulan catatan tertentu dari zona yang ditentukan.
Anda tidak dapat menghapus rekaman SOA atau server nama (NS) yang secara otomatis dibuat di zona apex.

Anda dapat menyampaikan **objek RecordSet** ke cmdlet ini menggunakan operator pipeline atau sebagai parameter.
Untuk mengidentifikasi kumpulan rekaman berdasarkan nama dan tipe tanpa menggunakan objek **RecordSet,** Anda harus melewati zona sebagai objek **DnsZone** ke cmdlet ini menggunakan operator pipeline atau sebagai parameter, atau alternatifnya Anda dapat menentukan parameter *ZoneName* dan *ResourceGroupName.*

Anda bisa menggunakan parameter Konfirmasi dan $ConfirmPreference Windows PowerShell kontrol apakah cmdlet meminta konfirmasi Anda.

Saat menentukan kumpulan data menggunakan objek **RecordSet,** kumpulan data tidak dihapus jika telah diubah di Azure DNS sejak objek **RecordSet** lokal diambil.
Ini menyediakan perlindungan untuk perubahan serentak.
Anda dapat menyembunyikan hal ini menggunakan parameter *Timpa,* yang menghapus kumpulan rekaman terlepas dari perubahan serentak.

## EXAMPLES

### Contoh 1: Menghapus kumpulan rekaman
```
PS C:\> $RecordSet = Get-AzureRmDnsRecordSet -Name "www" -ResourceGroupName "MyResourceGroup" -ZoneName "myzone.com"
PS C:\> Remove-AzureRmDnsRecordSet -RecordSet $RecordSet
```

Perintah pertama mendapatkan kumpulan data tertentu, lalu menyimpannya dalam $RecordSet tertentu. Perintah kedua menghapus kumpulan rekaman di $RecordSet.

### Contoh 2: Menghapus kumpulan data dan menyembunyikan semua konfirmasi
```
PS C:\> $RecordSet = Get-AzureRmDnsRecordSet -Name "www" -ZoneName "myzone.com" -ResourceGroupName "MyResourceGroup"
PS C:\> Remove-AzureRmDnsRecordSet -RecordSet $RecordSet -Confirm:$False -Overwrite

# Alternatively, the record set can be removed as follows.  In this case,
# because the record set is specified by name rather than by object, the
# Overwrite parameter is not applicable.

PS C:\> Remove-AzureRmDnsRecordSet -Name "www" -ZoneName "myzone.com" -ResourceGroupName "MyResourceGroup" -Confirm:$False
```

Perintah pertama mendapatkan kumpulan data tertentu.

Perintah kedua menghapus kumpulan catatan tersebut, meskipun telah berubah untuk sementara.
Perintah konfirmasi akan disingggahkan.

## PARAMETERS

### -Force
Parameter ini tidak berlaku bagi cmdlet ini.
File akan dihapus pada rilis mendatang.

Untuk mengontrol apakah cmdlet ini meminta konfirmasi Anda, gunakan parameter *Konfirmasi.*

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

### -Nama
Menentukan nama **RecordSet untuk** dihapus.
Saat menentukan kumpulan catatan menurut nama, zona DNS harus ditentukan menggunakan *parameter* Zona atau parameter *ZoneName* dan *ResourceGroupName.*

Alternatifnya, kumpulan rekaman dapat ditentukan menggunakan objek **RecordSet,** yang diteruskan menggunakan parameter *RecordSet.*

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
Saat menentukan kumpulan data menggunakan objek **RecordSet,** kumpulan data tidak dihapus jika telah diubah di Azure DNS sejak objek **RecordSet** lokal diambil.
Ini menyediakan perlindungan untuk perubahan serentak.
Hal ini dapat menyembunyikan penggunaan parameter *Overwrite,* yang menghapus kumpulan data terlepas dari perubahan serentak.

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

Alternatifnya, kumpulan catatan dapat ditentukan  menggunakan parameter Nama dan *Zona,* atau menggunakan parameter *Nama,* *Nama ZoneName,* *dan ResourceGroupName.*

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
- TXT

Catatan SOA akan dihapus secara otomatis ketika zona dihapus.
Anda tidak dapat menghapus catatan SOA secara manual.

```yaml
Type: Microsoft.Azure.Management.Dns.Models.RecordType
Parameter Sets: Fields, Mixed
Aliases: 
Accepted values: A, AAAA, CNAME, MX, NS, PTR, SOA, SRV, TXT

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan grup sumber daya yang berisi zona DNS yang berisi **RecordSet untuk** dihapus.
Parameter ini hanya berlaku ketika kumpulan catatan dan zona DNS ditentukan menggunakan parameter *Nama dan* *Nama ZoneName.*

Alternatifnya, Anda dapat menentukan kumpulan rekaman menggunakan parameter *RecordSet,* atau *parameter Nama* *dan* Zona.

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
Parameter ini hanya berlaku ketika menentukan kumpulan data menggunakan parameter *Name.*

Alternatifnya, Anda dapat menentukan kumpulan data menggunakan parameter *RecordSet,* atau parameter *Name*, *ZoneName*, *dan ResourceGroupName.*

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
Anda juga harus menentukan *parameter Nama* dan *ResourceGroupName.*

Alternatifnya, kumpulan catatan dapat ditentukan menggunakan parameter *RecordSet,* atau *parameter Nama* *dan* Zona.

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

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Microsoft.Azure.Commands.Dns.DnsRecordSet
Anda dapat pipa objek **RecordSet** ke cmdlet ini.

## OUTPUTS

### Tidak ada
Cmdlet ini tidak menghasilkan output apa pun.

## CATATAN
Anda dapat menggunakan parameter *Konfirmasi* untuk mengontrol apakah cmdlet ini meminta konfirmasi.
Secara default, cmdlet meminta konfirmasi Anda jika variabel $ConfirmPreference Windows PowerShell memiliki nilai Sedang atau lebih rendah.

Jika Anda menentukan *Konfirmasi* *atau Konfirmasi:$True*, cmdlet ini akan meminta konfirmasi sebelum dijalankan.
Jika Anda menentukan *Confirm:$False*, cmdlet tidak akan meminta konfirmasi Anda.

## RELATED LINKS

[Get-AzureRmDnsRecordSet](./Get-AzureRmDnsRecordSet.md)

[New-AzureRmDnsRecordSet](./New-AzureRmDnsRecordSet.md)

[Set-AzureRmDnsRecordSet](./Set-AzureRmDnsRecordSet.md)
