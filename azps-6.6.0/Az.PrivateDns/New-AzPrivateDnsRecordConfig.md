---
external help file: Microsoft.Azure.PowerShell.Cmdlets.PrivateDns.dll-Help.xml
Module Name: Az.PrivateDns
online version: https://docs.microsoft.com/powershell/module/az.privatedns/new-azprivatednsrecordconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/PrivateDns/PrivateDns/help/New-AzPrivateDnsRecordConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/PrivateDns/PrivateDns/help/New-AzPrivateDnsRecordConfig.md
ms.openlocfilehash: ec2c1a34e70e358267b289ac88511fdbb4e84357
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136386940"
---
# New-AzPrivateDnsRecordConfig

## SYNOPSIS
Membuat objek lokal catatan DNS Privat baru.

## SYNTAX

### A (Default)
```
New-AzPrivateDnsRecordConfig -Ipv4Address <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### AAAA
```
New-AzPrivateDnsRecordConfig -Ipv6Address <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### MX
```
New-AzPrivateDnsRecordConfig -Exchange <String> -Preference <UInt16> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### PTR
```
New-AzPrivateDnsRecordConfig -Ptrdname <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### TXT
```
New-AzPrivateDnsRecordConfig -Value <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### SRV
```
New-AzPrivateDnsRecordConfig -Priority <UInt16> -Target <String> -Port <UInt16> -Weight <UInt16>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### CNAME
```
New-AzPrivateDnsRecordConfig -Cname <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet New-AzPrivateDnsRecordConfig membuat objek PSPrivateDnsRecord lokal. Array objek ini akan diteruskan ke cmdlet New-AzPrivateDnsRecordSet menggunakan parameter PrivateDnsRecord untuk menentukan rekaman untuk dibuat dalam kumpulan rekaman.

## EXAMPLES

### Contoh 1: Membuat Set Rekaman tipe A
```powershell
PS C:\> $Records = @()
PS C:\> $Records += New-AzPrivateDnsRecordConfig -IPv4Address 1.2.3.4
PS C:\> $RecordSet = New-AzPrivateDnsRecordSet -Name "www" -RecordType A -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -PrivateDnsRecords $Records

# When creating a RecordSet containing a single record, the above sequence can also be condensed into a single line:

PS C:\> $RecordSet = New-AzPrivateDnsRecordSet -Name "www" -RecordType A -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -PrivateDnsRecords (New-AzPrivateDnsRecordConfig -IPv4Address 1.2.3.4)

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

PS C:\> $Records = @()
PS C:\> $Records += New-AzPrivateDnsRecordConfig -IPv4Address 1.2.3.4
PS C:\> $Records += New-AzPrivateDnsRecordConfig -IPv4Address 5.6.7.8
PS C:\> $RecordSet = New-AzPrivateDnsRecordSet -Name "www" -RecordType A -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -PrivateDnsRecords $Records

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

Contoh ini membuat RecordSet bernama www di zona privat myzone.com. Kumpulan catatan berjenis A dan memiliki TTL 1 jam (3600 detik). Daftar ini berisi satu catatan DNS Privat.

### Contoh 2: Membuat RecordSet tipe AAAA
```powershell
PS C:\> $Records = @()
PS C:\> $Records += New-AzPrivateDnsRecordConfig -Ipv6Address 2001:db8::1
PS C:\> $RecordSet = New-AzPrivateDnsRecordSet -Name "www" -RecordType AAAA -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -PrivateDnsRecords $Records

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

Contoh ini membuat RecordSet bernama www di zona privat myzone.com. Kumpulan catatan merupakan tipe AAAA dan memiliki TTL 1 jam (3600 detik). Daftar ini berisi satu catatan DNS Privat. Untuk membuat Kumpulan Rekaman menggunakan hanya satu baris pn_PowerShell_short, atau untuk membuat kumpulan catatan dengan beberapa rekaman, lihat Contoh 1.

### Contoh 3: Membuat RecordSet tipe CNAME
```powershell
PS C:\> $Records = @()
PS C:\> $Records += New-AzPrivateDnsRecordConfig -Cname www.contoso.com
PS C:\> $RecordSet = New-AzPrivateDnsRecordSet -Name "www" -RecordType CNAME -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -PrivateDnsRecords $Records

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

Contoh ini membuat RecordSet bernama www di zona privat myzone.com. Kumpulan catatan merupakan tipe CNAME dan memiliki TTL 1 jam (3600 detik). Daftar ini berisi satu catatan DNS Privat. Untuk membuat Kumpulan Rekaman menggunakan hanya satu baris pn_PowerShell_short, atau untuk membuat kumpulan catatan dengan beberapa rekaman, lihat Contoh 1.

### Contoh 4: Membuat Set Rekaman tipe MX
```powershell
PS C:\> $Records = @()
PS C:\> $Records += New-AzPrivateDnsRecordConfig -Exchange "mail.microsoft.com" -Preference 5
PS C:\> $RecordSet = New-AzPrivateDnsRecordSet -Name "www" -RecordType MX -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -PrivateDnsRecords $Records

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

Perintah ini membuat RecordSet bernama www di zona privat myzone.com. Kumpulan catatan berjenis MX dan memiliki TTL 1 jam (3600 detik). Daftar ini berisi satu catatan DNS Privat. Untuk membuat Kumpulan Rekaman menggunakan hanya satu baris pn_PowerShell_short, atau untuk membuat kumpulan catatan dengan beberapa rekaman, lihat Contoh 1.

### Contoh 5: Membuat Set Rekaman tipe PTR
```powershell
PS C:\> $Records = @()
PS C:\> $Records += New-AzPrivateDnsRecordConfig -Ptrdname www.contoso.com
PS C:\> $RecordSet = New-AzPrivateDnsRecordSet -Name "4" -RecordType PTR -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "3.2.1.in-addr.arpa" -PrivateDnsRecords $Records

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

Perintah ini membuat RecordSet bernama 4 dalam zona privat 3.2.1.in-addr.arpa. Kumpulan catatan merupakan tipe PTR dan memiliki TTL 1 jam (3600 detik). Daftar ini berisi satu catatan DNS Privat. Untuk membuat Kumpulan Rekaman menggunakan hanya satu baris pn_PowerShell_short, atau untuk membuat kumpulan catatan dengan beberapa rekaman, lihat Contoh 1.

### Contoh 6: Membuat RecordSet tipe SRV
```powershell
PS C:\> $Records = @()
PS C:\> $Records += New-AzPrivateDnsRecordConfig -Priority 0 -Weight 5 -Port 8080 -Target sipservice.contoso.com
PS C:\> $RecordSet = New-AzPrivateDnsRecordSet -Name "_sip._tcp" -RecordType SRV -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -PrivateDnsRecords $Records

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

Perintah ini membuat RecordSet bernama _sip._tcp dalam zona privat myzone.com. Kumpulan catatan berjenis SRV dan memiliki TTL 1 jam (3600 detik). Daftar ini berisi satu catatan DNS Privat, yang mengarah ke alamat IP 2001.2.3.4. Layanan (sip) dan protokol (tcp) ditentukan sebagai bagian dari nama kumpulan catatan, bukan sebagai bagian dari data rekaman. Untuk membuat Kumpulan Rekaman menggunakan hanya satu baris pn_PowerShell_short, atau untuk membuat kumpulan catatan dengan beberapa rekaman, lihat Contoh 1.

### Contoh 7: Buat RecordSet tipe TXT
```powershell
PS C:\> $Records = @()
PS C:\> $Records += New-AzPrivateDnsRecordConfig -Value "This is a TXT Record"
PS C:\> $RecordSet = New-AzPrivateDnsRecordSet -Name "text" -RecordType TXT -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -PrivateDnsRecords $Records

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

Perintah ini akan membuat teks bernama RecordSet dalam zona myzone.com. Kumpulan catatan merupakan tipe TXT dan memiliki TTL 1 jam (3600 detik). Daftar ini berisi satu catatan DNS Privat. Untuk membuat Kumpulan Rekaman menggunakan hanya satu baris pn_PowerShell_short, atau untuk membuat kumpulan catatan dengan beberapa rekaman, lihat Contoh 1.

## PARAMETERS

### -Cname
Nama kanonis untuk catatan CNAME untuk ditambahkan.
Tidak boleh terkait dengan nama zona.
Titik harus tidak mempunyai titik yang berakhiran

```yaml
Type: System.String
Parameter Sets: CNAME
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -Exchange
Host pertukaran email untuk catatan MX yang akan ditambahkan.
Tidak boleh terkait dengan nama zona.
Titik harus tidak mempunyai titik yang berakhiran

```yaml
Type: System.String
Parameter Sets: MX
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Ipv4Address
Alamat IPv4 untuk catatan A untuk ditambahkan.

```yaml
Type: System.String
Parameter Sets: A
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Ipv6Address
Alamat IPv6 untuk catatan AAAA untuk ditambahkan.

```yaml
Type: System.String
Parameter Sets: AAAA
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Port
Nomor port untuk catatan SRV yang akan ditambahkan.

```yaml
Type: System.UInt16
Parameter Sets: SRV
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Preferensi
Nilai preferensi untuk catatan MX yang akan ditambahkan.

```yaml
Type: System.UInt16
Parameter Sets: MX
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Prioritas
Catatan nilai prioritas SRV untuk ditambahkan.

```yaml
Type: System.UInt16
Parameter Sets: SRV
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Ptrdname
Host target untuk catatan PTR yang akan ditambahkan.
Tidak boleh terkait dengan nama zona.
Titik harus tidak mempunyai titik yang berakhiran

```yaml
Type: System.String
Parameter Sets: PTR
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Target
Host target untuk catatan SRV yang akan ditambahkan.
Tidak boleh terkait dengan nama zona.
Titik harus tidak mempunyai titik yang berakhiran

```yaml
Type: System.String
Parameter Sets: SRV
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Value
Nilai teks untuk catatan TXT yang akan ditambahkan.

```yaml
Type: System.String
Parameter Sets: TXT
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Bobot
Nilai bobot untuk catatan SRV yang akan ditambahkan.

```yaml
Type: System.UInt16
Parameter Sets: SRV
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.PrivateDns.Models.PSPrivateDnsRecordSet

## CATATAN

## RELATED LINKS
