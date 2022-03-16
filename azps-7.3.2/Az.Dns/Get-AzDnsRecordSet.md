---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Dns.dll-Help.xml
Module Name: Az.Dns
ms.assetid: 40179CF3-7896-4C45-BC18-4CB653B245B6
online version: https://docs.microsoft.com/powershell/module/az.dns/get-azdnsrecordset
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Dns/Dns/help/Get-AzDnsRecordSet.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Dns/Dns/help/Get-AzDnsRecordSet.md
ms.openlocfilehash: 3b3f36b58d3c817eed3932e3e10657b1d3e187c7
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140187035"
---
# Get-AzDnsRecordSet

## SYNOPSIS
Mendapatkan kumpulan catatan DNS.

## SYNTAX

### Bidang
```
Get-AzDnsRecordSet [-Name <String>] -ZoneName <String> -ResourceGroupName <String> [-RecordType <RecordType>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### Object
```
Get-AzDnsRecordSet [-Name <String>] -Zone <DnsZone> [-RecordType <RecordType>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzDnsRecordSet** mendapatkan kumpulan catatan Domain Name System (DNS) dengan nama dan tipe yang ditentukan, dalam zona yang ditentukan.
Jika Anda tidak menentukan parameter *Name* atau *RecordType* , cmdlet ini akan mengembalikan semua kumpulan data tipe yang ditentukan dalam zona.
Jika Anda menentukan parameter *RecordType* tetapi bukan parameter *Name* , cmdlet ini akan mengembalikan semua kumpulan data tipe catatan yang ditentukan.
Anda dapat menggunakan operator pipeline untuk menyampaikan objek **DnsZone** ke cmdlet ini, atau anda dapat melewati objek **DnsZone** *sebagai parameter Zona* , atau menentukan zona dan grup sumber daya berdasarkan nama.

## EXAMPLES

### Contoh 1: Mendapatkan kumpulan rekaman dengan nama dan tipe yang ditentukan
```
PS C:\>$RecordSet = Get-AzDnsRecordSet -ResourceGroupName "MyResourceGroup" -ZoneName "myzone.com" -Name "www" -RecordType A
```

Perintah ini mendapatkan kumpulan catatan tipe catatan A bernama www dalam grup dan zona sumber daya yang ditentukan, lalu menyimpannya di $RecordSet sumber daya.
Karena parameter *Nama* *dan RecordType* ditentukan, hanya satu **objek RecordSet** yang dikembalikan.

### Contoh 2: Mendapatkan kumpulan rekaman dari tipe tertentu
```
PS C:\>$RecordSets = Get-AzDnsRecordSet -ResourceGroupName "MyResourceGroup" -ZoneName "myzone.com" -RecordType A
```

Perintah ini mendapatkan array dari semua kumpulan data tipe data A dalam zona yang bernama myzone.com dalam grup sumber daya yang bernama MyResourceGroup, lalu menyimpannya di $RecordSets sumber daya.

### Contoh 3: Mendapatkan semua kumpulan rekaman dalam satu zona
```
PS C:\>$RecordSets = Get-AzDnsRecordSet -ResourceGroupName "MyResourceGroup" -ZoneName "myzone.com"
```

Perintah ini mendapatkan array semua kumpulan data dalam zona yang bernama myzone.com dalam grup sumber daya yang bernama MyResourceGroup, lalu menyimpannya dalam $RecordSets sumber daya.

### Contoh 4: Mendapatkan semua kumpulan rekaman dalam satu zona, menggunakan objek DnsZone
```
PS C:\> $Zone = Get-AzDnsZone -Name "myzone.com" -ResourceGroupName "MyResourceGroup"
PS C:\> $RecordSets = Get-AzDnsRecordSet -Zone $Zone
```

Contoh ini sama dengan Contoh 3 di atas.
Saat ini, zona ditentukan menggunakan objek zona.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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

### -Nama
Menentukan nama **RecordSet untuk** mendapatkan.
Jika Anda tidak menentukan parameter *Name* , semua kumpulan data dari tipe tertentu akan dikembalikan.

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
- TXT Jika Anda tidak menentukan parameter *RecordType* , Anda juga harus menghilangkan parameter *Name* . Cmdlet ini lalu mengembalikan semua kumpulan data dalam zona (semua nama dan tipe).

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
Alternatifnya, Anda dapat menentukan zona dan grup sumber daya dengan memberikan **objek DnsZone** menggunakan *parameter Zona* .

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

### -Zone
Menentukan zona DNS yang berisi kumpulan data yang akan cmdlet ini dapatkan.
Alternatifnya, Anda bisa menentukan zona menggunakan parameter *ZoneName* *dan ResourceGroupName* .

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
Menentukan nama zona DNS yang berisi catatan yang akan mendapatkannya.
Grup sumber daya yang berisi zona juga harus ditentukan, menggunakan parameter *ResourceGroupName* .
Alternatifnya, Anda dapat menentukan grup zona dan sumber daya dengan memberikan objek Zona DNS menggunakan *parameter Zona* .

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

### System.Nullable'1[[Microsoft.Azure.Management.Dns.Models.RecordType, Microsoft.Azure.Management.Dns, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35]]

## OUTPUTS

### Microsoft.Azure.Commands.Dns.DnsRecordSet

## CATATAN

## RELATED LINKS

[New-AzDnsRecordSet](./New-AzDnsRecordSet.md)

[Remove-AzDnsRecordSet](./Remove-AzDnsRecordSet.md)

[Set-AzDnsRecordSet](./Set-AzDnsRecordSet.md)


