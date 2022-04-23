---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Dns.dll-Help.xml
Module Name: Az.Dns
ms.assetid: D1A2326C-CD41-45A6-B37A-FC6176193B01
online version: https://docs.microsoft.com/powershell/module/az.dns/remove-azdnsrecordconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Dns/Dns/help/Remove-AzDnsRecordConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Dns/Dns/help/Remove-AzDnsRecordConfig.md
ms.openlocfilehash: eacf2cc53e78cbcabd112aafb598a95ea59cd263
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143287505"
---
# Remove-AzDnsRecordConfig

## SYNOPSIS
Menghapus catatan DNS dari objek kumpulan catatan lokal.

## SYNTAX

### J
```
Remove-AzDnsRecordConfig -RecordSet <DnsRecordSet> -Ipv4Address <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### AAAA
```
Remove-AzDnsRecordConfig -RecordSet <DnsRecordSet> -Ipv6Address <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### NS
```
Remove-AzDnsRecordConfig -RecordSet <DnsRecordSet> -Nsdname <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### MX
```
Remove-AzDnsRecordConfig -RecordSet <DnsRecordSet> -Exchange <String> -Preference <UInt16>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### PTR
```
Remove-AzDnsRecordConfig -RecordSet <DnsRecordSet> -Ptrdname <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### TXT
```
Remove-AzDnsRecordConfig -RecordSet <DnsRecordSet> -Value <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### SRV
```
Remove-AzDnsRecordConfig -RecordSet <DnsRecordSet> -Priority <UInt16> -Target <String> -Port <UInt16>
 -Weight <UInt16> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### CNAME
```
Remove-AzDnsRecordConfig -RecordSet <DnsRecordSet> -Cname <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### Caa
```
Remove-AzDnsRecordConfig -RecordSet <DnsRecordSet> -CaaFlags <Byte> -CaaTag <String> -CaaValue <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzDnsRecordConfig** menghapus catatan Domain Name System (DNS) dari kumpulan catatan.
Objek **RecordSet** adalah objek offline, dan perubahannya tidak mengubah respons DNS hingga Anda menjalankan cmdlet Set-AzDnsRecordSet untuk tetap melakukan perubahan ke layanan MICROSOFT AZURE DNS.
Untuk menghapus catatan, semua bidang untuk tipe catatan tersebut harus sama persis.
Anda tidak bisa menambahkan atau menghapus catatan SOA.
Catatan SOA dibuat secara otomatis ketika zona DNS dibuat dan dihapus secara otomatis saat zona DNS dihapus.
Anda dapat mengirimkan objek **RecordSet** ke cmdlet ini sebagai parameter atau menggunakan operator pipeline.

## EXAMPLES

### Contoh 1: Menghapus catatan A dari kumpulan catatan
```powershell
$RecordSet = Get-AzDnsRecordSet -Name "www" -RecordType A -ResourceGroupName "MyResourceGroup" -ZoneName "myzone.com"
Remove-AzDnsRecordConfig -RecordSet $RecordSet -Ipv4Address 1.2.3.4
Set-AzDnsRecordSet -RecordSet $RecordSet

# The above sequence can also be piped:

Get-AzDnsRecordSet -Name "www" -RecordType A -ResourceGroupName "MyResourceGroup" -ZoneName "myzone.com" | Remove-AzDnsRecordConfig -Ipv4Address 1.2.3.4 | Set-AzDnsRecordSet
```

Contoh ini menghapus catatan A dari kumpulan catatan yang sudah ada.
Jika ini adalah satu-satunya catatan dalam kumpulan catatan, hasilnya akan berupa kumpulan catatan kosong.
Untuk menghapus kumpulan catatan secara keseluruhan, lihat Remove-AzDnsRecordSet.

### Contoh 2: Menghapus catatan AAAA dari kumpulan rekaman
```powershell
$RecordSet = Get-AzDnsRecordSet -Name "www" -RecordType AAAA -ResourceGroupName "MyResourceGroup" -ZoneName "myzone.com"
Remove-AzDnsRecordConfig -RecordSet $RecordSet -Ipv6Address 2001:DB80:4009:1803::1005
Set-AzDnsRecordSet -RecordSet $RecordSet

# The above sequence can also be piped:

Get-AzDnsRecordSet -Name "www" -RecordType AAAA -ResourceGroupName "MyResourceGroup" -ZoneName "myzone.com" | Remove-AzDnsRecordConfig -Ipv6Address 2001:DB80:4009:1803::1005 | Set-AzDnsRecordSet
```

Contoh ini menghapus catatan AAAA dari kumpulan catatan yang sudah ada.
Jika ini adalah satu-satunya catatan dalam kumpulan catatan, hasilnya akan berupa kumpulan catatan kosong.
Untuk menghapus kumpulan catatan secara keseluruhan, lihat Remove-AzDnsRecordSet.

### Contoh 3: Menghapus catatan CNAME dari kumpulan catatan
```powershell
$RecordSet = Get-AzDnsRecordSet -Name "www" -RecordType CNAME -ResourceGroupName "MyResourceGroup" -ZoneName "myzone.com"
Remove-AzDnsRecordConfig -RecordSet $RecordSet -Cname contoso.com
Set-AzDnsRecordSet -RecordSet $RecordSet

# The above sequence can also be piped:

Get-AzDnsRecordSet -Name "www" -RecordType CNAME -ResourceGroupName "MyResourceGroup" -ZoneName "myzone.com" | Remove-AzDnsRecordConfig -Cname contoso.com | Set-AzDnsRecordSet
```

Contoh ini menghapus catatan CNAME dari kumpulan catatan yang sudah ada.
Karena kumpulan catatan CNAME bisa berisi paling banyak satu catatan, hasilnya adalah kumpulan catatan kosong.

### Contoh 4: Menghapus rekaman MX dari kumpulan catatan
```powershell
$RecordSet = Get-AzDnsRecordSet -Name "@" -RecordType MX -ResourceGroupName "MyResourceGroup" -ZoneName "myzone.com"
Remove-AzDnsRecordConfig -Exchange mail.microsoft.com -Preference 5 -RecordSet $RecordSet
Set-AzDnsRecordSet -RecordSet $RecordSet

# The above sequence can also be piped:

Get-AzDnsRecordSet -Name "@" -RecordType MX -ResourceGroupName "MyResourceGroup" -ZoneName "myzone.com" | Remove-AzDnsRecordConfig -Exchange mail.microsoft.com -Preference 5 | Set-AzDnsRecordSet
```

Contoh ini menghapus catatan MX dari kumpulan catatan yang sudah ada.
Nama catatan "@" menunjukkan kumpulan catatan di zona apex.
Jika ini adalah satu-satunya catatan dalam kumpulan catatan, hasilnya adalah kumpulan catatan kosong.
Untuk menghapus kumpulan catatan secara keseluruhan, lihat Remove-AzDnsRecordSet.

### Contoh 5: Menghapus catatan NS dari kumpulan catatan
```powershell
$RecordSet = Get-AzDnsRecordSet -Name "abc" -RecordType NS -ResourceGroupName "MyResourceGroup" -ZoneName "myzone.com"
Remove-AzDnsRecordConfig -Nsdname ns1.myzone.com -RecordSet $RecordSet
Set-AzDnsRecordSet -RecordSet $RecordSet

# The above sequence can also be piped:

Get-AzDnsRecordSet -Name "abc" -RecordType NS -ResourceGroupName "MyResourceGroup" -ZoneName "myzone.com" | Remove-AzDnsRecordConfig -Nsdname "ns1.myzone.com" | Set-AzDnsRecordSet
```

Contoh ini menghapus catatan NS dari kumpulan catatan yang sudah ada.
Jika ini adalah satu-satunya catatan dalam kumpulan catatan, hasilnya adalah kumpulan catatan kosong.
Untuk menghapus kumpulan catatan secara keseluruhan, lihat Remove-AzDnsRecordSet.

### Contoh 6: Menghapus catatan PTR dari kumpulan rekaman
```powershell
$RecordSet = Get-AzDnsRecordSet -Name "4" -RecordType PTR -ResourceGroupName "MyResourceGroup" -ZoneName 3.2.1.in-addr.arpa
Remove-AzDnsRecordConfig -Ptrdname www.contoso.com -RecordSet $RecordSet
Set-AzDnsRecordSet -RecordSet $RecordSet

# The above sequence can also be piped:

Get-AzDnsRecordSet -Name "4" -RecordType PTR -ResourceGroupName "MyResourceGroup" -ZoneName "3.2.1.in-addr.arpa" | Remove-AzDnsRecordConfig -Ptrdname www.contoso.com | Set-AzDnsRecordSet
```

Contoh ini menghapus catatan PTR dari kumpulan catatan yang sudah ada.
Jika ini adalah satu-satunya catatan dalam kumpulan catatan, hasilnya adalah kumpulan catatan kosong.
Untuk menghapus kumpulan catatan secara keseluruhan, lihat Remove-AzDnsRecordSet.

### Contoh 7: Menghapus catatan SRV dari kumpulan catatan
```powershell
$RecordSet = Get-AzDnsRecordSet -Name "_sip._tcp" -RecordType SRV -ResourceGroupName "MyResourceGroup" -ZoneName "myzone.com"
Remove-AzDnsRecordConfig -RecordSet $RecordSet -Priority 0 -Weight 5 -Port 8080 -Target target.example.com
Set-AzDnsRecordSet -RecordSet $RecordSet

# The above sequence can also be piped:

Get-AzDnsRecordSet -Name "_sip._tcp" -RecordType SRV -ResourceGroupName "MyResourceGroup" -ZoneName "myzone.com" | Remove-AzDnsRecordConfig -Priority 0 -Weight 5 -Port 8080 -Target target.example.com  | Set-AzDnsRecordSet
```

Contoh ini menghapus catatan SRV dari kumpulan catatan yang sudah ada.
Jika ini adalah satu-satunya catatan dalam kumpulan catatan, hasilnya adalah kumpulan catatan kosong.
Untuk menghapus kumpulan catatan secara keseluruhan, lihat Remove-AzDnsRecordSet.

### Contoh 8: Menghapus catatan TXT dari kumpulan catatan
```powershell
$RecordSet = Get-AzDnsRecordSet -Name "text" -RecordType TXT -ResourceGroupName "MyResourceGroup" -ZoneName "myzone.com"
Remove-AzDnsRecordConfig -RecordSet $RecordSet -Value "This is a TXT Record"
Set-AzDnsRecordSet -RecordSet $RecordSet

# The above sequence can also be piped:

Get-AzDnsRecordSet -Name "text" -RecordType TXT -ResourceGroupName "MyResourceGroup" -ZoneName "myzone.com" | Remove-AzDnsRecordConfig -Value "This is a TXT Record"  | Set-AzDnsRecordSet
```

Contoh ini menghapus catatan TXT dari kumpulan catatan yang sudah ada.
Jika ini adalah satu-satunya catatan dalam kumpulan catatan, hasilnya adalah kumpulan catatan kosong.
Untuk menghapus kumpulan catatan secara keseluruhan, lihat Remove-AzDnsRecordSet.

## PARAMETERS

### -CaaFlags
Bendera untuk catatan CAA untuk ditambahkan. Harus berupa angka antara 0 dan 255.

```yaml
Type: System.Byte
Parameter Sets: Caa
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CaaTag
Bidang tag catatan CAA untuk ditambahkan.

```yaml
Type: System.String
Parameter Sets: Caa
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CaaValue
Bidang nilai untuk catatan CAA untuk ditambahkan.

```yaml
Type: System.String
Parameter Sets: Caa
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Cname
Menentukan nama domain untuk catatan nama kanonis (CNAME).

```yaml
Type: System.String
Parameter Sets: CNAME
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

### -Exchange
Menentukan nama server mail exchange untuk catatan mail exchange (MX).

```yaml
Type: System.String
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
Type: System.String
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
Type: System.String
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
Type: System.String
Parameter Sets: NS
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Port
Menentukan port untuk data layanan (SRV).

```yaml
Type: System.UInt16
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
Type: System.UInt16
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
Type: System.UInt16
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
Type: System.String
Parameter Sets: PTR
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RecordSet
Menentukan objek **RecordSet** yang berisi catatan untuk dihapus.

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

### -Target
Menentukan target untuk catatan SRV.

```yaml
Type: System.String
Parameter Sets: SRV
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Value
Menentukan nilai untuk catatan TXT.

```yaml
Type: System.String
Parameter Sets: TXT
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Berat
Menentukan bobot untuk catatan SRV.

```yaml
Type: System.UInt16
Parameter Sets: SRV
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Dns.DnsRecordSet

### System.String

### System.UInt16

### System.Byte

## OUTPUTS

### Microsoft.Azure.Commands.Dns.DnsRecordSet

## NOTES

## RELATED LINKS

[Add-AzDnsRecordConfig](./Add-AzDnsRecordConfig.md)

[Get-AzDnsRecordSet](./Get-AzDnsRecordSet.md)

[Set-AzDnsRecordSet](./Set-AzDnsRecordSet.md)
