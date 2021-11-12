---
external help file: Microsoft.Azure.Commands.Dns.dll-Help.xml
ms.assetid: 40179CF3-7896-4C45-BC18-4CB653B245B6
online version: ''
schema: 2.0.0
ms.openlocfilehash: 4027b13fb398d69bee09be5c0a939ff86a099e39
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132428772"
---
# Get-AzureRmDnsRecordSet

## SYNOPSIS
Mendapatkan kumpulan catatan DNS.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### Bidang
```
Get-AzureRmDnsRecordSet [-Name <String>] -ZoneName <String> -ResourceGroupName <String>
 [-RecordType <RecordType>] [<CommonParameters>]
```

### Object
```
Get-AzureRmDnsRecordSet [-Name <String>] -Zone <DnsZone> [-RecordType <RecordType>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmDnsRecordSet** mendapatkan kumpulan catatan Domain Name System (DNS) dengan nama dan tipe yang ditentukan, dalam zona yang ditentukan.

Jika Anda tidak menentukan parameter *Name* atau *RecordType,* cmdlet ini akan mengembalikan semua kumpulan data tipe yang ditentukan dalam zona.
Jika Anda menentukan parameter *RecordType* tetapi bukan parameter *Name,* cmdlet ini akan mengembalikan semua kumpulan data tipe catatan yang ditentukan.

Anda dapat menggunakan operator pipeline untuk menyampaikan objek **DnsZone** ke cmdlet ini, atau anda dapat melewati objek **DnsZone** sebagai *parameter* Zona, atau menentukan zona dan grup sumber daya berdasarkan nama.

## EXAMPLES

### Contoh 1: Mendapatkan kumpulan rekaman dengan nama dan tipe yang ditentukan
```
PS C:\>$RecordSet = Get-AzureRmDnsRecordSet -ResourceGroupName "MyResourceGroup" -ZoneName "myzone.com" -Name "www" -RecordType A
```

Perintah ini mendapatkan kumpulan catatan tipe catatan A bernama www dalam grup dan zona sumber daya yang ditentukan, lalu menyimpannya di $RecordSet sumber daya.
Karena parameter *Nama* *dan RecordType* ditentukan, hanya satu **objek RecordSet** yang dikembalikan.

### Contoh 2: Mendapatkan kumpulan rekaman dari tipe tertentu
```
PS C:\>$RecordSets = Get-AzureRmDnsRecordSet -ResourceGroupName "MyResourceGroup" -ZoneName "myzone.com" -RecordType A
```

Perintah ini mendapatkan array dari semua kumpulan data tipe data A dalam zona yang bernama myzone.com di grup sumber daya yang bernama MyResourceGroup, lalu menyimpannya di $RecordSets sumber daya.

### Contoh 3: Mendapatkan semua kumpulan rekaman dalam satu zona
```
PS C:\>$RecordSets = Get-AzureRmDnsRecordSet -ResourceGroupName "MyResourceGroup" -ZoneName "myzone.com"
```

Perintah ini mendapatkan array semua kumpulan data dalam zona yang bernama myzone.com dalam grup sumber daya yang bernama MyResourceGroup, lalu menyimpannya dalam $RecordSets sumber daya.

### Contoh 4: Mendapatkan semua kumpulan rekaman dalam satu zona, menggunakan objek DnsZone
```
PS C:\> $Zone = Get-AzureRmDnsZone -Name "myzone.com" -ResourceGroupName "MyResourceGroup"
PS C:\> $RecordSets = Get-AzureRmDnsRecordSet -Zone $Zone
```

Contoh ini sama dengan Contoh 3 di atas.
Saat ini, zona ditentukan menggunakan objek zona.

## PARAMETERS

### -Nama
Menentukan nama **RecordSet untuk** mendapatkan.
Jika Anda tidak menentukan parameter *Name,* semua kumpulan data dari tipe tertentu akan dikembalikan.

```yaml
Type: String
Parameter Sets: Fields
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: Object
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RecordType
Menentukan tipe catatan DNS yang akan dapatkan cmdlet ini.

Nilai valid adalah: 

- A
- AAAA
- CNAME
- MX
- NS
- PTR
- SOA
- SRV
- TXT

Jika Anda tidak menentukan parameter *RecordType,* Anda juga harus menghilangkan parameter *Name.* Cmdlet ini lalu mengembalikan semua kumpulan data dalam zona (semua nama dan tipe).

```yaml
Type: RecordType
Parameter Sets: (All)
Aliases: 
Accepted values: A, AAAA, CNAME, MX, NS, PTR, SOA, SRV, TXT

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan grup sumber daya yang berisi zona DNS.
Nama zona juga harus ditentukan, menggunakan parameter *ZoneName.*

Alternatifnya, Anda dapat menentukan zona dan grup sumber daya dengan memberikan **objek DnsZone** menggunakan *parameter Zona.*

```yaml
Type: String
Parameter Sets: Fields
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Zone
Menentukan zona DNS yang berisi kumpulan data yang akan cmdlet ini dapatkan.
Alternatifnya, Anda bisa menentukan zona menggunakan parameter *ZoneName* *dan ResourceGroupName.*

```yaml
Type: DnsZone
Parameter Sets: Object
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ZoneName
Menentukan nama zona DNS yang berisi catatan yang akan mendapatkannya.
Grup sumber daya yang berisi zona juga harus ditentukan, menggunakan parameter *ResourceGroupName.*

Alternatifnya, Anda dapat menentukan grup zona dan sumber daya dengan memberikan objek Zona DNS menggunakan *parameter Zona.*

```yaml
Type: String
Parameter Sets: Fields
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Microsoft.Azure.Commands.Dns.DnsZone
Anda dapat pipa objek **DnsZone** ke cmdlet ini.
Objek **DnsZone** mewakili zona untuk mencari objek **RecordSet.**

## OUTPUTS

### Microsoft.Azure.Commands.Dns.DnsRecordSet
Cmdlet ini mengembalikan satu atau beberapa objek yang mewakili kumpulan data yang ditemukan.
Akan ada di sebagian besar **RecordSet** yang dikembalikan jika parameter Nama dan *RecordType* ditentukan, jika tidak beberapa objek  **RecordSet** dikembalikan sebagai array.

## CATATAN

## RELATED LINKS

[New-AzureRmDnsRecordSet](./New-AzureRmDnsRecordSet.md)

[Remove-AzureRmDnsRecordSet](./Remove-AzureRmDnsRecordSet.md)

[Set-AzureRmDnsRecordSet](./Set-AzureRmDnsRecordSet.md)


