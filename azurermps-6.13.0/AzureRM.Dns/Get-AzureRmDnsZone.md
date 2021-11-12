---
external help file: Microsoft.Azure.Commands.Dns.dll-Help.xml
Module Name: AzureRM.Dns
ms.assetid: B831ABE6-348C-4DD6-9295-18D23A1FDF63
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.dns/get-azurermdnszone
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Dns/Commands.Dns/help/Get-AzureRmDnsZone.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Dns/Commands.Dns/help/Get-AzureRmDnsZone.md
ms.openlocfilehash: c52c9e743555c0c66afa8cc72343215a0888a7c5
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132424532"
---
# Get-AzureRmDnsZone

## SYNOPSIS
Mendapatkan zona DNS.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### Default (Default)
```
Get-AzureRmDnsZone [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ResourceGroup
```
Get-AzureRmDnsZone [-Name <String>] -ResourceGroupName <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
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

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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

### -Nama
Menentukan nama zona DNS yang akan dapatkan.
Jika Anda tidak menentukan nilai untuk parameter *Nama,* cmdlet ini mendapatkan semua zona DNS dalam grup sumber daya yang ditentukan.
Jika Anda juga menghilangkan parameter *ResourceGroupName,* cmdlet ini akan mendapatkan semua zona DNS di langganan Azure saat ini.

```yaml
Type: System.String
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
Type: System.String
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

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Dns.DnsZone

## CATATAN

## RELATED LINKS

[New-AzureRmDnsZone](./New-AzureRmDnsZone.md)

[Remove-AzureRmDnsZone](./Remove-AzureRmDnsZone.md)

[Set-AzureRmDnsZone](./Set-AzureRmDnsZone.md)
