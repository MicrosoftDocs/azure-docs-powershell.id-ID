---
external help file: Microsoft.Azure.Commands.Dns.dll-Help.xml
ms.assetid: 40179CF3-7896-4C45-BC18-4CB653B245B6
online version: ''
schema: 2.0.0
ms.openlocfilehash: 4027b13fb398d69bee09be5c0a939ff86a099e39
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143113653"
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

### Objek
```
Get-AzureRmDnsRecordSet [-Name <String>] -Zone <DnsZone> [-RecordType <RecordType>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmDnsRecordSet** mendapatkan kumpulan catatan Domain Name System (DNS) dengan nama dan tipe yang ditentukan, dalam zona yang ditentukan.

Jika Anda tidak menentukan parameter *Name* atau *RecordType* , cmdlet ini mengembalikan semua kumpulan rekaman dari tipe yang ditentukan dalam zona.
Jika Anda menentukan parameter *RecordType* tapi bukan parameter *Nama* , cmdlet ini mengembalikan semua kumpulan rekaman dari tipe catatan yang ditentukan.

Anda bisa menggunakan operator pipeline untuk mengirimkan objek **DnsZone** ke cmdlet ini, atau Anda bisa melewati objek **DnsZone** sebagai parameter *Zona* , atau alternatifnya Anda bisa menentukan zona dan grup sumber daya menurut nama.

## EXAMPLES

### Contoh 1: Mendapatkan kumpulan catatan dengan nama dan tipe yang ditentukan
```
PS C:\>$RecordSet = Get-AzureRmDnsRecordSet -ResourceGroupName "MyResourceGroup" -ZoneName "myzone.com" -Name "www" -RecordType A
```

Perintah ini mendapatkan kumpulan catatan tipe catatan A bernama www dalam grup dan zona sumber daya tertentu, lalu menyimpannya dalam variabel $RecordSet.
Karena parameter *Name* dan *RecordType* ditentukan, hanya satu objek **RecordSet** yang dikembalikan.

### Contoh 2: Mendapatkan kumpulan rekaman dari tipe yang ditentukan
```
PS C:\>$RecordSets = Get-AzureRmDnsRecordSet -ResourceGroupName "MyResourceGroup" -ZoneName "myzone.com" -RecordType A
```

Perintah ini mendapatkan array dari semua kumpulan rekaman tipe A di zona bernama myzone.com dalam grup sumber daya bernama MyResourceGroup, lalu menyimpannya dalam variabel $RecordSets.

### Contoh 3: Mendapatkan semua kumpulan rekaman dalam zona
```
PS C:\>$RecordSets = Get-AzureRmDnsRecordSet -ResourceGroupName "MyResourceGroup" -ZoneName "myzone.com"
```

Perintah ini mendapatkan array semua kumpulan rekaman dalam zona bernama myzone.com dalam grup sumber daya bernama MyResourceGroup, lalu menyimpannya dalam variabel $RecordSets.

### Contoh 4: Dapatkan semua kumpulan catatan dalam zona, menggunakan objek DnsZone
```
PS C:\> $Zone = Get-AzureRmDnsZone -Name "myzone.com" -ResourceGroupName "MyResourceGroup"
PS C:\> $RecordSets = Get-AzureRmDnsRecordSet -Zone $Zone
```

Contoh ini sama dengan Contoh 3 di atas.
Kali ini, zona ditentukan menggunakan objek zona.

## PARAMETERS

### -Nama
Menentukan nama **RecordSet** yang akan didapatkan.
Jika Anda tidak menentukan parameter *Nama* , semua kumpulan rekaman dari tipe yang ditentukan akan dikembalikan.

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
Menentukan tipe catatan DNS yang didapat cmdlet ini.

Nilai yang valid adalah: 

- J
- AAAA
- CNAME
- MX
- NS
- PTR
- SOA
- SRV
- TXT

Jika tidak menentukan parameter *RecordType* , Anda juga harus menghilangkan parameter *Nama* . Cmdlet ini kemudian mengembalikan semua kumpulan rekaman dalam zona (dari semua nama dan tipe).

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
Nama zona juga harus ditentukan, menggunakan parameter *ZoneName* .

Atau, Anda dapat menentukan zona dan grup sumber daya dengan masuk ke objek **DnsZone** menggunakan parameter *Zona* .

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

### -Zona
Menentukan zona DNS yang berisi kumpulan catatan yang didapatkan cmdlet ini.
Atau, Anda dapat menentukan zona menggunakan parameter *ZoneName* dan *ResourceGroupName* .

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
Menentukan nama zona DNS yang berisi kumpulan catatan untuk didapatkan.
Grup sumber daya yang berisi zona juga harus ditentukan, menggunakan parameter *ResourceGroupName* .

Alternatifnya, Anda dapat menentukan zona dan grup sumber daya dengan masuk ke objek Zona DNS menggunakan parameter *Zona* .

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Dns.DnsZone
Anda dapat menyalurkan objek **DnsZone** ke cmdlet ini.
Objek **DnsZone** mewakili zona untuk mencari objek **RecordSet** .

## OUTPUTS

### Microsoft.Azure.Commands.Dns.DnsRecordSet
Cmdlet ini mengembalikan satu atau beberapa objek yang mewakili kumpulan rekaman yang ditemukan.
Akan ada paling banyak satu **RecordSet** yang dikembalikan jika parameter *Name* dan *RecordType* ditentukan, jika tidak beberapa objek **RecordSet** dikembalikan sebagai array.

## NOTES

## RELATED LINKS

[New-AzureRmDnsRecordSet](./New-AzureRmDnsRecordSet.md)

[Remove-AzureRmDnsRecordSet](./Remove-AzureRmDnsRecordSet.md)

[Set-AzureRmDnsRecordSet](./Set-AzureRmDnsRecordSet.md)


