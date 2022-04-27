---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Dns.dll-Help.xml
Module Name: Az.Dns
ms.assetid: CD119EBE-E1A4-4E9D-B3BA-FDAF89BF0DDB
online version: https://docs.microsoft.com/powershell/module/az.dns/add-azdnsrecordconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Dns/Dns/help/Add-AzDnsRecordConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Dns/Dns/help/Add-AzDnsRecordConfig.md
ms.openlocfilehash: 5cfb5c59c4f22b26c84e5c120c272d961549bb81
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144188907"
---
# Add-AzDnsRecordConfig

## SYNOPSIS
Menambahkan catatan DNS ke objek kumpulan catatan lokal.

## SYNTAX

### A
```
Add-AzDnsRecordConfig -RecordSet <DnsRecordSet> -Ipv4Address <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### AAAA
```
Add-AzDnsRecordConfig -RecordSet <DnsRecordSet> -Ipv6Address <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### NS
```
Add-AzDnsRecordConfig -RecordSet <DnsRecordSet> -Nsdname <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### MX
```
Add-AzDnsRecordConfig -RecordSet <DnsRecordSet> -Exchange <String> -Preference <UInt16>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### PTR
```
Add-AzDnsRecordConfig -RecordSet <DnsRecordSet> -Ptrdname <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### TXT
```
Add-AzDnsRecordConfig -RecordSet <DnsRecordSet> -Value <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### SRV
```
Add-AzDnsRecordConfig -RecordSet <DnsRecordSet> -Priority <UInt16> -Target <String> -Port <UInt16>
 -Weight <UInt16> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### CNAME
```
Add-AzDnsRecordConfig -RecordSet <DnsRecordSet> -Cname <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### Caa
```
Add-AzDnsRecordConfig -RecordSet <DnsRecordSet> -CaaFlags <Byte> -CaaTag <String> -CaaValue <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzDnsRecordConfig** menambahkan catatan Sistem Nama Domain (DNS) ke objek **RecordSet** .
Objek **RecordSet** adalah objek offline, dan perubahannya tidak mengubah respons DNS hingga setelah Anda menjalankan cmdlet Set-AzDnsRecordSet untuk mempertahankan perubahan ke layanan DNS Microsoft Azure.
Catatan SOA dibuat saat zona DNS dibuat, dan dihapus saat zona DNS dihapus.
Anda tidak dapat menambahkan atau menghapus rekaman SOA, tetapi Anda bisa mengeditnya.
Anda dapat meneruskan objek **RecordSet** ke cmdlet ini sebagai parameter atau dengan menggunakan operator alur.

## EXAMPLES

### Contoh 1: Menambahkan catatan A ke kumpulan catatan
```powershell
$RecordSet = Get-AzDnsRecordSet -Name www -RecordType A -ResourceGroupName MyResourceGroup -ZoneName myzone.com
Add-AzDnsRecordConfig -RecordSet $RecordSet -Ipv4Address 1.2.3.4
Set-AzDnsRecordSet -RecordSet $RecordSet

# You can also pipe the above sequence:

Get-AzDnsRecordSet -Name www -RecordType A -ResourceGroupName MyResourceGroup -ZoneName myzone.com | Add-AzDnsRecordConfig -Ipv4Address 1.2.3.4 | Set-AzDnsRecordSet
```

Contoh ini menambahkan catatan A ke kumpulan catatan yang sudah ada.

### Contoh 2: Menambahkan catatan AAAA ke kumpulan catatan
```powershell
$RecordSet = Get-AzDnsRecordSet -Name www -RecordType AAAA -ResourceGroupName MyResourceGroup -ZoneName myzone.com
Add-AzDnsRecordConfig -RecordSet $RecordSet -Ipv6Address 2001:DB80:4009:1803::1005
Set-AzDnsRecordSet -RecordSet $RecordSet

# You can also pipe the above sequence:

Get-AzDnsRecordSet -Name www -RecordType AAAA -ResourceGroupName MyResourceGroup -ZoneName myzone.com | Add-AzDnsRecordConfig -Ipv6Address 2001:DB80:4009:1803::1005 | Set-AzDnsRecordSet
```

Contoh ini menambahkan catatan AAAA ke kumpulan catatan yang sudah ada.

### Contoh 3: Menambahkan data CNAME ke kumpulan catatan
```powershell
$RecordSet = Get-AzDnsRecordSet -Name www -RecordType CNAME -ResourceGroupName MyResourceGroup -ZoneName myzone.com
Add-AzDnsRecordConfig -RecordSet $RecordSet -Cname contoso.com
Set-AzDnsRecordSet -RecordSet $RecordSet

# You can also pipe the above sequence:

Get-AzDnsRecordSet -Name www -RecordType CNAME -ResourceGroupName MyResourceGroup -ZoneName myzone.com | Add-AzDnsRecordConfig -Cname contoso.com | Set-AzDnsRecordSet
```

Contoh ini menambahkan data CNAME ke kumpulan catatan yang sudah ada.
Karena kumpulan catatan CNAME dapat berisi paling banyak satu catatan, kumpulan data awalnya harus berupa kumpulan catatan kosong, atau rekaman yang ada harus dihapus menggunakan Remove-AzDnsRecordConfig.

### Contoh 4: Menambahkan catatan MX ke kumpulan catatan
```powershell
$RecordSet = Get-AzDnsRecordSet -Name "@" -RecordType MX -ResourceGroupName MyResourceGroup -ZoneName myzone.com
Add-AzDnsRecordConfig -Exchange mail.microsoft.com -Preference 5 -RecordSet $RecordSet
Set-AzDnsRecordSet -RecordSet $RecordSet

# You can also pipe the above sequence:

Get-AzDnsRecordSet -Name "@" -RecordType MX -ResourceGroupName MyResourceGroup -ZoneName myzone.com | Add-AzDnsRecordConfig -Exchange mail.microsoft.com -Preference 5 | Set-AzDnsRecordSet
```

Contoh ini menambahkan catatan MX ke kumpulan catatan yang sudah ada.
Nama catatan "@" menunjukkan kumpulan catatan di puncak zona.

### Contoh 5: Menambahkan catatan NS ke kumpulan catatan
```powershell
$RecordSet = Get-AzDnsRecordSet -Name abc -RecordType NS -ResourceGroupName MyResourceGroup -ZoneName myzone.com
Add-AzDnsRecordConfig -Nsdname ns1.myzone.com -RecordSet $RecordSet
Set-AzDnsRecordSet -RecordSet $RecordSet

# You can also pipe the above sequence:

Get-AzDnsRecordSet -Name abc -RecordType NS -ResourceGroupName MyResourceGroup -ZoneName myzone.com | Add-AzDnsRecordConfig -Nsdname ns1.myzone.com | Set-AzDnsRecordSet
```

Contoh ini menambahkan catatan NS ke kumpulan catatan yang sudah ada.

### Contoh 6: Menambahkan catatan PTR ke kumpulan catatan
```powershell
$RecordSet = Get-AzDnsRecordSet -Name 4 -RecordType PTR -ResourceGroupName MyResourceGroup -ZoneName 3.2.1.in-addr.arpa
Add-AzDnsRecordConfig -Ptrdname www.contoso.com -RecordSet $RecordSet
Set-AzDnsRecordSet -RecordSet $RecordSet

# The above sequence can also be piped:

Get-AzDnsRecordSet -Name 4 -RecordType PTR -ResourceGroupName MyResourceGroup -ZoneName 3.2.1.in-addr.arpa | Add-AzDnsRecordConfig -Ptrdname www.contoso.com | Set-AzDnsRecordSet
```

Contoh ini menambahkan catatan PTR ke kumpulan catatan yang sudah ada.

### Contoh 7: Menambahkan catatan SRV ke kumpulan catatan
```powershell
$RecordSet = Get-AzDnsRecordSet -Name _sip._tcp -RecordType SRV -ResourceGroupName MyResourceGroup -ZoneName myzone.com
Add-AzDnsRecordConfig -RecordSet $RecordSet -Priority 0 -Weight 5 -Port 8080 -Target target.example.com
Set-AzDnsRecordSet -RecordSet $RecordSet

# The above sequence can also be piped:

Get-AzDnsRecordSet -Name _sip._tcp -RecordType SRV -ResourceGroupName MyResourceGroup -ZoneName myzone.com | Add-AzDnsRecordConfig -Priority 0 -Weight 5 -Port 8080 -Target target.example.com  | Set-AzDnsRecordSet
```

Contoh ini menambahkan catatan SRV ke kumpulan catatan yang sudah ada.

### Contoh 8: Menambahkan catatan TXT ke kumpulan catatan
```powershell
$RecordSet = Get-AzDnsRecordSet -Name text -RecordType TXT -ResourceGroupName MyResourceGroup -ZoneName myzone.com
Add-AzDnsRecordConfig -RecordSet $RecordSet -Value "This is a TXT Record"
Set-AzDnsRecordSet -RecordSet $RecordSet

# The above sequence can also be piped:

Get-AzDnsRecordSet -Name text -RecordType TXT -ResourceGroupName MyResourceGroup -ZoneName myzone.com | Add-AzDnsRecordConfig -Value "This is a TXT Record" | Set-AzDnsRecordSet
```

Contoh ini menambahkan catatan TXT ke kumpulan catatan yang sudah ada.

## PARAMETERS

### -CaaFlags
Bendera untuk catatan CAA yang akan ditambahkan. Harus berupa angka antara 0 dan 255.

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
Bidang tag rekaman CAA yang akan ditambahkan.

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
Bidang nilai untuk catatan CAA yang akan ditambahkan.

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
Menentukan nama server pertukaran email untuk rekaman pertukaran email (MX).

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
Menentukan alamat IPv4 untuk rekaman A.

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
Menentukan nama server nama untuk rekaman server nama (NS).

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
Menentukan port untuk rekaman layanan (SRV).

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
Menentukan nama domain target rekaman sumber daya penunjuk (PTR).

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
Menentukan objek **RecordSet** yang akan diedit.

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
Menentukan target untuk rekaman SRV.

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

### -Nilai
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Dns.DnsRecordSet

### System.String

### System.UInt16

### System.Byte

## OUTPUTS

### Microsoft.Azure.Commands.Dns.DnsRecordSet

## NOTES

## RELATED LINKS

[Get-AzDnsRecordSet](./Get-AzDnsRecordSet.md)

[Remove-AzDnsRecordConfig](./Remove-AzDnsRecordConfig.md)

[Set-AzDnsRecordSet](./Set-AzDnsRecordSet.md)
