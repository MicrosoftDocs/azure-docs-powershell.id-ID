---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Dns.dll-Help.xml
Module Name: Az.Dns
ms.assetid: 45DF71E0-77E1-4D20-AD09-2C06680F659F
online version: https://docs.microsoft.com/powershell/module/az.dns/new-azdnsrecordset
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Dns/Dns/help/New-AzDnsRecordSet.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Dns/Dns/help/New-AzDnsRecordSet.md
ms.openlocfilehash: 047744082bd6e6e47a31ce9ae9a08ac56935e373
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145740484"
---
# New-AzDnsRecordSet

## SYNOPSIS
Membuat kumpulan catatan DNS.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.dns/new-azdnsrecordset) untuk informasi terbaru.

## SYNTAX

### Bidang (Default)
```
New-AzDnsRecordSet -Name <String> -ZoneName <String> -ResourceGroupName <String> -Ttl <UInt32>
 -RecordType <RecordType> [-Metadata <Hashtable>] [-DnsRecords <DnsRecordBase[]>] [-Overwrite]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AliasFields
```
New-AzDnsRecordSet -Name <String> -ZoneName <String> -ResourceGroupName <String> [-Ttl <UInt32>]
 -RecordType <RecordType> -TargetResourceId <String> [-Metadata <Hashtable>] [-DnsRecords <DnsRecordBase[]>]
 [-Overwrite] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Objek
```
New-AzDnsRecordSet -Name <String> -Zone <DnsZone> -Ttl <UInt32> -RecordType <RecordType>
 [-Metadata <Hashtable>] [-DnsRecords <DnsRecordBase[]>] [-Overwrite]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### AliasObject
```
New-AzDnsRecordSet -Name <String> -Zone <DnsZone> [-Ttl <UInt32>] -RecordType <RecordType>
 -TargetResourceId <String> [-Metadata <Hashtable>] [-DnsRecords <DnsRecordBase[]>] [-Overwrite]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzDnsRecordSet** membuat kumpulan catatan Sistem Nama Domain (DNS) baru dengan nama dan jenis yang ditentukan di zona yang ditentukan.
Objek **RecordSet** adalah sekumpulan catatan DNS dengan nama dan jenis yang sama.
Perhatikan bahwa namanya relatif terhadap zona dan bukan nama yang sepenuhnya memenuhi syarat.
Parameter *DnsRecords* menentukan rekaman dalam kumpulan catatan.
Parameter ini mengambil array rekaman DNS, yang dibangun menggunakan New-AzDnsRecordConfig.
Anda dapat menggunakan operator alur untuk meneruskan objek **DnsZone** ke cmdlet ini, atau Anda dapat meneruskan objek **DnsZone** sebagai parameter *Zona* , atau atau Anda dapat menentukan zona berdasarkan nama.
Anda dapat menggunakan parameter *Konfirmasi* dan variabel $ConfirmPreference Windows PowerShell untuk mengontrol apakah cmdlet meminta konfirmasi.
Jika **RecordSet** yang cocok sudah ada (nama dan jenis rekaman yang sama), Anda harus menentukan parameter *Timpa* , jika tidak cmdlet tidak akan membuat **RecordSet** baru.

## EXAMPLES

### Contoh 1: Membuat RecordSet tipe A
```powershell
$Records = @()
$Records += New-AzDnsRecordConfig -IPv4Address 1.2.3.4
$RecordSet = New-AzDnsRecordSet -Name "www" -RecordType A -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -DnsRecords $Records

# When creating a RecordSet containing a single record, the above sequence can also be condensed into a single line:

$RecordSet = New-AzDnsRecordSet -Name "www" -RecordType A -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -DnsRecords (New-AzDnsRecordConfig -IPv4Address 1.2.3.4)

# To create a record set containing multiple records, use New-AzDnsRecordConfig to add each record to the $Records array,
# then call New-AzDnsRecordSet, as follows:

$Records = @()
$Records += New-AzDnsRecordConfig -IPv4Address 1.2.3.4
$Records += New-AzDnsRecordConfig -IPv4Address 5.6.7.8
$RecordSet = New-AzDnsRecordSet -Name "www" -RecordType A -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -DnsRecords $Records
```

Contoh ini membuat **RecordSet** bernama www di zona myzone.com.
Kumpulan catatan berjenis A dan memiliki TTL 1 jam (3600 detik).
Ini berisi satu catatan DNS.

### Contoh 2: Membuat RecordSet jenis AAAA
```powershell
$Records = @()
$Records += New-AzDnsRecordConfig -Ipv6Address 2001:db8::1
$RecordSet = New-AzDnsRecordSet -Name "www" -RecordType AAAA -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -DnsRecords $Records
```

Contoh ini membuat **RecordSet** bernama www di zona myzone.com.
Kumpulan catatan berjenis AAAA dan memiliki TTL 1 jam (3600 detik).
Ini berisi satu catatan DNS.
Untuk membuat **RecordSet** hanya menggunakan satu baris pn_PowerShell_short, atau untuk membuat kumpulan catatan dengan beberapa rekaman, lihat Contoh 1.

### Contoh 3: Membuat RecordSet jenis CNAME
```powershell
$Records = @()
$Records += New-AzDnsRecordConfig -Cname www.contoso.com
$RecordSet = New-AzDnsRecordSet -Name "www" -RecordType CNAME -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -DnsRecords $Records
```

Contoh ini membuat **RecordSet** bernama www di zona myzone.com.
Kumpulan catatan berjenis CNAME dan memiliki TTL 1 jam (3600 detik).
Ini berisi satu catatan DNS.
Untuk membuat **RecordSet** hanya menggunakan satu baris pn_PowerShell_short, atau untuk membuat kumpulan catatan dengan beberapa rekaman, lihat Contoh 1.

### Contoh 4: Membuat RecordSet jenis MX
```powershell
$Records = @()
$Records += New-AzDnsRecordConfig -Exchange "mail.microsoft.com" -Preference 5
$RecordSet = New-AzDnsRecordSet -Name "mail" -RecordType MX -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -DnsRecords $Records
```

Perintah ini membuat **RecordSet** bernama www di zona myzone.com.
Kumpulan catatan berjenis MX dan memiliki TTL 1 jam (3600 detik).
Ini berisi satu catatan DNS.
Untuk membuat **RecordSet** hanya menggunakan satu baris pn_PowerShell_short, atau untuk membuat kumpulan catatan dengan beberapa rekaman, lihat Contoh 1.

### Contoh 5: Membuat RecordSet jenis NS
```powershell
$Records = @()
$Records += New-AzDnsRecordConfig -Nsdname ns1-01.azure-dns.com
$RecordSet = New-AzDnsRecordSet -Name "ns1" -RecordType NS -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -DnsRecords $Records
```

Perintah ini membuat **RecordSet** bernama ns1 di zona myzone.com.
Kumpulan catatan berjenis NS dan memiliki TTL 1 jam (3600 detik).
Ini berisi satu catatan DNS.
Untuk membuat **RecordSet** hanya menggunakan satu baris pn_PowerShell_short, atau untuk membuat kumpulan catatan dengan beberapa rekaman, lihat Contoh 1.

### Contoh 6: Membuat RecordSet jenis PTR
```powershell
$Records = @()
$Records += New-AzDnsRecordConfig -Ptrdname www.contoso.com
$RecordSet = New-AzDnsRecordSet -Name "4" -RecordType PTR -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "3.2.1.in-addr.arpa" -DnsRecords $Records
```

Perintah ini membuat **RecordSet** bernama 4 di zona 3.2.1.in-addr.arpa.
Kumpulan catatan berjenis PTR dan memiliki TTL 1 jam (3600 detik).
Ini berisi satu catatan DNS.
Untuk membuat **RecordSet** hanya menggunakan satu baris pn_PowerShell_short, atau untuk membuat kumpulan catatan dengan beberapa rekaman, lihat Contoh 1.

### Contoh 7: Membuat RecordSet jenis SRV
```powershell
$Records = @()
$Records += New-AzDnsRecordConfig -Priority 0 -Weight 5 -Port 8080 -Target sipservice.contoso.com
$RecordSet = New-AzDnsRecordSet -Name "_sip._tcp" -RecordType SRV -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -DnsRecords $Records
```

Perintah ini membuat **RecordSet** bernama _sip._tcp di zona myzone.com.
Kumpulan catatan berjenis SRV dan memiliki TTL 1 jam (3600 detik).
Ini berisi satu catatan DNS, menunjuk ke alamat IP 2001.2.3.4.
Layanan (sip) dan protokol (tcp) ditentukan sebagai bagian dari nama kumpulan catatan, bukan sebagai bagian dari data rekaman.
Untuk membuat **RecordSet** hanya menggunakan satu baris pn_PowerShell_short, atau untuk membuat kumpulan catatan dengan beberapa rekaman, lihat Contoh 1.

### Contoh 8: Membuat RecordSet jenis TXT
```powershell
$Records = @()
$Records += New-AzDnsRecordConfig -Value "This is a TXT Record"
$RecordSet = New-AzDnsRecordSet -Name "text" -RecordType TXT -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -DnsRecords $Records
```

Perintah ini membuat **teks bernama RecordSet** di zona myzone.com.
Kumpulan catatan berjenis TXT dan memiliki TTL 1 jam (3600 detik).
Ini berisi satu catatan DNS.
Untuk membuat **RecordSet** hanya menggunakan satu baris pn_PowerShell_short, atau untuk membuat kumpulan catatan dengan beberapa rekaman, lihat Contoh 1.

### Contoh 9: Membuat RecordSet di puncak zona
```powershell
$Records = @()
$Records += New-AzDnsRecordConfig -Ipv4Address 1.2.3.4
$RecordSet = New-AzDnsRecordSet -Name "@" -RecordType A -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -DnsRecords $Records
```

Perintah ini membuat **RecordSet** di puncak (atau akar) zona myzone.com.
Untuk melakukan ini, nama kumpulan catatan ditentukan sebagai "@" (termasuk tanda kutip ganda).
Anda tidak dapat membuat data CNAME di puncak zona.
Ini adalah batasan dari standar DNS; ini bukan batasan Azure DNS.
Untuk membuat **RecordSet** hanya menggunakan satu baris pn_PowerShell_short, atau untuk membuat kumpulan catatan dengan beberapa rekaman, lihat Contoh 1.

### Contoh 10: Membuat Kumpulan Catatan kartubebas
```powershell
$Records = @()
$Records += New-AzDnsRecordConfig -Ipv4Address 1.2.3.4
$RecordSet = New-AzDnsRecordSet -Name "*" -RecordType A -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -DnsRecords $Records
```

Perintah ini membuat **RecordSet** bernama * di zona myzone.com.
Ini adalah kumpulan catatan kartubebas.
Untuk membuat **RecordSet** hanya menggunakan satu baris pn_PowerShell_short, atau untuk membuat kumpulan catatan dengan beberapa rekaman, lihat Contoh 1.

### Contoh 11: Membuat kumpulan catatan kosong
```powershell
$RecordSet = New-AzDnsRecordSet -Name "www" -RecordType A -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -DnsRecords @()
```

Perintah ini membuat **RecordSet** bernama www di zona myzone.com.
Kumpulan catatan berjenis A dan memiliki TTL 1 jam (3600 detik).
Ini adalah kumpulan catatan kosong, yang bertindak sebagai tempat penampung tempat Anda nantinya bisa menambahkan rekaman.

### Contoh 12: Membuat kumpulan catatan dan menekan semua konfirmasi
```powershell
$RecordSet = New-AzDnsRecordSet -Name "www" -RecordType A -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -DnsRecords (New-AzDnsRecordConfig -Ipv4Address 1.2.3.4) -Confirm:$False -Overwrite
```

Perintah ini membuat **RecordSet**.
Parameter *Timpa* memastikan bahwa kumpulan catatan ini menimpa kumpulan catatan yang sudah ada sebelumnya dengan nama dan jenis yang sama (rekaman yang sudah ada dalam kumpulan catatan tersebut hilang).
Parameter *Konfirmasi* dengan nilai $False menekan prompt konfirmasi.

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

### -DnsRecords
Menentukan array rekaman DNS untuk disertakan dalam kumpulan catatan.
Anda bisa menggunakan cmdlet New-AzDnsRecordConfig untuk membuat objek rekaman DNS.
Lihat contoh untuk informasi selengkapnya.

```yaml
Type: Microsoft.Azure.Commands.Dns.DnsRecordBase[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Metadata
Menentukan array metadata untuk dikaitkan dengan RecordSet.
Metadata ditentukan menggunakan pasangan nama-nilai yang direpresentasikan sebagai tabel hash, misalnya @{"dept"="shopping";" env"="production"}.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Menentukan nama **RecordSet** yang akan dibuat.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Timpa
Menunjukkan bahwa cmdlet ini menimpa **RecordSet** yang ditentukan jika sudah ada.

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

### -RecordType
Menentukan tipe catatan DNS yang akan dibuat.
Nilai yang valid adalah:
- A
- AAAA
- CNAME
- MX
- NS
- PTR
- SRV
- Catatan SOA TXT dibuat secara otomatis ketika zona dibuat dan tidak dapat dibuat secara manual.

```yaml
Type: Microsoft.Azure.Management.Dns.Models.RecordType
Parameter Sets: (All)
Aliases:
Accepted values: A, AAAA, CAA, CNAME, MX, NS, PTR, SOA, SRV, TXT

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan grup sumber daya yang berisi zona DNS.
Anda juga harus menentukan parameter *ZoneName* untuk menentukan nama zona.
Atau, Anda dapat menentukan zona dan grup sumber daya dengan meneruskan objek Zona DNS menggunakan parameter *Zona* .

```yaml
Type: System.String
Parameter Sets: Fields, AliasFields
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TargetResourceId
Id Sumber Daya Target Alias.

```yaml
Type: System.String
Parameter Sets: AliasFields, AliasObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Ttl
Menentukan Time to Live (TTL) untuk RecordSet DNS.

```yaml
Type: System.UInt32
Parameter Sets: Fields, Object
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: System.UInt32
Parameter Sets: AliasFields, AliasObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Zona
Menentukan DnsZone untuk membuat **RecordSet**.
Atau, Anda dapat menentukan zona menggunakan parameter *ZoneName* dan *ResourceGroupName* .

```yaml
Type: Microsoft.Azure.Commands.Dns.DnsZone
Parameter Sets: Object, AliasObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ZoneName
Menentukan nama zona untuk membuat **RecordSet**.
Anda juga harus menentukan grup sumber daya yang berisi zona menggunakan parameter *ResourceGroupName* .
Atau, Anda dapat menentukan zona dan grup sumber daya dengan meneruskan objek Zona DNS menggunakan parameter *Zona* .

```yaml
Type: System.String
Parameter Sets: Fields, AliasFields
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

### System.String

### Microsoft.Azure.Commands.Dns.DnsZone

### System.UInt32

### Microsoft.Azure.Management.Dns.Models.RecordType

### System.Collections.Hashtable

### Microsoft.Azure.Commands.Dns.DnsRecordBase[]

## OUTPUTS

### Microsoft.Azure.Commands.Dns.DnsRecordSet

## NOTES
Anda dapat menggunakan parameter *Konfirmasi* untuk mengontrol apakah cmdlet ini meminta konfirmasi.
Secara default, cmdlet meminta konfirmasi kepada Anda jika variabel $ConfirmPreference Windows PowerShell memiliki nilai Sedang atau lebih rendah.
Jika Anda menentukan *Konfirmasi* atau *Konfirmasi:$True*, cmdlet ini akan meminta konfirmasi sebelum dijalankan.
Jika Anda menentukan *Confirm:$False*, cmdlet tidak meminta konfirmasi kepada Anda.

## RELATED LINKS

[Add-AzDnsRecordConfig](./Add-AzDnsRecordConfig.md)

[Get-AzDnsRecordSet](./Get-AzDnsRecordSet.md)

[New-AzDnsRecordConfig](./New-AzDnsRecordConfig.md)

[Remove-AzDnsRecordSet](./Remove-AzDnsRecordSet.md)

[Set-AzDnsRecordSet](./Set-AzDnsRecordSet.md)
