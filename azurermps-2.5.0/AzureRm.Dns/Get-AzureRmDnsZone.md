---
external help file: Microsoft.Azure.Commands.Dns.dll-Help.xml
ms.assetid: B831ABE6-348C-4DD6-9295-18D23A1FDF63
online version: ''
schema: 2.0.0
ms.openlocfilehash: 8b71c522a8d4dc006428ca2a400160a0ce7ce68b
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132428781"
---
# Get-AzureRmDnsZone

## SYNOPSIS
Mendapatkan zona DNS.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### Default (Default)
```
Get-AzureRmDnsZone [<CommonParameters>]
```

### ResourceGroup
```
Get-AzureRmDnsZone [-Name <String>] -ResourceGroupName <String> [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmDnsZone** mendapatkan zona Domain Name System (DNS) dari grup sumber daya yang ditentukan.
Jika Anda *menentukan* parameter Nama, satu **objek DnsZone** akan dikembalikan.
Jika Anda tidak menentukan parameter *Name,* array yang berisi semua zona dalam grup sumber daya yang ditentukan akan dikembalikan.
Anda dapat menggunakan **objek DnsZone** untuk memperbarui zona, misalnya Anda dapat menambahkan **objek RecordSet** ke zona tersebut.

## EXAMPLES

### Contoh 1: Dapatkan zona
```
PS C:\> $Zone = Get-AzureRmDnsZone -ResourceGroupName "MyResourceGroup" -Name "myzone.com"
```

Contoh ini mendapatkan zona DNS yang bernama myzone.com grup sumber daya yang ditentukan, lalu menyimpannya di $Zone tertentu.

### Contoh 2: Mendapatkan semua zona dalam grup sumber daya
```
PS C:\> $Zones = Get-AzureRmDnsZone -ResourceGroupName "MyResourceGroup"
```

Contoh ini mendapatkan semua zona DNS di grup sumber daya yang ditentukan, lalu menyimpannya di $Zones kontrol.

### Contoh 3: Mendapatkan semua zona dalam langganan
```
PS C:\> $Zones = Get-AzureRmDnsZone
```

Contoh ini mendapatkan semua zona DNS di langganan Azure saat ini, lalu menyimpannya dalam $Zones baru.

## PARAMETERS

### -Nama
Menentukan nama zona DNS yang akan dapatkan.

Jika Anda tidak menentukan nilai untuk parameter *Nama,* cmdlet ini mendapatkan semua zona DNS dalam grup sumber daya yang ditentukan.
Jika Anda juga menghilangkan parameter *ResourceGroupName,* cmdlet ini akan mendapatkan semua zona DNS di langganan Azure saat ini.

```yaml
Type: String
Parameter Sets: ResourceGroup
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya yang berisi zona DNS yang akan dapatkan.

Jika Anda tidak menentukan *ResourceGroupName,* maka Anda juga harus menghilangkan parameter *Name.*
Dalam hal ini, cmdlet ini akan mendapatkan semua zona DNS dalam langganan Azure saat ini.

```yaml
Type: String
Parameter Sets: ResourceGroup
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

### Tidak ada
Cmdlet ini tidak memungkinkan Anda untuk pipa input.

## OUTPUTS

### Microsoft.Azure.Commands.Dns.DnsZone
Cmdlet ini mengembalikan objek yang mewakili zona DNS.
Jika nama zona tidak ditentukan, larik objek zona akan dikembalikan.

## CATATAN

## RELATED LINKS

[New-AzureRmDnsZone](./New-AzureRmDnsZone.md)

[Remove-AzureRmDnsZone](./Remove-AzureRmDnsZone.md)

[Set-AzureRmDnsZone](./Set-AzureRmDnsZone.md)
