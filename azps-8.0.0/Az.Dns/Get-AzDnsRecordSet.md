---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Dns.dll-Help.xml
Module Name: Az.Dns
ms.assetid: 40179CF3-7896-4C45-BC18-4CB653B245B6
online version: https://docs.microsoft.com/powershell/module/az.dns/get-azdnsrecordset
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Dns/Dns/help/Get-AzDnsRecordSet.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Dns/Dns/help/Get-AzDnsRecordSet.md
ms.openlocfilehash: 73c7d311786a30ff423af51b91295f9bfa9fe87b
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145517050"
---
# Get-AzDnsRecordSet

## SYNOPSIS
Mendapatkan rangkaian data DNS.

## SYNTAX

### Bidang
```
Get-AzDnsRecordSet [-Name <String>] -ZoneName <String> -ResourceGroupName <String> [-RecordType <RecordType>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### Objek
```
Get-AzDnsRecordSet [-Name <String>] -Zone <DnsZone> [-RecordType <RecordType>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzDnsRecordSet** mendapatkan kumpulan catatan Sistem Nama Domain (DNS) dengan nama dan jenis yang ditentukan, di zona yang ditentukan.
Jika Anda tidak menentukan parameter *Nama* atau *RecordType* , cmdlet ini mengembalikan semua kumpulan catatan dari jenis yang ditentukan di zona tersebut.
Jika Anda menentukan parameter *RecordType* tetapi bukan parameter *Nama* , cmdlet ini mengembalikan semua kumpulan catatan dari jenis catatan yang ditentukan.
Anda dapat menggunakan operator alur untuk meneruskan objek **DnsZone** ke cmdlet ini, atau Anda dapat meneruskan objek **DnsZone** sebagai parameter *Zona* , atau anda dapat menentukan zona dan grup sumber daya berdasarkan nama.

## EXAMPLES

### Contoh 1: Mendapatkan kumpulan catatan dengan nama dan jenis tertentu
```powershell
$RecordSet = Get-AzDnsRecordSet -ResourceGroupName "MyResourceGroup" -ZoneName "myzone.com" -Name "www" -RecordType A
```

Perintah ini mendapatkan kumpulan catatan jenis catatan A bernama www di grup dan zona sumber daya yang ditentukan, lalu menyimpannya dalam variabel $RecordSet.
Karena parameter *Nama* dan *RecordType* ditentukan, hanya satu objek **RecordSet** yang dikembalikan.

### Contoh 2: Mendapatkan kumpulan catatan dari jenis tertentu
```powershell
$RecordSets = Get-AzDnsRecordSet -ResourceGroupName "MyResourceGroup" -ZoneName "myzone.com" -RecordType A
```

Perintah ini mendapatkan array dari semua kumpulan catatan jenis catatan A di zona bernama myzone.com dalam grup sumber daya bernama MyResourceGroup, lalu menyimpannya dalam variabel $RecordSets.

### Contoh 3: Mendapatkan semua kumpulan catatan dalam zona
```powershell
$RecordSets = Get-AzDnsRecordSet -ResourceGroupName "MyResourceGroup" -ZoneName "myzone.com"
```

Perintah ini mendapatkan array semua kumpulan catatan di zona bernama myzone.com dalam grup sumber daya bernama MyResourceGroup, lalu menyimpannya dalam variabel $RecordSets.

### Contoh 4: Mendapatkan semua kumpulan catatan di zona, menggunakan objek DnsZone
```powershell
$Zone = Get-AzDnsZone -Name "myzone.com" -ResourceGroupName "MyResourceGroup"
$RecordSets = Get-AzDnsRecordSet -Zone $Zone
```

Contoh ini setara dengan Contoh 3 di atas.
Kali ini, zona ditentukan menggunakan objek zona.

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

### -Name
Menentukan nama **RecordSet** yang akan didapatkan.
Jika Anda tidak menentukan parameter *Nama* , semua kumpulan catatan dari jenis yang ditentukan akan dikembalikan.

```yaml
Type: System.String
Parameter Sets: Fields
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: Object
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RecordType
Menentukan jenis catatan DNS yang didapat cmdlet ini.
Nilai yang valid adalah: 
- A
- AAAA
- CNAME
- MX
- NS
- PTR
- SOA
- SRV
- TXT Jika Anda tidak menentukan parameter *RecordType* , Anda juga harus menghilangkan parameter *Nama* . Cmdlet ini kemudian mengembalikan semua kumpulan catatan di zona (dari semua nama dan jenis).

```yaml
Type: System.Nullable`1[Microsoft.Azure.Management.Dns.Models.RecordType]
Parameter Sets: (All)
Aliases:
Accepted values: A, AAAA, CAA, CNAME, MX, NS, PTR, SOA, SRV, TXT

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan grup sumber daya yang berisi zona DNS.
Nama zona juga harus ditentukan, menggunakan parameter *ZoneName* .
Atau, Anda dapat menentukan zona dan grup sumber daya dengan meneruskan objek **DnsZone** menggunakan parameter *Zona* .

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

### -Zona
Menentukan zona DNS yang berisi kumpulan catatan yang didapat cmdlet ini.
Atau, Anda dapat menentukan zona menggunakan parameter *ZoneName* dan *ResourceGroupName* .

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
Menentukan nama zona DNS yang berisi kumpulan catatan yang akan didapatkan.
Grup sumber daya yang berisi zona juga harus ditentukan, menggunakan parameter *ResourceGroupName* .
Atau, Anda dapat menentukan zona dan grup sumber daya dengan meneruskan objek Zona DNS menggunakan parameter *Zona* .

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.Dns.DnsZone

### System.Nullable'1[[Microsoft.Azure.Management.Dns.Models.RecordType, Microsoft.Azure.Management.Dns, Version=3.0.0.0, Culture=netral, PublicKeyToken=31bf3856ad364e35]]

## OUTPUTS

### Microsoft.Azure.Commands.Dns.DnsRecordSet

## NOTES

## RELATED LINKS

[New-AzDnsRecordSet](./New-AzDnsRecordSet.md)

[Remove-AzDnsRecordSet](./Remove-AzDnsRecordSet.md)

[Set-AzDnsRecordSet](./Set-AzDnsRecordSet.md)


