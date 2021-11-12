---
external help file: Microsoft.Azure.Commands.Dns.dll-Help.xml
Module Name: AzureRM.Dns
ms.assetid: 45DF71E0-77E1-4D20-AD09-2C06680F659F
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Dns/Commands.Dns/help/New-AzureRmDnsRecordSet.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Dns/Commands.Dns/help/New-AzureRmDnsRecordSet.md
ms.openlocfilehash: 4ceba6333d382b48e8e93ce6c63bde9e02b8f7ff
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132426126"
---
# New-AzureRmDnsRecordSet

## SYNOPSIS
Membuat kumpulan catatan DNS.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### Bidang
```
New-AzureRmDnsRecordSet -Name <String> -ZoneName <String> -ResourceGroupName <String> -Ttl <UInt32>
 -RecordType <RecordType> [-Metadata <Hashtable>] [-DnsRecords <DnsRecordBase[]>] [-Overwrite] [-Force]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Object
```
New-AzureRmDnsRecordSet -Name <String> -Zone <DnsZone> -Ttl <UInt32> -RecordType <RecordType>
 [-Metadata <Hashtable>] [-DnsRecords <DnsRecordBase[]>] [-Overwrite] [-Force]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureRmDnsRecordSet** membuat kumpulan catatan Domain Name System (DNS) baru dengan nama dan tipe yang ditentukan di zona yang ditentukan.
Objek **RecordSet** adalah kumpulan catatan DNS dengan nama dan tipe yang sama.
Perhatikan bahwa nama relatif terhadap zona dan bukan nama yang sepenuhnya memenuhi syarat.

Parameter *DnsRecords* menentukan data dalam kumpulan data.
Parameter ini mengambil array catatan DNS, yang dibangun menggunakan New-AzureRmDnsRecordConfig.

Anda dapat menggunakan operator pipeline untuk menyampaikan objek **DnsZone** ke cmdlet ini, atau Anda dapat melewati objek **DnsZone** sebagai *parameter* Zona, atau menentukan zona menurut nama.

Anda dapat menggunakan *perintah* Konfirmasi parameter $ConfirmPreference Windows PowerShell variabel untuk mengontrol apakah cmdlet meminta konfirmasi Anda.

Jika **RecordSet yang** cocok sudah ada (nama dan tipe catatan yang sama), Anda harus menentukan parameter *Timpa,* jika tidak cmdlet tidak akan membuat **RecordSet baru.**

## EXAMPLES

### Contoh 1: Membuat Set Rekaman tipe A
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

Contoh ini membuat **RecordSet bernama** www di zona myzone.com.
Kumpulan catatan berjenis A dan memiliki TTL 1 jam (3600 detik).
Daftar ini berisi satu catatan DNS.

### Contoh 2: Membuat RecordSet tipe AAAA
```
PS C:\> $Records = @()
PS C:\> $Records += New-AzureRmDnsRecordConfig -Ipv6Address 2001:db8::1
PS C:\> $RecordSet = New-AzureRmDnsRecordSet -Name "www" -RecordType AAAA -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -DnsRecords $Records
```

Contoh ini membuat **RecordSet bernama** www di zona myzone.com.
Kumpulan catatan merupakan tipe AAAA dan memiliki TTL 1 jam (3600 detik).
Daftar ini berisi satu catatan DNS.

Untuk membuat Kumpulan **Rekaman** menggunakan hanya satu baris pn_PowerShell_short, atau untuk membuat kumpulan catatan dengan beberapa rekaman, lihat Contoh 1.

### Contoh 3: Membuat RecordSet tipe CNAME
```
PS C:\> $Records = @()
PS C:\> $Records += New-AzureRmDnsRecordConfig -Cname www.contoso.com
PS C:\> $RecordSet = New-AzureRmDnsRecordSet -Name "www" -RecordType CNAME -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -DnsRecords $Records
```

Contoh ini membuat **RecordSet bernama** www di zona myzone.com.
Kumpulan catatan merupakan tipe CNAME dan memiliki TTL 1 jam (3600 detik).
Daftar ini berisi satu catatan DNS.

Untuk membuat Kumpulan **Rekaman** menggunakan hanya satu baris pn_PowerShell_short, atau untuk membuat kumpulan catatan dengan beberapa rekaman, lihat Contoh 1.

### Contoh 4: Membuat Set Rekaman tipe MX
```
PS C:\> $Records = @()
PS C:\> $Records += New-AzureRmDnsRecordConfig -Exchange "mail.microsoft.com" -Preference 5
PS C:\> $RecordSet = New-AzureRmDnsRecordSet -Name "www" -RecordType AAAA -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -DnsRecords $Records
```

Perintah ini akan membuat **RecordSet** bernama www dalam zona myzone.com.
Kumpulan catatan berjenis MX dan memiliki TTL 1 jam (3600 detik).
Daftar ini berisi satu catatan DNS.

Untuk membuat Kumpulan **Rekaman** menggunakan hanya satu baris pn_PowerShell_short, atau untuk membuat kumpulan catatan dengan beberapa rekaman, lihat Contoh 1.

### Contoh 5: Membuat Set Rekaman tipe NS
```
PS C:\> $Records = @()
PS C:\> $Records += New-AzureRmDnsRecordConfig -Nsdname ns1-01.azure-dns.com
PS C:\> $RecordSet = New-AzureRmDnsRecordSet -Name "ns1" -RecordType NS -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -DnsRecords $Records
```

Perintah ini membuat **RecordSet bernama** ns1 dalam zona myzone.com.
Kumpulan rekaman berjenis NS dan memiliki TTL 1 jam (3600 detik).
Daftar ini berisi satu catatan DNS.

Untuk membuat Kumpulan **Rekaman** menggunakan hanya satu baris pn_PowerShell_short, atau untuk membuat kumpulan catatan dengan beberapa rekaman, lihat Contoh 1.

### Contoh 6: Membuat Set Rekaman tipe PTR
```
PS C:\> $Records = @()
PS C:\> $Records += New-AzureRmDnsRecordConfig -Ptrdname www.contoso.com
PS C:\> $RecordSet = New-AzureRmDnsRecordSet -Name "4" -RecordType PTR -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "3.2.1.in-addr.arpa" -DnsRecords $Records
```

Perintah ini membuat **RecordSet bernama** 4 dalam zona 3.2.1.in-addr.arpa.
Kumpulan catatan merupakan tipe PTR dan memiliki TTL 1 jam (3600 detik).
Daftar ini berisi satu catatan DNS.

Untuk membuat Kumpulan **Rekaman** menggunakan hanya satu baris pn_PowerShell_short, atau untuk membuat kumpulan catatan dengan beberapa rekaman, lihat Contoh 1.

### Contoh 7: Membuat RecordSet tipe SRV
```
PS C:\> $Records = @()
PS C:\> $Records += New-AzureRmDnsRecordConfig -Priority 0 -Weight 5 -Port 8080 -Target sipservice.contoso.com
PS C:\> $RecordSet = New-AzureRmDnsRecordSet -Name "_sip._tcp" -RecordType SRV -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -DnsRecords $Records
```

Perintah ini membuat **RecordSet bernama** _sip._tcp dalam zona myzone.com.
Kumpulan catatan berjenis SRV dan memiliki TTL 1 jam (3600 detik).
Daftar ini berisi satu catatan DNS, mengarahkan ke alamat IP 2001.2.3.4.

Layanan (sip) dan protokol (tcp) ditentukan sebagai bagian dari nama kumpulan catatan, bukan sebagai bagian dari data rekaman.

Untuk membuat Kumpulan **Rekaman** menggunakan hanya satu baris pn_PowerShell_short, atau untuk membuat kumpulan catatan dengan beberapa rekaman, lihat Contoh 1.

### Contoh 8: Buat RecordSet tipe TXT
```
PS C:\> $Records = @()
PS C:\> $Records += New-AzureRmDnsRecordConfig -Value "This is a TXT Record"
PS C:\> $RecordSet = New-AzureRmDnsRecordSet -Name "text" -RecordType TXT -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -DnsRecords $Records
```

Perintah ini akan membuat **teks bernama RecordSet** dalam zona myzone.com.
Kumpulan catatan merupakan tipe TXT dan memiliki TTL 1 jam (3600 detik).
Daftar ini berisi satu catatan DNS.

Untuk membuat Kumpulan **Rekaman** menggunakan hanya satu baris pn_PowerShell_short, atau untuk membuat kumpulan catatan dengan beberapa rekaman, lihat Contoh 1.

### Contoh 9: Create a RecordSet at the zone apex
```
PS C:\> $Records = @()
PS C:\> $Records += New-AzureRmDnsRecordConfig -Ipv4Address 1.2.3.4
PS C:\> $RecordSet = New-AzureRmDnsRecordSet -Name "@" -RecordType A -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -DnsRecords $Records
```

Perintah ini membuat **RecordSet** di ujung (atau akar) zona myzone.com.
Untuk melakukan ini, nama kumpulan catatan ditentukan sebagai "@" (termasuk tanda kutip ganda).

Anda tidak dapat membuat data CNAME di bagian atas zona.
Ini adalah batasan standar DNS; namun tidak terbatas pada Azure DNS.

Untuk membuat Kumpulan **Rekaman** menggunakan hanya satu baris pn_PowerShell_short, atau untuk membuat kumpulan catatan dengan beberapa rekaman, lihat Contoh 1.

### Contoh 10: Membuat Kumpulan Rekaman wildcard
```
PS C:\> $Records = @()
PS C:\> $Records += New-AzureRmDnsRecordConfig -Ipv4Address 1.2.3.4
PS C:\> $RecordSet = New-AzureRmDnsRecordSet -Name "*" -RecordType A -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -DnsRecords $Records
```

Perintah ini akan membuat **RecordSet** bernama * dalam zona myzone.com.
Ini adalah kumpulan catatan wildcard.

Untuk membuat Kumpulan **Rekaman** menggunakan hanya satu baris pn_PowerShell_short, atau untuk membuat kumpulan catatan dengan beberapa rekaman, lihat Contoh 1.

### Contoh 11: Membuat kumpulan data kosong
```
PS C:\>$RecordSet = New-AzureRmDnsRecordSet -Name "www" -RecordType A -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -DnsRecords @()
```

Perintah ini akan membuat **RecordSet** bernama www dalam zona myzone.com.
Kumpulan catatan berjenis A dan memiliki TTL 1 jam (3600 detik).
Ini adalah kumpulan catatan kosong, yang bertindak sebagai tempat penampung untuk kemudian bisa Anda tambahkan catatan.

### Contoh 12: Membuat kumpulan data dan menyembunyikan semua konfirmasi
```
PS C:\>$RecordSet = New-AzureRmDnsRecordSet -Name "www" -RecordType A -ResourceGroupName "MyResourceGroup" -TTL 3600 -ZoneName "myzone.com" -DnsRecords (New-AzureRmDnsRecordConfig -Ipv4Address 1.2.3.4) -Confirm:$False -Overwrite
```

Perintah ini akan membuat **RecordSet**.
Parameter *Overwrite* memastikan bahwa kumpulan data ini menimpa kumpulan data apa pun yang sudah ada sebelumnya dengan nama dan tipe yang sama (catatan yang sudah ada dalam kumpulan catatan tersebut akan hilang).
Parameter *Konfirmasi* dengan nilai $False menyembunyikan perintah konfirmasi.

## PARAMETERS

### -DnsRecords
Menentukan array catatan DNS yang akan disertakan dalam kumpulan catatan.
Anda bisa menggunakan cmdlet New-AzureRmDnsRecordConfig untuk membuat objek catatan DNS.
Lihat contoh-contoh untuk informasi selengkapnya.

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

### -Force
Parameter ini tidak berlaku bagi cmdlet ini.
File akan dihapus pada rilis mendatang.

Untuk mengontrol apakah cmdlet ini akan meminta konfirmasi Anda, gunakan parameter *Konfirmasi.*

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

### -Metadata
Menentukan array metadata yang akan dikaitkan dengan Set Rekaman.
Metadata ditentukan menggunakan pasangan nilai nama yang dinyatakan sebagai tabel hash, misalnya @(@{"Name"="dept"; "Value"="shopping"}, @{"Name"="env"; "Value"="production"}).

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

### -Nama
Menentukan nama **RecordSet untuk** dibuat.

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

### -Overwrite
Mengindikasikan bahwa cmdlet ini menimpa **RecordSet tertentu** jika sudah ada.

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

Nilai valid adalah:

- A
- AAAA
- CNAME
- MX
- NS
- PTR
- SRV
- TXT

Catatan SOA dibuat secara otomatis saat zona dibuat dan tidak dapat dibuat secara manual.

```yaml
Type: Microsoft.Azure.Management.Dns.Models.RecordType
Parameter Sets: (All)
Aliases: 
Accepted values: A, AAAA, CNAME, MX, NS, PTR, SOA, SRV, TXT

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan grup sumber daya yang berisi zona DNS.
Anda juga harus menentukan parameter *ZoneName* untuk menentukan nama zona.

Alternatifnya, Anda dapat menentukan grup zona dan sumber daya dengan memberikan objek Zona DNS menggunakan *parameter Zona.*

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

### -Ttl
Menentukan Waktu untuk Live (TTL) untuk Catatan DNSSet.

```yaml
Type: System.UInt32
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Zone
Menentukan Zona Dns untuk membuat **RecordSet**.
Alternatifnya, Anda bisa menentukan zona menggunakan parameter *ZoneName* *dan ResourceGroupName.*

```yaml
Type: Microsoft.Azure.Commands.Dns.DnsZone
Parameter Sets: Object
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ZoneName
Menentukan nama zona untuk membuat **RecordSet**.
Anda juga harus menentukan grup sumber daya yang berisi zona menggunakan parameter *ResourceGroupName.*

Alternatifnya, Anda dapat menentukan grup zona dan sumber daya dengan memberikan objek Zona DNS menggunakan *parameter Zona.*

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

### Microsoft.Azure.Commands.Dns.DnsZone
Anda dapat pipa objek DnsZone ke cmdlet ini.

## OUTPUTS

### Microsoft.Azure.Commands.Dns.DnsRecordSet
Cmdlet ini mengembalikan objek **RecordSet.**

## CATATAN
Anda dapat menggunakan parameter *Konfirmasi* untuk mengontrol apakah cmdlet ini meminta konfirmasi.
Secara default, cmdlet akan meminta konfirmasi Anda jika $ConfirmPreference Windows PowerShell variabel memiliki nilai Sedang atau lebih rendah.

Jika Anda menetapkan *Konfirmasi* *atau Konfirmasi:$True*, cmdlet ini akan meminta konfirmasi sebelum dijalankan.
Jika Anda menentukan *Confirm:$False*, cmdlet tidak akan meminta konfirmasi Anda.

## RELATED LINKS

[Add-AzureRmDnsRecordConfig](./Add-AzureRmDnsRecordConfig.md)

[Get-AzureRmDnsRecordSet](./Get-AzureRmDnsRecordSet.md)

[New-AzureRmDnsRecordConfig](./New-AzureRmDnsRecordConfig.md)

[Remove-AzureRmDnsRecordSet](./Remove-AzureRmDnsRecordSet.md)

[Set-AzureRmDnsRecordSet](./Set-AzureRmDnsRecordSet.md)
