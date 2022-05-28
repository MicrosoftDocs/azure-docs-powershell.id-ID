---
external help file: Microsoft.Azure.PowerShell.Cmdlets.PrivateDns.dll-Help.xml
Module Name: Az.PrivateDns
online version: https://docs.microsoft.com/powershell/module/az.privatedns/new-azprivatednsrecordset
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/PrivateDns/PrivateDns/help/New-AzPrivateDnsRecordSet.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/PrivateDns/PrivateDns/help/New-AzPrivateDnsRecordSet.md
ms.openlocfilehash: 4da8cc4b2c01b47fab1afd5a89ca7440075c4e45
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145516006"
---
# New-AzPrivateDnsRecordSet

## SYNOPSIS
Membuat kumpulan catatan di zona DNS Privat.

## SYNTAX

### Bidang (Default)
```
New-AzPrivateDnsRecordSet -ResourceGroupName <String> -ZoneName <String> -Name <String>
 -RecordType <RecordType> -Ttl <UInt32> [-Metadata <Hashtable>] [-PrivateDnsRecord <PSPrivateDnsRecordBase[]>]
 [-Overwrite] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Objek
```
New-AzPrivateDnsRecordSet -Zone <PSPrivateDnsZone> -Name <String> -RecordType <RecordType> -Ttl <UInt32>
 [-Metadata <Hashtable>] [-PrivateDnsRecord <PSPrivateDnsRecordBase[]>] [-Overwrite]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ResourceId
```
New-AzPrivateDnsRecordSet -ParentResourceId <String> -Name <String> -RecordType <RecordType> -Ttl <UInt32>
 [-Metadata <Hashtable>] [-PrivateDnsRecord <PSPrivateDnsRecordBase[]>] [-Overwrite]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet New-AzPrivateDnsRecordSet membuat kumpulan catatan Sistem Nama Domain Privat (DNS) baru dengan nama dan jenis yang ditentukan di zona privat yang ditentukan. Objek RecordSet adalah sekumpulan catatan DNS Privat dengan nama dan jenis yang sama. Perhatikan bahwa namanya relatif terhadap zona privat dan bukan nama yang sepenuhnya memenuhi syarat. Parameter PrivateDnsRecord menentukan rekaman dalam kumpulan catatan. Parameter ini mengambil array rekaman DNS Privat, yang dibangun menggunakan New-AzPrivateDnsRecordConfig. Anda dapat menggunakan operator alur untuk meneruskan objek PSPrivateDnsZone ke cmdlet ini, atau Anda dapat meneruskan objek PSPrivateDnsZone sebagai parameter Zona, atau Anda dapat menentukan zona dengan ResourceId-nya, atau Anda dapat menentukan zona berdasarkan nama. Anda dapat menggunakan parameter Konfirmasi dan variabel $ConfirmPreference Windows PowerShell untuk mengontrol apakah cmdlet meminta konfirmasi. Jika RecordSet yang cocok sudah ada (nama dan jenis rekaman yang sama), Anda harus menentukan parameter Timpa, jika tidak, cmdlet tidak akan membuat RecordSet baru.

## EXAMPLES

### Contoh 1: Membuat RecordSet tipe A
```powershell
$Records = @()
$Records += New-AzPrivateDnsRecordConfig -IPv4Address 1.2.3.4
$RecordSet = New-AzPrivateDnsRecordSet -Name "www" -RecordType A -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -PrivateDnsRecords $Records

# When creating a RecordSet containing a single record, the above sequence can also be condensed into a single line:

$RecordSet = New-AzPrivateDnsRecordSet -Name "www" -RecordType A -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -PrivateDnsRecords (New-AzPrivateDnsRecordConfig -IPv4Address 1.2.3.4)

Id                : /subscriptions/xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/MyResourceGroup/providers/Microsoft.Netwo
                    rk/privateDnsZones/myzone.com/A/www
Name              : www
ZoneName          : myzone.com
ResourceGroupName : MyResourceGroup
Ttl               : 3600
Etag              : xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
RecordType        : A
Records           : {1.2.3.4}
Metadata          :
IsAutoRegistered  :


# To create a record set containing multiple records, use New-AzPrivateDnsRecordConfig to add each record to the $Records array,
# then call New-AzPrivateDnsRecordSet, as follows:

$Records = @()
$Records += New-AzPrivateDnsRecordConfig -IPv4Address 1.2.3.4
$Records += New-AzPrivateDnsRecordConfig -IPv4Address 5.6.7.8
$RecordSet = New-AzPrivateDnsRecordSet -Name "www" -RecordType A -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -PrivateDnsRecords $Records

Id                : /subscriptions/xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/MyResourceGroup/providers/Microsoft.Netwo
                    rk/privateDnsZones/myzone.com/A/www
Name              : www
ZoneName          : myzone.com
ResourceGroupName : MyResourceGroup
Ttl               : 3600
Etag              : xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
RecordType        : A
Records           : {1.2.3.4, 5.6.7.8}
Metadata          :
IsAutoRegistered  :
```

Contoh ini membuat RecordSet bernama www di zona privat myzone.com. Kumpulan catatan berjenis A dan memiliki TTL 1 jam (3600 detik). Ini berisi satu catatan DNS Privat.

### Contoh 2: Membuat RecordSet jenis AAAA
```powershell
$Records = @()
$Records += New-AzPrivateDnsRecordConfig -Ipv6Address 2001:db8::1
$RecordSet = New-AzPrivateDnsRecordSet -Name "www" -RecordType AAAA -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -PrivateDnsRecords $Records
```

```output
Id                : /subscriptions/xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/myresourcegroup/providers/Micros
                    oft.Network/privateDnsZones/myzone.com/AAAA/www
Name              : www
ZoneName          : myzone.com
ResourceGroupName : MyResourceGroup
Ttl               : 3600
Etag              : xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
RecordType        : AAAA
Records           : {2001:db8::1}
Metadata          :
IsAutoRegistered  :
```

Contoh ini membuat RecordSet bernama www di zona privat myzone.com. Kumpulan catatan berjenis AAAA dan memiliki TTL 1 jam (3600 detik). Ini berisi satu catatan DNS Privat. Untuk membuat RecordSet hanya menggunakan satu baris pn_PowerShell_short, atau untuk membuat kumpulan catatan dengan beberapa rekaman, lihat Contoh 1.

### Contoh 3: Membuat RecordSet jenis CNAME
```powershell
$Records = @()
$Records += New-AzPrivateDnsRecordConfig -Cname www.contoso.com
$RecordSet = New-AzPrivateDnsRecordSet -Name "www" -RecordType CNAME -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -PrivateDnsRecords $Records
```

```output
Id                : /subscriptions/xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/myresourcegroup/providers/Micros
                    oft.Network/privateDnsZones/myzone.com/CNAME/www
Name              : www
ZoneName          : myzone.com
ResourceGroupName : MyResourceGroup
Ttl               : 3600
Etag              : xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
RecordType        : CNAME
Records           : {www.contoso.com}
Metadata          :
IsAutoRegistered  :
```

Contoh ini membuat RecordSet bernama www di zona privat myzone.com. Kumpulan catatan berjenis CNAME dan memiliki TTL 1 jam (3600 detik). Ini berisi satu catatan DNS Privat. Untuk membuat RecordSet hanya menggunakan satu baris pn_PowerShell_short, atau untuk membuat kumpulan catatan dengan beberapa rekaman, lihat Contoh 1.

### Contoh 4: Membuat RecordSet jenis MX
```powershell
$Records = @()
$Records += New-AzPrivateDnsRecordConfig -Exchange "mail.microsoft.com" -Preference 5
$RecordSet = New-AzPrivateDnsRecordSet -Name "www" -RecordType MX -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -PrivateDnsRecords $Records
```

```output
Id                : /subscriptions/xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/myresourcegroup/providers/Micros
                    oft.Network/privateDnsZones/myzone.com/MX/www
Name              : www
ZoneName          : myzone.com
ResourceGroupName : MyResourceGroup
Ttl               : 3600
Etag              : xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
RecordType        : MX
Records           : {[5,mail.microsoft.com]}
Metadata          :
IsAutoRegistered  :
```

Perintah ini membuat RecordSet bernama www di zona privat myzone.com. Kumpulan catatan berjenis MX dan memiliki TTL 1 jam (3600 detik). Ini berisi satu catatan DNS Privat. Untuk membuat RecordSet hanya menggunakan satu baris pn_PowerShell_short, atau untuk membuat kumpulan catatan dengan beberapa rekaman, lihat Contoh 1.

### Contoh 5: Membuat RecordSet jenis PTR
```powershell
$Records = @()
$Records += New-AzPrivateDnsRecordConfig -Ptrdname www.contoso.com
$RecordSet = New-AzPrivateDnsRecordSet -Name "4" -RecordType PTR -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "3.2.1.in-addr.arpa" -PrivateDnsRecords $Records
```

```output
Id                : /subscriptions/xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/myresourcegroup/providers/Micros
                    oft.Network/privateDnsZones/3.2.1.in-addr.arpa/PTR/4
Name              : 4
ZoneName          : 3.2.1.in-addr.arpa
ResourceGroupName : MyResourceGroup
Ttl               : 3600
Etag              : xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
RecordType        : PTR
Records           : {www.contoso.com}
Metadata          :
IsAutoRegistered  :
```

Perintah ini membuat RecordSet bernama 4 di zona privat 3.2.1.in-addr.arpa. Kumpulan catatan berjenis PTR dan memiliki TTL 1 jam (3600 detik). Ini berisi satu catatan DNS Privat. Untuk membuat RecordSet hanya menggunakan satu baris pn_PowerShell_short, atau untuk membuat kumpulan catatan dengan beberapa rekaman, lihat Contoh 1.

### Contoh 6: Membuat RecordSet jenis SRV
```powershell
$Records = @()
$Records += New-AzPrivateDnsRecordConfig -Priority 0 -Weight 5 -Port 8080 -Target sipservice.contoso.com
$RecordSet = New-AzPrivateDnsRecordSet -Name "_sip._tcp" -RecordType SRV -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -PrivateDnsRecords $Records
```

```output
Id                : /subscriptions/xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/myresourcegroup/providers/Micros
                    oft.Network/privateDnsZones/myzone.com/SRV/_sip._tcp
Name              : _sip._tcp
ZoneName          : myzone.com
ResourceGroupName : MyResourceGroup
Ttl               : 3600
Etag              : xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
RecordType        : SRV
Records           : {[0,5,8080,sipservice.contoso.com]}
Metadata          :
IsAutoRegistered  :
```

Perintah ini membuat RecordSet bernama _sip._tcp di zona privat myzone.com. Kumpulan catatan berjenis SRV dan memiliki TTL 1 jam (3600 detik). Ini berisi satu catatan DNS Privat, menunjuk ke alamat IP 2001.2.3.4. Layanan (sip) dan protokol (tcp) ditentukan sebagai bagian dari nama kumpulan catatan, bukan sebagai bagian dari data rekaman. Untuk membuat RecordSet hanya menggunakan satu baris pn_PowerShell_short, atau untuk membuat kumpulan catatan dengan beberapa rekaman, lihat Contoh 1.

### Contoh 7: Membuat RecordSet jenis TXT
```powershell
$Records = @()
$Records += New-AzPrivateDnsRecordConfig -Value "This is a TXT Record"
$RecordSet = New-AzPrivateDnsRecordSet -Name "text" -RecordType TXT -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -PrivateDnsRecords $Records
```

```output
Id                : /subscriptions/xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/myresourcegroup/providers/Micros
                    oft.Network/privateDnsZones/myzone.com/TXT/text
Name              : text
ZoneName          : myzone.com
ResourceGroupName : MyResourceGroup
Ttl               : 3600
Etag              : xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
RecordType        : TXT
Records           : {This is a TXT Record}
Metadata          :
IsAutoRegistered  :
```

Perintah ini membuat teks bernama RecordSet di zona privat myzone.com. Kumpulan catatan berjenis TXT dan memiliki TTL 1 jam (3600 detik). Ini berisi satu catatan DNS Privat. Untuk membuat RecordSet hanya menggunakan satu baris pn_PowerShell_short, atau untuk membuat kumpulan catatan dengan beberapa rekaman, lihat Contoh 1.

### Contoh 8: Membuat RecordSet di puncak zona
```powershell
$Records = @()
$Records += New-AzPrivateDnsRecordConfig -Ipv4Address 1.2.3.4
$RecordSet = New-AzPrivateDnsRecordSet -Name "@" -RecordType A -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -PrivateDnsRecords $Records
```

```output
Id                : /subscriptions/xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/myresourcegroup/providers/Micros
                    oft.Network/privateDnsZones/myzone.com/A/@
Name              : @
ZoneName          : myzone.com
ResourceGroupName : MyResourceGroup
Ttl               : 3600
Etag              : xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
RecordType        : A
Records           : {1.2.3.4}
Metadata          :
IsAutoRegistered  :
```

Perintah ini membuat RecordSet di puncak (atau akar) zona privat myzone.com. Untuk melakukan ini, nama kumpulan catatan ditentukan sebagai "@" (termasuk tanda kutip ganda). Anda tidak dapat membuat data CNAME di puncak zona. Ini adalah batasan dari standar DNS; ini bukan batasan Azure Private DNS. Untuk membuat RecordSet hanya menggunakan satu baris pn_PowerShell_short, atau untuk membuat kumpulan catatan dengan beberapa rekaman, lihat Contoh 1.

### Contoh 9: Membuat Kumpulan Catatan kartubebas

```powershell
$Records = @()
$Records += New-AzPrivateDnsRecordConfig -Ipv4Address 1.2.3.4
$RecordSet = New-AzPrivateDnsRecordSet -Name "*" -RecordType A -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -PrivateDnsRecords $Records
```

```output
Id                : /subscriptions/xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/myresourcegroup/providers/Micros
                    oft.Network/privateDnsZones/myzone.com/A/@
Name              : *
ZoneName          : myzone.com
ResourceGroupName : MyResourceGroup
Ttl               : 3600
Etag              : xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
RecordType        : A
Records           : {1.2.3.4}
Metadata          :
IsAutoRegistered  :
```

Perintah ini membuat RecordSet bernama * di zona privat myzone.com. Ini adalah kumpulan catatan kartubebas. Untuk membuat RecordSet hanya menggunakan satu baris pn_PowerShell_short, atau untuk membuat kumpulan catatan dengan beberapa rekaman, lihat Contoh 1.

### Contoh 10: Membuat Kumpulan Catatan kosong

```powershell
$RecordSet = New-AzPrivateDnsRecordSet -Name "www" -RecordType A -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -PrivateDnsRecords @()
```

```output
Id                : /subscriptions/xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/myresourcegroup/providers/Micros
                    oft.Network/privateDnsZones/myzone.com/A/@
Name              : *
ZoneName          : myzone.com
ResourceGroupName : MyResourceGroup
Ttl               : 3600
Etag              : xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
RecordType        : A
Records           : {}
Metadata          :
IsAutoRegistered  :
```

Perintah ini membuat RecordSet bernama * di zona privat myzone.com. Kumpulan catatan berjenis A dan memiliki TTL 1 jam (3600 detik). Ini adalah kumpulan catatan kosong, yang bertindak sebagai tempat penampung tempat Anda nantinya bisa menambahkan rekaman.

### Contoh 11: Membuat kumpulan catatan dan menyembunyikan semua konfirmasi

```powershell
$RecordSet = New-AzPrivateDnsRecordSet -Name "www" -RecordType A -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -PrivateDnsRecords (New-AzDnsRecordConfig -Ipv4Address 1.2.3.4) -Confirm:$False -Overwrite
```

Perintah ini membuat RecordSet. Parameter Timpa memastikan bahwa kumpulan catatan ini menimpa kumpulan catatan yang sudah ada sebelumnya dengan nama dan jenis yang sama (rekaman yang sudah ada dalam kumpulan catatan tersebut hilang). Parameter Konfirmasi dengan nilai $False menekan prompt konfirmasi.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

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

### -Metadata
Tabel hash yang mewakili tag sumber daya.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Nama rekaman dalam kumpulan catatan ini (relatif terhadap nama zona dan tanpa titik yang mengakhiri).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Timpa
Jangan gagal jika kumpulan catatan sudah ada.

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

### -ParentResourceId
ResourceID Zona DNS Privat.

```yaml
Type: System.String
Parameter Sets: ResourceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PrivateDnsRecord
Catatan dns privat yang merupakan bagian dari kumpulan catatan ini.

```yaml
Type: Microsoft.Azure.Commands.PrivateDns.Models.PSPrivateDnsRecordBase[]
Parameter Sets: (All)
Aliases: PrivateDnsRecords

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecordType
Tipe catatan DNS Privat dalam kumpulan catatan ini.

```yaml
Type: Microsoft.Azure.Management.PrivateDns.Models.RecordType
Parameter Sets: (All)
Aliases:
Accepted values: A, AAAA, CNAME, MX, PTR, SOA, SRV, TXT

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Grup sumber daya tempat zona berada.

```yaml
Type: System.String
Parameter Sets: Fields
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Ttl
Nilai TTL dari semua rekaman dalam kumpulan catatan ini.

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Zona
Objek PrivateDnsZone yang mewakili zona untuk membuat kumpulan catatan.

```yaml
Type: Microsoft.Azure.Commands.PrivateDns.Models.PSPrivateDnsZone
Parameter Sets: Object
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ZoneName
Zona untuk membuat kumpulan catatan (tanpa titik yang mengakhiri).

```yaml
Type: System.String
Parameter Sets: Fields
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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
Default value: None
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.PrivateDns.Models.PSPrivateDnsZone

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.PrivateDns.Models.PSPrivateDnsRecordSet

## NOTES

## RELATED LINKS
