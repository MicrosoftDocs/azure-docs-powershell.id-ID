---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Dns.dll-Help.xml
Module Name: Az.Dns
ms.assetid: D1A2326C-CD41-45A6-B37A-FC6176193B01
online version: https://docs.microsoft.com/en-us/powershell/module/az.dns/remove-azdnsrecordconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Dns/Dns/help/Remove-AzDnsRecordConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Dns/Dns/help/Remove-AzDnsRecordConfig.md
ms.openlocfilehash: e00b31783554b8ea70760809c36f23a6a62575ca
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132426218"
---
# Remove-AzDnsRecordConfig

## SYNOPSIS
Menghapus catatan DNS dari objek kumpulan catatan lokal.

## SYNTAX

### A
```
Remove-AzDnsRecordConfig -RecordSet <DnsRecordSet> -Ipv4Address <String> [<CommonParameters>]
```

### AAAA
```
Remove-AzDnsRecordConfig -RecordSet <DnsRecordSet> -Ipv6Address <String> [<CommonParameters>]
```

### NS
```
Remove-AzDnsRecordConfig -RecordSet <DnsRecordSet> -Nsdname <String> [<CommonParameters>]
```

### MX
```
Remove-AzDnsRecordConfig -RecordSet <DnsRecordSet> -Exchange <String> -Preference <UInt16>
 [<CommonParameters>]
```

### PTR
```
Remove-AzDnsRecordConfig -RecordSet <DnsRecordSet> -Ptrdname <String> [<CommonParameters>]
```

### TXT
```
Remove-AzDnsRecordConfig -RecordSet <DnsRecordSet> -Value <String> [<CommonParameters>]
```

### SRV
```
Remove-AzDnsRecordConfig -RecordSet <DnsRecordSet> -Priority <UInt16> -Target <String> -Port <UInt16>
 -Weight <UInt16> [<CommonParameters>]
```

### CNAME
```
Remove-AzDnsRecordConfig -RecordSet <DnsRecordSet> -Cname <String> [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzDnsRecordConfig** menghapus catatan Domain Name System (DNS) dari kumpulan catatan.
Objek **RecordSet** merupakan objek offline, dan perubahan pada objek tersebut tidak mengubah respons DNS hingga Anda menjalankan cmdlet Set-AzDnsRecordSet untuk tetap menyimpan perubahan ke Microsoft Azure DNS.

Untuk menghapus catatan, semua bidang untuk tipe catatan tersebut harus benar-benar cocok.
Anda tidak bisa menambahkan atau menghapus catatan SOA.
Catatan SOA secara otomatis dibuat saat zona DNS dibuat dan dihapus secara otomatis saat zona DNS dihapus.

Anda dapat menyampaikan **objek RecordSet** ke cmdlet ini sebagai parameter atau menggunakan operator pipeline.

## EXAMPLES

### Contoh 1: Menghapus rekaman A dari kumpulan catatan
```
PS C:\> $RecordSet = Get-AzDnsRecordSet -Name "www" -RecordType A -ResouceGroupName "MyResourceGroup" -ZoneName "myzone.com"
PS C:\> Remove-AzDnsRecordConfig -RecordSet $RecordSet -Ipv4Address 1.2.3.4
PS C:\> Set-AzDnsRecordSet -RecordSet $RecordSet

# The above sequence can also be piped:

PS C:\> Get-AzDnsRecordSet -Name "www" -RecordType A -ResouceGroupName "MyResourceGroup" -ZoneName "myzone.com" | Remove-AzDnsRecordConfig -Ipv4Address 1.2.3.4 | Set-AzDnsRecordSet
```

Contoh ini menghapus catatan A dari kumpulan catatan yang sudah ada.
Jika ini adalah satu-satunya rekaman dalam kumpulan rekaman, hasilnya akan menjadi kumpulan rekaman kosong.
Untuk menghapus kumpulan catatan secara keseluruhan, lihat Remove-AzDnsRecordSet.

### Contoh 2: Menghapus catatan AAAA dari kumpulan catatan
```
PS C:\> $RecordSet = Get-AzDnsRecordSet -Name "www" -RecordType AAAA -ResouceGroupName "MyResourceGroup" -ZoneName "myzone.com"
PS C:\> Remove-AzDnsRecordConfig -RecordSet $RecordSet -Ipv6Address 2001:DB80:4009:1803::1005
PS C:\> Set-AzDnsRecordSet -RecordSet $RecordSet

# The above sequence can also be piped:

PS C:\> Get-AzDnsRecordSet -Name "www" -RecordType AAAA -ResouceGroupName "MyResourceGroup" -ZoneName "myzone.com" | Remove-AzDnsRecordConfig -Ipv6Address 2001:DB80:4009:1803::1005 | Set-AzDnsRecordSet
```

Contoh ini menghapus catatan AAAA dari kumpulan catatan yang sudah ada.
Jika ini adalah satu-satunya rekaman dalam kumpulan rekaman, hasilnya akan menjadi kumpulan rekaman kosong.
Untuk menghapus kumpulan catatan secara keseluruhan, lihat Remove-AzDnsRecordSet.

### Contoh 3: Menghapus data CNAME dari kumpulan data
```
PS C:\> $RecordSet = Get-AzDnsRecordSet -Name "www" -RecordType CNAME -ResouceGroupName "MyResourceGroup" -ZoneName "myzone.com"
PS C:\> Remove-AzDnsRecordConfig -RecordSet $RecordSet -Cname contoso.com
PS C:\> Set-AzDnsRecordSet -RecordSet $RecordSet

# The above sequence can also be piped:

PS C:\> Get-AzDnsRecordSet -Name "www" -RecordType CNAME -ResouceGroupName "MyResourceGroup" -ZoneName "myzone.com" | Remove-AzDnsRecordConfig -Cname contoso.com | Set-AzDnsRecordSet
```

Contoh ini menghapus data CNAME dari kumpulan data yang sudah ada.
Karena kumpulan data CNAME dapat berisi paling banyak satu data, hasilnya adalah kumpulan catatan kosong.

### Contoh 4: Menghapus rekaman MX dari kumpulan rekaman
```
PS C:\> $RecordSet = Get-AzDnsRecordSet -Name "@" -RecordType MX -ResouceGroupName "MyResourceGroup" -ZoneName "myzone.com"
PS C:\> Remove-AzDnsRecordConfig -Exchange mail.microsoft.com -Preference 5 -RecordSet $RecordSet
PS C:\> Set-AzDnsRecordSet -RecordSet $RecordSet

# The above sequence can also be piped:

PS C:\> Get-AzDnsRecordSet -Name "@" -RecordType MX -ResouceGroupName "MyResourceGroup" -ZoneName "myzone.com" | Remove-AzDnsRecordConfig -Exchange mail.microsoft.com -Preference 5 | Set-AzDnsRecordSet
```

Contoh ini menghapus rekaman MX dari kumpulan catatan yang sudah ada.
Nama catatan "@" menunjukkan kumpulan data pada zona apex.
Jika ini satu-satunya rekaman dalam kumpulan rekaman, hasilnya adalah kumpulan rekaman kosong.
Untuk menghapus kumpulan catatan secara keseluruhan, lihat Remove-AzDnsRecordSet.

### Contoh 5: Menghapus catatan NS dari kumpulan catatan
```
PS C:\> $RecordSet = Get-AzDnsRecordSet -Name "abc" -RecordType NS -ResouceGroupName "MyResourceGroup" -ZoneName "myzone.com"
PS C:\> Remove-AzDnsRecordConfig -Nsdname ns1.myzone.com -RecordSet $RecordSet
PS C:\> Set-AzDnsRecordSet -RecordSet $RecordSet

# The above sequence can also be piped:

PS C:\> Get-AzDnsRecordSet -Name "abc" -RecordType NS -ResouceGroupName "MyResourceGroup" -ZoneName "myzone.com" | Remove-AzDnsRecordConfig -Nsdname "ns1.myzone.com" | Set-AzDnsRecordSet
```

Contoh ini menghapus catatan NS dari kumpulan catatan yang ada.
Jika ini satu-satunya rekaman dalam kumpulan rekaman, hasilnya adalah kumpulan rekaman kosong.
Untuk menghapus kumpulan catatan secara keseluruhan, lihat Remove-AzDnsRecordSet.

### Contoh 6: Menghapus catatan PTR dari kumpulan catatan
```
PS C:\> $RecordSet = Get-AzDnsRecordSet -Name "4" -RecordType PTR -ResouceGroupName "MyResourceGroup" -ZoneName 3.2.1.in-addr.arpa
PS C:\> Remove-AzDnsRecordConfig -Ptrdname www.contoso.com -RecordSet $RecordSet
PS C:\> Set-AzDnsRecordSet -RecordSet $RecordSet

# The above sequence can also be piped:

PS C:\> Get-AzDnsRecordSet -Name "4" -RecordType PTR -ResouceGroupName "MyResourceGroup" -ZoneName "3.2.1.in-addr.arpa" | Remove-AzDnsRecordConfig -Ptrdname www.contoso.com | Set-AzDnsRecordSet
```

Contoh ini menghapus rekaman PTR dari kumpulan catatan yang ada.
Jika ini satu-satunya rekaman dalam kumpulan rekaman, hasilnya adalah kumpulan rekaman kosong.
Untuk menghapus kumpulan catatan secara keseluruhan, lihat Remove-AzDnsRecordSet.

### Contoh 7: Menghapus catatan SRV dari kumpulan catatan
```
PS C:\> $RecordSet = Get-AzDnsRecordSet -Name "_sip._tcp" -RecordType SRV -ResouceGroupName "MyResourceGroup" -ZoneName "myzone.com"
PS C:\> Remove-AzDnsRecordConfig -RecordSet $RecordSet -Priority 0 -Weight 5 -Port 8080 -Target target.example.com
PS C:\> Set-AzDnsRecordSet -RecordSet $RecordSet

# The above sequence can also be piped:

PS C:\> Get-AzDnsRecordSet -Name "_sip._tcp" -RecordType SRV -ResouceGroupName "MyResourceGroup" -ZoneName "myzone.com" | Remove-AzDnsRecordConfig -Priority 0 -Weight 5 -Port 8080 -Target target.example.com  | Set-AzDnsRecordSet
```

Contoh ini menghapus catatan SRV dari kumpulan catatan yang sudah ada.
Jika ini satu-satunya rekaman dalam kumpulan rekaman, hasilnya adalah kumpulan rekaman kosong.
Untuk menghapus kumpulan catatan secara keseluruhan, lihat Remove-AzDnsRecordSet.

### Contoh 8: Menghapus rekaman TXT dari kumpulan catatan
```
PS C:\> $RecordSet = Get-AzDnsRecordSet -Name "text" -RecordType TXT -ResouceGroupName "MyResourceGroup" -ZoneName "myzone.com"
PS C:\> Remove-AzDnsRecordConfig -RecordSet $RecordSet -Value "This is a TXT Record"
PS C:\> Set-AzDnsRecordSet -RecordSet $RecordSet

# The above sequence can also be piped:

PS C:\> Get-AzDnsRecordSet -Name "text" -RecordType TXT -ResouceGroupName "MyResourceGroup" -ZoneName "myzone.com" | Remove-AzDnsRecordConfig -Value "This is a TXT Record"  | Set-AzDnsRecordSet
```

Contoh ini menghapus rekaman TXT dari kumpulan catatan yang ada.
Jika ini satu-satunya rekaman dalam kumpulan rekaman, hasilnya adalah kumpulan rekaman kosong.
Untuk menghapus kumpulan catatan secara keseluruhan, lihat Remove-AzDnsRecordSet.

## PARAMETERS

### -Cname
Menentukan nama domain untuk catatan nama kanonis (CNAME).

```yaml
Type: String
Parameter Sets: CNAME
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Exchange
Menentukan nama server mail exchange untuk rekaman mail exchange (MX).

```yaml
Type: String
Parameter Sets: MX
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Ipv4Address
Menentukan alamat IPv4 untuk catatan A.

```yaml
Type: String
Parameter Sets: A
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Ipv6Address
Menentukan alamat IPv6 untuk catatan AAAA.

```yaml
Type: String
Parameter Sets: AAAA
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nsdname
Menentukan server nama untuk catatan server nama (NS).

```yaml
Type: String
Parameter Sets: NS
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Port
Menentukan port untuk catatan layanan (SRV).

```yaml
Type: UInt16
Parameter Sets: SRV
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Preferensi
Menentukan preferensi untuk catatan MX.

```yaml
Type: UInt16
Parameter Sets: MX
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Prioritas
Menentukan prioritas untuk catatan SRV.

```yaml
Type: UInt16
Parameter Sets: SRV
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Ptrdname
Menentukan nama domain target catatan penunjuk (PTR).

```yaml
Type: String
Parameter Sets: PTR
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RecordSet
Menentukan objek **RecordSet** yang berisi data yang akan dihapus.

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

### -Target
Menentukan target untuk catatan SRV.

```yaml
Type: String
Parameter Sets: SRV
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Value
Menentukan nilai untuk rekaman TXT.

```yaml
Type: String
Parameter Sets: TXT
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Bobot
Menentukan bobot untuk catatan SRV.

```yaml
Type: UInt16
Parameter Sets: SRV
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Microsoft.Azure.Commands.Dns.DnsRecordSet
Anda dapat pipa objek **DnsRecordSet** ke cmdlet ini.
Ini adalah representasi offline kumpulan catatan dan pembaruan untuk kumpulan catatan itu tidak mengubah respons DNS hingga Anda menjalankan Set-AzDnsRecordSet.

## OUTPUTS

### Microsoft.Azure.Commands.Dns.DnsRecordSet
Cmdlet ini mengembalikan objek **RecordSet yang** diubah.

## CATATAN

## RELATED LINKS

[Add-AzDnsRecordConfig](./Add-AzDnsRecordConfig.md)

[Get-AzDnsRecordSet](./Get-AzDnsRecordSet.md)

[Set-AzDnsRecordSet](./Set-AzDnsRecordSet.md)
