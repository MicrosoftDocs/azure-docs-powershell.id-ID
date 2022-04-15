---
external help file: Microsoft.Azure.Commands.Dns.dll-Help.xml
ms.assetid: AD97BCAF-69BA-4C16-8B57-AB243D796B71
online version: ''
schema: 2.0.0
ms.openlocfilehash: 6368cffa168772a384deb99f5a8388aef84f85b2
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142362645"
---
# New-AzureRmDnsRecordConfig

## SYNOPSIS
Membuat objek lokal catatan DNS baru.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### J
```
New-AzureRmDnsRecordConfig -Ipv4Address <String> [<CommonParameters>]
```

### Aaaa
```
New-AzureRmDnsRecordConfig -Ipv6Address <String> [<CommonParameters>]
```

### Ns
```
New-AzureRmDnsRecordConfig -Nsdname <String> [<CommonParameters>]
```

### Mx
```
New-AzureRmDnsRecordConfig -Exchange <String> -Preference <UInt16> [<CommonParameters>]
```

### Ptr
```
New-AzureRmDnsRecordConfig -Ptrdname <String> [<CommonParameters>]
```

### Txt
```
New-AzureRmDnsRecordConfig -Value <String> [<CommonParameters>]
```

### Srv
```
New-AzureRmDnsRecordConfig -Priority <UInt16> -Target <String> -Port <UInt16> -Weight <UInt16>
 [<CommonParameters>]
```

### CName
```
New-AzureRmDnsRecordConfig -Cname <String> [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureRmDnsRecordConfig** membuat objek **DnsRecord** lokal.
Array objek ini diteruskan ke cmdlet New-AzureRmDnsRecordSet menggunakan parameter *DnsRecords* untuk menentukan rekaman yang akan dibuat dalam kumpulan catatan.

## EXAMPLES

### Contoh 1: Membuat Kumpulan Rekaman tipe A
```
PS C:\> $Records = @()
PS C:\> $Records += New-AzureRmDnsRecordConfig -IPv4Address 1.2.3.4
PS C:\> $RecordSet = New-AzureRmDnsRecordSet -Name "www" -RecordType A -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -DnsRecords $Records

# When creating a RecordSet containing a single record, the above sequence can also be condensed into a single line:

PS C:\> $RecordSet = New-AzureRmDnsRecordSet -Name "www" -RecordType A -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -DnsRecords (New-AzureRmDnsRecordConfig -IPv4Address 1.2.3.4)

# To create a record set containing multiple records, use New-AzureRmDnsRecordConfig to add each record to the $Records array,
# then call New-AzureRmDnsRecordSet, as follows:

PS C:\> $Records = @()
PS C:\> $Records += New-AzureRmDnsRecordConfig -IPv4Address 1.2.3.4
PS C:\> $Records += New-AzureRmDnsRecordConfig -IPv4Address 5.6.7.8
PS C:\> $RecordSet = New-AzureRmDnsRecordSet -Name "www" -RecordType A -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -DnsRecords $Records
```

Contoh ini membuat **RecordSet** bernama www di zona myzone.com.
Kumpulan catatan adalah tipe A dan memiliki TTL 1 jam (3600 detik).
Ini berisi satu catatan DNS.

### Contoh 2: Membuat Kumpulan Rekaman dari tipe AAAA
```
PS C:\> $Records = @()
PS C:\> $Records += New-AzureRmDnsRecordConfig -Ipv6Address 2001:db8::1
PS C:\> $RecordSet = New-AzureRmDnsRecordSet -Name "www" -RecordType AAAA -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -DnsRecords $Records
```

Contoh ini membuat **RecordSet** bernama www di zona myzone.com.
Kumpulan catatan adalah tipe AAAA dan memiliki TTL 1 jam (3600 detik).
Ini berisi satu catatan DNS.

Untuk membuat **Kumpulan Rekaman** hanya menggunakan satu baris pn_PowerShell_short, atau untuk membuat kumpulan catatan dengan beberapa catatan, lihat Contoh 1.

### Contoh 3: Membuat Kumpulan Rekaman tipe CNAME
```
PS C:\> $Records = @()
PS C:\> $Records += New-AzureRmDnsRecordConfig -Cname www.contoso.com
PS C:\> $RecordSet = New-AzureRmDnsRecordSet -Name "www" -RecordType CNAME -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -DnsRecords $Records
```

Contoh ini membuat **RecordSet** bernama www di zona myzone.com.
Kumpulan catatan adalah tipe CNAME dan memiliki TTL 1 jam (3600 detik).
Ini berisi satu catatan DNS.

Untuk membuat **Kumpulan Rekaman** hanya menggunakan satu baris pn_PowerShell_short, atau untuk membuat kumpulan catatan dengan beberapa catatan, lihat Contoh 1.

### Contoh 4: Membuat RecordSet tipe MX
```
PS C:\> $Records = @()
PS C:\> $Records += New-AzureRmDnsRecordConfig -Exchange "mail.microsoft.com" -Preference 5
PS C:\> $RecordSet = New-AzureRmDnsRecordSet -Name "www" -RecordType AAAA -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -DnsRecords $Records
```

Perintah ini membuat **RecordSet** bernama www di zona myzone.com.
Kumpulan catatan adalah tipe MX dan memiliki TTL 1 jam (3600 detik).
Ini berisi satu catatan DNS.

Untuk membuat **Kumpulan Rekaman** hanya menggunakan satu baris pn_PowerShell_short, atau untuk membuat kumpulan catatan dengan beberapa catatan, lihat Contoh 1.

### Contoh 5: Membuat Kumpulan Data tipe NS
```
PS C:\> $Records = @()
PS C:\> $Records += New-AzureRmDnsRecordConfig -Nsdname ns1-01.azure-dns.com
PS C:\> $RecordSet = New-AzureRmDnsRecordSet -Name "ns1" -RecordType NS -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -DnsRecords $Records
```

Perintah ini membuat **RecordSet** bernama ns1 di zona myzone.com.
Kumpulan catatan adalah tipe NS dan memiliki TTL 1 jam (3600 detik).
Ini berisi satu catatan DNS.

Untuk membuat **Kumpulan Rekaman** hanya menggunakan satu baris pn_PowerShell_short, atau untuk membuat kumpulan catatan dengan beberapa catatan, lihat Contoh 1.

### Contoh 6: Membuat RecordSet tipe PTR
```
PS C:\> $Records = @()
PS C:\> $Records += New-AzureRmDnsRecordConfig -Ptrdname www.contoso.com
PS C:\> $RecordSet = New-AzureRmDnsRecordSet -Name "4" -RecordType PTR -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "3.2.1.in-addr.arpa" -DnsRecords $Records
```

Perintah ini membuat **RecordSet** bernama 4 di zona 3.2.1.in-addr.arpa.
Kumpulan rekor adalah tipe PTR dan memiliki TTL 1 jam (3600 detik).
Ini berisi satu catatan DNS.

Untuk membuat **Kumpulan Rekaman** hanya menggunakan satu baris pn_PowerShell_short, atau untuk membuat kumpulan catatan dengan beberapa catatan, lihat Contoh 1.

### Contoh 7: Membuat Kumpulan Data tipe SRV
```
PS C:\> $Records = @()
PS C:\> $Records += New-AzureRmDnsRecordConfig -Priority 0 -Weight 5 -Port 8080 -Target sipservice.contoso.com
PS C:\> $RecordSet = New-AzureRmDnsRecordSet -Name "_sip._tcp" -RecordType SRV -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -DnsRecords $Records
```

Perintah ini membuat **RecordSet** bernama _sip._tcp di myzone.com zona.
Kumpulan catatan adalah tipe SRV dan memiliki TTL 1 jam (3600 detik).
Ini berisi satu catatan DNS, mengarah ke alamat IP 2001.2.3.4.

Layanan (sip) dan protokol (tcp) ditentukan sebagai bagian dari nama kumpulan catatan, bukan sebagai bagian dari data rekaman.

Untuk membuat **Kumpulan Rekaman** hanya menggunakan satu baris pn_PowerShell_short, atau untuk membuat kumpulan catatan dengan beberapa catatan, lihat Contoh 1.

### Contoh 8: Membuat Kumpulan Data tipe TXT
```
PS C:\> $Records = @()
PS C:\> $Records += New-AzureRmDnsRecordConfig -Value "This is a TXT Record"
PS C:\> $RecordSet = New-AzureRmDnsRecordSet -Name "text" -RecordType TXT -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -DnsRecords $Records
```

Perintah ini membuat teks **bernama RecordSet** di zona myzone.com.
Kumpulan catatan adalah tipe TXT dan memiliki TTL 1 jam (3600 detik).
Ini berisi satu catatan DNS.

Untuk membuat **Kumpulan Rekaman** hanya menggunakan satu baris pn_PowerShell_short, atau untuk membuat kumpulan catatan dengan beberapa catatan, lihat Contoh 1.

## PARAMETERS

### -Cname
Menentukan nama domain untuk catatan nama kanonis (CNAME).

```yaml
Type: String
Parameter Sets: CName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Exchange
Menentukan nama server mail exchange untuk catatan mail exchange (MX).

```yaml
Type: String
Parameter Sets: Mx
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
Parameter Sets: Aaaa
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nsdname
Menentukan nama server nama untuk catatan server nama (NS).

```yaml
Type: String
Parameter Sets: Ns
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
Type: UInt16
Parameter Sets: Srv
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
Parameter Sets: Mx
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
Parameter Sets: Srv
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Ptrdname
Menentukan nama domain target catatan sumber daya penunjuk (PTR).

```yaml
Type: String
Parameter Sets: Ptr
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Target
Menentukan target untuk catatan SRV.

```yaml
Type: String
Parameter Sets: Srv
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
Type: String
Parameter Sets: Txt
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
Type: UInt16
Parameter Sets: Srv
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak.

## OUTPUTS

### Microsoft.Azure.Commands.Dns.DnsRecordBase

## CATATAN

## RELATED LINKS

[Add-AzureRmDnsRecordConfig](./Add-AzureRmDnsRecordConfig.md)

[New-AzureRmDnsRecordSet](./New-AzureRmDnsRecordSet.md)

[Hapus-AzureRmDnsRecordConfig](./Remove-AzureRmDnsRecordConfig.md)
